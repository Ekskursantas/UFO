# Monitoring & Logging - The dynamic duo

 
    Zygimantas Pranka & Florent Haxha

*One of the big problems with auto-scaling cloud computing is the risk of amassing big loss in profit. This is a two parter, first it’s the service you provide is hogging too many resources and thus your bill will be a lot higher than expected, second is the risk of your service crashing and thus loss of profit because the service wasn’t available. By using monitoring we can cut down the loses by being proactive, and with logging we can understand the exact problem flow, with this we can reactively plan for improvements and a fix. With this in mind we end up with a system that can help our development process as well as creating valuable updates for our customers and our own company.*

## Target Audience

This blog aims to handle and answer some of the questions and issues companies can have with their IT infrastructure. We will discuss the strengths of monitoring and logging, and how you can use these to plan improvements or expansions. The main targets would be DevOps, while the data gathered can be used by managers to plan and strategize further.

## Monitoring

One of the advantages of monitoring is that it gives us a visual overview of a services health, and by using this we can implement alarms and triggers to handle issues where the service exceeds our thresholds. With this we can provide a more efficient service to our users by making sure that our service can handle the influx of users. One of the ways to handle this would be to set-up a trigger on our load balancer that as soon as the cpu usage on one of our machines exceeds 80% the load balancer will spin up a new machine and send new users towards that specific machine. This is one of the ways to use monitoring as a proactive tool to handle the influx of traffic. But there are other areas where we can use the data provided by monitoring to improve, that would be - Cost reduction, Performance improvements and real time system updates.

  

Cost reduction is focused on the domain of are we using resources that we don’t need to use, so make sure we down scale the amount of servers running when there are no users using your service. This is a very important metric to have and use to reduce the cost of our operations

  

Performance improvements is about finding the specific bottlenecks in your software that is causing an overuse of resources which can lead to excessive operation costs.

  
  
  

Real time system updates is the key to making your service react to different changes, this would be a increase in users, service crashed and becomes non responsive and so on. This is one of the tools we can use to expand the domain of monitoring by picking out data we find more valuable

  

As we can see in the image below this is the default monitoring dashboard AWS provides for us. It gives us a good overview of different metrics, like CPU usage, total requests, networking in/out and so on. There are also possibilities to expand this and add more data.

  

