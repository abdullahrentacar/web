# Abdullah Rent-A-Car: SEO audit and Google Business Profile checklist

Prepared 31 Oct 2026. Site files are in `abdullah-rent-a-car-site/`.

## 1. What I could and could not check

- **Google Business Profile (GMB):** I could not open the profile. Google blocks automated access to the share link (`https://share.google/MZHHuM2Co3DIEhM1e`), and a search for the business name found nothing. The GMB section below is a checklist to compare against the live profile, not a review of it. Open your profile and tick each line.
- **Competition:** searches for "rent a car Rajshahi" and "Noah rent Rajshahi to Dhaka" mostly return marketplaces and aggregators (Expedia, Skyscanner, Bikroy, GoByTaxi). A small local business wins these searches through the Google Maps "local pack", so the GMB profile matters as much as the website.
- **Live site:** the site has no domain yet, so there is nothing for Google to crawl. Everything below assumes you will host the folder on a real domain.

## 2. What is now built into the site

| Area | Added |
|---|---|
| Title and description | Title "Rent a Car in Rajshahi \| Abdullah Rent-A-Car, Open 24/7" (55 characters). Description 152 characters, with the phone number. |
| Indexing | Canonical URL, robots meta (index, follow, large image previews), `robots.txt`, `sitemap.xml` with images. |
| Social sharing | Open Graph and Twitter card tags, 1200x630 share image made from your banner. |
| Local SEO | `AutoRental` structured data (JSON-LD): name, Bengali name, address, both phone numbers, 24/7 hours, 7 service districts, 10 services, GMB link in `sameAs` and `hasMap`. Also `WebSite` and `WebPage`. `geo.region` BD-54, `geo.placename` Rajshahi. |
| Page content | One H1 "Rent a car in Rajshahi". H2s carry the search terms: "Car rental services in Rajshahi", "Sedan, SUV and Noah microbus for rent", "Rajshahi to Dhaka and nearby districts". A plain-language business summary in English and Bengali at the bottom. |
| Bengali | `lang="bn"` text with Noto Sans Bengali so Bengali searches have matching words on the page. |
| AI search (GEO, AEO, LLM) | `llms.txt` with the facts in a clean list. `robots.txt` explicitly allows GPTBot, OAI-SearchBot, ChatGPT-User, ClaudeBot, Claude-SearchBot, PerplexityBot, Google-Extended and Applebot-Extended. The facts (name, address, hours, phone, vehicles, areas) also appear as visible plain text, which is what answer engines quote. |
| Speed | Hero image preloaded as WebP, other image lazy-loaded, fonts use `display=swap`, no heavy scripts, cache headers in `vercel.json`. |
| Icons | Favicon (ico and svg), Apple touch icon, 192 and 512 icons, web manifest. |

Left out on purpose:
- **Star ratings and review schema:** I do not have your real reviews. Fake or unverified rating markup can get the site penalised.
- **FAQ schema:** the FAQ section was removed from the design, and Google only shows FAQ rich results for a few site types now. Add it back only if you add a visible FAQ.
- **Map coordinates:** I do not know the exact point. Add `geo` to the JSON-LD from the GMB pin if you want it.

## 3. Things only you can do (in order)

1. **Buy or choose the domain**, then replace the placeholder in four files:
   `sed -i 's#https://YOUR-DOMAIN.com#https://yourdomain.com#g' index.html robots.txt sitemap.xml llms.txt`
   (Use the real domain with `https`. Pick one version, with or without `www`, and redirect the other.)
2. **Deploy** the folder (Vercel works as is).
3. **Google Search Console:** add the domain, submit `/sitemap.xml`, request indexing for the home page.
4. **Bing Webmaster Tools:** import from Search Console. Bing feeds ChatGPT search and others.
5. **Put the website URL on the GMB profile** (see section 4).
6. **Confirm the facts on the page with the owner.** I wrote these from your checklist, not from the owner:
   - "Well-kept cars and careful driving" and "Clean, comfortable seats" (Why choose us)
   - Which services are really offered, and which districts
   - Whether a driver is included (the page does not say either way)
   - Business start year, if you want to add "serving Rajshahi since ..." (strong trust signal)
7. **Replace the Sedan and SUV drawings with real photos** of the real cars. Add the Noah photos too. Real photos help Google Images and make people trust the page more.
8. **Get the Facebook page link** and add it to `sameAs` in the JSON-LD.

## 4. Google Business Profile: what to check and change

Compare each line with the live profile.

