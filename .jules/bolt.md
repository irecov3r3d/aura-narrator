## 2024-03-24 - Parallelizing TTS Chunks
**Learning:** Sequential TTS API generation causes a massive waterfall bottleneck for long stories, scaling latency linearly O(N).
**Action:** When making bulk requests for separate chunks of content to the Gemini API, use Promise.all to fetch concurrently. This reduces total wait time to roughly the time of the single longest generation request.
