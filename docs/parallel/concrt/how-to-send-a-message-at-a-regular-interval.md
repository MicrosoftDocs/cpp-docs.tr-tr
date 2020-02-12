---
title: 'Nasıl yapılır: Düzenli Aralıkla İleti Gönderme'
ms.date: 11/04/2016
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
ms.openlocfilehash: c51a5cab6fcae5eb45b9d9b54c0dad8e8ec393b2
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142456"
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>Nasıl yapılır: Düzenli Aralıkla İleti Gönderme

Bu örnek, düzenli aralıklarla bir ileti göndermek için concurrency::[Timer sınıfının](../../parallel/concrt/reference/timer-class.md) nasıl kullanılacağını gösterir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, uzun bir işlem sırasında ilerlemeyi raporlamak için bir `timer` nesnesi kullanır. Bu örnek `timer` nesnesini bir [concurrency:: Call](../../parallel/concrt/reference/call-class.md) nesnesine bağlar. `call` nesnesi, düzenli aralıklarla konsola ilerleme göstergesini yazdırır. [Concurrency:: Timer:: Start](reference/timer-class.md#start) yöntemi, zamanlayıcıyı ayrı bir bağlam üzerinde çalıştırır. `perform_lengthy_operation` işlevi, zaman alan bir işlemin benzetimini yapmak için ana bağlamdaki [concurrency:: wait](reference/concurrency-namespace-functions.md#wait) işlevini çağırır.

[!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]

Bu örnek aşağıdaki örnek çıktıyı üretir:

```Output
Performing a lengthy operation..........done.
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `report-progress.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Report-Progress. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)
