---
title: "Eşzamanlılık Çalışma zamanı genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Concurrency Runtime, requirements
- Concurrency Runtime, architecture
- Concurrency Runtime, overview
- Concurrency Runtime, lambda expressions
ms.assetid: 56237d96-10b0-494a-9cb4-f5c5090436c5
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ce1967b04770f53c2e1acbd49342f9080a7e3c12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-the-concurrency-runtime"></a>Eşzamanlılık Çalışma Zamanına Genel Bakış
Bu belge eşzamanlılık çalışma zamanı genel bir bakış sağlar. Eşzamanlılık Çalışma zamanı yararlarını açıklar ne zaman kullanılmalı ve bileşenlerinin birbirleriyle ve işletim sistemi ve uygulamalar ile nasıl etkileşime.  
  
> [!IMPORTANT]
>  Visual Studio 2015 ve sonraki sürümlerinde, eşzamanlılık çalışma zamanı Görev Zamanlayıcısı'nı artık Zamanlayıcı görevi sınıfı ve ppltasks.h ilgili türleri için değil. Bu türlerde artık Windows iş parçacığı havuzu daha iyi performans ve birlikte çalışabilirlik için Windows eşitleme temelleri ile kullanın. Parallel_for gibi paralel algoritmalar eşzamanlılık çalışma zamanı Görev Zamanlayıcısı'nı kullanmaya devam edin.  
  
##  <a name="top"></a>Bölümler  
 Bu belgede aşağıdaki bölümler yer alır:  
  
