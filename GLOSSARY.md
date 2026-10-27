# Video Studio

A local tool that turns an idea into a narrated short video. The user reviews and edits the written Story and Storyboard first, then renders. Many videos can be produced from the same saved configuration.

## Language

### Authoring

**Idea**:
The short brief a user types to start a video (topic, angle, audience).
_Avoid_: Prompt, topic

**Story**:
The editable script of a video: an ordered list of Scenes, each with narration. Written by an LLM or by the user.
_Avoid_: Script, screenplay, content

**Scene**:
One unit of a Story: a narration line, who speaks it, and what is shown while it plays.
_Avoid_: Shot, clip, segment

**Storyboard**:
A still preview of every Scene drawn in the chosen Style pack. The user must approve it before a Render, unless a previously approved Preset skips the gate.
_Avoid_: Preview, thumbnails

**Scene template**:
A shape a deterministic Style pack can draw, with a schema of slots (character, location, mood, camera) that a Scene fills in.
_Avoid_: Layout, scene type

### Look and sound

**Style pack**:
A self-contained, pluggable look for a video: which Orientations it supports, which options the user may change and, for deterministic packs, the Scene templates it can draw. Deterministic (same artifacts, same pixels) or agent-driven (an AI agent writes new drawing code per film; not reproducible, slow, uses account quota).
_Avoid_: Theme, template, animation type

**Voice**:
The narration sound for a video: engine, character of the voice, speed and language. May be previewed before the full Render.
_Avoid_: Narrator, TTS, dub

**Speaker**:
The identity a Scene's narration is attributed to, so one Story can later use several Voices.
_Avoid_: Character, actor

**Orientation**:
The aspect ratio of the video: 9:16, 16:9 or 1:1. Each Style pack declares which it supports.
_Avoid_: Format, ratio

### Production

**Job**:
One tracked run of the pipeline with its own id and status, from approved Story to exported video.
_Avoid_: Task, build, render request

**Render**:
The final step of a Job that produces the video file from an approved Story, Storyboard, Voice and Style pack.
_Avoid_: Export, generate

**Preset**:
A saved set of choices (Style pack, Voice, Orientation, Target duration, options) that can be reused to make many videos from different Ideas.
_Avoid_: Profile, template, config

**Target duration**:
The length the user asks for, a constraint on a Job. Tolerance is the allowed deviation.
_Avoid_: Length, runtime

**Actual duration**:
The length of the video once real narration audio exists. It can differ from the Target duration.
_Avoid_: Final length

**Voice provider**:
A pluggable source of narration (local model, cloud service, or the user's own recordings) declaring what it can do and its terms: clone, multi-speaker, word timestamps, licence, whether it sends text off the machine.
_Avoid_: TTS engine, backend

**Project**:
One video's folder of editable files: Idea, Story, Preset and the Jobs run from them.
_Avoid_: Episode, film

**Receipt**:
The manifest a Job writes: content hashes of every input and the exact tool, engine and Style pack versions it ran with. Reproducibility holds only where an environment and artifacts match it.
_Avoid_: Log, metadata
