# API Spec

This doc includes a gap analysis of where we currently are on the data purchasing side of things,
as well as the basic flow for a user to purchase data.

## Gap Analysis

### Current Processes

For discovery, clients have to talk to @BOC111 to find out what datasets we have available.

For access, they have to supply an AWS IAM principal ARN that we configure manually on our side.

There are no systems in place for automating any parts of this, and there no mechanisms to actually handle dataset subscriptions.

We have a sample cleanroom available for evaluation, but it requires hands-on work from multiple TIKI staff.

### Needs

A user needs to be able to do all the following (without involvement from TIKI staff):

- Explore available datasets
- Create a SQL query as the basis for a dataset subscription
- Estimate the costs (incl. basic stats and a small sample of data)
- Create dataset subscriptions
- Configure access to cleanrooms (via an API)

### How to Get There

- Build data purchasing APIs: https://github.com/tiki/purchase/issues/43
- Develop the Subscription Builder UI components for the website: https://github.com/tiki/website/issues/4
- Integrate Subscription Builder UI with the new website (embed as an iframe on readme.com)
- Update website to include new APIs
- Add additional screens for exploring available datasets
- Integrate Stripe for payment handling
- Create sample cleanroom evaluation agreement

## Buyer Journey

This is the process a user should go through to purchase data.

### Core Needs / Flow

1. Explore summary of available datasets
2. View details about specific datasets
3. Estimate cost of dataset subscription
4. Create dataset subscriptions

### One-time Setup

1. Add a payment method
2. Configure data cleanroom access
3. Configure delivery channels (for external data delivery)
