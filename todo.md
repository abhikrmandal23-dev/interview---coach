# Project TODO

- [x] Public dark-themed landing page with hero, feature highlights, sign-up CTA, and login CTA
- [x] Manus OAuth authentication flow and protected dashboard/app routes
- [x] Dashboard with exactly three metrics: sessions completed, average score, and streak
- [x] Quick-start dashboard actions and recent interview history
- [x] Interview setup with role, industry, difficulty, and exact interview types: behavioral, technical, mixed
- [x] Interactive AI mock interview room with question-by-question response capture
- [x] Post-interview analysis report with per-answer scoring, feedback, strengths, weaknesses, and overall score
- [x] CV/resume upload flow with ATS score, keyword gap report, and improvement suggestions as distinct result components
- [x] Interview history list with links to individual reports
- [x] Responsive layouts and smooth dark-theme micro-interactions across screen sizes
- [x] Unit tests for interactive scoring and CV analysis demo behavior
- [x] Visual verification of landing, dashboard, interview room, report, and CV checker screens

## Change history

- [x] Revised scope: dark SaaS interface and exact option/metric constraints from latest user brief

- [x] Add real-time coaching feedback state during interview recording
- [x] Add live coaching panel with pacing, structure, filler-word, and confidence guidance
- [x] Add backend-ready live feedback contract with deterministic demo fallback
- [x] Add unit tests for live coaching feedback updates and recording lifecycle

- [x] Replace periodic live coaching polling with a streaming feedback channel
- [x] Add server-side stream cancellation and structured feedback parsing
- [x] Add client streaming consumer with incremental feedback updates and fallback
- [x] Add tests for stream parsing, cancellation, and fallback behavior

- [x] Add server SSE heartbeat events and heartbeat timer cleanup
- [x] Add client heartbeat timeout detection and exponential reconnect backoff
- [x] Surface streaming connection and reconnect status in the live coach UI
- [x] Add tests for heartbeat parsing, reconnect delay, and cleanup behavior

- [x] Keep the live coaching stream stable across recording timer updates
- [x] Add explicit client and server stream cleanup coverage

- [x] Add server-side SSE lifecycle abstraction and disconnect cleanup tests

- [x] Add integration-level coverage for the SSE route disconnect and abort path

- [x] Fix landing-page Get started button click flow
- [x] Add regression coverage for the Get started CTA navigation/auth behavior
- [x] Verify the CTA in the browser and confirm no console errors

- [x] Add a testable landing CTA click handler that asserts navigation to interview onboarding
- [x] Inspect browser console output specifically for CTA-flow errors after verification

- [x] Resolve failed Home.tsx visual deletion edit manually
- [x] Verify the updated landing page and save a new checkpoint

- [x] Diagnose and fix dashboard Failed to fetch error
- [x] Remove the dashboard box targeted by the visual edit comment
- [x] Verify dashboard rendering, tests, and browser console output

- [x] Add retry handling for transient auth.me network failures
- [x] Verify a successful auth.me request on the dashboard after restart
- [x] Confirm no new dashboard API fetch errors beyond benign analytics noise

- [x] Replace fixed ATS keyword recommendations with CV and job-description-grounded analysis
- [x] Add CV content extraction and target-domain inference without role contamination
- [x] Add job-description parsing with required/preferred/technical/soft/tool/certification signals
- [x] Add strong, partial, and missing keyword categories with traceable importance and rationale
- [x] Add general resume analysis mode when no job description is provided
- [x] Reset prior ATS state on every new CV upload and isolate analyses
- [x] Calculate ATS score from dynamic relevance, match, alignment, structure, and formatting signals
- [x] Add tests for dynamic role matching and cross-CV/session isolation
- [x] Verify ATS upload, role-specific, no-JD, and regression flows

- [x] Implement real PDF/DOCX CV text extraction before analysis
- [x] Reset target role and job description state on every new CV upload
- [x] Parse job-description signal categories beyond generic n-grams
- [x] Expand ATS scoring for education, experience depth, structure, formatting, and quantified achievements
- [x] Add upload/session isolation tests and browser-flow verification coverage

