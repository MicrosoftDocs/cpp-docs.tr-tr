---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: belirli Zamanlayıcı Ilkeleri belirtme'
title: 'Nasıl yapılır: Belirli Zamanlayıcı İlkeleri Belirtme'
ms.date: 11/04/2016
helpviewer_keywords:
- specifying scheduler policies [Concurrency Runtime]
- scheduler policies, specifying [Concurrency Runtime]
ms.assetid: 9c5149f9-ac34-4ff3-9e79-0bad103e4e6b
ms.openlocfilehash: c4aeeea04d69613ef3eb80f36863b16530e18e37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197263"
---
# <a name="how-to-specify-specific-scheduler-policies"></a>Nasıl yapılır: Belirli Zamanlayıcı İlkeleri Belirtme

Zamanlayıcı ilkeleri, Scheduler 'ın görevleri yönetirken kullandığı stratejiyi denetlemenize olanak tanır. Bu konuda, bir Zamanlayıcı ilkesinin, konsola ilerleme göstergesini yazdıran bir görevin iş parçacığı önceliğini artırmak için nasıl kullanılacağı gösterilmektedir.

Özel Zamanlayıcı ilkelerini zaman uyumsuz aracılarla birlikte kullanan bir örnek için bkz. [nasıl yapılır: belirli Zamanlayıcı Ilkelerini kullanan aracılar oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek paralel olarak iki görevi gerçekleştirir. İlk<sup>görev n.</sup> fibonaccı numarasını hesaplar. İkinci görev konsola bir ilerleme göstergesi yazdırır.

İlk görev, Fibonaccı numarasını hesaplamak için özyinelemeli ayrıştırma kullanır. Diğer bir deyişle, her bir görev, genel sonucu hesaplamak için yinelemeli olarak alt görevler oluşturur. Özyinelemeli ayrıştırma kullanan bir görev, kullanılabilir tüm kaynakları kullanabilir ve bu nedenle diğer görevleri de daha sonra harekete çıkabilir. Bu örnekte, ilerleme göstergesini yazdıran görev, bilgi işlem kaynaklarına zamanında erişim alamayabilir.

İşlem kaynaklarına yönelik bir ilerleme durumu iletisi erişimi yazdıran görevi sağlamak için bu örnek, özel ilkeye sahip bir zamanlayıcı örneği oluşturmak için [bir zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) bölümünde açıklanan adımları kullanır. Özel ilke, en yüksek öncelik sınıfı olacak iş parçacığı önceliğini belirtir.

Bu örnek, ilerleme göstergesini yazdırmak için [concurrency:: Call](../../parallel/concrt/reference/call-class.md) ve [concurrency:: Timer](../../parallel/concrt/reference/timer-class.md) sınıflarını kullanır. Bu sınıfların, kendilerini zamanlayan [eşzamanlılık:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) nesnesine başvuru alan oluşturucularının sürümleri vardır. Örnek, ilerleme göstergesini yazdıran görevi zamanlamak için Fibonaccı numarasını ve zamanlayıcı örneğini hesaplayan görevi zamanlamak için varsayılan zamanlayıcıyı kullanır.

Özel ilkeye sahip bir Scheduler kullanmanın avantajlarını göstermek için bu örnek genel görevi iki kez gerçekleştirir. Örnek öncelikle her iki görevi zamanlamak için varsayılan zamanlayıcıyı kullanır. Örnek daha sonra ilk görevi zamanlamak için varsayılan zamanlayıcıyı ve ikinci görevi zamanlamak için özel bir ilkeye sahip bir zamanlayıcıyı kullanır.

[!code-cpp[concrt-scheduler-policy#1](../../parallel/concrt/codesnippet/cpp/how-to-specify-specific-scheduler-policies_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Default scheduler:
...........................................................................done
Scheduler that has a custom policy:
...........................................................................done
```

Her iki görev kümesi de aynı sonucu oluşturuyor olsa da, özel bir ilke kullanan sürüm, ilerleme göstergesini yazdıran görevin, daha fazla boyutlandırılabilir davranması için yükseltilmiş bir önceliğe göre çalıştırılmasını sağlar.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `scheduler-policy.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Scheduler-Policy. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zamanlayıcı Ilkeleri](../../parallel/concrt/scheduler-policies.md)<br/>
[Nasıl yapılır: zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[Nasıl yapılır: belirli Zamanlayıcı Ilkelerini kullanan aracılar oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)
