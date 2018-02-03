---
layout:     post
title:      Stop with the unhelpful loading spinners
date:       2018-02-03
summary:    Give some context to your users with some helpful loading text
---

I get a train to work every day and have recently renewed my season ticket for a new e-ticket directly on my phone. I no longer have to carry around a ticket wallet, I just flash my phone when needed. Very convenient. However, when the ticket man comes by I load up the TPExpress app, go to my tickets and BOOM, get hit with a loading spinner as the ticket man looms over me impatiently waiting. It usually loads for ~5 seconds - but why? What is it doing? The ticket can be used offline, what on earth is it checking for? And why does it take so long?

The problem here isn’t so much the wait. It’s the lack of feedback to the user of what’s going on. I see it a lot in apps and on websites that just hang on loading screens when you open them or when you perform some kind of action such as on a form or checkout process.

What I like to do is actually inform the user of what’s going on and avoid unhelpful loading spinners at all costs. This is especially handy for multi-step processes such as payment forms where you might have to:

1. reserve the items
2. create a user
3. create a new card
4. create a payment token with stripe
5. and finally send the payment request to the backend to handle

Each of these steps are an API call that take time to complete. If you simply show the same “loading” indicator for all of these steps, it just looks like your platform is extremely slow. The user isn’t aware of that multi step process. If these APIs are somewhat slow, a slightly impatient user might even exit out or refresh because they think it’s broken.

It something in that process fails, it’s also less indicative of /where/ it failed. You’ll thank yourself when you’re sent screenshots from QA/users with the specific text of the step it’s hanging on.

I’m not saying you have to tell the exactly what’s user what’s happening at each step, but give some kind of indication to the user of why things are taking so long to load and that something is actually happening. Your process will feel a lot more responsive and users (me) will be a lot happier.