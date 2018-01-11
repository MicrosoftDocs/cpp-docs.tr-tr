---
title: "Görev Zamanlayıcı (eşzamanlılık çalışma zamanı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- oversubscription [Concurrency Runtime]
- task scheduler [Concurrency Runtime], oversubscription
- schedule groups [Concurrency Runtime]
- task scheduler [Concurrency Runtime], lightweight tasks
- task scheduler [Concurrency Runtime]
- lightweight tasks [Concurrency Runtime]
- task scheduler [Concurrency Runtime], scheduler policies
- task scheduler [Concurrency Runtime], schedule groups
- wait function [Concurrency Runtime]
- task scheduler [Concurrency Runtime], scheduler instances
- scheduler instances [Concurrency Runtime]
- scheduler policies [Concurrency Runtime]
- task scheduler [Concurrency Runtime], wait function
ms.assetid: 9aba278c-e0c9-4ede-b7c6-fedf7a365d90
caps.latest.revision: "42"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf8577b9fcb5ac734ee9eb935688002dbfe162da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="task-scheduler-concurrency-runtime"></a>Görev Zamanlayıcı (Eşzamanlılık Çalışma Zamanı)
Belgelerin Bu kısımdaki konular eşzamanlılık çalışma zamanı Görev Zamanlayıcısı'nın önemli özelliklerini açıklar. Görev Zamanlayıcısı'nı eşzamanlılık çalışma zamanı kullanan mevcut kodunuzu performansını ince ayarını yapmak istediğinizde kullanışlıdır.  
  
> [!IMPORTANT]
>  Görev Zamanlayıcısı'nı kullanılabilir olmayan bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulama. Daha fazla bilgi için bkz: [Windows mağazası uygulamalarında C++ zaman uyumsuz işlemler oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).  
>   
>  Visual Studio 2015 ve sonraki sürümlerinde, [concurrency::task](../../parallel/concrt/reference/task-class.md) sınıfı ve ppltasks.h ilgili türleri kendi Zamanlayıcı Windows iş parçacığı havuzu kullanın. Bu konu artık ppltasks.h içinde tanımlanan türler için de geçerlidir. Parallel_for gibi paralel algoritmalar eşzamanlılık çalışma zamanı varsayılan Zamanlayıcısı'nı kullanmaya devam edin.  
  
> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar ve bu nedenle, uygulamanızda oluşturmak için gerekli değildir. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ince ayar yardımcı olduğundan, ile başlamanızı öneririz [paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Eşzamanlılık Çalışma zamanı için yeni.  
  
 Görev Zamanlayıcısı'nı zamanlar ve çalışma zamanında görevleri düzenler. A *görev* belirli bir iş gerçekleştiren iş birimidir. Bir görev, genellikle diğer görevlerle Paralel çalıştırabilirsiniz. Görev Grup öğeleri, paralel algoritmalar ve zaman uyumsuz aracılar tarafından gerçekleştirilen iş görevlerinin tüm örnekler verilmiştir.  
  
 Görev Zamanlayıcı görevleri birden çok işlem kaynaklarının bilgisayarlara verimli bir şekilde zamanlamak için ilgili ayrıntıları yönetir. Görev Zamanlayıcı'yı da temel işletim sistemini en son özelliklerini kullanır. Bu nedenle, otomatik olarak eşzamanlılık çalışma zamanı kullanan uygulamaları ölçeklendirme ve yetenekleri genişletilmiştir donanımda geliştirmek.  
  
 [Diğer eşzamanlılık modelleriyle karşılaştırma](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md) PreEmptive tarafından ve işbirlikçi zamanlama mekanizmaları arasındaki farklar açıklanmaktadır. Görev Zamanlayıcısı'nı kaynakları işleme en fazla kullanım elde etmek için işbirlikçi zamanlama ve işletim sisteminin PreEmptive tarafından Zamanlayıcı ile birlikte bir iş çalarak algoritması kullanır.  
  
 Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sunar, böylece altyapı ayrıntıları yönetmek zorunda değilsiniz. Bu nedenle, genellikle Görev Zamanlayıcısı'nı doğrudan kullanmayın. Ancak, uygulamanızın kalite ihtiyaçlarını karşılamak için belirli görevler ile kendi zamanlama ilkesi veya ilişkilendirme zamanlayıcılar sağlamak için Görev Zamanlayıcısı'nı kullanabilirsiniz. Örneğin, dört işlemci ölçeklenmez yordamı sıralama paralel olduğunu varsayalım. Kullanabileceğiniz *Zamanlayıcı ilkeleri* dörtten fazla eş zamanlı görevleri oluşturan Zamanlayıcı oluşturma. Sıralama yordamı Bu zamanlayıcı üzerinde çalışan tüm kalan işlem kaynaklarını kullanmak etkin diğer zamanlayıcılar sağlar.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Zamanlayıcı Örnekleri](../../parallel/concrt/scheduler-instances.md)|Zamanlayıcı örnekleri ve nasıl kullanılacağını açıklar `concurrency::Scheduler` ve `concurrency::CurrentScheduler` bunları yönetmek için sınıflar. Zamanlayıcı örnekleri açık zamanlama ilkeleri belirli iş yükleri türleri ile ilişkilendirmek istediğiniz kullanın.|  
|[Scheduler İlkeleri](../../parallel/concrt/scheduler-policies.md)|Zamanlayıcı ilkeleri rolü açıklanmaktadır. Zamanlayıcı görevleri yönettiğinde kullanan stratejisi kontrol etmek istediğinizde Zamanlayıcı ilkeleri kullanın.|  
|[Zamanlama Grupları](../../parallel/concrt/schedule-groups.md)|Zamanlama grupları rolü açıklanmaktadır. İlgili görevleri grubunu zaman yere göre görevleri arasında yüksek derecede Örneğin, gerekirse, kullanım zamanlama grupları aynı işlemci düğümde yürütülen yararlanır.|  
|[Basit Görevler](../../parallel/concrt/lightweight-tasks.md)|Basit görevler rolü açıklanmaktadır. Basit görevler eşzamanlılık çalışma zamanı zamanlama işlevselliğini kullanmak için var olan kodu uyum olduğunda yararlıdır.|  
|[Bağlamlar](../../parallel/concrt/contexts.md)|Bağlamı, rolü açıklanmaktadır `concurrency::wait` işlevini ve `concurrency::Context` sınıfı. Ne zaman bağlamları engellemek, engellemesini kaldırmak ve verim veya aşırı abonelik uygulamanızda etkinleştirmek istediğiniz zaman denetime ihtiyacınız olduğunda bu işlevi kullanın.|  
|[Bellek Yönetimi İşlevleri](../../parallel/concrt/memory-management-functions.md)|Açıklar `concurrency::Alloc` ve `concurrency::Free` işlevleri. Bu işlevler bellek ayırma ve eş zamanlı bir biçimde bellek boşaltma olarak performansı artırabilir.|  
|[Diğer eşzamanlılık modelleriyle karşılaştırma](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|PreEmptive tarafından ve işbirlikçi zamanlama mekanizmaları arasındaki farklar açıklanmaktadır.|  
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Uygulamalarınızda çeşitli paralel desen, örneğin, paralel algoritmalar kullanmayı açıklar.|  
|[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)|Uygulamalarınızda zaman uyumsuz aracılar kullanmayı açıklar.|  
|[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)|Paralel Programlama basitleştiren ve ilgili konulara bağlantılar içerir eşzamanlılık çalışma, açıklar.|

