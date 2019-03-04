---
title: 'Nasıl yapılır: Belirli Zamanlayıcı ilkeleri belirtme'
ms.date: 11/04/2016
helpviewer_keywords:
- specifying scheduler policies [Concurrency Runtime]
- scheduler policies, specifying [Concurrency Runtime]
ms.assetid: 9c5149f9-ac34-4ff3-9e79-0bad103e4e6b
ms.openlocfilehash: 3c03ef6661ebefe0bfe9fab62938ce9987a4bca1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57277865"
---
# <a name="how-to-specify-specific-scheduler-policies"></a>Nasıl yapılır: Belirli Zamanlayıcı ilkeleri belirtme

Zamanlayıcı ilkeleri görevleri yönettiğinde, Zamanlayıcı kullanan stratejisi denetlemenize olanak tanır. Bu konuda, bir zamanlayıcı İlkesi bir İlerleme göstergesi konsola yazdırır. bir görevin iş parçacığı öncelik sırasını artırmak için nasıl kullanılacağını gösterir.

Zaman uyumsuz aracılar ile birlikte özel Zamanlayıcı ilkelerini kullanan bir örnek için bkz: [nasıl yapılır: Belirli Zamanlayıcı ilkelerini kullanan aracılar oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, iki görevi paralel olarak gerçekleştirir. İlk görev n hesaplar<sup>th</sup> Fibonacci sayı. İkinci görev bir İlerleme göstergesi konsola yazdırır.

İlk görev özyinelemeli ayrıştırma Fibonacci sayısını hesaplamak için kullanır. Diğer bir deyişle, her görev yinelemeli olarak alt görevlerin işlem genel sonuç oluşturur. Özyinelemeli ayrıştırma kullanan bir görev tüm kullanılabilir kaynakları kullanabilir ve böylece diğer görevleri yeterli kaynak kalmamasına neden. Bu örnekte, bilgi işlem kaynakları zamanında erişimi İlerleme göstergesi yazdırır görev almayabilir.

Bilgi işlem kaynakları için bir ilerleme iletisi adil erişim yazdırır görev sağlamak için bu örnekte açıklanan adımları kullanır [nasıl yapılır: Zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) özel bir ilke bir zamanlayıcı örneği oluşturulamadı. Özel ilke, iş parçacığı önceliği en yüksek öncelikli sınıf olduğunu belirtir.

Bu örnekte [concurrency::call](../../parallel/concrt/reference/call-class.md) ve [concurrency::timer](../../parallel/concrt/reference/timer-class.md) İlerleme göstergesi yazdırmak için sınıflar. Bu sınıfların oluşturucuları bir başvuru alan bir sürümü bir [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) bunları zamanlar nesne. Örnek Fibonacci sayısı ve İlerleme göstergesi yazdırır görevi zamanlamak için Zamanlayıcı örneğini hesaplar görevi zamanlamak için varsayılan Zamanlayıcı kullanır.

Bu örnek özel bir ilke bir Zamanlayıcı kullanmanın avantajları göstermek için iki kez genel görev gerçekleştirir. Örnek, ilk iki görevleri zamanlamak için varsayılan Zamanlayıcı kullanır. Örnek daha sonra ilk görevi zamanlamak için varsayılan Zamanlayıcı ve ikinci görevi zamanlamak için özel bir ilke bir zamanlayıcı kullanır.

[!code-cpp[concrt-scheduler-policy#1](../../parallel/concrt/codesnippet/cpp/how-to-specify-specific-scheduler-policies_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Default scheduler:
...........................................................................done
Scheduler that has a custom policy:
...........................................................................done
```

İki görev aynı sonucu üretir, özel bir ilke kullanan bir sürümü daha duyarlı bir şekilde davranması yükseltilmiş bir öncelikli olarak çalıştırmak için İlerleme göstergesi yazdırır görev etkinleştirir.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `scheduler-policy.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc Zamanlayıcı-policy.cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Scheduler İlkeleri](../../parallel/concrt/scheduler-policies.md)<br/>
[Nasıl yapılır: Zamanlayıcı Örneğini Yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[Nasıl yapılır: Belirli Zamanlayıcı İlkelerini Kullanan Aracılar Oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)
