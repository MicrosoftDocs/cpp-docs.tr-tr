---
title: 'Nasıl yapılır: belirli Zamanlayıcı ilkelerini kullanan aracılar oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scheduler policies, agents [Concurrency Runtime]
- creating agents that use specific policies [Concurrency Runtime]
ms.assetid: 46a3e265-0777-4ec3-a142-967bafc49d67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9efa40d24ed4eaee5b9fd3995a4cf9ed696eb39a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-create-agents-that-use-specific-scheduler-policies"></a>Nasıl yapılır: Belirli Zamanlayıcı İlkelerini Kullanan Aracılar Oluşturma
Bir aracı zaman uyumsuz olarak daha büyük hesaplama görevlerini çözümlemek için diğer bileşenlerle birlikte çalışan bir uygulama bileşendir. Bir aracı tipik olarak ayarlanmış bir yaşam döngüsü sahiptir ve durumu korur.  
  
 Her aracı benzersiz uygulama gereksinimleri olabilir. Örneğin, (girişi alma veya çıkış görüntüleme) kullanıcı etkileşimi sağlayan bir aracı bilgi işlem kaynakları yüksek öncelikli erişimi gerektirebilir. Zamanlayıcı ilkeleri Zamanlayıcısı görevleri yönettiğinde kullanan stratejisi denetlemenize olanak verir. Bu konuda, belirli Zamanlayıcı ilkelerini kullanan aracılar oluşturma gösterilir.  
  
 Zaman uyumsuz ileti blokları birlikte özel Zamanlayıcı ilkeleri kullanan temel bir örnek için bkz: [nasıl yapılır: belirli Zamanlayıcı ilkeleri belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).  
  
 Bu konuda aracıları, ileti blokları ve ileti geçirme işlevleri gibi zaman uyumsuz aracılar kitaplığı işlerini yapmak için ana kadar işlevi kullanır. Zaman uyumsuz aracılar Kitaplığı hakkında daha fazla bilgi için bkz: [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, türetilen iki sınıf tanımlar [concurrency::agent](../../parallel/concrt/reference/agent-class.md): `permutor` ve `printer`. `permutor` Sınıfı, belirli bir giriş dizesi tüm permütasyon hesaplar. `printer` Sınıfı ilerleme durumu iletilerini konsola yazdırır. `permutor` Sınıfı, tüm kullanılabilir bilgi işlem kaynakları kullanabilir pkı'ya yoğun bir işlem gerçekleştirir. Yararlı olacak şekilde `printer` sınıfı zamanında her ilerleme iletisi yazdırma gerekir.  
  
 Sağlamak için `printer` sınıfı Orta bilgi işlem kaynaklarına erişim Bu örnekte açıklanan adımları [nasıl yapılır: Zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) özel bir ilke olan Zamanlayıcı örneğini oluşturmak için. Özel ilke en yüksek öncelik sınıf olmak için iş parçacığı önceliği belirtir.  
  
 Özel bir ilke bir Zamanlayıcı kullanmanın avantajları göstermek için bu örnek iki kez genel görevi gerçekleştirir. Örnek, varsayılan Zamanlayıcı ilk iki görev zamanlama için kullanır. Örnek zamanlamak için varsayılan Zamanlayıcı sonra kullanır `permutor` nesne ve zamanlamak için özel bir ilke bir zamanlayıcı `printer` nesnesi.  
  
 [!code-cpp[concrt-permute-strings#1](../../parallel/concrt/codesnippet/cpp/how-to-create-agents-that-use-specific-scheduler-policies_1.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
With default scheduler:  
Computing all permutations of 'Grapefruit'...  
100% complete...  
 
With higher context priority:  
Computing all permutations of 'Grapefruit'...  
100% complete...  
```  
  
 İki görevlerin aynı sonucu verir ancak özel bir ilke kullanan sürüm etkinleştirir `printer` daha responsively davranması yükseltilmiş öncelikli olarak çalıştırmak için nesne.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `permute-strings.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **permute cl.exe /EHsc-strings.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zamanlayıcı ilkeleri](../../parallel/concrt/scheduler-policies.md)   
 [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)   
 

