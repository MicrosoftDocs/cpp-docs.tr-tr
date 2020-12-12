---
description: 'Aşağıdakiler hakkında daha fazla bilgi edinin: nasıl yapılır: tamamlanan görevler arasında seçim yapma'
title: 'Nasıl yapılır: Tamamlanan Görevler Arasında Seçim Yapma'
ms.date: 11/04/2016
helpviewer_keywords:
- selecting among completed tasks [Concurrency Runtime]
- completed tasks, selecting among [Concurrency Runtime]
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
ms.openlocfilehash: a23092e4572188898f5e544f25406febc63d0c06
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197342"
---
# <a name="how-to-select-among-completed-tasks"></a>Nasıl yapılır: Tamamlanan Görevler Arasında Seçim Yapma

Bu örnek, bir arama algoritmasını tamamlamaya yönelik ilk görevi seçmek için [concurrency:: Choice](../../parallel/concrt/reference/choice-class.md) ve [concurrency:: JOIN](../../parallel/concrt/reference/join-class.md) sınıflarının nasıl kullanılacağını gösterir.

## <a name="example"></a>Örnek

Aşağıdaki örnek paralel olarak iki arama algoritması gerçekleştirir ve tamamlanacak ilk algoritmayı seçer. Bu örnek, bir `employee` çalışan için sayısal tanımlayıcıyı ve bir maaş tutan türü tanımlar. `find_employee`İşlevi, belirtilen tanımlayıcıya veya belirtilen maaşa sahip olan ilk çalışanı bulur. `find_employee`İşlevi, çalışan tanımlayıcı veya ücret içeren bir çalışanın sahip olduğu durumu da işler. `wmain`İşlevi bir nesne dizisi oluşturur `employee` ve birkaç tanımlayıcı ve maaş değeri arar.

Örnek, `choice` aşağıdaki durumlar arasından seçim yapmak için bir nesnesi kullanır:

1. Belirtilen tanımlayıcıya sahip bir çalışan var.

1. Belirtilen maaşa sahip bir çalışan var.

1. Belirtilen tanımlayıcıya veya maaşa sahip çalışan yok.

İlk iki durum için örnek, tanımlayıcıyı tutmak için [concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) nesnesini ve `single_assignment` maaşı tutacak başka bir nesneyi kullanır. Örnek, üçüncü bir `join` durum için bir nesnesi kullanır. `join`Nesne, `single_assignment` biri, belirtilen tanımlayıcıya sahip olmayan bir çalışanın mevcut olmadığı, diğeri ise belirtilen maaşa sahip olmayan bir çalışana sahip olmadığı durumlarda iki ek nesneden oluşur. `join`Nesnesi, üyeleri bir ileti aldığında bir ileti gönderir. Bu örnekte, nesne, `join` belirtilen tanımlayıcı veya ücret bulunan bir çalışan olmadığında bir ileti gönderir.

Örnek, her iki arama algoritmasını paralel olarak çalıştırmak için bir [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnesi kullanır. Her arama görevi, `single_assignment` belirtilen çalışanın varolup olmadığını göstermek için nesnelerden birine yazar. Örnek, bir ileti ve sonucu yazdırmak için bir blok içeren ilk arabelleğin dizinini almak için [concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) işlevini kullanır **`switch`** .

[!code-cpp[concrt-find-employee#1](../../parallel/concrt/codesnippet/cpp/how-to-select-among-completed-tasks_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Employee with id 14758 has salary 27780.00.
Employee with salary 29150.00 has id 84345.
Employee with id 61935 has salary 29905.00.
No employee has id 899 or salary 31223.00.
```

Bu örnek, nesneleri oluşturmak için [concurrency:: make_choice](reference/concurrency-namespace-functions.md#make_choice) Helper işlevini `choice` ve nesneler oluşturmak için [concurrency:: make_join](reference/concurrency-namespace-functions.md#make_join) Helper işlevini kullanır `join` .

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `find-employee.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Find-Employee. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti geçirme Işlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[seçim sınıfı](../../parallel/concrt/reference/choice-class.md)<br/>
[JOIN sınıfı](../../parallel/concrt/reference/join-class.md)
