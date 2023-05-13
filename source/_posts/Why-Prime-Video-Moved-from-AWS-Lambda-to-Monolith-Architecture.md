---
title: Why Prime Video Moved from AWS Lambda to Monolith Architecture
date: 2023-05-13 13:00:24
tags:
---

Prime Video, one of the biggest streaming services in the world, has recently made a move that has surprised many: abandoning AWS Lambda in favor of a monolith architecture. This decision has generated a lot of discussion among industry insiders and tech enthusiasts alike, so let's take a closer look at what prompted this shift.

## The Emergence of AWS Lambda

AWS Lambda is a serverless computing platform that allows developers to run code without having to worry about the underlying infrastructure. In recent years, AWS Lambda has become increasingly popular, and for good reason. It offers many benefits, including scalability, cost-effectiveness, and reduced complexity. With AWS Lambda, developers can focus on writing code instead of managing servers.

## The Challenges of AWS Lambda

Despite these benefits, AWS Lambda is not without its challenges. One of the biggest drawbacks is that it can be difficult to manage complex applications. When a system becomes too complex, it can be challenging to debug, monitor, and maintain. This can lead to performance issues, downtime, and other problems. Another issue with AWS Lambda is that it can be more expensive than a monolith architecture in certain cases. While AWS Lambda is cost-effective for small, simple applications, it can become more expensive as the application grows in complexity and scale.

## Why Prime Video Made the Switch

### Complexity

As Prime Video's application grew in size and complexity, it became increasingly difficult to manage with AWS Lambda. The company found that it was spending too much time and resources on debugging and monitoring the system, which was impacting performance and user experience.

### Cost

While AWS Lambda was cost-effective for Prime Video in the early stages, it became more expensive as the application grew in size. With a monolith architecture, the company could optimize costs and reduce expenses.

### Performance

Prime Video found that a monolith architecture was better suited to their needs in terms of performance. With a monolith architecture, the company could better manage and optimize resources to deliver a faster, more reliable streaming experience.

## The Advantages of Monolith Architecture

A monolith architecture is a traditional approach to building applications. It involves building a single, self-contained application that handles all of the functionality of the system. While this approach has fallen out of favor in recent years, it still has some advantages over a serverless architecture like AWS Lambda.

One of the biggest advantages of a monolith architecture is that it is easier to manage and debug. Because all of the functionality is contained within a single application, developers can more easily monitor and debug the system. Additionally, a monolith architecture can be more cost-effective than a serverless architecture in certain cases, as the fixed costs of maintaining the system can be spread out over a larger number of users.

# Conclusion

In conclusion, the decision to move from Lambda functions to monolith architecture was a significant one for the Prime Video team. The team spent a lot of time evaluating the pros and cons of each approach before ultimately deciding that monolith architecture was the best fit for their needs.

Since making the switch, the Prime Video team has seen several benefits, including improved performance, increased efficiency, simplified infrastructure, and more control over the platform’s infrastructure. The transition was not without its challenges, but the team was able to manage them effectively and minimize disruption to users.

Moving forward, the team has plans to continue to improve the platform and explore new technologies to deliver even better video experiences to users. While monolith architecture may not be suitable for every application, it has proven to be a great fit for Prime Video, and it will likely continue to be a key component of the platform’s infrastructure for years to come.