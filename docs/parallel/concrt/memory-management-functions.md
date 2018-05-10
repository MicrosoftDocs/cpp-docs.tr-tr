---
title: Bellek Yönetimi işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory management functions [Concurrency Runtime]
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0a298c7fb9e50bb17d37224b69ce342c54115d7
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="memory-management-functions"></a>Bellek Yönetimi İşlevleri
Bu belgede eşzamanlılık çalışma zamanı ayırın ve eş zamanlı bir biçimde belleği serbest yardımcı olmak için sağladığı bellek yönetimi işlevleri açıklanmaktadır.  
  
> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar ve bu nedenle, uygulamanızda oluşturmak için gerekli değildir. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ince ayar yardımcı olduğundan, ile başlamanızı öneririz [paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Eşzamanlılık Çalışma zamanı için yeni.  
  
 Eşzamanlılık Çalışma zamanı ayırma ve bellek bloklarını eşzamanlı bir biçimde boşaltma için iyileştirilmiş iki bellek yönetimi işlevleri sağlar. [Concurrency::Alloc](reference/concurrency-namespace-functions.md#alloc) işlevi, belirtilen boyut kullanarak bir bellek bloğu ayırır. [Concurrency::Free](reference/concurrency-namespace-functions.md#free) işlevi tarafından ayrılmış bellek boşaltır `Alloc`.  
  
> [!NOTE]
>  `Alloc` Ve `Free` işlevleri birbirine dayanır. Kullanım `Free` işlevi yalnızca kullanarak tahsis belleği serbest `Alloc` işlevi. Ayrıca, kullandığınızda `Alloc` bellek ayıramadı, yalnızca kullanın işlevi `Free` belleğin yayımlamayı işlevi.  
  
 Kullanım `Alloc` ve `Free` ayırın ve farklı iş parçacıklarındaki veya görevler ayırma boyutları sabit bir dizi boş olduğunda çalışır. Eşzamanlılık Çalışma zamanı C çalışma zamanı yığınından ayırır bellek önbelleğe alır. Eşzamanlılık Çalışma zamanı her çalışan iş parçacığı için ayrı bir önbellek tutar; Bu nedenle, çalışma zamanı bellek kilitleri ya da bellek engelleri kullanmadan yönetir. Bir uygulama'dan daha fazla avantaj `Alloc` ve `Free` önbellek daha sık erişilen çalışır. Örneğin, sık her ikisi de çağıran bir iş parçacığı `Alloc` ve `Free` avantajları öncelikle çağıran iş parçacığı'den fazla `Alloc` veya `Free`.  
  
> [!NOTE]
>  Bu bellek yönetimi işlevleri kullandığınızda ve, uygulamanın kullandığı miktarda bellek, uygulama girebilirsiniz düşük bellek koşulunu er beklediğiniz. Bir iş parçacığı tarafından önbelleğe alınan bellek blokları herhangi başka bir iş parçacığı için bir iş parçacığı miktarda bellek tutuyorsa kullanılabilir olmadığından, bu bellek kullanılabilir değil.  
  
## <a name="example"></a>Örnek  
 Kullanan bir örnek `Alloc` ve `Free` işlevleri bellek performansını iyileştirmek için bkz: [nasıl yapılır: kullanım ayırma ve serbest bellek performansını artırmak için](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)

