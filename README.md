# מפת דרכים לאיתור באגים ב-Fullstack

לא ניתן לפתוח קישורים באופן ישיר, רק עם לחיצה-אמצעית, CTRL+click (או Command+click), או לחיצה-ימנית ופתיחה בטאב חדש.

## בכתיבת הקוד
```mermaid
graph LR
Start((Start)) --> N001[Syntax error?]
Start --> N002[Typescript] --> N003[Type error?] & N004[Missing NPM package?]
N001 & N003 & N004 --> N005( )
N005 --> N006([Editor: Squiggles/Problems view])

style Start fill:#c91831
style N002 fill:#203d7e
style N006 fill:#1b5f58

click N006 "https://github.com/zspitz/debuggingProcess/blob/main/tools/code-editor.md"
click N002 "https://github.com/zspitz/debuggingProcess/blob/main/tools/code-editor.md#%D7%A9%D7%A4%D7%AA-typescript"
```

## בהפעלת הקוד

### צד לקוח

```mermaid
graph LR
N019[HTML] & N020[CSS] & N021[Javascript] & N022[React]

N019 --> N023[Is HTML valid?] --> N024[Are tags closed? Do they need to be?] & N025[Valid tag nesting?] & N026[Attributes with double-quotes?] & N027[Are attribute values valid?] --> N028([Editor: Squiggles/Problems view])

N019 --> N029[Is the intended element being usefd?] & N030[Intended attributes/values?] --> N031( ) --> N032([Source files]) & N033([Browser: Elements inspector])

N020 --> N034[Valid property names/values?] --> N028

N034 --> N037([Browser: Console]) & N038([Style inspector])

N020 --> N039[Style rules that have no effect?] --> N040[Rule doesn't include element] & N041[Overridden by other rules?] --> N038

N020 --> N043[Properties that have no effect?] --> N044([Browser: Style inspector warnings])

N021 --> N045[Runtime error?] --> N046[What is the error?] & N047[In which source file?] --> N037

N045 --> N049[What led up to the error?] --> N051([Browser: Console stack trace]) & N050([Client-side debugger])

N021 --> N053[Unexpected behavior?] --> N050

N022 --> N056[Was the component rendered?] & N057[Are state/props/context correct?] --> N058[ ] --> N050 & N060([React DevTools: Components]) & N061([console.log])

N022 --> N062[JSX doesn't correctly represent state/props/context?]

N022 --> N063[Over-rendering?] --> N064[console.log at beginning of component] & N065([React DevTools Profiler])

N022 --> N066[Performance] --> N065

N022 --> N068[React Router] --> N069[No matching route?] --> N070([Browser: Console - 'No routes match location'])

N068 --> N071[Route parameters specified in both route definition and address?]

N068 --> N072[Child routes?] --> N073[Is Outlet properly placed?]

style N019 fill:#203d7e
style N020 fill:#203d7e
style N021 fill:#203d7e
style N022 fill:#203d7e
style N068 fill:#203d7e

style N028 fill:#1b5f58
style N032 fill:#1b5f58
style N033 fill:#1b5f58
style N037 fill:#1b5f58
style N038 fill:#1b5f58
style N044 fill:#1b5f58
style N050 fill:#1b5f58
style N051 fill:#1b5f58
style N060 fill:#1b5f58
style N061 fill:#1b5f58
style N064 fill:#1b5f58
style N065 fill:#1b5f58
style N070 fill:#1b5f58

click N028 "https://github.com/zspitz/debuggingProcess/blob/main/tools/code-editor.md"
```

### בקשה מצד לקוח לצד שרת

```mermaid
graph LR
Start((Start)) --> N074[Was the request sent?]

Start --> N075[What HTTP method?]

Start --> N076[Did the request have a payload? Was it supposed to?] --> N077[Does the payload fit the server's expectation?]

Start --> N078[Missing CORS headers?]

N074 & N075 & N077 & N078 --> N079([Network inspector])

Start --> N080[Is a token/authorization required?] --> N081[Was the token sent?] & N082[Is it valid?] & N083[Does it contain the right info?]

N081 --> N079

N082 & N083 --> N084([https://jwt.io])

style Start fill:#c91831
style N079 fill:#1b5f58
style N084 fill:#1b5f58

click N084 "https://jwt.io"
```

### צד שרת

```mermaid
graph LR
Start((Start)) --> N085[Not responding] --> N086[What URL is being handled?] & N087[What HTTP method?] --> N088([Browser: Network inspector])

N085 --> N089[Is CORS configured properly?]

N085 --> N090[Is there a defined endpoint?] -->  N105([Install & use a route-listing package])

N090 --> N091[Is the endpoint reached?] & N092[Is there middleware before the endpoint?] --> N093[ ] --> N094([console.log in endpoint/middleware]) & N095([Server-side debugger])

Start --> N096[Runtime error] --> N097[What is the error?] & N098[In which source file is the error happening?] --> N099[ ] --> N104([Terminal output]) & N100([try/catch + console.log]) & N095

N096 --> N102[What led up to the error?] --> N095

Start --> N103[Unexpected behavior] --> N095

style Start fill:#c91831
style N088 fill:#1b5f58
style N094 fill:#1b5f58
style N095 fill:#1b5f58
style N104 fill:#1b5f58
style N100 fill:#1b5f58
style N105 fill:#1b5f58

```

### תגובת שרת ללקוח

```mermaid
graph LR
Start((Start)) --> N104[Did the request return?] & N105[What HTTP code came back?] & N106[Was there a response payload? Should there have been?]

N106 --> N107[Does the payload shape match the expected shape?]

N104 & N105 & N107 --> N108[ ] --> N109([Browser: Network inspector]) & N110([Postman]) & N111([VS Code: REST client extension])

style Start fill:#c91831
style N109 fill:#1b5f58
style N110 fill:#1b5f58
style N111 fill:#1b5f58
```
