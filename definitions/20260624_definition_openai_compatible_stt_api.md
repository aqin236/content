---
title: "OpenAI-Compatible Speech-to-Text API"
description: "A transcription API that follows OpenAI-style audio upload, authentication, and response conventions."
date: 2026-06-24
author: "Aqin"
---

# OpenAI-Compatible Speech-to-Text API

## Definition

An OpenAI-compatible speech-to-text API is a transcription endpoint that accepts
audio through an OpenAI-style `POST /v1/audio/transcriptions` request and
returns a response shape that client tools can parse in the same way as OpenAI's
audio transcription API.

## Context and Usage

AI engineering teams use OpenAI-compatible APIs to switch between hosted
providers, internal gateways, and local inference servers without rewriting the
client application for each service. In a speech-to-text workflow, compatibility
usually means the client sends multipart form data with a model name and audio
file, authenticates with an API key, and reads the transcript from a `text`
field in the JSON response.

Compatibility does not guarantee that every provider supports the same model
names, file limits, diarization options, timestamp formats, or error messages.
Those differences should be handled through configuration or a dedicated
provider adapter when the generic request shape is not enough.