- [x] Add explicit experience-depth and formatting-quality score factors with deterministic tests
- [x] Add end-to-end ATS flow coverage for upload, job-specific mode, no-JD mode, and new-upload reset

- [x] Diagnose ATS mutation HTML response and endpoint routing failure
- [x] Prevent HTML/non-JSON responses from surfacing as raw JSON parse errors
- [x] Add regression coverage for malformed ATS mutation responses
- [x] Verify the CV checker mutation flow and save a checkpoint

- [x] Add friendly client handling for non-JSON or HTML ATS mutation failures
- [x] Add regression coverage for malformed ATS mutation responses
- [x] Run a live-browser CV checker verification against the real mutation endpoint

- [x] Add a browser regression that simulates an HTML ATS response and verifies the friendly error UI
- [x] Run a real browser CV checker request against the live ATS endpoint without intercepting the mutation

- [x] Verify the live multipart ATS endpoint returns JSON and the authenticated ATS procedure accepts PDF bytes

- [x] Diagnose the latest recurring ATS mutation HTML response
- [x] Harden ATS request size and response handling for the live CV checker
- [x] Add regression coverage for the recurring failure path
- [x] Verify the repaired CV checker and save a checkpoint

- [x] Add comprehensive categorized job-role catalog across the requested industries and career fields
- [x] Replace limited role input with searchable categorized dropdown and custom-role entry
- [x] Accept any valid custom job title without predefined-list rejection
- [x] Add job-description field and prioritize JD over custom role over selected role context
- [x] Generate dynamic interview questions from role, JD, experience level, difficulty, industry, skills, and optional CV
- [x] Prevent prior-role context from contaminating new interview question generation
- [x] Add tests for role search, custom roles, JD priority, and question-context isolation
- [x] Verify interview setup and question generation across desktop and mobile layouts

- [x] Wire skills and optional CV context into interview question generation from the setup flow
- [x] Make deterministic fallback questions reflect difficulty and experience level
- [x] Verify generated question rendering and navigation in the room on desktop and mobile viewports

## Urgent mock-interview recording and scoring fix

- [x] Make camera and microphone preview start correctly with explicit permission/error states
- [x] Add pause, stop, retake, and continue-without-video recording behavior
- [x] Persist each recording and answer against a stable interview/question mapping
- [x] Transcribe saved audio without fabricating transcript text
- [x] Detect empty, skipped, and insufficient answers and assign zero/low scores
- [x] Score answers from actual question, role context, transcript, and available media signals
- [x] Aggregate question-level scores into truthful interview reports
- [x] Replace placeholder Answers Reviewed content with actual answer transcripts and playback
- [x] Add regression tests for recording lifecycle, validation, persistence, scoring, and report mapping
- [x] Verify desktop and mobile recording/review flows and save a final checkpoint

- [x] Make pause suspend timer, transcript, and live-coach lifecycle while excluding paused time from duration
- [x] Prevent retake from persisting the discarded recording
- [x] Scope local answer fallback storage by interview session identifier

- [x] Derive an honest audio pacing/confidence signal from transcript duration and document video/body-language limitations
- [x] Add automated persisted-report mapping coverage for transcript, playback URL, and question-level score rendering
- [x] Run the complete recording-to-report browser flow on desktop and mobile before the final checkpoint

- [x] Add explicit report copy explaining transcript-pace confidence and unavailable body-language/video scoring
- [x] Add one desktop/mobile end-to-end browser flow from recording through completed report review
- [x] Save a new final checkpoint after the complete recording-to-report flow passes

## Interview-room Failed to fetch regression

- [x] Identify the exact interview-room mutation producing the Failed to fetch error
- [x] Fix the client/server network or mutation failure path without breaking answer persistence
- [x] Add regression coverage for the failed mutation and user-visible error handling
- [x] Verify the interview room with type checks, tests, browser flow, and a new checkpoint

- [x] Definitively reproduce whether saveAnswer or completeSession is the live failing mutation
- [x] Fix the confirmed underlying live fetch failure rather than only masking it with retries
- [x] Save a new checkpoint after rerunning full mutation verification

- [x] Re-run the real authenticated saveAnswer flow after the single-request transport change
- [x] Complete a live interview-room skip/save and finish flow without request interception

