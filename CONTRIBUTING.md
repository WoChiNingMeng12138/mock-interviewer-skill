# Contributing

Thanks for helping improve Mock Interviewer! Contributions of all sizes are welcome.

## Ways to contribute

- **Report a problem.** Open an issue when the interviewer breaks a rule: asking several questions at once, skipping a stage, inventing company facts, giving answers during the interview, or scoring things the candidate never said. Include the prompt you used, what happened, and what you expected.
- **Improve the skill.** Clearer rules, better follow-up strategies, fairer scoring, or better support for specific kinds of roles.
- **Share an example session.** A complete interview for a role or industry not yet covered in `examples/`.

## Privacy first

Before you submit an example session, an issue, or a transcript, remove:

- Your name, contact details, and any other personal information from the resume
- Real names of people at the company
- Anything you were told in confidence during a real interview process, including real interview questions shared under a non-disclosure agreement

Use a fictional candidate and resume in example sessions. Pull requests that include personal or confidential details will be asked to remove them before merging.

## Adding an example session

1. Add a Markdown file to `examples/`, named after the role and company, for example `backend-engineer-stripe.md`.
2. Include all four stages: the company briefing, the interviewer's opening, the interview, and the evaluation report.
3. Check the company briefing against the company's official sources. Correct or mark anything that is out of date.
4. In your pull request, name the role, the company, and the interview settings you used.

## Changing the skill

- **One change per pull request.** It keeps the effect of each change easy to see.
- **Write rules as behaviors.** "Ask one question per reply" works better than "be realistic".
- **Test before submitting.** Run at least one full interview with your change, including:
  - an ambiguous or little-known company name,
  - saying "I don't know" until the replacement limit is reached,
  - asking for a hint,
  - ending the interview early.

  Describe what you tested in the pull request.
- **Keep the stages consistent.** If you change a rule or template, check that nothing elsewhere in `SKILL.md` refers to the old behavior.
- **Keep `SKILL.md` free of non-English text**, so it works the same for every user. The skill replies in the user's language on its own.
- If you change files under `mock-interviewer/`, bump `version` in `.claude-plugin/plugin.json` so plugin users receive the update.

## Commit messages

Say what changed and why, for example:

```
Limit replacement questions per slot

The interviewer kept replacing questions when the candidate said they did not know.
```

## License

By contributing, you agree that your contributions are licensed under the MIT License.
