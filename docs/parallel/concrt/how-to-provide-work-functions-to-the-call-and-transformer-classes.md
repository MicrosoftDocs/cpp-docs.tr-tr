---
title: 'Nasıl yapılır: Call ve transformer sınıflarına iş işlevleri sağlama'
ms.date: 11/04/2016
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
ms.openlocfilehash: c41c29dae277105f268171503e662e2a02e3857e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57277698"
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>Nasıl yapılır: Call ve transformer sınıflarına iş işlevleri sağlama

Bu konuda iş işlevleri sağlama için çeşitli yollar gösterir [concurrency::call](../../parallel/concrt/reference/call-class.md) ve [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) sınıfları.

İlk örnek, bir lambda ifadesi geçirilecek gösterilmiştir bir `call` nesne. İkinci örnek, bir işlev nesnesi geçirilecek gösterilmiştir bir `call` nesne. Üçüncü örnek, bir sınıf yönteme bağlama işlemi gösterilmektedir bir `call` nesne.

Çizim için bu konudaki her örnekte `call` sınıfı. Kullanan bir örnek için `transformer` sınıfı [nasıl yapılır: Veri ardışık düzeninde transformer kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).

## <a name="example"></a>Örnek

Kullanmak için en yaygın yolu aşağıdaki örnekte `call` sınıfı. Bu örnekte bir lambda işleve geçirir `call` Oluşturucusu.

[!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
13 squared is 169.
```

## <a name="example"></a>Örnek

Aşağıdaki örnek Öncekine benzer kullandığı `call` birlikte bir işlev nesnesi (functor) sınıfı.

[!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek Öncekine benzer kullanır [std::bind1st](../../standard-library/functional-functions.md#bind1st) ve [std::mem_fun](../../standard-library/functional-functions.md#mem_fun) bağlamak için işlevleri bir `call` nesne için bir sınıf yöntemi.

Bağlamak varsa, bu tekniği bir `call` veya `transformer` nesne işlev çağrısı işleci, yerine belirli bir sınıf yönteme `operator()`.

[!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]

Sonucunu da atayabilirsiniz `bind1st` işlevi bir [std::function](../../standard-library/function-class.md) kullanın ya da nesne `auto` anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi.

[!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `call.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc call.cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Nasıl yapılır: Veri İşlem Hattında transformer Kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
[call Sınıfı](../../parallel/concrt/reference/call-class.md)<br/>
[transformer Sınıfı](../../parallel/concrt/reference/transformer-class.md)
