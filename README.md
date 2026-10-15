# OneCare — Medical Value Travel website + Patient Portal

Static site (plain HTML/CSS/JS, no build step). Every page is a single self-contained `.html` file;
images are in `images/` (website) and `images/portal/` (portal screens).

## Publish on GitHub Pages
1. Upload **the contents of this folder** (not the folder itself) to the root of your repository,
   including the hidden `.nojekyll` file.
2. Repository → **Settings → Pages** → Source: **Deploy from a branch** → Branch: `main`, folder `/ (root)` → Save.
3. After a minute the site is live at `https://<your-username>.github.io/<repo-name>/` — it opens `index.html` (the home page).

If you use a custom domain, keep your existing `CNAME` file in the repo root.
File names are lowercase/kebab-case with no spaces, because GitHub Pages is case-sensitive.

## Pages
**Website (before login)**
| Page | File |
|---|---|
| Home | `index.html` |
| Hospitals & Doctors | `hospitals.html` |
| Hospital detail | `hospital.html` |
| Care packages | `packages.html` |
| Patient Login + OTP | `login.html` — opened by every *Patient Login* / *Book consultation* button |
| Registration (5 steps) | `register.html` |

**Patient Portal (after login)**
| Page | File |
|---|---|
| Dashboard | `dashboard.html` (registration pending → start consultation) · `dashboard-screen.html` |
| Doctor listing → booking → confirmed | `Doctor-Listing_2.html` → `booking-screen.html` → `booking-confirmed.html` |
| Dashboard after video consultation | `consultation-summary.html` (Medical Diagnosis Summary) |
| Package selection → deposit | `package-selection.html` → `deposit-payment.html` |
| Browse hospitals by city (optional) | `screen1_main.html` → `screen2_main.html` → `screen3_main.html` |
| Payments | `viewpayment.html`, `payment.html` |
| My Journey | `arrival_trial.html` → `treatment_trial.html` → `recovery_trial.html` → `discharge.html` / `afterdischarge.html` → `postcare.html` |
| OneCare AI | `chat.html` |

## Full flow
Home → *Book consultation* → Login → OTP → Registration → Dashboard → Start → Doctor listing → Book → Booking confirmed →
Join video consultation → **Consultation summary** → Package selection → Deposit payment → My Journey → Post care.

## Prototype notes
- Any 6-digit OTP is accepted. The session is kept in the browser (`localStorage` key `onecare:portal`); click **Logout** to restart.
- The sample patient is **Michael**; the name entered during registration replaces it on every portal screen.
