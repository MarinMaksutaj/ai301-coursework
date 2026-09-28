# Voice guide: how I talk upstream

## Who I am in threads

I am Marin, an AI301 student making a first contribution to this Path Review project.
I am here to investigate one issue and share evidence others can check.
I write plainly about what I ran, what happened, and what I still do not know.

## Rules I write by

### Rule: Name the actual behavior

Name this issue's trigger or component and the next investigation step. Avoid a generic request that could be pasted onto any issue.

- Wrong: "Please assign this to me. I am excited to contribute!"
- Right: "I will investigate the empty-index search crash and post the command and output from my run."

### Rule: Promise investigation, not a fix or a date

Commit to investigating and reporting the result. Do not promise a successful fix or a delivery date before understanding the problem.

- Wrong: "I will fix this tonight, guaranteed."
- Right: "I will try the reported input on the current revision and follow up with the result."

### Rule: Separate facts from guesses

Use first-person observations for completed work. Label suspected causes and do not generalize a local result to every environment.

- Wrong: "This definitely fails everywhere because the parser is broken."
- Right: "On my tested revision, the input produced the exception below. I suspect the parser path, but have not confirmed the cause."

### Rule: Show my own evidence

Include my actual tested environment, reproducible actions, and observed result. A classmate's result cannot substitute for mine.

- Wrong: "Same as above, can confirm."
- Right: "I ran the command below on the recorded revision; it returned an empty list for the supplied input."

### Rule: Own the work

Take responsibility for checking every statement and artifact. Follow the repository's disclosure rules when it has them, and do not present an AI-generated explanation as observed fact.

- Wrong: "AI says this is the bug. Why has nobody fixed it?"
- Right: "The command below produced this traceback in my environment. Is this the expected behavior for this input?"

## Things I never post

- A promised fix or deadline I cannot support.
- "Reproduced" before I have run the trigger and checked the observed result.
- A claim that I performed a test, read a file, or verified a result when I did not.
- A classmate's output presented as my own, or "same as above" in place of proof.
- Blame, demands for urgency, or an unqualified AI-generated explanation.
