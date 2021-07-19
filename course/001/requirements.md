# Requirements - Zero to MVP: Livestreaming Platform

This document describes the overall goals/requirements of the system.

## Video live streaming

The core functionality of a live streaming platform is the transport and
distribution of live video streams. The main technical challenge our system
needs to solve is therefore getting live video streams from the streamers to
the viewers.

The rough outline of features regarding the live streams themselves:

- Low latency streamer -> viewer video transport.

  *The stream should not be delayed by more than a couple of seconds in the
  worst case when passing through the system.*

- The system must be highly scalable to accommodate high viewership.

  *The overall number of viewers should be without any technical limitation and
  achievable purely by horizontal scaling. The system must support an unlimited
  number of concurrent viewers per stream; however, we will limit ourselves to
  scaling up to ˜10k viewers per stream for the MVP.*

- Per-stream resiliency.

  *A single stream always represents a single point of failure; however, the
  system needs to be capable of fast recovery when a system failure interrupts
  the streaming capability. All components on the critical path of the video
  stream must support fast failover.*

## Social elements

A crucial part of live streaming platforms is the interaction between the
viewers and the streamer. For the MVP, we will limit ourselves to a small set
of features and focus on easy extensibility.

### Chat

- Viewers perspective:

  *Viewers will be able to send chat messages and receive all chat messages
  from other viewers. Large streams will be automatically throttled (slow-mode).*

- Streamers perspective:

  *Streamers will receive chat messages and view chat history. They will also
  have access to moderation tools: delete a message, timeout a user or ban them.*

### Notifications

- Viewers perspective:

  *Viewers will be able to favourite streamers and receive notifications when
  their favourited streamers start streaming.*

- Streamers perspective:

  *Streamers can adjust their “going live” message and stream details like the
  name or tags.*

## UI

The MVP will focus on a web UI only. Beyond surfacing the already mentioned
video live streaming and social capabilities, the UI needs to offer the
following features:

- Account management: register, login, get stream keys.

- A per-streamer profile page will, at a minimum, show the current stream or an
  offline message when the streamer is not currently streaming.

- Stream browser, where viewers can browse through currently live streams.
