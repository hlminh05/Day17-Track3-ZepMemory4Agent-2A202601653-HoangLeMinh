# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **20/20**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1957.8 ms**
- Average token reduction vs full source context: **6.7%**
- Golden bonus: **10/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.2 | 227 | 0.0% |  |
| G02 | short_term | PASS | 0.0 | 133 | 0.0% |  |
| G08 | long_term | PASS | 3367.8 | 813 | 0.0% |  |
| G09 | long_term | PASS | 4532.8 | 1639 | 0.0% |  |
| G12 | semantic | PASS | 299.5 | 418 | 8.9% |  |
| G14 | semantic | PASS | 268.0 | 270 | 30.2% |  |
| G15 | semantic | PASS | 833.2 | 270 | 41.2% |  |
| G19 | mixed | PASS | 3433.8 | 581 | 0.0% |  |
| G03 | long_term | PASS | 1974.4 | 1660 | 0.0% |  |
| G04 | long_term | PASS | 2775.6 | 1651 | 0.0% |  |
| G05 | long_term | PASS | 2293.1 | 1639 | 0.0% |  |
| G10 | episodic | PASS | 4089.3 | 208 | 5.9% |  |
| G11 | episodic | PASS | 289.1 | 233 | 0.0% |  |
| G13 | semantic | PASS | 275.9 | 416 | 26.4% |  |
| G16 | mixed | PASS | 2177.0 | 581 | 0.0% |  |
| G18 | mixed | PASS | 632.6 | 489 | 13.5% |  |
| G20 | mixed | PASS | 2399.3 | 788 | 0.0% |  |
| G06 | long_term | PASS | 5002.6 | 1649 | 0.0% |  |
| G07 | long_term | PASS | 1628.3 | 1650 | 0.0% |  |
| G17 | mixed | PASS | 2883.5 | 581 | 8.1% |  |

## Evidence excerpts

### G01 - short_term

`<SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. | assistant: Noted staging constraint. | user: Filler A about button padding. | assistant: Filler A. | user: Filler B about color tokens. | assistant: Filler B. | user: Filler C about copy tone. | assistant: Filler C. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. - user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. - assistant: Noted staging constraint. </DURA`

### G02 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G08 - long_term

`<USER_SUMMARY> The user's project is LOTUS-88, with a focus on Java and Spring Boot for backend examples. They do not use Python for backend development. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backend exa`

### G09 - long_term

`<USER_SUMMARY> Minh works on the company project BLUEBIRD-42, which requires TypeScript with NestJS for the backend, and explicitly prohibits Python for this project. Minh also works on a personal project named ORCHID-27, for which Python is preferred.  Minh prefers Python and dislikes Java. For code explanations, Minh wants short examples. Minh wants explanations of async/await and the difference between coroutines and Tasks presented using a timeline. Python is preferred for the personal project ORCHID-27.  For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. Python is still preferred for the personal project ORCHI`

### G12 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} metadata= EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. metadata= EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, epis`

### G14 - semantic

`EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marke`

### G15 - semantic

`EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marke`

### G19 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's project is LOTUS-88, with a focus on Java and Spring Boot for backend examples. They do not use Python for backend development. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho`

### G03 - long_term

`<USER_SUMMARY> Minh works on the company project BLUEBIRD-42, which requires TypeScript with NestJS for the backend, and explicitly prohibits Python for this project. Minh also works on a personal project named ORCHID-27, for which Python is preferred.  Minh prefers Python and dislikes Java. For code explanations, Minh wants short examples. Minh wants explanations of async/await and the difference between coroutines and Tasks presented using a timeline. Python is preferred for the personal project ORCHID-27.  For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. Python is still preferred for the personal project ORCHI`

### G04 - long_term

`<USER_SUMMARY> Minh works on the company project BLUEBIRD-42, which requires TypeScript with NestJS for the backend, and explicitly prohibits Python for this project. Minh also works on a personal project named ORCHID-27, for which Python is preferred.  Minh prefers Python and dislikes Java. For code explanations, Minh wants short examples. Minh wants explanations of async/await and the difference between coroutines and Tasks presented using a timeline. Python is preferred for the personal project ORCHID-27.  For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. Python is still preferred for the personal project ORCHI`

### G05 - long_term

`<USER_SUMMARY> Minh works on the company project BLUEBIRD-42, which requires TypeScript with NestJS for the backend, and explicitly prohibits Python for this project. Minh also works on a personal project named ORCHID-27, for which Python is preferred.  Minh prefers Python and dislikes Java. For code explanations, Minh wants short examples. Minh wants explanations of async/await and the difference between coroutines and Tasks presented using a timeline. Python is preferred for the personal project ORCHID-27.  For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. Python is still preferred for the personal project ORCHI`

