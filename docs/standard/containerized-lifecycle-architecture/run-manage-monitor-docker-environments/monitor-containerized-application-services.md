---
title: "监视容器化应用程序服务"
description: "使用 Microsoft 平台和工具的 Docker 容器化应用程序生命周期"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 3e4a78eb47d0e6712919c89b6f52ec8e4248fb23
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2017
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="7f271-104">监视容器化应用程序服务</span><span class="sxs-lookup"><span data-stu-id="7f271-104">Monitor containerized application services</span></span>

<span data-ttu-id="7f271-105">这非常重要将拆分为多个容器和微服务的应用程序可以有一种方式监视和分析应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="7f271-105">It is critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the application.</span></span>

## <a name="microsoft-application-insights"></a><span data-ttu-id="7f271-106">Microsoft Application Insights</span><span class="sxs-lookup"><span data-stu-id="7f271-106">Microsoft Application Insights</span></span>

<span data-ttu-id="7f271-107">[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview)是一种可扩展的分析服务监控你实时应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f271-107">[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="7f271-108">它可帮助你可以检测和诊断性能问题，可以了解用户实际执行的操作与你的应用。</span><span class="sxs-lookup"><span data-stu-id="7f271-108">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="7f271-109">它旨在为开发人员，目的是为了帮助您持续改进性能和可用性的服务或应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f271-109">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="7f271-110">Application Insights 适用于 web/服务和独立上了多种不同的平台，如.NET、 Java、 Node.js 和许多其他平台，托管在本地或云中的应用。</span><span class="sxs-lookup"><span data-stu-id="7f271-110">Application Insights works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a><span data-ttu-id="7f271-111">使用 Application Insights QA 环境中的分析 Docker 应用</span><span class="sxs-lookup"><span data-stu-id="7f271-111">Analyzing Docker apps in QA environments using Application Insights</span></span>