-   [Eşzamanlılık Çalışma Zamanı Modülü önemli neden olduğunu](#runtime)  
  
-   [Mimari](#architecture)  
  
-   [C++ Lambda ifadeleri](#lambda)  
  
-   [Gereksinimler](#requirements)  
  
##  <a name="runtime"></a>Eşzamanlılık Çalışma Zamanı Modülü önemli neden olduğunu  
 Eşzamanlılık Çalışma Zamanı Modülü bütünlüğünü ve öngörülebilirlik uygulamaları ve aynı anda çalışmasına uygulama bileşenleri için sağlar. Eşzamanlılık Çalışma zamanı avantajları iki örnek verilmiştir *işbirlikçi görev zamanlama* ve *işbirlikçi engelleme*.  
  
 Eşzamanlılık Çalışma Zamanı İş bilgi işlem kaynakları arasında verimli bir şekilde dağıtmak için bir iş çalarak algoritması uygulayan bir işbirlikçi Görev Zamanlayıcısı'nı kullanır. Örneğin, her ikisi de aynı çalışma zamanı tarafından yönetilen iki iş parçacığı olan bir uygulama göz önünde bulundurun. Bir iş parçacığı, zamanlanmış görevini tamamlanırsa başka bir iş parçacığı işten boşaltabilir. Bu mekanizma uygulama genel iş yükünü dengeler.  
  
 Eşzamanlılık Çalışma zamanı kullanan işbirlikçi engelleme kaynaklarına erişimi eşitlemek için eşitleme temelleri de sağlar. Örneğin, paylaşılan bir kaynağa özel erişim olmalıdır bir görev göz önünde bulundurun. Çalışma işlevinizde engelleyerek, kaynak için ilk görev bekler gibi başka bir görevi gerçekleştirmek için kalan Zamanlayıcının kullanabilirsiniz. Bu düzenek, bilgi işlem kaynaklarının en fazla kullanım yükseltir.  
  
 [[Üst](#top)]  
  
##  <a name="architecture"></a>Mimarisi  
 Eşzamanlılık Çalışma zamanı dört bileşenlerine ayrılır: paralel Desen kitaplığı (PPL), zaman uyumsuz aracılar kitaplığı, Görev Zamanlayıcısı'nı ve Resource Manager. Bu bileşenler işletim sistemi ve uygulamalar arasında bulunur. Aşağıdaki çizimde eşzamanlılık çalışma zamanı bileşenleri işletim sistemi ve uygulamalar arasında nasıl etkileşim kurduğu gösterilmektedir:  
  
 **Eşzamanlılık Çalışma zamanı mimarisi**  
  
 ![Eşzamanlılık Çalışma zamanı mimarisi](../../parallel/concrt/media/concurrencyrun.png "concurrencyrun")  
  
> [!IMPORTANT]
>  Görev Zamanlayıcı ve Resource Manager bileşenleri kullanılabilir olmayan bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulama veya görev sınıfı veya diğer türleri içinde ppltasks.h kullandığınızda.  
  
 Eşzamanlılık Çalışma zamanı yüksek olan *birleştirilebilir*, diğer bir deyişle, daha fazla yapmak için var olan işlevselliği birleştirebilirsiniz. Eşzamanlılık Çalışma zamanı, alt düzey bileşenlerden paralel algoritmalar gibi birçok özellik oluşturur.  
  
 Eşzamanlılık Çalışma zamanı kullanan işbirlikçi engelleme kaynaklarına erişimi eşitlemek için eşitleme temelleri de sağlar. Bu eşitleme temelleri hakkında daha fazla bilgi için bkz: [eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md).  
  
 Aşağıdaki bölümler, her bileşenin ne sağlar ve ne zaman kullanılmalı kısa bir genel bakış sağlar.  
  
### <a name="parallel-patterns-library"></a>Paralel Desen Kitaplığı  
 Paralel Desen kitaplığı (PPL), hassas paralellik gerçekleştirmek için genel amaçlı kapsayıcıları ve algoritmaları sağlar. PPL'de sağlayan *kesinlik temelli veri paralelliği* bilgi işlem kaynakları arasında hesaplamalar koleksiyonları veya veri kümesi dağıtma paralel algoritmalar sağlayarak. Ayrıca sağlar *görev paralelliği* bilgi işlem kaynakları arasında birden çok bağımsız işlemler dağıtmak görev nesneleri sağlayarak.  
  
 Paralel Desen kitaplığı paralel çalıştırmadan yararlanırlar yerel bir hesaplama sahip olduğunuzda kullanın. Örneğin, kullanabileceğiniz [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) varolan dönüştürmek için algoritma `for` paralel olarak davranmak üzere döngü.  
  
 Paralel desen Kitaplığı hakkında daha fazla bilgi için bkz: [paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md).  
  
### <a name="asynchronous-agents-library"></a>Zaman Uyumsuz Aracılar Kitaplığı  
 Zaman uyumsuz aracılar kitaplığı (veya yalnızca *Aracılar Kitaplığı*) bir aktör tabanlı programlama modeli ve ileti geçirme parçalı veri akışı için arabirimleri ve görevleri ardışık düzen sağlar. Zaman uyumsuz aracılar için verileri diğer bileşenleri bekleyen iş gerçekleştirerek gecikme verimli kullanılmasını sağlamak etkinleştirin.  
  
 Zaman uyumsuz olarak birbirleriyle iletişim birden çok varlık varsa aracılar kitaplığı kullanın. Örneğin, bir dosya veya ağ bağlantısından veri okuyan ve bu verileri başka bir aracıya göndermek için ileti arabirimleri geçirme kullanan bir aracı oluşturabilirsiniz.  
  
 Aracılar Kitaplığı hakkında daha fazla bilgi için bkz: [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md).  
  
### <a name="task-scheduler"></a>Görev Zamanlayıcısı  
 Görev Zamanlayıcısı'nı zamanlar ve çalışma zamanında görevleri düzenler. Görev Zamanlayıcı işbirlikçi ve işleme kaynaklarına, en fazla kullanım elde etmek için bir iş çalarak algoritması kullanır.  
  
 Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sunar, böylece altyapı ayrıntıları yönetmek zorunda değilsiniz. Ancak, uygulamanızın kalite ihtiyaçlarını karşılamak üzere, ayrıca belirli görevler zamanlama kendi ilke ya da ilişkilendirme belirli zamanlayıcılar sağlayabilirsiniz.  
  
 Görev Zamanlayıcısı'nı hakkında daha fazla bilgi için bkz: [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
### <a name="resource-manager"></a>Kaynak Yöneticisi  
 Kaynak Yöneticisi'nin işlemciler ve bellek gibi bilgi işlem kaynaklarını yönetmek için rolüdür. Bunlar burada en etkili olabilirler için kaynakları atayarak çalışma zamanında değiştikçe Resource Manager iş yükleri için yanıt verir.  
  
 Kaynak Yöneticisi'ni bilgi işlem kaynakları bir Özet hizmet verir ve öncelikle Görev Zamanlayıcısı ile etkileşim kurar. Kitaplıklar ve uygulamaların performansını ince ayar yapmak için Kaynak Yöneticisi'ni kullanabilirsiniz ancak genellikle paralel Desen kitaplığı, aracılar kitaplığı ve Görev Zamanlayıcı tarafından sağlanan işlevselliği kullanın. Bu kitaplıklar, iş yüklerini değiştirme gibi kaynakları dinamik olarak yeniden dengelemeniz Kaynak Yöneticisi'ni kullanın.  
  
 [[Üst](#top)]  
  
##  <a name="lambda"></a>C++ Lambda ifadeleri  
 Eşzamanlılık Çalışma zamanı tarafından tanımlanan algoritmaları ve türleri çoğunu C++ şablonları uygulanır. Bu türleri ve algoritmaları bazıları çalışma gerçekleştirir bir yordama parametre olarak alın. Bu parametre bir lambda işlevi, bir işlev nesnesi veya bir işlev işaretçisi olabilir. Bu varlıklar olarak da adlandırılan *iş işlevleri* veya *çalışma yordamları*.  
  
 Lambda ifadeleri önemli bir yeni Visual C++ dili özelliği olduklarından paralel işleme iş işlevleri tanımlamak için kısa bir yol sağlar. İşlev nesneleri ve işlev işaretçileri eşzamanlılık çalışma zamanı ile varolan kodunuzu kullanmanıza olanak sağlar. Ancak, sağladıkları güvenliği ve üretkenlik avantajları nedeniyle yeni kodu yazarken lambda ifadeleri kullanmanızı öneririz.  
  
 Aşağıdaki örnek sözdizimi lambda işlevleri, işlev nesneleri ve birden çok çağrılarında işlev işaretçileri karşılaştırır [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritması. Her çağrı `parallel_for_each` her bir öğe kare hesaplamak için farklı bir teknik kullanan bir [std::array](../../standard-library/array-class-stl.md) nesnesi.  
  
 [!code-cpp[concrt-comparing-work-functions#1](../../parallel/concrt/codesnippet/cpp/overview-of-the-concurrency-runtime_1.cpp)]  
  
 **Output**  
  
```Output  
1  
256  
6561  
65536  
390625  
```  
  
 C++'ta lambda işlevleri hakkında daha fazla bilgi için bkz: [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).  
  
 [[Üst](#top)]  
  
##  <a name="requirements"></a>Gereksinimleri  
 Aşağıdaki tabloda her eşzamanlılık çalışma zamanı bileşeni ile ilişkili olan üstbilgi dosyaları gösterilmektedir:  
  
|Bileşen|Üstbilgi Dosyaları|  
|---------------|------------------|  
|Paralel Desen Kitaplığı (PPL)|ppl.h<br /><br /> concurrent_queue.h<br /><br /> concurrent_vector.h|  
|Zaman Uyumsuz Aracılar Kitaplığı|Agents.h|  
|Görev Zamanlayıcısı|concrt.h|  
|Kaynak Yöneticisi|concrtrm.h|  
  
 Eşzamanlılık Çalışma zamanı içinde bildirilen [eşzamanlılık](../../parallel/concrt/reference/concurrency-namespace.md) ad alanı. (Aynı zamanda [eşzamanlılık](../../parallel/concrt/reference/concurrency-namespace.md), bu ad alanı için bir diğer ad değil.) `concurrency::details` Ad alanı eşzamanlılık çalışma zamanı çerçevesi destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
 Eşzamanlılık Çalışma zamanı C çalışma zamanı kitaplığı (CRT) bir parçası olarak sağlanır. CRT kullanan bir uygulama oluşturma hakkında daha fazla bilgi için bkz: [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).  
  
 [[Üst](#top)]



