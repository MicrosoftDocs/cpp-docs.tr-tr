---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: düzenli bir aralıkta Ileti gönderme'
title: 'Nasıl yapılır: Düzenli Aralıkla İleti Gönderme'
ms.date: 11/04/2016
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
ms.openlocfilehash: f65226d8101ddbadaee97a16f63512b9c8dcb41e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197292"
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>Nasıl yapılır: Düzenli Aralıkla İleti Gönderme

Bu örnek, düzenli aralıklarla bir ileti göndermek için concurrency::[Timer sınıfının](../../parallel/concrt/reference/timer-class.md) nasıl kullanılacağını gösterir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `timer` uzun bir işlem sırasında ilerlemeyi raporlamak için bir nesnesi kullanır. Bu örnek, `timer` nesnesini bir [concurrency:: Call](../../parallel/concrt/reference/call-class.md) nesnesine bağlar. `call`Nesnesi, düzenli aralıklarla konsola ilerleme göstergesini yazdırır. [Concurrency:: Timer:: Start](reference/timer-class.md#start) yöntemi, zamanlayıcıyı ayrı bir bağlam üzerinde çalıştırır. `perform_lengthy_operation`İşlevi, zaman alan bir işlemin benzetimini yapmak için ana bağlamda [concurrency:: wait](reference/concurrency-namespace-functions.md#wait) işlevini çağırır.

[!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]

Bu örnek aşağıdaki örnek çıktıyı üretir:

```Output
Performing a lengthy operation..........done.
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `report-progress.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Report-Progress. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti geçirme Işlevleri](../../parallel/concrt/message-passing-functions.md)
