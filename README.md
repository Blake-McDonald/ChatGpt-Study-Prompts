<h1> SC-200 Study Guide MCQ Prompts </h1>

<i>The following prompts are custom‑built for creating study guides. The following text was written by a human and checked for grammar by an AI</i>
<hr>

**Configuration Note**

These prompts are shown in their original form, so some details may not fit every situation. Adjust the values as needed when using them elsewhere.

**Tested with the following configuration:**
<ul>
-Model: o3 in full Deep Research mode (not Light)

-Sources: Official course documentation split into 50‑page, OCR‑searchable PDF chunks
</ul>

**Workflow (per query):**

<ul>
-Upload one 50‑page PDF directly to ChatGPT.
</ul>
<ul>
-Disable web browsing.
</ul>
<ul>
-Provide a Box link that contains only the same PDF.
</ul>
<ul>
-After each query, replace the Box file with the next chunk and restate the initial prompt.
</ul>

**Reasoning**
<ul>
-Context window limits. ChatGPT can handle roughly 50 pages per pass. Splitting the document prevents the model from reading only a fraction of a large file. Because LLMs have a context‑window limit (about 4,096 tokens), they may ignore earlier content once that limit is reached.

-OCR for accuracy. Making the PDFs OCR‑searchable lets the AI read every word, even inside diagrams. Without OCR, it would have to guess the text in images.

-One chunk at a time. Feeding PDFs individually keeps the AI focused; combining many chunks in one chat increases the risk of hallucination.

-Web browsing off. Disabling browsing limits hallucinations drawn from the internet. The Box account mirrors only the PDF already provided, so if the AI reaches out, it re‑reads the same file—an approach similar to Retrieval‑Augmented Generation that grounds answers in the source text.

-Prompt repetition. Restating the initial prompt (sometimes along with prior results) reinforces the ruleset and reduces data duplication. Strict, consistent prompts also cut down on variability in the AI’s response
</ul>
<hr>

**Prompts**
<details>
<summary><strong>SC-200 Study Guide MCQ Prompt v1.0:</strong></summary>

This prompt works best when given the official coursework and study guides from Microsoft:
   
This prompt is grounded in metacognitive learning principles, including Bloom’s taxonomy. Its goal is to craft scenario‑based, multiple‑choice questions that push students to make sound logical decisions in varied contexts. It also aims to curb hallucinations and avoid predictable answer patterns for example, preventing the longest option from always being correct or the answers from lining up as A‑A‑A‑A. Finally, be sure to verify that every answer is accurate and that no obvious pattern gives it away without reading the question.

<hr>

ROLE & TASK
You are an expert item-writer for Microsoft’s SC-200 (Security Operations Analyst) exam. Create multiple-choice questions (MCQs) that follow EVERY rule below.

GLOBAL FLAGS  (integer, default 0) — treat as bit field; add values to combine.
  • 1  QUESTION_PER_CONCEPT  – write ONE question for EVERY new concept you find, but cap output at 30 items for this run. 
  • 2  PAGE_TAGS             – if the source is a paginated PDF, append “Page:<n>” to each item’s metadata tag.
  • 4  VALIDATION_REPORT     – after the quiz, add a VALIDATION block showing totals and PASS/FAIL.
  • 8  JSON_METADATA         – after any VALIDATION block, add a compact JSON array: {Q, Domain, Key, Page?}.
  • 16 TOKEN_EFFICIENT       – keep stems under 70 words.

RUN SIZE
• Produce **≤ 30 items** each run.  
• Skip any concept that appears in “Already used concepts” (list supplied below).  
• If you exhaust new concepts before 30 items, stop early.

CONTENT RULES
1. Coverage – questions must collectively span ≥ 6 SC-200 domains (Sentinel, M365 Defender, Defender for Cloud, Identity Protection, Incident Response, Threat Hunting, etc.).  
2. Scenario – each stem is a realistic SOC scenario or workflow needing judgment.  
3. Bloom’s Level – target **Analyze/Evaluate**; avoid simple recall.  
4. Stem Style – one clear issue per stem, phrased positively, ends with “?”.  
5. Options – four choices A–D; one correct, three plausible distractors.  
   • Options parallel in grammar, length spread ≤ 10 characters, no “All/None”.  
   • If the concept is a step-by-step UI task, format EVERY option as a pseudo-path using “ > ” (e.g., “Menu > Settings > Subscriptions”).  
6. Difficulty – aim for p-value 0.30–0.60 and point-biserial ≥ 0.25.  
7. Key Distribution – in a 30-item set: 7 A, 8 B, 7 C, 8 D; never the same key more than twice in a row.  
8. Template – use exactly this layout for each item:

   Q<n>. <Stem> [Domain: <Primary>[, Secondary: <Optional>][, Page:<n>]]
   A. <Option A>
   B. <Option B>
   C. <Option C>
   D. <Option D>
   Correct Answer: <A-D>

9. Technical Accuracy – align with current Microsoft guidance.  
10. Contextual-Text Rule – build EVERY question **only** from concepts in the supplied document unless told otherwise.

INPUT FORMAT
<<BEGIN DOCUMENT>>
{insert SC-200 text chunk here}
<<END DOCUMENT>>

Already used concepts (do NOT reuse): {comma-separated list, may be empty}

OUTPUT
Return ONLY the quiz in the template above.  
If Flag 4 set, append VALIDATION block.  
If Flag 8 set, append JSON_METADATA block after any VALIDATION block.  
No markdown or extra commentary.  
Verify all rules before final output.

</details>

</hr>

<details>
   
<summary><strong>SC-200 Study Guide MCQ Prompt v1.0.1:</strong></summary>

  
The following prompt is an improvement on the last. I found that when using the original, there were several issues with consistency as well as adherence to Bloom's Taxonomy. To rectify this, the query has been adjusted by providing research studies and peer-reviewed data in reference to the usage of Bloom's Taxonomy, as well as leading research papers on Machine Learning and Prompt Engineering. This was done with the intention of creating more depth-based rule systems that will better allow the prompt to create more challenging and consistent outputs, particularly in the context of pattern visual recognition. This aims to mitigate any visually identifiable trends that could blindly indicate the answer without having to engage with the content of the generated question.

</details>

