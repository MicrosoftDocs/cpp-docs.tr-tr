---
title: 'Nasıl yapılır: Tamamlanan görevler arasında seçim'
ms.date: 11/04/2016
helpviewer_keywords:
- selecting among completed tasks [Concurrency Runtime]
- completed tasks, selecting among [Concurrency Runtime]
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
ms.openlocfilehash: 0d31f9bd16aaa70cc773e60e4f1193e66ec520f0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278034"
---
# <a name="how-to-select-among-completed-tasks"></a>Nasıl yapılır: Tamamlanan görevler arasında seçim

Bu örnek nasıl kullanılacağını gösterir [concurrency::choice](../../parallel/concrt/reference/choice-class.md) ve [concurrency::join](../../parallel/concrt/reference/join-class.md) sınıflar arama algoritması tamamlamak için ilk görevi seçin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, iki arama algoritmaları paralel olarak gerçekleştirir ve tamamlamak için ilk algoritmasını seçer. Bu örnek tanımlar `employee` türü, bir çalışan için bir sayısal tanımlayıcı ve bir ücret tutar. `find_employee` İşlevi için sağlanan tanımlayıcı veya sağlanan maaş sahip ilk çalışanın bulur. `find_employee` İşlevi ayrıca sağlanan tanımlayıcı veya Maaş çalışan bulunduğu durumu işler. `wmain` İşlevi bir dizi oluşturur `employee` nesneleri ve tanımlayıcı ve maaş değerlerden arar.

Örnekte bir `choice` arasında aşağıdaki durumlarda Seçilecek nesne:

1. Belirtilen tanımlayıcı bir çalışan var.

1. Sağlanan maaş bir çalışan var.

1. Belirtilen tanımlayıcı veya maaş hiçbir çalışan var.

İlk iki durumlarda, örnekte bir [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) tanımlayıcısı ve başka tutacak nesne `single_assignment` maaş tutacak nesne. Örnekte bir `join` üçüncü durumda nesne. `join` Nesne iki ek oluşur `single_assignment` nesneleri, sağlanan tanımlayıcı hiçbir çalışan mevcut olduğu durum için bir tane ve sağlanan maaş hiçbir çalışan mevcut olduğu durum için bir tane. `join` Nesneyi her üyenin bir ileti alındığında bir ileti gönderir. Bu örnekte, `join` maaş yok veya nesne belirtilen tanımlayıcı sahip hiçbir çalışanı, bir ileti gönderir.

Örnekte bir [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) her iki arama algoritmaları paralel olarak çalıştırmak için nesne. Her arama görevi birine Yazar `single_assignment` verilen çalışan mevcut olup olmadığını belirtmek için nesnelerdeki. Örnekte [concurrency::receive](reference/concurrency-namespace-functions.md#receive) bir ileti içeren ilk arabellek dizinini elde etmek için işlevi ve bir `switch` bloğu sonucu yazdırın.

[!code-cpp[concrt-find-employee#1](../../parallel/concrt/codesnippet/cpp/how-to-select-among-completed-tasks_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Employee with id 14758 has salary 27780.00.
Employee with salary 29150.00 has id 84345.
Employee with id 61935 has salary 29905.00.
No employee has id 899 or salary 31223.00.
```

Bu örnekte [concurrency::make_choice](reference/concurrency-namespace-functions.md#make_choice) oluşturmak için yardımcı işlevini `choice` nesneleri ve [concurrency::make_join](reference/concurrency-namespace-functions.md#make_join) oluşturmak için yardımcı işlevini `join` nesneleri.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `find-employee.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc Bul-employee.cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[choice Sınıfı](../../parallel/concrt/reference/choice-class.md)<br/>
[join Sınıfı](../../parallel/concrt/reference/join-class.md)
