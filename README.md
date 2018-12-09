## Abstract

One of the big problems with auto-scaling cloud computing is the risk of amassing big loss in profit. This is a two parter, first it’s the service you provide is hogging too many resources and therefore your bill will be a lot higher than expected, second is the risk of your service crashing and therefore loss of profit because the service wasn’t available. By using monitoring we can cut down the loses by being proactive, and with logging we can understand the exact problem flow, with this we can reactively plan for improvements and a fix. With this in mind we end up with a system that can help our development process as well as creating valuable updates for our customers and our own company.

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

When it comes to reactive improvements a proper logging strategy is our best friend. That is because we can access the errors and activities of the specific time it happened. And if we have a transparent error logging strategy in our software we can easily track down the area where the error was thrown and why. But other than improvements on our code we can also look into where and what users used to access our service.

As we can see on this “access.log” file, there is data on which browser, version, ip and date - the user connected to our service. And with this information we can start tracking trends, this could f.ex lead to an understanding of our user-base when it comes to visual improvements to our site, if the majority of our users aren’t using a newer browser then maybe we shouldn’t use the newest version of Javascript or css. Or we could start tracking nationalities of our users to maybe end up adding support for a new language, f.ex if we have a large group of russian users and our website is right now only in english maybe we would like to create a translated page for russian users, to try and get more users from that region. As language gaps can be a barrier for new users.

  

![](https://lh6.googleusercontent.com/tjeKHFt3sKC5e_9i3vRFi0_qZlgymbiJzEp_WZqFIqCx_-fgxDlKXTUpk2VMarQrr2ygJRW-hcHfA810x7UmcEa_5ZQjVPm8wcsIty5B5MDX65x3oN4Ko08gZuNzFfJiFW4Cv5Z4)

  

For this log file we are presented with the information that our application writes into our log file, as we can see there are some error messages with users using wrong credentials, others can’t post because there is no text body. These types of logs can be very helpful and valuable for our developers, as they precisely tell us what and when something went wrong. From there we can try to find out why and how it went wrong. This example is very basic and simple, because of the complexity of our project. With larger services you might want to log more data, so it’s easier to recreate the errors and then fix the issues. In the end the value of our log files reflect our exception handling and logging in our software, this is very important to remember.

![](https://lh5.googleusercontent.com/0-IrfceSmQa1ht6oh9eV8ZJfBzFyQ1cjmxxqNlaOhCLCalh6Yfo8iHBOL3VgPmKUdqRHUTgQPg9v6G8CIvsKtOYDYLp5PCCh0A62VoZe5lVeFBD-Wu4up2blvikpFX2pSTmVOQPK)

  
  

## Our solution

We chose AWS as our hosting platform because of Elastic Beanstalk service strengths which enabled us to solely focus on developing and improving our service without worrying about scaling. That is because AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications and services. You can simply upload your code and Elastic Beanstalk automatically handles the deployment, from capacity provisioning, load balancing, auto-scaling to application health monitoring. At the same time, you retain full control over the AWS resources powering your application and can access the underlying resources at any time. There is no additional charge for Elastic Beanstalk - you pay only for the AWS resources needed to store and run your applications, so it is also cost efficient on its own.

  

Elastic Beanstalk Logging & Monitoring services provides us with the ability to set-up alarms on decided threshold levels, to assure the stability and safety of our service. Also, using monitoring of our service we can see if we get an influx of user and if the threshold is reached or exceeded AWS will increase our server computing power, to make sure our service can handle the needs and keep it stable.

  
  

## Conclusion

Monitoring and logging by themselves are not the saviors of our services. The role they fulfill is that of reporting and archiving problems that come up. So how we handle that information is up to us and us alone, but we need to know and learn how to collect and use this data.

  
  

## Resources

[AWS Elastic Beanstalk documentation](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html)