![](https://lh5.googleusercontent.com/LDNYIOWSd_jzSbUQGvunphMAXD_Bk5fFkKTCk74OGboE_SDpBCdHp32IttUS_efCNJzyb0NrSElHaVPm1DhV2VaA2y4gUph7NjNMRRfola1oNl66NX8IIo11eAc1JgkKpVmL_Fx3)

  
  

## Logging

When it comes to reactive improvements a proper logging strategy is our best friend. That is because we can access the errors and activities of the specific time it happened. And if we have a transparent error logging strategy in our software we can easily track down the area where the error was thrown and why. But other than improvements on our code we can also look into where and what users used to access our service.As we can see on this “access.log” file, there is data on which browser, version, ip and date - the user connected to our service. And with this information we can start tracking trends, this could f.ex lead to an understanding of our user-base when it comes to visual improvements to our site, if the majority of our users aren’t using a newer browser then maybe we shouldn’t use the newest version of Javascript or css. Or we could start tracking nationalities of our users to maybe end up adding support for a new language, f.ex if we have a large group of russian users and our website is right now only in english maybe we would like to create a translated page for russian users, to try and get more users from that region. As language gaps can be a barrier for new users.

  

![](https://lh6.googleusercontent.com/tjeKHFt3sKC5e_9i3vRFi0_qZlgymbiJzEp_WZqFIqCx_-fgxDlKXTUpk2VMarQrr2ygJRW-hcHfA810x7UmcEa_5ZQjVPm8wcsIty5B5MDX65x3oN4Ko08gZuNzFfJiFW4Cv5Z4)

  

For this log file we are presented with the information that our application writes into our log file, as we can see there are some error messages with users using wrong credentials, others can’t post because there is no text body. These types of logs can be very helpful and valuable for our developers, as they precisely tell us what and when something went wrong. From there we can try to find out why and how it went wrong. This example is very basic and simple, because of the complexity of our project. With larger services you might want to log more data, so it’s easier to recreate the errors and then fix the issues. In the end the value of our log files reflect our exception handling and logging in our software, this is very important to remember.

![](https://lh5.googleusercontent.com/0-IrfceSmQa1ht6oh9eV8ZJfBzFyQ1cjmxxqNlaOhCLCalh6Yfo8iHBOL3VgPmKUdqRHUTgQPg9v6G8CIvsKtOYDYLp5PCCh0A62VoZe5lVeFBD-Wu4up2blvikpFX2pSTmVOQPK)

  
  

## Strategies & Best practices

Now that we have covered the bits and pieces on why monitoring and logging is a valuable tool to use, let’s delve a bit into the do’s and don'ts. We will start by covering monitoring and talking about which options we have to find the fitting option for you.

  

### Monitoring - When & What

*“Rework costs generally comprise 40–50% of overall software development costs; typically, 80% of the rework costs are caused by the highest-risk 20% of the software problems encountered.” - Barry Boehm* [3]

  

##### When should we start monitoring our software?

As stated by Barry Boehm in his paper on *Software risk management* [3],  Majority cost of rework is caused by the highest-risk minority. Could we resolve this issue earlier and thus cheaper if we can catch it? We would say “Yes” with a proper monitoring setup we would be able to find these bugs or error-prone areas, before they grow to big, or worst case scenario, makes it into release. So we would be able to use monitoring to help us analyse potential risks and identify new issues.

This could be exposed in the way of high usage of resource or bottlenecks, and the earlier we identify and understand how it happens, earlier we can then resolve them. And cost is tightly coupled to this, the earlier we get to resolve our problems the less and money is wasted.

So in short - We want to have monitoring setup as early as possible, if it makes sense. And the “if” is very important because one size, doesn't fit all.

  

##### What kind of data is interesting?

This point is unquestionably case specific, We will cover some of the most common data to collect and use. But keep in mind that different use cases call for different data.

To reference back to the “When” we need to talk about feedback loops and stability. It’s very important that we keep the feedback loop small and tight, this gives us the power of making rapid changes without many users encountering bugs or mistakes. This might be that we patch a bottleneck before we get a big influx of users, etc. or when we roll out a new update, that system metric behave correctly based on the resources that are available. A lot of these can be caught and fixed in one sprint, thus having monitoring on our development setup is just as important as on our online setup.

  

User data! Realistic user data! What do we mean by “Realistic user data”, well what is important is that you don’t bite off more than you can chew. F.ex. if we are a business that sells some products on our website, some data that might be useful is the user traffic and sales. If we have an understanding of our user base habits we can plan ahead. This could be timed campaigns, rebate and so on, also if we have users that fill up their shopping cart but then suddenly leaves our site, that might mean that our shipping price or shipping areas are to expensive or restricted. Suddenly we have the ability to make fast and surface level user surveys.

### Logging - Creating & Managing

  

##### What to consider when creating logs?

When it comes to creating and writing logs, there are many factors we need to take into consideration. One of the first things to consider is standard structured format for the log, one of the first examples that comes to our mind is a very reliable and very widely used structure - JSON [7]. Custom formats and raw text logs need custom parsing rules to extract data for analysis which we don’t want to spend our time on. While having a standard for structure is good we should never forget to have one for our fields as well. We don’t want to create a rat’s nest by adding fields ad hoc. A standard lets everyone know where to look. Hurray for Standards, but let’s not forget that we don’t want logging to block our application. Writing logs asynchronously with a buffer or queue avoids the storm that may come. As of now our logging system is structured and protected from unexpected blockedge, however we need to make sure that we are aware of restrictions in Platform as a Service (PaaS) or container-based environments. Environments like Heroku and Docker set restrictions on host access, syslog daemons, and more [6]. Make sure that you are receiving the necessary access for your logging.

  
  

##### What is the focus when managing logs?

We have our logs created and written. Now we need to manage them. There are many best practices when approaching them. I will reference the ones we believe are the focus points when managing the logs. Here’s a situation: suddenly the is a massive storm and a power outage appears you still need the logs you have, so it is necessary to make sure and store the logs outside the data center. Some of the options are different availability zone or region. And here we have saved and secured logs in the time of emergency. When we know our logs are safe and secured we can go on and do some testing for search performance at full volume and query complexity, to see how well our “just from a storm saved” logging system performs, because efficiency is of a big importance for us. Don’t use small scale test because realistically they are meaningless, so send realistic volumes and test real-world queries to really test the performance. The final practice that we consider important when managing logs is to parse them automatically instead because parsing logs on search time is slower and automatic rules save time over custom ones.

  

## Our solution

We chose AWS [1, 2] as our hosting platform because of Elastic Beanstalk service strengths which enabled us to solely focus on developing and improving our service without worrying about scaling. That is because AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications and services. You can simply upload your code and Elastic Beanstalk automatically handles the deployment, from capacity provisioning, load balancing, auto-scaling to application health monitoring. At the same time, you retain full control over the AWS resources powering your application and can access the underlying resources at any time. There is no additional charge for Elastic Beanstalk - you pay only for the AWS resources needed to store and run your applications, so it is also cost efficient on its own.

  

Elastic Beanstalk Logging & Monitoring services provides us with the ability to set-up alarms on decided threshold levels, to assure the stability and safety of our service. Also, using monitoring of our service we can see if we get an influx of user and if the threshold is reached or exceeded AWS will increase our server computing power, to make sure our service can handle the needs and keep it stable.

  

## Conclusion

Monitoring and logging by themselves are not the saviors of our services. The role they fulfill is that of reporting and archiving problems that come up. So how we handle that information is up to us and us alone. But we need to know, what and how to collect and use this data.

  

## Resources & References

1.  [AWS Elastic Beanstalk documentation](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html)
    
2.  [AWS Elastic Beanstalk Monitoring](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/environments-health.html)
    
3.  [Barry Boehm - Software risk management](https://link.springer.com/chapter/10.1007/3-540-51635-2_29)
    
4.  [Best practices Logging](https://www.loggly.com/blog/30-best-practices-logging-scale/)
    
5.  [Monitoring tips and strategies](http://blog.catchpoint.com/08/17/10-tips-for-an-effective-monitoring-strategy/)
    
6.  [Heroku Limits](https://devcenter.heroku.com/articles/limits)
    
7.  [JSON Docs](https://www.json.org/)
