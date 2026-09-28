# Evidence guide: where proof lives in a reproduction package

## Environment

Where it lives: In eval, the issue context and repo-facts template describe the target; the candidate repro report records the tested version/revision, OS, runtime, installation method, and relevant configuration. In live mode compare the posted issue and repo setup/template requirements with the environment stated in the draft itself.

What good looks like: The record identifies the tested setup and relevant differences from the original report. A newer version or different OS can support an honest cannot-reproduce result if the difference is called out. Do not silently substitute the issue author's environment for the contributor's. Details irrelevant to the behavior are not mandatory unless the repo explicitly requests them.

## Steps

Where it lives: Read the report's preparation, exact input/fixture, commands or UI actions, and trigger. In live mode the issue thread and public setup docs explain prerequisites, but the candidate comment must contain or explicitly reference what readers need.

What good looks like: A stranger can create the starting state, supply the same input, and reach the trigger. Check exact syntax, flags, paths, and configuration, not how many numbered steps are present. A referenced local fixture that is neither included nor publicly accessible is missing evidence; other unquoted workspace files do not repair the posted package.

## Behavior shown

Where it lives: First extract the issue's expected result, actual symptom, and necessary triggering conditions. Then inspect the candidate report's command/output pairs, log excerpts, screenshots, or explicit UI observations. Eval uses only the frozen bundle; live mode compares the issue and drafted artifacts.

What good looks like: Trace input to executed action to observed result. Ask whether execution reached the reported failing operation and whether the signature matches. For example, invalid HCL rejected for a missing equals sign does not reproduce a panic on a valid HCL non-string key. A detailed UI-state observation can be evidence without a terminal trace; a general "confirmed" cannot. Cannot-reproduce evidence should show the relevant attempt and actual nonfailure, not an unrelated setup error.

## Honesty

Where it lives: Compare the candidate claim and the report's conclusion/analysis to the concrete artifacts and tested environment. In live claim-only mode check only what the author actually asserts so far.

What good looks like: "I will test the empty-index case and post the output" is a prospective plan. "I reproduced it" needs supporting observations in a full package. An untested cause remains a hypothesis; results on one setup do not establish every platform is affected. A supported cannot-reproduce report is useful and can pass. Repetition and confidence do not turn the wrong failure into proof.

## Comms

Where it lives: Compare the claim with specific details from the issue. In eval, read the repo-facts bug-report template and contribution policy, then the candidate claim and report. In live mode read root/.github/docs contributor guidance, linked policy files, issue/PR templates as applicable, the issue thread, and the installed voice guide.

What good looks like: The claim names a relevant trigger or component and a concrete next step. The comments satisfy applicable explicit repo requests, including disclosure of AI assistance when required. A template's substantive fields can appear in ordinary prose; headings alone are not proof. Silence about an AI policy is not a ban or a disclosure obligation; unavailable policy evidence is not the same as verified silence. Claim-only checking postpones report-only requirements. In Path Review, other students' claims do not block posting, but the author must supply their own observations rather than piggyback on another report.