<span data-ttu-id="7f271-112">有关 Docker，你可以图表生命周期事件和 Application Insights 上的 Docker 容器的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="7f271-112">As it pertains to Docker, you can chart life-cycle events and performance counters from Docker containers on Application Insights.</span></span> <span data-ttu-id="7f271-113">你只需运行[应用程序 Insights Docker 映像](https://hub.docker.com/r/microsoft/applicationinsights/)由于中你的主机，和它的容器将与其他 Docker 映像，以及主机中显示性能计数器。</span><span class="sxs-lookup"><span data-stu-id="7f271-113">You just need to run the [Application Insights Docker image](https://hub.docker.com/r/microsoft/applicationinsights/) as a container in your host, and it will display performance counters for the host as well as for the other Docker images.</span></span> <span data-ttu-id="7f271-114">此应用程序 Insights Docker 映像 (图 6-1） 可帮助你通过收集关于性能和活动的 Docker 主机 (即，Linux Vm)、 Docker 容器和运行的应用程序的遥测监视容器化应用程序在其中。</span><span class="sxs-lookup"><span data-stu-id="7f271-114">This Application Insights Docker image (Figure 6-1) helps you to monitor your containerized applications by collecting telemetry about the performance and activity of your Docker host (that is, your Linux VMs), Docker containers and the applications running within them.</span></span>

![示例](./media/image1.png)

<span data-ttu-id="7f271-116">图 6-1: Application Insights 监视 Docker 主机和容器</span><span class="sxs-lookup"><span data-stu-id="7f271-116">Figure 6-1: Application Insights monitoring Docker hosts and containers</span></span>

<span data-ttu-id="7f271-117">当你运行[应用程序 Insights Docker 映像](https://hub.docker.com/r/microsoft/applicationinsights/)你的 Docker 主机，您受益于以下：</span><span class="sxs-lookup"><span data-stu-id="7f271-117">When you run the [Application Insights Docker image](https://hub.docker.com/r/microsoft/applicationinsights/) on your Docker host, you benefit from the following:</span></span>

-   <span data-ttu-id="7f271-118">生命周期有关主机上运行的所有容器的遥测-启动、 停止和等。</span><span class="sxs-lookup"><span data-stu-id="7f271-118">Life-cycle telemetry about all the containers running on the host—start, stop, and so on.</span></span>

-   <span data-ttu-id="7f271-119">所有容器的性能计数器： CPU、 内存、 网络使用情况，和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7f271-119">Performance counters for all the containers: CPU, memory, network usage, and more.</span></span>

-   <span data-ttu-id="7f271-120">如果还安装[Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)在容器中运行的应用，这些应用程序的所有遥测将都包含标识的容器和主机计算机的附加属性。</span><span class="sxs-lookup"><span data-stu-id="7f271-120">If you also installed [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) in the apps running in the containers, all the telemetry of those apps will have additional properties identifying the container and host machine.</span></span> <span data-ttu-id="7f271-121">因此，例如，如果你有多个主机中运行的应用程序的实例，你将轻松能够筛选由主机应用遥测。</span><span class="sxs-lookup"><span data-stu-id="7f271-121">So, for example, if you have instances of an app running in more than one host, you'll easily be able to filter your app telemetry by host.</span></span>

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a><span data-ttu-id="7f271-122">设置 Application Insights 监视 Docker 应用程序和 Docker 主机</span><span class="sxs-lookup"><span data-stu-id="7f271-122">Setting up Application Insights to monitor Docker applications and Docker hosts</span></span>

<span data-ttu-id="7f271-123">若要创建 Application Insights 资源时，请执行后面的列表中显示的文章中的说明。</span><span class="sxs-lookup"><span data-stu-id="7f271-123">To create an Application Insights resource, follow the instructions in the articles presented in the list that follows.</span></span> <span data-ttu-id="7f271-124">Azure 门户将为你创建所需的脚本。</span><span class="sxs-lookup"><span data-stu-id="7f271-124">Azure Portal will create the necessary script for you.</span></span>

-   <span data-ttu-id="7f271-125">**监视 Docker Application Insights 中的应用程序：**[https://docs.microsoft.com/azure/application-insights/app-insights-docker  ](https://docs.microsoft.com/azure/application-insights/app-insights-docker)</span><span class="sxs-lookup"><span data-stu-id="7f271-125">**Monitor Docker applications in Application Insights:**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)</span></span>

-   <span data-ttu-id="7f271-126">**在 Docker Hub 和 Github 的应用程序 Insights Docker 映像：**</span><span class="sxs-lookup"><span data-stu-id="7f271-126">**Application Insights Docker image at Docker Hub and Github:**</span></span>  
<span data-ttu-id="7f271-127">[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/)和<https://github.com/Microsoft/ApplicationInsights-Docker></span><span class="sxs-lookup"><span data-stu-id="7f271-127">[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) and <https://github.com/Microsoft/ApplicationInsights-Docker></span></span>

-   <span data-ttu-id="7f271-128">**为 ASP.NET 配置 Application Insights 设置：**</span><span class="sxs-lookup"><span data-stu-id="7f271-128">**Set up Application Insights for ASP.NET:**</span></span>  
[<span data-ttu-id="7f271-129">https://docs.microsoft.com/azure/application-insights/app-insights-asp-net</span><span class="sxs-lookup"><span data-stu-id="7f271-129">https://docs.microsoft.com/azure/application-insights/app-insights-asp-net</span></span>](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   <span data-ttu-id="7f271-130">**网页的应用程序 Insights:**</span><span class="sxs-lookup"><span data-stu-id="7f271-130">**Application Insights for web pages:**</span></span>  
<span data-ttu-id="7f271-131"><https://docs.microsoft.com/azure/application-insights/app-insights-javascript></span><span class="sxs-lookup"><span data-stu-id="7f271-131"><https://docs.microsoft.com/azure/application-insights/app-insights-javascript></span></span>

## <a name="microsoft-operations-management-suite"></a><span data-ttu-id="7f271-132">Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="7f271-132">Microsoft Operations Management Suite</span></span>

<span data-ttu-id="7f271-133">[Operations Management Suite](http://microsoft.com/oms)是简化的 IT 管理解决方案，提供日志分析、 自动化、 备份和站点恢复。</span><span class="sxs-lookup"><span data-stu-id="7f271-133">[Operations Management Suite](http://microsoft.com/oms) is a simplified IT management solution that provides log analytics, automation, backup, and site recovery.</span></span> <span data-ttu-id="7f271-134">基于[查询](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/)中 Operations Management Suite，可以引发[警报](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts)并设置修正通过[Azure 自动化](https://docs.microsoft.com/azure/automation/)。</span><span class="sxs-lookup"><span data-stu-id="7f271-134">Based on [queries](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) in Operations Management Suite, you can raise [alerts](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) and set remediation via [Azure Automation](https://docs.microsoft.com/azure/automation/).</span></span> <span data-ttu-id="7f271-135">它还无缝集成与你现有的管理解决方案，以提供单一的窗格中的半透明视图。</span><span class="sxs-lookup"><span data-stu-id="7f271-135">It also seamlessly integrates with your existing management solutions to provide a single pane-of-glass view.</span></span> <span data-ttu-id="7f271-136">Operations Management Suite 可帮助你管理和保护本地和云基础结构。</span><span class="sxs-lookup"><span data-stu-id="7f271-136">Operations Management Suite helps you to manage and protect your on-premises and cloud infrastructure.</span></span>

### <a name="operations-management-suitehttpmicrosoftcomoms-container-solution-for-docker"></a><span data-ttu-id="7f271-137">[Operations Management Suite](http://microsoft.com/oms) for Docker 容器解决方案</span><span class="sxs-lookup"><span data-stu-id="7f271-137">[Operations Management Suite](http://microsoft.com/oms) Container Solution for Docker</span></span>

<span data-ttu-id="7f271-138">除了在其自身提供有价值的服务，操作管理套件容器解决方案可以管理和监视通过显示有关你的容器和容器主机在哪里，信息的 Docker 主机和容器容器正在运行或未通过，以及 Docker 守护程序和容器的日志发送到*stdout*和*stderr*。</span><span class="sxs-lookup"><span data-stu-id="7f271-138">In addition to providing valuable services on its own, the Operations Management Suite Container Solution can manage and monitor Docker hosts and containers by showing information about where your containers and container hosts are, which containers are running or failed, and Docker daemon and container logs sent to *stdout* and *stderr*.</span></span> <span data-ttu-id="7f271-139">它还显示性能度量值，如 CPU、 内存、 网络和存储对容器和主机来帮助你排查和查找干扰邻居容器。</span><span class="sxs-lookup"><span data-stu-id="7f271-139">It also shows performance metrics such as CPU, memory, network, and storage for the container and hosts to help you troubleshoot and find noisy neighbor containers.</span></span>

![](./media/image2.png)

<span data-ttu-id="7f271-140">有关 Docker 容器的 Operations Management Suite 所示的图 6-2： 信息</span><span class="sxs-lookup"><span data-stu-id="7f271-140">Figure 6-2: Information about Docker containers shown by Operations Management Suite</span></span>

<span data-ttu-id="7f271-141">Application Insights 和 Operations Management Suite 专注于监视活动;但是，Application Insights 更侧重于监视应用本身由于其 SDK 在应用内运行。</span><span class="sxs-lookup"><span data-stu-id="7f271-141">Application Insights and Operations Management Suite both focus on monitoring activities; however, Application Insights focuses more on monitoring the apps themselves thanks to its SDK running within the app.</span></span> <span data-ttu-id="7f271-142">但是，Operations Management Suite 得多重点解决主机，基础结构以及它提供的同时，提供一个十分灵活，数据驱动搜索/查询系统在规模较大的日志的深入分析。</span><span class="sxs-lookup"><span data-stu-id="7f271-142">However, Operations Management Suite focuses much more on the infrastructure around the hosts, plus it offers deep analysis on logs at scale while providing a very flexible data-driven search/query system.</span></span>

<span data-ttu-id="7f271-143">由于 Operations Management Suite 作为一项基于云的服务实现的你可以使其启动并正在运行快速基础结构服务中的最小投资。</span><span class="sxs-lookup"><span data-stu-id="7f271-143">Because Operations Management Suite is implemented as a cloud-based service, you can have it up and running quickly with minimal investment in infrastructure services.</span></span> <span data-ttu-id="7f271-144">新增功能，将自动传递，从而使您正在进行维护和升级的成本。</span><span class="sxs-lookup"><span data-stu-id="7f271-144">New features are delivered automatically, saving you from ongoing maintenance and upgrade costs.</span></span>

<span data-ttu-id="7f271-145">使用 Operations Management Suite 容器解决方案时，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7f271-145">Using Operations Management Suite Container Solution, you can do the following:</span></span>

-   <span data-ttu-id="7f271-146">集中并关联数以百万计的大规模的 Docker 容器中的日志</span><span class="sxs-lookup"><span data-stu-id="7f271-146">Centralize and correlate millions of logs from Docker containers at scale</span></span>

-   <span data-ttu-id="7f271-147">请参阅有关在单个位置的所有容器主机的信息</span><span class="sxs-lookup"><span data-stu-id="7f271-147">See information about all container hosts in a single location</span></span>

-   <span data-ttu-id="7f271-148">了解哪些容器是运行，哪些映像它们正在运行，请和其中运行它们</span><span class="sxs-lookup"><span data-stu-id="7f271-148">Know which containers are running, what image they're running, and where they're running</span></span>

-   <span data-ttu-id="7f271-149">快速诊断"干扰邻居"容器，可以在容器主机上会出现问题</span><span class="sxs-lookup"><span data-stu-id="7f271-149">Quickly diagnose "noisy neighbor" containers that can cause problems on container hosts</span></span>

-   <span data-ttu-id="7f271-150">请参阅在容器上的操作的审核跟踪</span><span class="sxs-lookup"><span data-stu-id="7f271-150">See an audit trail for actions on containers</span></span>

-   <span data-ttu-id="7f271-151">通过查看和搜索没有远程处理与 Docker 主机的集中式的日志疑难解答</span><span class="sxs-lookup"><span data-stu-id="7f271-151">Troubleshoot by viewing and searching centralized logs without remoting to the Docker hosts</span></span>

-   <span data-ttu-id="7f271-152">查找可能是"干扰性邻居"，在主机上的使用过多资源的容器</span><span class="sxs-lookup"><span data-stu-id="7f271-152">Find containers that might be "noisy neighbors" and consuming excess resources on a host</span></span>

-   <span data-ttu-id="7f271-153">查看集中式的 CPU、 内存、 存储和容器的网络使用情况和性能信息</span><span class="sxs-lookup"><span data-stu-id="7f271-153">View centralized CPU, memory, storage, and network usage and performance information for containers</span></span>

-   <span data-ttu-id="7f271-154">生成测试与 Azure 自动化的 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="7f271-154">Generate test Docker containers with Azure Automation</span></span>

<span data-ttu-id="7f271-155">你可以通过运行类似类型的查询来查看性能信息 = 性能，在图 6-3 中所示。</span><span class="sxs-lookup"><span data-stu-id="7f271-155">You can see performance information by running queries like Type=Perf, as shown in Figure 6-3.</span></span>

![DockerPerfMetricsView](./media/image3.png)<span data-ttu-id="7f271-157">{宽度 ="5.78625 中"height ="3.25 in"}</span><span class="sxs-lookup"><span data-stu-id="7f271-157">{width="5.78625in" height="3.25in"}</span></span>

<span data-ttu-id="7f271-158">图 6-3： 性能度量值的 Operations Management Suite 所示的 Docker 主机</span><span class="sxs-lookup"><span data-stu-id="7f271-158">Figure 6-3: Performance metrics of Docker hosts shown by Operations Management Suite</span></span>

<span data-ttu-id="7f271-159">保存查询也是中 Operations Management Suite 的标准功能，可帮助你保持查询已发现非常有用，并在你的系统中发现趋势。</span><span class="sxs-lookup"><span data-stu-id="7f271-159">Saving queries is also a standard feature in Operations Management Suite and can help you keep queries you've found useful and discover trends in your system.</span></span>

<span data-ttu-id="7f271-160">**详细信息** 若要查找有关安装和配置 Docker 容器中的解决方案[Operations Management Suite](http://microsoft.com/oms)，请转到<https://docs.microsoft.com/azure/日志-分析/日志-分析-容器>。</span><span class="sxs-lookup"><span data-stu-id="7f271-160">**More info** To find information on installing and configuring the Docker container solution in [Operations Management Suite](http://microsoft.com/oms), go to <https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="7f271-161">[以前](管理-生产-docker-environments.md) [下一步] (.../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="7f271-161">[Previous] (manage-production-docker-environments.md) [Next] (../key-takeaways/index.md)</span></span>