- [x] Run a real authenticated browser interview-room flow that performs skip/save, Finish, and report verification without network interception

## Full specification follow-up

- [x] Add an explicit incomplete-interview confirmation before Finish when unanswered questions remain
- [x] Show answered/skipped/not-answered counts and prevent final-score presentation before completion data is available
- [x] Add truthful analysis loading and AI-failure states with retry/watch-recording actions
- [x] Verify no demo/sample data is mixed into real interview reports
- [x] Add regression coverage for completion safeguards, analysis states, and full report metrics
- [x] Complete authenticated browser UI verification after the user signs in

## Final verification gap follow-up

- [x] Add browser coverage for report loading and analysis-failure recovery states
- [x] Add browser assertions for answered/skipped/not-answered summary and confidence metric rendering
- [x] Save a checkpoint that includes the latest completion/report changes and all final verification coverage

## Recorded-answer playback fix

- [x] Trace actual recording URL, MIME type, storage response, database answer mapping, and report video element
- [x] Reproduce why a saved answer cannot be played in the report
- [x] Ensure uploaded recordings are stored with playable media metadata and a retrievable URL
- [x] Render actual answer playback with clear loading/error/unavailable states and transcript context
- [x] Add regression coverage for recording URL persistence and playable report media
- [x] Verify playback on desktop and mobile, then save a new checkpoint

## Playback verification follow-up

- [x] Preserve verified WebM MIME metadata at upload and confirm the proxy fallback remains compatible
- [x] Add explicit media loading and playback-error UI to each report answer
- [x] Verify real persisted recording playback at a mobile viewport
- [x] Save a final checkpoint after the playback-specific verification pass

## Interview history delete option

- [x] Add a protected delete-session procedure restricted to the owning user
- [x] Delete related answer records safely with the interview session
- [x] Add a confirmation dialog and delete action to each history entry
- [x] Refresh history and handle deletion errors without losing the list state
- [x] Add tests for successful deletion, missing sessions, ownership protection, and cascade cleanup
- [x] Verify desktop/mobile history UI and save a new checkpoint

## History-delete verification follow-up

- [x] Add dedicated deletion tests for success, missing session, owner protection, and answer cascade cleanup
- [x] Run the history delete browser flow at a desktop viewport
- [x] Save a checkpoint after the complete history-delete verification pass

## History-delete coverage gap

- [x] Add integrated deleteSession procedure coverage proving a non-owner cannot delete another user's session
- [x] Add integrated cascade coverage proving related answer rows are removed with the owned session
- [x] Save the final history-delete checkpoint after the integrated coverage passes

## Searchable interview history filters

- [x] Add case-insensitive role search to interview history
- [x] Add interview-type filtering for behavioral, technical, mixed, and all types
- [x] Add date filtering with a clear all-dates option
- [x] Show filtered result counts and a useful no-matches state
- [x] Preserve report navigation and delete actions for filtered rows
- [x] Add desktop/mobile filter regression coverage and save a checkpoint

- [x] Save a checkpoint after the searchable history filters and responsive regression pass

## Home Interview History navigation

- [x] Add a visible Interview History option to the home/dashboard navigation
- [x] Route the option to the searchable interview history page
- [x] Verify the link on desktop and mobile and save a checkpoint

- [x] Make the decorative landing-page hero overlay ignore pointer events so header navigation remains clickable

- [x] Save a checkpoint after the home-page Interview History navigation change and desktop/mobile verification

## CV AI Detection and grounded ATS optimization

- [x] Add AI-generated content detection with confidence score and section-level signals
- [x] Produce grounded ATS improvement suggestions for keyword usage, formatting, readability, and alignment
- [x] Integrate AI Detection and ATS Optimization panels into the CV checker UI
- [x] Add unit assertions for AI detection defaults and grounded recommendations
- [x] Verify job-specific and general CV flows in the browser regression
- [x] Verify PDF/DOCX upload flows with the new fields
- [x] Add mobile viewport assertions for the new result panels
- [x] Save a checkpoint after the complete verification pass

> Note: AI-content detection is presented as a confidence signal, not definitive proof of authorship. Suggestions remain grounded in the submitted CV and target job description.
