Disclaimer: I have not confirmed the validity of the tech history I describe here. I'm planning to talk to people who actually worked on this stuff at the time, but for now I'm writing from my vague understanding.

In general, I think it's good to look at tech industry movements and trends through a historical lens. I will try to do the topic justice.

## In the old old days: a single operator

Not the earliest days of the internet, but in the 90s and early 2000s. Most websites lived on a physical server in a closet on-site in some office building or college campus. There was one webmaster who managed everything, from the HTML marquees to the skinny dial-up cables. This person usually also ran the email server and other services core to the business, all of which lived on physical machines in physical server rooms.

In this era, uptime was easy to measure. If your server was running, the website was up. If the server stopped running, the website was down.

## In the old days: the dev/ops divide

Eventually, both software development and system operations became complex enough that we needed specialists to write code and configure infrastructure.

### The Cloud

Along the way we got Amazon and the Cloud. The 2010s were the decade of cloud migrations.

## DevOps part 1: teaching ops how to code

First half of the DevOps movement: teaching sysadmins to code. From that we got infrastructure as code (Terraform, Cloudformation), configuration as code (Chef, Ansible), CI/CD (Jenkins, TravisCI, CircleCI).

## DevOps part 2: devs living in prod

I (and my colleagues) argue that the second half of the DevOps movement should be about teaching developers to take ownership of their service in production. Thanks to decades of work from SREs, sysadmins, infra and ops engineers, and others, we now take for granted many mechanisms to make our services more reliable: autoscaling, load balancing, retries, failovers.

That means what's left are much more interesting problems--subtle ones that are hard to debug and often involve a confluence of factors, in both the business logic and the infrastructure. Ops engineers can't be expected to respond to these issues alone.

On top of that, I believe both parts of the DevOps movement can reduce burnout and improve job satisfaction. We've gotten good at identifying and reducing problematic toil, but that's not enough. Practitioners need to see the impact of their work.

Most people want to do a good job, but without tight feedback loops it's difficult to know if what you're doing is right for your users. If you're going months between releases then by the time a change goes out you've long since forgotten about it. It's easy to extrapolate how a team with such a long release cycle would end up on a death march, building the entirely wrong product according to spec and burning out in the process.

It's not just about making engineers happy, as much as we love to talk about that. Helping your team improve their practices enables them to do better work, more efficiently, and with fewer issues. Most people want to do a good job. As practitioners, we take pride in our work. Help us pour that into making your business more successful. Don't let that priceless enthusiasm go to waste.