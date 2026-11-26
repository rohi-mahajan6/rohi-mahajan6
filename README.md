# Hi, I'm Rohit Mahajan 👋

**Senior QA Automation Engineer / SDET (FinTech)**

I build test automation that runs in CI, finds real defects, and backs every claim with a CI run you can open.

[LinkedIn](https://www.linkedin.com/in/YOUR-LINKEDIN-HANDLE) · [Email](mailto:YOUR-EMAIL@example.com)

---

## Tech stack

- **UI and mobile:** Playwright · Selenium 4 · Appium (UiAutomator2)
- **API and contracts:** REST Assured · Playwright API testing · JSON Schema / OpenAPI (AJV)
- **Performance:** k6
- **Languages:** Java · TypeScript · JavaScript
- **Frameworks and reporting:** TestNG · Playwright Test · Allure
- **Infrastructure and CI/CD:** Docker · GitHub Actions · GitHub Pages · Android emulator in CI
- **AI/Automation:** Claude Code · Python (python-docx, reportlab)

---

## Portfolio projects

| Project | What it proves | Stack | Evidence |
| ------- | -------------- | ----- | -------- |
| **[saucedemo-playwright-ts](https://github.com/rohi-mahajan6/saucedemo-playwright-ts)** | E2E checkout testing across 6 user personas and 3 browsers (Chromium, Firefox, WebKit). The demo's seeded defects are tracked as expected failures, so the defect list can't go out of date unnoticed. | Playwright, TypeScript, GitHub Actions | [Live report](https://rohi-mahajan6.github.io/saucedemo-playwright-ts/) |
| **[parabank-api-ui-java](https://github.com/rohi-mahajan6/parabank-api-ui-java)** | Banking money movements checked to the cent, with the UI and the REST API cross-checked. Read-only checks on the public site; write tests only against a Docker container, enforced in code. | Java 17, Selenium 4, REST Assured, TestNG, Allure, Docker | [Live Allure report](https://rohi-mahajan6.github.io/parabank-api-ui-java/) · [CI run](https://github.com/rohi-mahajan6/parabank-api-ui-java/actions/runs/45376749272) |
| **[demo-sites-synthetic-monitor](https://github.com/rohi-mahajan6/demo-sites-synthetic-monitor)** | Scheduled synthetic monitoring of 3 public demo sites. Results are stored on a data branch, with alerts and an uptime dashboard. | Node.js, Playwright, GitHub Actions (cron), Chart.js | [Live dashboard](https://rohi-mahajan6.github.io/demo-sites-synthetic-monitor/) · [CI run](https://github.com/rohi-mahajan6/demo-sites-synthetic-monitor/actions/runs/45400063311) |
| **[inventree-api-rbac-tests](https://github.com/rohi-mahajan6/inventree-api-rbac-tests)** | A 192-row role-based access matrix for an inventory API, contract tests against the vendor's own OpenAPI schemas, and a k6 load test. Read-only checks on the public demo; real writes and load only on Docker. | JavaScript, Playwright API, AJV, k6, Docker | [Live matrix report](https://rohi-mahajan6.github.io/inventree-api-rbac-tests/) · [CI run](https://github.com/rohi-mahajan6/inventree-api-rbac-tests/actions/runs/45427115534) |
| **[mydemoapp-appium-android](https://github.com/rohi-mahajan6/mydemoapp-appium-android)** | Android app automation on a real emulator in CI: login, cart, checkout, background and foreground, and Android 12 camera and location permission dialogs, with a GPS position set on the emulator and checked on screen. | Java 17, Appium 2, UiAutomator2, TestNG, Allure, Android emulator | [Live Allure report](https://rohi-mahajan6.github.io/mydemoapp-appium-android/) · [CI run](https://github.com/rohi-mahajan6/mydemoapp-appium-android/actions/runs/45452401750) |
| **[job-search-agent](https://github.com/rohi-mahajan6/job-search-agent)** | Rule-driven job search agent using Claude Code to automate Naukri workflows, prescreen jobs with custom scoring, and generate tailored resumes. | Python, Claude Code, JS extractors, python-docx, reportlab | [Repo](https://github.com/rohi-mahajan6/job-search-agent) |

---

## Open source contributions

| Project | Contribution | Status |
| ------- | ------------ | ------ |
| [Abhijayshah/English-Tutor-AI](https://github.com/Abhijayshah/English-Tutor-AI) | Fixed the AI tutor not replying: replaced the retired `gpt-3.5-turbo` default with a configurable `AI_MODEL` setting, and added handling for empty model replies and clearer rate-limit logs. | [PR #1](https://github.com/Abhijayshah/English-Tutor-AI/pull/1) (open) |

---

## Key achievements

- **Found money-movement defects in ParaBank.** The transfer API accepted a **negative amount** (−5.00), which moved money backwards (PB-003). It also accepted an **overdraft** transfer larger than the source balance (PB-004), plus zero-amount and same-account transfers. Each defect is reproduced in CI and pinned by a test.
- **Found an access-control data exposure in InvenTree.** An account with **no roles** can list every user and read each one's email address and staff, superuser and active flags (FIND-001). I also documented 3 places where the API breaks its own published schema, and 1 where the real permissions differ from the documentation.
- **Diagnosed a flaky login check in CI.** The InvenTree check in my monitor failed in CI because it typed into the login form before the page had finished resetting the form. I traced the cause from the CI evidence and fixed the check to wait for the page to finish loading and to verify the typed values before submitting.
- **Automated Android 12 permission flows on a CI emulator.** This includes the repeated camera prompt and the precise-location choice. Two app behaviours are documented with evidence.
- **Built a privacy-first job search agent** that automates Naukri workflows, prescreening, and resume generation.

---

## How I work

- **No invented results.** Every number in these READMEs comes from a real CI run or a logged local run, with a link to it.
- **Safe on shared systems.** Public demo sites get read-only, rate-limited checks. Anything that writes data or adds load runs against a throwaway Docker container, and the code enforces this.
- **Defects are pinned, not hidden.** A known bug gets a test that asserts the correct behaviour. If the bug is fixed, the test result changes, so the defect list stays current.
- **Debugging from evidence.** When CI fails, I read the screenshots, Appium logs, logcat and traces before changing code.