**Basics**
- [ ] Profile is **verified** (video or phone). Unverified profiles do not rank.
- [ ] **Name** is exactly "Abdullah Rent-A-Car", the same as the signboard and logo. No extra keywords such as "Best Rent A Car Rajshahi". Google suspends profiles for this.
- [ ] **Primary category:** "Car rental agency". Add secondary categories only if they are true and offered in your dashboard (for example van rental, airport shuttle, taxi service).
- [ ] **Address:** Shalbagan, Sopura, Rajshahi, and the map pin sits on the actual office. If customers do not come to the office, set it as a service-area business and hide the address.
- [ ] **Service area:** Rajshahi, Dhaka, Natore, Naogaon, Bogura, Pabna, Chapainawabganj.
- [ ] **Hours:** "Open 24 hours" on all 7 days. Add holiday hours before Eid.
- [ ] **Phone:** primary 01761-280031, additional 01755-964871. Both exactly as on the website.
- [ ] **Website:** your new domain. Use `https://yourdomain.com/?utm_source=google&utm_medium=gbp` so you can see GMB visits in analytics.
- [ ] **Booking or appointment link:** `https://wa.me/8801755964871`
- [ ] **Messaging** turned on if you can reply within a few hours.

**Content**
- [ ] **Description** (750 characters maximum). Draft:
  > Abdullah Rent-A-Car is a car rental service in Shalbagan, Sopura, Rajshahi. Rent a sedan, SUV or Noah microbus for city rides, weddings, airport transfers, family trips, corporate travel and Rajshahi to Dhaka journeys. We also serve Natore, Naogaon, Bogura, Pabna and Chapainawabganj. Open 24 hours, 7 days a week. Safe Ride, Comfort Journey, Your Trust. Call 01761-280031 or message us on WhatsApp 01755-964871 for availability and pricing.
- [ ] **Services list:** add each as a service with a one-line description: Rajshahi to Dhaka car rental, Daily car rental, Monthly car rental, Airport transfer, Family trip, Wedding car rental, Corporate travel, Long distance, One way trip, Round trip. Add price or "Contact for pricing".
- [ ] **Products:** add Sedan, SUV and Noah / Microbus as products with a real photo each.
- [ ] **Photos:** at least 10 real photos. Exterior and interior of each car, the office or signboard, the logo, a cover photo. Add 2 or 3 new photos a month. No stock photos.
- [ ] **Posts:** one short post a week (an offer, a route, a wedding season note) with a call button.
- [ ] **Q&A:** add and answer the questions customers ask: fares, advance payment, night trips, Dhaka trips.
- [ ] **Attributes:** tick all that apply (open 24 hours, appointment needed, online booking if you use WhatsApp).

**Reviews (the biggest ranking lever)**
- [ ] Create the short review link from the dashboard ("Ask for reviews") and send it by WhatsApp after every trip. Make a QR code for the cars.
- [ ] Reply to every review, good or bad, within 2 days. Mention the route or service naturally (for example "thank you for travelling Rajshahi to Dhaka with us").
- [ ] Target: 25 or more real reviews in the first 2 months, then 4 to 8 a month.
- [ ] Never buy reviews or ask staff to post them. Google removes them and can suspend the profile.

**Consistency**
- [ ] Name, address and phone are identical on GMB, the website, Facebook and any directory. Even "Shalbagan" versus "Sholbagan" counts. Pick one spelling and use it everywhere.
- [ ] List the business in a few Bangladesh directories and local pages. Always the same name, address and phone.

## 5. Search terms to target

| English | Bengali |
|---|---|
| rent a car Rajshahi | রাজশাহীতে গাড়ি ভাড়া |
| car rental Rajshahi | রেন্ট এ কার রাজশাহী |
| Rajshahi to Dhaka car rental | রাজশাহী থেকে ঢাকা গাড়ি ভাড়া |
| microbus rent Rajshahi, Noah rent Rajshahi | মাইক্রোবাস ভাড়া রাজশাহী, নোয়াহ ভাড়া |
| wedding car rental Rajshahi | বিয়ের গাড়ি ভাড়া রাজশাহী |
| Rajshahi airport transfer | রাজশাহী এয়ারপোর্ট গাড়ি |

## 6. Honest expectations

- A new domain usually takes a few weeks to be indexed and a few months to rank. I cannot promise a number one position for "rent a car".
- For a local business, the fastest gain is the GMB profile (complete profile, real photos, steady reviews). The website then supports it.
- Fastest ways to add ranking power to the site later: a page per route (for example "Rajshahi to Dhaka car rental" with fare ranges and trip time), real customer reviews on the page, and a few links from local sites, Facebook and directories.

## 7. First 30 days

| When | Do |
|---|---|
| Day 1 to 2 | Domain, deploy, replace placeholder, Search Console, Bing, GMB website and booking links |
| Day 3 to 7 | Real photos on GMB and site, fix the description, services and hours, confirm the copy with the owner |
| Week 2 | Start the review routine, add the Facebook link, list in 3 to 5 directories |
| Week 3 to 4 | Weekly GMB posts, reply to all reviews, check Search Console for indexing and queries |
