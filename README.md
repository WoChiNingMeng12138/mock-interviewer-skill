# Mock Interviewer

Practice the interview you're actually going to have.

Mock Interviewer is a [Claude skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) that runs a realistic, company-tailored mock interview. Name a company, share your target role and resume, and it researches the company, becomes an interviewer from that team, asks you one question at a time with real follow-ups, and ends with a scored evaluation and a plan to improve.

## Why

Generic interview prep asks generic questions. Real interviewers ask about their company's products, dig into the projects on your resume, and keep pushing until they find the edge of what you know. Mock Interviewer is built to do the same, and to tell you honestly how you did.

## How it works

1. **Company briefing.** Name a company. You get a structured briefing on its core business, secondary business, and products, with sources. Anything that can't be confirmed is marked as missing instead of guessed.
2. **Interview setup.** Share your target role and resume, and optionally choose how many questions you want.
3. **Live interview.** A fictional interviewer from the company introduces themselves and asks one question at a time: technical questions tied to the company and your resume, LeetCode-style algorithm problems for engineering roles, and behavioral questions in the STAR format. Each question comes with follow-ups on details, metrics, your personal contribution, and edge cases.
4. **Evaluation.** You get an overall score, scores on four dimensions, a question-by-question review, and a plan covering your resume, the knowledge to strengthen, and model answer frameworks for your weak answers.

## Features

- **Fact-checked company research.** Every claim has a source. Unknown facts are flagged, never invented.
- **One question at a time.** No question lists. The interviewer waits for your answer, then follows up like a real one would.
- **Tailored to you.** Questions draw on the company's business and the projects on your resume.
- **Configurable.** Set the number of technical and behavioral questions, the number of follow-ups, and how many times a question can be replaced if you don't know it.

  | Setting | Default |
  |---|---|
  | Technical questions | 5 (including 2 algorithm problems for engineering roles) |
  | Behavioral questions | 2 |
  | Follow-ups per question | 1 to 2 |
  | Replacements per question | Up to 3, then move on |

- **Stays in character.** No hints, answers, or scores during the interview unless you ask for a hint. All feedback comes at the end.
- **Non-engineering roles too.** For roles that don't involve coding, algorithm problems are replaced with role-specific case or design problems.
- **Any language.** The interviewer replies in the language you write in.

## Repository structure

```
mock-interviewer-skill/
├── .claude-plugin/
│   ├── plugin.json            # Claude Code plugin manifest
│   └── marketplace.json       # Lets Claude Code install this repo as a plugin
├── mock-interviewer/          # The skill
│   └── SKILL.md
├── examples/
│   └── sample-session.md      # A complete example interview
├── CONTRIBUTING.md
├── README.md
└── LICENSE
```

## Installation

**Claude apps (web, desktop, mobile)**
1. Download `mock-interviewer.zip` from the [latest release](https://github.com/WoChiNingMeng12138/mock-interviewer-skill/releases/latest).
2. Upload the zip as a skill in Claude's settings.

**Claude Code (as a plugin)**

In a Claude Code session, run:
```
/plugin install mock-interviewer-skill --marketplace WoChiNingMeng12138/mock-interviewer-skill
```

On older versions of Claude Code, add the marketplace first, then install:
```
/plugin marketplace add WoChiNingMeng12138/mock-interviewer-skill
/plugin install mock-interviewer-skill@mock-interviewer-skill
```

**Claude Code (manual)**
```bash
git clone https://github.com/WoChiNingMeng12138/mock-interviewer-skill.git
cp -r mock-interviewer-skill/mock-interviewer ~/.claude/skills/
```

**Other AI tools**
Tools that support the Agent Skills format can load the `mock-interviewer` folder directly. For other tools, paste the contents of `SKILL.md` into the system prompt or custom instructions.

## Usage

Start a new conversation and say something like:

> I have an interview at Stripe next week. Can you run a mock interview?

> Mock interview for a data analyst role at Spotify.

Then follow the steps: read the briefing, send your role and resume, and answer the questions. During the interview you can:

- Ask for a hint: "Can I get a hint?"
- Skip a question you don't know: "I don't know this one."
- Stop at any time: "End the interview." You'll get an evaluation of the questions answered so far.

**Tip:** Turn on web search if your Claude app supports it. The company briefing will be more current and will include links to its sources.

## Limitations

- Company information comes from web search or the model's training data and may be incomplete or out of date. Check important facts on the company's official website.
- The interviewer is a simulation. It doesn't know any company's real interview questions or hiring criteria.
- Scores are practice feedback, not a prediction of your interview outcome.

## Privacy

Your resume is used only within your conversation. Before sharing a session transcript publicly, remove your contact details and other personal information.

## Contributing

Issues and pull requests are welcome; see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

[MIT](LICENSE)
