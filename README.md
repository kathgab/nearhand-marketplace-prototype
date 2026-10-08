# Nearhand: Local Freelance Marketplace (Prototype)

Nearhand is a front-end prototype of a freelance marketplace that connects employers who need local work done with workers who bid on those jobs. It covers the full job lifecycle, from posting and bidding through simulated escrow payment to two-way reviews.

> **This is a prototype.** All users, emails, payments and reviews are simulated. No real money moves, no real emails are sent, and passwords are stored in plain text in your browser. Do not enter real personal or payment information.

## Live demo

https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/

(Replace with your GitHub Pages link after enabling Pages in the repo settings.)

## Running it locally

There is no build step and there are no dependencies.

1. Download or clone this repository.
2. Open `index.html` in any modern browser.

The page loads two web fonts from Google Fonts. It still works offline with fallback fonts.

## Try it in two minutes

A demo bar at the bottom of the screen lets you switch users. All seeded accounts use the password `demo1234`.

1. Sign in as **Dana Whitfield** (employer) and post a job.
2. Switch to **Marcus Reyes** (worker), find the job and submit a bid.
3. Switch back to Dana. Optionally send a counter-offer, then hire Marcus.
4. Fund escrow with the pre-filled demo card.
5. Switch to Marcus. Start the work and mark it complete.
6. Switch to Dana. Confirm completion, and the simulated payment shows as released.
7. Both users can now leave a review, and ratings update automatically.

Use **Reset demo data** in the demo bar to restore the starting data.

## Features

**Accounts**
- Two roles, Employer and Worker, chosen at signup and fixed afterward
- Signup requires name, email, password, phone and location
- Simulated email verification and password reset (an on-screen mock inbox)

**Employers**
- Create, edit and remove job postings with title, description, one of ten categories, location, required experience, budget range and other details
- Dashboard of posted jobs with status and a progress indicator
- View all bids, inspect worker profiles and reviews, send counter-offers, and hire
- Search and browse worker profiles

**Workers**
- Search open jobs by keyword, category, location and budget
- Detailed profile: photo, bio, skills, experience, pricing, average rating, reviews and completed-job count
- Submit bids with a price, message and optional photos of past work
- Edit or withdraw bids while a job is open, and respond to counter-offers

**Job workflow**

`Open for Bids` → `Worker Selected` → `Payment Funded` → `In Progress` → `Awaiting Approval` → `Completed`

- Bidding closes once a worker is selected
- An agreement summary shows the employer, worker, agreed price, description and status

**Simulated escrow**
- The employer funds the agreed amount, and the platform shows it as held
- Payment is released after the employer confirms completion
- No platform fees, and all card data is fake

**Reviews**
- One to five stars plus written feedback, both directions (employer to worker, worker to employer)
- Only available after a job is completed, and only to the two people on that job
- Average ratings and completed-job counts update automatically

## Project structure

The app is a single self-contained `index.html` with the CSS and JavaScript inline. Inside the script, the code is organized in layers so it could be split into modules or connected to a backend later:

| Layer | Purpose |
|---|---|
| Constants and models | Statuses, categories, and documented shapes for `User`, `EmployerProfile`, `WorkerProfile`, `Job`, `Bid`, `Review` and `Transaction` |
| Seed data | Example employers, workers, jobs in every status, bids, reviews and payments |
| Store | Persistence in the browser's `localStorage` |
| Queries (`Q`) | Read helpers such as ratings and completed-job counts |
| Services (`S`) | Business rules such as who can bid, hire, fund, complete and review |
| UI | Reusable components, views and a hash-based router |

Data is saved in `localStorage`, so it persists across refreshes in the same browser but is private to each browser.

## Planned features

These are not implemented, but the data model leaves room for them (for example, `Job.dispute` and the `Transaction` status field).

- In-app messaging
- Worker portfolio uploads
- Real payment processing
- Administrative dispute resolution
- Notifications, map and distance search, and a real backend with secure authentication

## Contributing and forking

Fork the repository, make your changes on a branch, and open a pull request. Ideas for classmates:

- Split the script into modules
- Add a feature from the planned list
- Write automated tests for the business rules in the Services layer
- Improve accessibility or the mobile layout

## License

Add a license of your choice, for example MIT. See [choosealicense.com](https://choosealicense.com/).