### G10 - episodic

`EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Minh dang lam kiem ke lai mo hinh cac du an backend de bao cao, ma minh rat so cai vu bi gan nham du an cua nguoi khac vao ho so cua minh, chuyen do tung xay ra roi nen lan nay min EPISODE: Sang mai minh phai hop review tien do voi mentor nen toi nay minh muon don dep lai het may thu con dang do. Minh biet minh con vai viec chua chot xong nhung dau oc dang roi qua kho EPISODE: Minh dang setup lai moi truong dev cho mot buoi ngo`

### G11 - episodic

`EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Cap nhat moi: voi du an cong ty BLUEBIRD-42, backend bat buoc dung TypeScript voi NestJS; khong dung Python cho backend du an nay. Preference Python van dung cho demo ca nhan ORCHI EPISODE: Minh dang lam kiem ke lai mo hinh cac du an backend de bao cao, ma minh rat so cai vu bi gan nham du an cua nguoi khac vao ho so cua minh, chuyen do tung xay ra roi nen lan nay min EPISODE: Sang mai minh phai hop review tien do voi mentor nen toi nay minh muon don dep lai het may thu con dang do. Minh biet minh con vai viec ch`

### G13 - semantic

`EPISODE: {"id":"kb-async-http","entity":"Async HTTP Incident Playbook","summary":"When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST.","source":"incident-playbook-2026","updated_at":"2026-08-11T00:00:00Z"} metadata= EPISODE: When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST. metadata= EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 per`

### G16 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh works on the company project BLUEBIRD-42, which requires TypeScript with NestJS for the backend, and explicitly prohibits Python for this project. Minh also works on a personal project named ORCHID-27, for which Python is preferred.  Minh prefers Python and dislikes Java. For code explanations, Minh wants short examples. Minh wants explanations of async/await and the difference between coroutines and Tasks presented using a timeline. Python is preferred for the personal project ORCHID-27.  For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. Python is still preferred for the personal p`

### G18 - mixed

`<EPISODIC> EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Minh dang lam kiem ke lai mo hinh cac du an backend de bao cao, ma minh rat so cai vu bi gan nham du an cua nguoi khac vao ho so cua minh, chuyen do tung xay ra roi nen lan nay min EPISODE: Sang mai minh phai hop review tien do voi mentor nen toi nay minh muon don dep lai het may thu con dang do. Minh biet minh con vai viec chua chot xong nhung dau oc dang roi qua kho EPISODE: Minh dang setup lai moi truong dev cho mot buoi ngoi code mot minh cuoi tuan nay, kieu khong co ai chung nhom, chi lam project `

### G20 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh works on the company project BLUEBIRD-42, which requires TypeScript with NestJS for the backend, and explicitly prohibits Python for this project. Minh also works on a personal project named ORCHID-27, for which Python is preferred.  Minh prefers Python and dislikes Java. For code explanations, Minh wants short examples. Minh wants explanations of async/await and the difference between coroutines and Tasks presented using a timeline. Python is preferred for the personal project ORCHID-27.  For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. Python is still preferred for the personal p`

### G06 - long_term

`<USER_SUMMARY> Minh works on the company project BLUEBIRD-42, which requires TypeScript with NestJS for the backend, and explicitly prohibits Python for this project. Minh also works on a personal project named ORCHID-27, for which Python is preferred.  Minh prefers Python and dislikes Java. For code explanations, Minh wants short examples. Minh wants explanations of async/await and the difference between coroutines and Tasks presented using a timeline. Python is preferred for the personal project ORCHID-27.  For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. Python is still preferred for the personal project ORCHI`

### G07 - long_term

`<USER_SUMMARY> Minh works on the company project BLUEBIRD-42, which requires TypeScript with NestJS for the backend, and explicitly prohibits Python for this project. Minh also works on a personal project named ORCHID-27, for which Python is preferred.  Minh prefers Python and dislikes Java. For code explanations, Minh wants short examples. Minh wants explanations of async/await and the difference between coroutines and Tasks presented using a timeline. Python is preferred for the personal project ORCHID-27.  For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. Python is still preferred for the personal project ORCHI`

### G17 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh works on the company project BLUEBIRD-42, which requires TypeScript with NestJS for the backend, and explicitly prohibits Python for this project. Minh also works on a personal project named ORCHID-27, for which Python is preferred.  Minh prefers Python and dislikes Java. For code explanations, Minh wants short examples. Minh wants explanations of async/await and the difference between coroutines and Tasks presented using a timeline. Python is preferred for the personal project ORCHID-27.  For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project. Python is still preferred for the personal p`
