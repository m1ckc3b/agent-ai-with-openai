# AI Agent with OpenAI

This project shows the minimal code needed for created an AI Agent with OpenAI.

To install dependencies:

```bash
bun install
```

To run:

```bash
bun run start
```

## How it works

1. Init a new ChatOpenAI instance :
```
const openai = new OpenAI({
  apiKey: process.env.OPENAI_API_KEY,
  dangerouslyAllowBrowser: true
})
```
2. Create an agent function (it is context less)
```
async function agent(query: string): Promise<string> {
  // Prompt Template
  const messages = [
    { role: "system", content: `You are a helpful AI agent. Give highly specific answers based on the information you're provided. 
    Prefer to gather information with the tools provided to you rather than giving basic, generic answers.` },
    { role: "user", content: query }
  ]

  runner returns a ChatCompletionsRunner
  const runner = openai.beta.chat.completions.runFunctions({
    model: "gpt-3.5-turbo",
    messages,
    functions
  })

  // Call the answer
  return await runner.finalContent()
}
```

This project was created with :
<div>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/bun/bun-original.svg" width="60px" height="60px"/>&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg" width="60px" height="60px"/>&nbsp;
  <img src="https://www.cdnlogo.com/logos/o/38/openai.svg" width="60px" height="60px"/>&nbsp;
</div>
