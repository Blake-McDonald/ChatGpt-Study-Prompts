# ChatGpt-Study-Prompts

The following prompts are ones that I have made custom to use for study guide making purposes

*Configuration Note*:

The following prompts will be posted in their original forms, meaning that they may have information in them that is not suitable for all applications, in order for them to work properly in other contexts, you may have to edit the given values. 

Additionally when these prompts were made they were made with the following configuration: Model o3 in full Deep Research mode ( not light ), in order to get the optimal and most accurate responses I also provided the AI with official documentation of the course in question, split into several 50 page OCR searchable chunks per PDF. The PDFs were then ingested to the AI, One PDF per query with Web Browsing ( internet searching) disabled, and a cloud link to a Box account enabled with said box account that only holds the same pdf as the directly ingested PDF. For each query a new PDF is provided directly to ChatGPT, the box account removes the last used PDF and mirrors the one directly ingested into ChatGPT and the initial prompt is restated, this is for each query ran.

 The reason for this is ChatGPT can only process a maximum of 50 Pages per pass, by dividing the pages it ensures that the AI will not only read part of the document ( say 10 pages of a 600 page document). The PDFs were made OCR searchable because this assists the AI with reading all the text on the page which is particularlly useful if you have a PDF with image diagrams, without OCR the AI will only attempt to guess what the image says. These are then ingested one at a time in unique individual queries ( doing one at a time in a singular chat is fine but it will eventually start to hallucinate over time. ) this allows the AI to not get confused and keep its focus on one time. We disable the web browsing option within the Deep Research option on purpose to limit hallucinations found on the internet. The connected box account is filled with only the mirrored file of the file already directly provided to the AI to instill focus, the AI will try to infer something or look for information and may skip over it in the initally provided doc, it will then reach up to the Box account, read the only doc available and then essentially double check the document. Lastly the prompts created will then be restated for each query, in some cases along side the results of previous queries in order to instill the ruleset and prevent duplication of data.  

<hr>

**Custom Prompts**

- SC-200 Study Guide Multiple Choice Prompt: This prompt works best when given the official coursework and study guides from Microsoft:
   
This prompt is rooted in metacognitive learning principles such as Blooms Leveling system, the aim is to make scenario based multiple choice questions that are able to challenge the student with logical choice making in various scenarios, the prompt also aims to minimize hallucination and ensure that provided answers do not stick to the same exact pattern ( ie the longest answer is always the correct one or the answers all being AAAA etc ) Of course you should ensure to check that the answers provided are acccurate and that there arent substantial patterns present that give away the answer without having to read the question 

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

