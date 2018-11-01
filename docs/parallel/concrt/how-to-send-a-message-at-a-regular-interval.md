---
title: 'Nasıl yapılır: Düzenli Aralıkla İleti Gönderme'
ms.date: 11/04/2016
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
ms.openlocfilehash: 05777b0c00f587f588a50733d5113d9a7362d247
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549623"
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>Nasıl yapılır: Düzenli Aralıkla İleti Gönderme

Bu örnek, eşzamanlılık kullanmayı gösterir.::[timer sınıfı](../../parallel/concrt/reference/timer-class.md) düzenli aralıkla ileti göndermek için.

## <a name="example"></a>Örnek

Aşağıdaki örnekte bir `timer` uzun bir işlem sırasında ilerleme durumunu raporlamak nesne. Bu örnek bağlantıları `timer` nesnesini bir [concurrency::call](../../parallel/concrt/reference/call-class.md) nesne. `call` Nesne düzenli aralıklarla bir İlerleme göstergesi konsola yazdırır. [Concurrency::timer::start](reference/timer-class.md#start) yöntemi Zamanlayıcı ayrı bir bağlamda çalışır. `perform_lengthy_operation` İşlev çağrılarında [concurrency::wait](reference/concurrency-namespace-functions.md#wait) uzun süren bir işlem benzetimini yapmak için ana içerik işlevi.

[!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]

Bu örnek, örnek aşağıdaki çıktıyı üretir:

```Output
Performing a lengthy operation..........done.
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `report-progress.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc rapor progress.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)
