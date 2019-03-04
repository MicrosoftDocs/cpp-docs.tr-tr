---
title: 'Nasıl yapılır: Belirli Zamanlayıcı ilkelerini kullanan aracılar oluşturma'
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler policies, agents [Concurrency Runtime]
- creating agents that use specific policies [Concurrency Runtime]
ms.assetid: 46a3e265-0777-4ec3-a142-967bafc49d67
ms.openlocfilehash: 5aac86801015549b5552b51c06a30f8398346a06
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57257377"
---
# <a name="how-to-create-agents-that-use-specific-scheduler-policies"></a>Nasıl yapılır: Belirli Zamanlayıcı ilkelerini kullanan aracılar oluşturma

Zaman uyumsuz olarak daha büyük bilgi işlem görevlerini çözümlemek için diğer bileşenlerle birlikte çalışan bir uygulama bileşeni aracısıdır. Bir aracı genellikle ayarlanmış bir ömrü vardır ve durumu korur.

Her aracı benzersiz uygulama gereksinimleri olabilir. Örneğin, kullanıcı etkileşimi (girişi alma ya da çıktıyı görüntülerken) sağlayan bir aracı, bilgi işlem kaynaklarını daha yüksek öncelikli erişimi gerektirebilir. Zamanlayıcı ilkeleri görevleri yönettiğinde, Zamanlayıcı kullanan stratejisi denetlemenize olanak tanır. Bu konuda, belirli Zamanlayıcı ilkelerini kullanan aracılar oluşturma işlemini gösterir.

Zaman uyumsuz ileti blokları birlikte özel Zamanlayıcı ilkelerini kullanan temel bir örnek için bkz. [nasıl yapılır: Belirli Zamanlayıcı ilkeleri belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).

Bu konuda çalışmayı gerçekleştirmek için aracıları ve ileti blokları ileti geçirme işlevleri gibi zaman uyumsuz aracılar Kitaplığı'ndan işlevselliğini kullanır. Zaman uyumsuz aracılar Kitaplığı hakkında daha fazla bilgi için bkz: [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, türetilen iki sınıf tanımlar [concurrency::agent](../../parallel/concrt/reference/agent-class.md): `permutor` ve `printer`. `permutor` Sınıfı belirli bir Giriş dizesinin tüm permütasyon hesaplar. `printer` Sınıfı ilerleme durumu iletilerini konsola yazdırır. `permutor` Sınıfı, tüm kullanılabilir bilgi işlem kaynakları kullanabilir işlem bakımından yoğun bir işlem gerçekleştirir. Yararlı olması için `printer` sınıfı her ilerleme iletisi zamanında yazdırma gerekir.

Sağlamak üzere `printer` sınıf bilgi işlem kaynaklarına adil erişim, bu örnekte açıklanan adımları [nasıl yapılır: Zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) özel bir ilke bir zamanlayıcı örneği oluşturulamadı. Özel ilke, iş parçacığı önceliği en yüksek öncelikli sınıf olduğunu belirtir.

Bu örnek özel bir ilke bir Zamanlayıcı kullanmanın avantajları göstermek için iki kez genel görev gerçekleştirir. Örnek, ilk iki görevleri zamanlamak için varsayılan Zamanlayıcı kullanır. Örnek daha sonra zamanlamak için varsayılan Zamanlayıcı kullanır `permutor` nesnesi ve bir özel ilke zamanlamak için bir zamanlayıcı `printer` nesne.

[!code-cpp[concrt-permute-strings#1](../../parallel/concrt/codesnippet/cpp/how-to-create-agents-that-use-specific-scheduler-policies_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
With default scheduler:
Computing all permutations of 'Grapefruit'...
100% complete...

With higher context priority:
Computing all permutations of 'Grapefruit'...
100% complete...
```

İki görev aynı sonucu üretir, özel bir ilke kullanan bir sürüm etkinleştirir `printer` nesne yükseltilmiş bir öncelikli olarak çalıştırın, böylece daha duyarlı bir şekilde davranır.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `permute-strings.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe /EHsc permute-strings.cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Scheduler İlkeleri](../../parallel/concrt/scheduler-policies.md)<br/>
[Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)
