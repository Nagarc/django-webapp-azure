Django - webapp azure - Deploy django to Azure app servcie - Architecture and Code 

Just trying to architect and impliment the dhango appliction to migrate to Azure webapss which has django verion 1.6 with python 2.7 

Migrating to Azure 

Notejam is developed using python 2.7 and django 1.6. Keeping business interests and cost optimization, We have 
two cloud migration strategies availbl. This strategy furtehr can be divided into the medium and long term migration 
options.

Short term options:


Lift and shift: 

We can migrate quickly and easily without much effort into development of appliction.

    Compute: Provison Virtual machines for application and database in multiple availabilty zones with auto sacling and
    Azure disater reovery to another 
    region for failover and failback. 
    
    Advantandages:
        
        - This stretegy involves very less effort and easy to realise cloud capabiites such as auto scaling to scale based on  demand requirements
        - Azure Disster recovery for any data center failures and failover to another region
        - Its quick and easy. No chnchanges needed in appliction or investment needed for upgrade of app to latest version
    
    Disadvantages: 
        - Doesnt offer most cost savings as we need to pay for the virtual machines and comparing to other methods explained
        below, this is less cost effective
        - More responsibilties are with client - infrastructure maintence like patching, backup, security an drecovering 
        machines during failures 

Medium Term: 

    Compute ( Infra refactoring) : Azure provides app services for web applictaions which supports Quickly build, deploy, and scale web apps and APIs on your terms. it 
    Work with .NET, .NET Core, Node.js, Java, Python or PHP, in containers or running on Windows or Linux. Azure supports Python version 3 running on windows
    or Linux. So to realise the medium term option and it web apps cabailites of Azure app servcies, this app need to be dockerised and deployed. 

    Advantages:

        - Built-in CI/CD integration and zero-downtime deployments
        - Fully managed platform with built-in infrastructure maintenance, security patching, and scaling based on usage metrics such as HTTP queue
        length, data io, memory and CPU usage 
        - Rigorous security and compliance, including SOC and PCI, for seamless deployments across public cloud, Azure Government, 
        and on-premises environments
        - Achieve high availability with SLA-backed uptime of 99.95 percent
        - Protect your applications with Web App Firewall and connect with virtual network integration
        - DTAP ( Development, Testing, Acceptence and Production) - support with slots. Test on production grade and deploy 
        - Lot of easy configurable options such as Appliction gatewey, appliction insights and log analytics 
        - very cost effective P1V2 costs $90 a month 

      Disadvantages: 
        - Its shared environemnt and many other applications run these servers but for this project its not an issue
        - Need to containarise this app as the current python verion is not supported and involves some effort. 

Long Term: 

    Sunsetting Python 2 - January 1, 2020, was the day that Python 2 was sunset and no longer supported hence the code need to be upgraded to 
    Python 3. Its good to invest in upgrading the code and migrating to app services. This can be planned after implimenting the medium term cloud startegy 
    as explained above. 

Best on the pros and cons, availability of the time and realization of ROI, I feel the best option would be to go first for cloud migration strategy for
medium term and then mobe the cloud journey to long term strategy to reliase full benifits.

.... image::  Django-Webapp-Azure/images/App Service Deployment-Architecture.png
    :alt: Account settings
    :width: 835
    :align: center



