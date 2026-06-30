# BookLeaf Publishing — AI Automation 

## AI Customer Query Bot

A multi-channel-ready query responder for BookLeaf Publishing authors.

### Tech Stack
- **n8n** — workflow orchestration
- **Groq (Llama 3.3)** — LLM for intent classification and response generation
- **Supabase** — author database with mocked data
- **Google Sheets** — query logging
- **Hoppscotch** — API testing interface

### Features
- Natural language query understanding
- Supabase DB lookup by author email
- Confidence scoring with human escalation (< 80%)
- Full query logging
- Error handling for DB failures and no-match scenarios
- Knowledge base integration via LLM system prompt

### How to run
1. Import `bookleaf_workflow.json` into n8n
2. Add your credentials (Groq API, Supabase, Google Sheets)
3. Activate the workflow
4. Send POST request to webhook URL:

```json
POST /webhook/bookleaf-query
{
  "question": "Is my book live yet?",
  "email": "sara.johnson@xyz.com"
}
```

### Sample Response
```json
{
  "success": true,
  "answer": "Hi Sara! Your book 'Whispers of Dawn' went live on 10th April 2026. Congratulations!",
  "intent": "book_status",
  "confidence": 95
}
```

## Identity Unification System

See `Identity_Unification_BookLeaf.docx` for full system design including:
- Matching logic and confidence scoring
- Pseudocode implementation
- LLM integration approach
- Recommended tech stack

