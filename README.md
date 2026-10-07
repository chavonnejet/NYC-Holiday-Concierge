# NYC Holiday Concierge

![NYC Holiday Concierge Prototype](nyc-holiday-concierge-prototype.png)

A conversational AI event concierge built with ElevenLabs to make evolving trip logistics easier to access through voice, text, and QR.

## Project Overview

I built the NYC Holiday Concierge while coordinating planning for a multi-day sales team holiday trip to New York City.

The operational planning itself was already being managed through Asana, but I wanted to explore a different question:

**Could conversational AI make changing event information easier for attendees to access without repeatedly searching through messages, itineraries, or project updates?**

I used ElevenLabs to prototype a voice-based concierge that attendees could ask about trip dates, lodging, dining, activities, and other event details.

The goal was not to replace the underlying project-management process. The goal was to create a simple, attendee-facing AI layer on top of structured event information.

## The Problem

Event planning changes constantly.

Hotels may still be under consideration.
Activities may be researched but not approved.
Restaurant plans may be incomplete.
Meeting times may shift.

If an AI assistant treats tentative information as confirmed, it creates more confusion instead of reducing it.

So the core challenge was not simply getting the agent to answer questions.

It was getting the agent to understand the difference between:

- confirmed information
- proposed information
- information still being researched
- information it does not know

## The Solution

I built a conversational voice agent in ElevenLabs called the **NYC Holiday Concierge**.

The experience was designed so an attendee could scan a QR code and ask questions conversationally, such as:

- When is the trip?
- What hotel are we staying at?
- What time are we going ice skating?
- Are we doing the scavenger hunt?
- Where are we having pizza?

The agent retrieves information from a controlled knowledge base and is instructed not to invent missing or unconfirmed details.

## Workflow

**Event planning in Asana**
→
**Sanitized attendee-facing information**
→
**ElevenLabs knowledge base**
→
**Conversational AI agent**
→
**Guardrails and testing**
→
**Published shareable experience**
→
**QR-code entry point designed in Canva**

## What I Built

### 1. Conversational Agent

I created an ElevenLabs voice agent from a blank agent rather than using a prebuilt template.

I configured:

- agent purpose and behavior
- first-message experience
- voice interaction
- concise response style
- knowledge-grounding rules
- handling of incomplete information

### 2. Structured Knowledge Base

I created a dedicated event-information knowledge base containing sanitized planning information.

The content was intentionally structured so the agent could distinguish confirmed plans from information still under consideration.

### 3. Anti-Hallucination Guardrails

The agent was instructed to:

- use only information available in its knowledge base
- never invent reservation details, times, locations, or activities
- clearly identify tentative plans
- say when information is still being finalized
- avoid presenting proposed plans as confirmed
- keep answers concise and conversational

### 4. Testing

I tested the agent using both normal questions and deliberate "trap" questions.

| Test Question | Expected Behavior | Result |
| --- | --- | --- |
| When is the trip? | Return the known travel dates | Passed |
| What hotel are we staying at? | Explain that the hotel was still under consideration | Passed |
| How much is the hotel? | Provide the known estimated rate while clarifying it was not final | Passed |
| What time are we going ice skating? | Refuse to invent a time | Passed |
| Are we doing the scavenger hunt? | Explain that the activity was still being researched | Passed |
| Where are we having pizza? | Explain that a restaurant had not been selected | Passed |

## Iteration

The first version of the agent answered accurately but was too verbose.

Testing revealed that almost every response ended with additional customer-service language and follow-up questions.

I revised the system prompt to:

- keep most responses to 1–3 sentences
- avoid repeating disclaimers unnecessarily
- stop ending every response with another question
- answer more like a knowledgeable event concierge

I then retested the agent to make sure the shorter responses still preserved the original accuracy and guardrails.

## Final User Experience

The finished prototype uses a simple QR-code entry point.

An attendee can scan the QR code, open the published ElevenLabs agent, and ask trip-related questions using voice or text.

The visual experience was designed in Canva as a lightweight front end for the conversational agent.

## Tools Used

- ElevenLabs
- ElevenAgents
- ElevenLabs Knowledge Base
- Asana
- ChatGPT
- Canva

## Skills Demonstrated

This project demonstrates how I approach AI from an operations perspective:

- identifying a practical use case
- structuring information before automating it
- designing clear agent behavior
- managing changing information
- building guardrails around uncertain data
- testing for hallucinations
- iterating based on user experience
- translating an internal operational process into a simple end-user experience

## Privacy & Data Handling

This repository contains a sanitized portfolio version of the project.

No confidential company information, employee contact information, reservation confirmation numbers, financial data, or other sensitive internal information is included.

The public portfolio does not expose the live production/share link.

## Status

**Concept Prototype**

The prototype successfully demonstrated the workflow from structured event planning through a published conversational AI experience.

Future iterations could include:

- finalized itinerary updates
- weather and dress guidance
- transportation information
- automated knowledge-base updates
- additional agent testing
- analytics on common attendee questions

## What I Learned

The most valuable part of this project was not simply learning how to create an AI voice agent.

It was learning how much the quality of an AI experience depends on the operational structure behind it.

The agent became more reliable when the source information was clearly categorized, uncertainty was explicitly represented, and the system prompt defined how the agent should behave when information was incomplete.

That reinforced something I already believe about operations:

**AI works best when the underlying process is clear.**
