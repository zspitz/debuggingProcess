# מפת דרכים לאיתור באגים ב-Fullstack

לא ניתן לפתוח קישורים באופן ישיר, רק עם לחיצה-אמצעית, CTRL+click (או Command+click), או לחיצה-ימנית ופתיחה בטאב חדש.

```mermaid
graph LR
N000[When writing code] --> N001[Is this a syntax error?]
N000 --> N002[Typescript] --> N003[Type error?] & N004[Missing NPM package?]
N001 & N003 & N004 --> N005( )
N005 --> N006[Squiggles/Problems view] & N007[Terminal output]

N008[When running code] --> N009[Client-side] & N010[Client-to-server request] & N011[Server-side] & N012[Server-to-client response]
N009 ---> N019[HTML] & N020[CSS] & N021[Javascript] & N022[React]

N019 --> N023[Is HTML valid?] --> N024[Are tags closed? Do they need to be?] & N025[Valid tag nesting?] & N026[Attributes with double-quotes?] & N027[Are attribute values valid?] --> N028[VS Code squiggles/Problems view]

N019 --> N029[Is the intended element being usd?] & N030[Intended attributes/values?] --> N031( ) --> N032[VS Code] & N033[Browser: elements inspector]

N020 --> N034[Valid property names/values?] --> N035[VS Code squiggles/Problems view]

N034 --> N036[Browser] --> N037[Console] & N038[Style inspector]

N020 --> N039[Style rules that have no effect?] --> N040[Rule doesn't include element] & N041[Overridden by other rules?] --> N042[Browser: style inspector]

N020 --> N043[Properties that have no effect?] --> N044[Browser: style inspector warnings]

N021 --> N045[Runtime error?] --> N046[What is the error?] & N047[In which source file?] --> N048[Browser console]

N045 --> N049[What led up to the error?] --> N050[Browser: Debugger] & N051[Browser: Console stack trace] & N052[VS Code: Debugger]

N021 --> N053[Unexpected behavior?] --> N054[Browser: Debugger] & N055[VS Code: Debugger]

N022 --> N056[Was the component rendered?] & N057[Are state/props/context correct?] --> N058[ ] --> N059[Browser: Debugger] & N060[React DevTools: Components] & N061[console.log]

N022 --> N062[JSX doesn't correctly represent state/props/context?]

N022 --> N063[Over-rendering?] --> N064[console.log at beginning of component] & N065[React DevTools Profiler]

N022 --> N066[Performance] --> N067[React DevTools Profiler]

N022 --> N068[React Router] --> N069[No matching rule?] --> N070[Browser: Console - 'No routes match location']

N068 --> N071[Route parameters specified in both route definition and address?]

N068 --> N072[Child routes?] --> N073[Is Outlet properly placed?]

N010 --> N074[Was the request sent?]

N010 --> N075[What HTTP method?]

N010 --> N076[Did the request have a payload? Was it supposed to?] --> N077[Does the payload fit the server's expectation?]

N010 --> N078[Missing CORS headers?]

N010 --> N079[Is a token/authorization required?]

%%N010 --> N014[Was the request sent?] & N015[What HTTP method?] & N016[Did the request have a payload? Was it supposed to?] & N017[Missing CORS headers?] & N018[Is a token/authorization required?]

```
