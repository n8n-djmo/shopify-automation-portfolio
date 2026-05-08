# Portfolio Project #3: Shopify Intelligence Suite

## The Problem

Most Shopify store owners find out about inventory problems after they've already cost them money.

A product runs out of stock on a Friday afternoon. Nobody notices until Monday. By then, customers have already clicked away to a competitor — and the marketing budget spent driving that traffic is gone. Meanwhile, another product has been sitting at full stock for three months with a product description so generic that it barely ranks in search, let alone convinces anyone to buy.

The math is brutal: <a href="https://tightly.io/newsroom/why-your-shopify-inventory-management-is-costing-you-money">retailers lose close to $1 trillion annually from stockouts and overstocking</a>, and the average Shopify store owner spends 10–20 hours per week on manual inventory tasks that should never require human attention.

The problem isn't that store owners don't care about their inventory. The problem is that Shopify's native tools only tell you what already happened. They don't warn you, analyze patterns for you, or take action for you.

This is the gap the Shopify Intelligence Suite was built to close.

---

## The Solution

The Shopify Intelligence Suite is a three-workflow automation system built on n8n and Claude AI that turns a store's inventory data into automatic alerts, weekly intelligence reports, and optimized product listings — all without the store owner lifting a finger.

**What it replaces:**
- Manually checking stock levels daily
- Scrambling to reorder after a stockout already happened
- Paying a copywriter every time a product description needs updating
- Waiting until end-of-week to realize which products are about to run out

**What it delivers:**
- Real-time low-stock alerts before stockouts happen
- A Monday morning AI-written inventory report with restock recommendations
- AI-generated, SEO-optimized product descriptions written directly into the Shopify product page

All three workflows run automatically. Once set up, the system requires zero manual input from the store owner.

---

## The Workflows

### Workflow 1: Low Stock Alert System

**Trigger:** Runs on a schedule (daily or configurable interval)

**What it does:**
The workflow pulls live inventory data from Shopify for all products. It checks each product's stock level against a configurable threshold (default: 5 units). Any product below the threshold triggers an immediate email alert to the store owner with the product name, current stock count, and a direct link to reorder.

**Why it matters:**
This is the difference between proactive and reactive inventory management. Store owners who relied on manual checks were always one busy day away from a stockout they didn't see coming. This workflow runs whether or not they're watching.

**Nodes used:** Schedule Trigger → Shopify (Get Products) → IF Node (inventory < threshold) → Gmail

---

### Workflow 2: AI Restock Intelligence Report

**Trigger:** Every Monday at 8:00 AM (configurable)

**What it does:**
The workflow pulls the full product inventory list from Shopify and batches it into a single input for Claude AI. Claude analyzes the data and writes a structured weekly report that includes: products at critical stock levels, products that are overstocked relative to typical sell-through patterns, and specific restock recommendations with priority rankings. The completed report is delivered directly to the store owner's inbox before their workweek begins.

**Why it matters:**
The difference between a raw low-stock alert and an intelligence report is decision support. The alert tells you something is low. The report tells you what to do about it, in order of priority, with context. Store owners using this workflow start every Monday already knowing exactly where their inventory attention needs to go.

**Claude prompt approach:** Temperature set to 0.3 for structured, consistent output. System prompt establishes Claude as a senior e-commerce operations analyst. Input includes full product inventory data. Output constrained to a formatted report with clear sections and actionable bullet points.

**Nodes used:** Schedule Trigger → Shopify (Get Products) → Aggregate Node → HTTP Request (Claude API) → Gmail

---

### Workflow 3: AI Product Description Generator

**Trigger:** Manual (run on-demand per product)

**What it does:**
The workflow fetches a product's existing data from Shopify — title, product type, tags, and existing description. It sends this data to Claude AI, which writes a new 150-word SEO-optimized product description in the store's brand voice. The finished description is written back directly into the Shopify product page via Shopify's API — no copy-paste required.

**Why it matters:**
Generic product descriptions are one of the most common silent revenue killers in e-commerce. They don't rank in search, they don't convert browsers into buyers, and they make a brand look indistinguishable from every other store selling the same product. This workflow produces a professional-quality rewrite in under 30 seconds — and publishes it automatically.

**Claude prompt approach:** Temperature set to 0.7 for creative, brand-aligned output. System prompt establishes tone, format, and SEO intent. Output constrained to 150 words with a specific structure (hook → features → call to action).

**Nodes used:** Manual Trigger → Shopify (Get Product) → HTTP Request (Claude API) → HTTP Request (Shopify PUT write-back)

---

## The Results

**From the test store (denmar-test-store.myshopify.com):**

- Low Stock Alert: Successfully detected 3 products below the 5-unit threshold and delivered email alerts within seconds of the schedule trigger firing
- Restock Intelligence Report: Claude produced a correctly structured, prioritized weekly report from live Shopify inventory data on the first run
- Product Description Generator: Wrote and published a 150-word SEO-optimized description for "The Collection Snowboard: Liquid" directly into the Shopify product page — full cycle completed in under 30 seconds

**What this means for a real store:**

A store running 200 SKUs that previously spent 15 hours a week on manual inventory checks would eliminate that entirely. A store that updates product descriptions twice a year because copywriting is expensive would be able to refresh listings on demand. A store that found out about stockouts after the fact would get a heads-up the moment stock drops below threshold — every single day, automatically.

---

## The Offer

**Shopify Intelligence Suite**
Three-workflow automation system — Low Stock Alert + AI Restock Report + AI Product Description Generator

**Investment:** $900–$1,500 one-time setup + $100–$200/month retainer

The setup fee covers full build, testing, and delivery of all three workflows configured to your store. The retainer covers monitoring, adjustments as your product catalog grows, and priority support.

Setup is completed in 5–7 business days. No Shopify apps to install. No subscriptions to manage. Runs on your existing store data.

**To get started or ask questions:**
📧 denmarjohnoropel@gmail.com
