---
title: 'Nasıl yapılır: Tamamlanan Görevler Arasında Seçim Yapma'
ms.date: 11/04/2016
helpviewer_keywords:
- selecting among completed tasks [Concurrency Runtime]
- completed tasks, selecting among [Concurrency Runtime]
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
ms.openlocfilehash: 75ecac8dd0e8845401e3e287e8c95ea614055970
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142478"
---
# <a name="how-to-select-among-completed-tasks"></a>Nasıl yapılır: Tamamlanan Görevler Arasında Seçim Yapma

Bu örnek, bir arama algoritmasını tamamlamaya yönelik ilk görevi seçmek için [concurrency:: Choice](../../parallel/concrt/reference/choice-class.md) ve [concurrency:: JOIN](../../parallel/concrt/reference/join-class.md) sınıflarının nasıl kullanılacağını gösterir.

## <a name="example"></a>Örnek

Aşağıdaki örnek paralel olarak iki arama algoritması gerçekleştirir ve tamamlanacak ilk algoritmayı seçer. Bu örnek, bir çalışan için sayısal tanımlayıcıyı ve bir maaş tutan `employee` türünü tanımlar. `find_employee` işlevi, belirtilen tanımlayıcıya veya belirtilen maaşa sahip olan ilk çalışanı bulur. `find_employee` işlevi, çalışan tanımlayıcı ya da maaş olmayan durumu da işler. `wmain` işlevi `employee` nesnelerden oluşan bir dizi oluşturur ve birkaç tanımlayıcı ve maaş değeri arar.

Örnek, aşağıdaki durumlar arasından seçim yapmak için bir `choice` nesnesi kullanır:

1. Belirtilen tanımlayıcıya sahip bir çalışan var.

1. Belirtilen maaşa sahip bir çalışan var.

1. Belirtilen tanımlayıcıya veya maaşa sahip çalışan yok.

İlk iki durumda örnek, tanımlayıcıyı tutmak için bir [eşzamanlılık:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) nesnesini ve maaşı tutacak başka bir `single_assignment` nesnesini kullanır. Örnek, üçüncü bir durum için `join` nesnesi kullanır. `join` nesnesi iki ek `single_assignment` nesnesinden oluşur, biri, belirtilen tanımlayıcıya sahip olmayan bir çalışan olmadığı ve bir çalışanın, belirtilen maaşa sahip olmadığı bir çalışan olmadığı durumlar için. `join` nesnesi, üyelerinden her biri bir ileti aldığında bir ileti gönderir. Bu örnekte, `join` nesnesi, belirtilen tanımlayıcı veya ücret bulunan bir çalışan olmadığında bir ileti gönderir.

Örnek, her iki arama algoritmasını paralel olarak çalıştırmak için bir [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnesi kullanır. Her arama görevi, verilen çalışanın varolup olmadığını belirtmek için `single_assignment` nesnelerinden birine yazar. Örnek, bir ileti içeren ilk arabelleğin dizinini ve sonucu yazdırmak için bir `switch` bloğunu almak üzere [concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) işlevini kullanır.

[!code-cpp[concrt-find-employee#1](../../parallel/concrt/codesnippet/cpp/how-to-select-among-completed-tasks_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Employee with id 14758 has salary 27780.00.
Employee with salary 29150.00 has id 84345.
Employee with id 61935 has salary 29905.00.
No employee has id 899 or salary 31223.00.
```

Bu örnek, `join` nesneleri oluşturmak için `choice` nesneleri ve [concurrency:: make_join](reference/concurrency-namespace-functions.md#make_join) yardımcı işlevini oluşturmak için [concurrency:: make_choice](reference/concurrency-namespace-functions.md#make_choice) Helper işlevini kullanır.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `find-employee.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Find-Employee. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[choice Sınıfı](../../parallel/concrt/reference/choice-class.md)<br/>
[join Sınıfı](../../parallel/concrt/reference/join-class.md)
