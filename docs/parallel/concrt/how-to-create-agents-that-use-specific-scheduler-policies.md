---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: belirli Zamanlayıcı Ilkelerini kullanan aracılar oluşturma'
title: 'Nasıl yapılır: Belirli Zamanlayıcı İlkelerini Kullanan Aracılar Oluşturma'
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler policies, agents [Concurrency Runtime]
- creating agents that use specific policies [Concurrency Runtime]
ms.assetid: 46a3e265-0777-4ec3-a142-967bafc49d67
ms.openlocfilehash: 06a7ffaf18f3d7024f99755a0595154197c396f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333459"
---
# <a name="how-to-create-agents-that-use-specific-scheduler-policies"></a>Nasıl yapılır: Belirli Zamanlayıcı İlkelerini Kullanan Aracılar Oluşturma

Aracı, daha büyük bilgi işlem görevlerini çözümlemek için diğer bileşenlerle zaman uyumsuz olarak çalışan bir uygulama bileşenidir. Bir aracı genellikle ayarlanmış bir yaşam döngüsüne sahiptir ve durumu korur.

Her aracı benzersiz uygulama gereksinimlerine sahip olabilir. Örneğin, kullanıcı etkileşimini sağlayan (giriş veya çıkış görüntüleme) bir aracı, bilgi işlem kaynaklarına daha yüksek öncelikli erişim gerektirebilir. Zamanlayıcı ilkeleri, Scheduler 'ın görevleri yönetirken kullandığı stratejiyi denetlemenize olanak tanır. Bu konuda, belirli Zamanlayıcı ilkelerini kullanan aracıların nasıl oluşturulacağı gösterilmektedir.

Özel Zamanlayıcı ilkelerini zaman uyumsuz ileti bloklarıyla birlikte kullanan temel bir örnek için bkz. [nasıl yapılır: belirli Zamanlayıcı Ilkeleri belirtme](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).

Bu konu, iş gerçekleştirmek için aracılar, ileti blokları ve ileti geçirme işlevleri gibi zaman uyumsuz aracılar kitaplığındaki işlevleri kullanır. Zaman uyumsuz aracılar Kitaplığı hakkında daha fazla bilgi için bkz. [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, [concurrency:: Agent](../../parallel/concrt/reference/agent-class.md): ve öğesinden türetilen iki sınıfı tanımlar `permutor` `printer` . `permutor`Sınıfı, belirli bir giriş dizesinin tüm permütasyonları hesaplar. `printer`Sınıfı, ilerleme mesajlarını konsola yazdırır. `permutor`Sınıfı, kullanılabilir tüm bilgi işlem kaynaklarını kullanan, hesaplama açısından yoğun bir işlem gerçekleştirir. Yararlı olması için, `printer` sınıf her bir ilerleme iletisini zamanında yazdırmalıdır.

`printer`Bu örnekte, sınıfa bilgi işlem kaynaklarına yönelik erişim sağlamak için, özel ilkeye sahip bir zamanlayıcı örneği oluşturmak için [bir zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) bölümünde açıklanan adımlar kullanılmaktadır. Özel ilke, en yüksek öncelik sınıfı olacak iş parçacığı önceliğini belirtir.

Özel ilkeye sahip bir Scheduler kullanmanın avantajlarını göstermek için bu örnek genel görevi iki kez gerçekleştirir. Örnek öncelikle her iki görevi zamanlamak için varsayılan zamanlayıcıyı kullanır. Örnek daha sonra, nesneyi zamanlamak için varsayılan zamanlayıcıyı `permutor` ve nesneyi zamanlamak için özel bir ilkeye sahip bir zamanlayıcıyı kullanır `printer` .

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

Her iki görev kümesi de aynı sonucu üretir, ancak özel bir ilke kullanan sürüm, `printer` nesnenin daha fazla boyutlandırılabilir davranması için yükseltilmiş öncelikte çalışmasına olanak sağlar.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `permute-strings.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc permute-Strings. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zamanlayıcı Ilkeleri](../../parallel/concrt/scheduler-policies.md)<br/>
[Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)
