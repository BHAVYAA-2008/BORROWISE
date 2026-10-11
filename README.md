# Borrowise: check before you borrow

**Theme:** Financial Inclusion & Livelihoods
**Built for:** Social Impact Hackathon 2026

Borrowise is a free web app that helps daily-wage workers, students and small vendors check loan offers and apps before they borrow, shows the real yearly cost of a loan, and guides victims of loan-app harassment to report it.

## The problem

Illegal and predatory loan apps reach people through SMS, WhatsApp links and APK files. They take 20 to 30 percent of the loan upfront, demand repayment within days, ask for access to contacts and photos, and then threaten borrowers and message their families. Most help today arrives after the harm is done. Borrowise works **before** the loan.

## Who it helps

People with limited access to formal credit: daily-wage workers, gig workers, small vendors, students and first-time borrowers, plus their families.

## What the prototype does

| Tab | What it does |
|---|---|
| **Link check** | Paste an SMS, email or WhatsApp message. Looks for scam signs: APK links, look-alike bank domains, shortened links, requests for OTP or upfront fees, threats and pressure. Never opens the link. If the risk is high, the user can **Reject** it. |
| **App check** | Look up an app name in a snapshot of RBI's Digital Lending Apps directory and get **Found / Not found / Similar names / Cannot confirm**. Then score the app on permissions, upfront deductions, review warnings and real cost. |
| **Loan cost** | Turns "you receive X, you repay Y in Z days" into a yearly cost and compares it with a 24 percent loan. Lists safer places to borrow. |
| **Radar** | Links and apps that people rejected or reported. Shared when the Claude runtime is available, otherwise it runs in **demo mode** and keeps reports on the device. |
| **Get help** | Checklist for people being threatened, a complaint draft for the cyber crime cell, a message to warn family, and Tele-MANAS (14416) support. |

## How it works

- **Rule-based engine.** Every score comes from visible rules, and each result lists the reasons. No AI is used to produce a score.
- **RBI directory snapshot.** A snapshot of 814 entries from RBI's public directory of digital lending apps, copied on 8 Oct 2026 from a public mirror (not from RBI directly). It covers names from A to O and part of P. Names after that return "Cannot confirm" instead of a wrong "Not found".
- **Privacy.** Messages stay in the browser. Only a website name or app name is shared with the Radar, and only when the user presses Reject or Report.
- **Single file.** `index.html` contains all the HTML, CSS and JavaScript. No build step and no server.

## Run it

Open `index.html` in a browser. That is all.

### Host on GitHub Pages

1. Upload `index.html` and `README.md` to a new repository.
2. Settings, Pages, Deploy from a branch, `main`, `/ (root)`, Save.
3. Open `https://<username>.github.io/<repository>/` after a minute.

## Access for judges

No login is needed for Link check, App check, Loan cost, Get help, or the Radar in demo mode. The shared Radar needs the Claude runtime and a signed-in user; without it the app falls back to demo mode.

## Limitations (honest list)

- Scores are a guide, not a final verdict. A brand-new scam will not match any rule.
- "Found in the RBI directory" does not prove an app is genuine. Copycat apps reuse real names, so the user should match the lender and developer on the store page.
- The RBI snapshot is partial and will go out of date. Always confirm on rbi.org.in.
- It does not check live blocklists such as Google Safe Browsing and cannot see how new a website is.
- The shared Radar has no moderation or verification yet.
- The "Try a sample" buttons use made-up text and a made-up app. They are not real scams or real companies.
- It is not legal advice and cannot stop harassing calls. It helps users organise evidence and report.

## Roadmap

- Complete the RBI directory (Q to Z) and sync it automatically.
- Live checks against Safe Browsing and domain-age data.
- Tamil and Hindi, voice input, and a WhatsApp bot for users without smartphones.
- Moderated Community Radar with district-level trends.
- Partnerships with self-help groups, banks and cyber police.

## Disclaimer

Borrowise is a hackathon prototype. It gives general information and risk signals, not financial or legal advice.
