---
title: 'Nasıl yapılır: call ve transformer Sınıflarına İş İşlevleri Sağlama'
ms.date: 11/04/2016
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
ms.openlocfilehash: 4d2b7b3c88b51003a96526ef14d9940a8c26c3b3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142484"
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>Nasıl yapılır: call ve transformer Sınıflarına İş İşlevleri Sağlama

Bu konuda [concurrency:: Call](../../parallel/concrt/reference/call-class.md) ve [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) sınıflarına çalışma işlevleri sağlamanın birkaç yolu gösterilmektedir.

İlk örnek, bir `call` nesnesine lambda ifadesinin nasıl geçirileceğini gösterir. İkinci örnek, bir işlev nesnesinin bir `call` nesnesine nasıl geçirileceğini gösterir. Üçüncü örnek, bir sınıf yönteminin bir `call` nesnesine nasıl bağlanacağını gösterir.

Çizimde, bu konudaki her örnek `call` sınıfını kullanır. `transformer` sınıfını kullanan bir örnek için bkz. [nasıl yapılır: bir veri ardışık düzeninde transformatör kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, `call` sınıfını kullanmanın yaygın bir yolunu gösterir. Bu örnek, `call` oluşturucusuna bir Lambda işlevi geçirir.

[!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
13 squared is 169.
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir işlev nesnesiyle (functor) birlikte `call` sınıfını kullanması dışında, öncekine benzer.

[!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek önceki bir örneğe benzer, ancak bir `call` nesnesini bir sınıf yöntemine bağlamak için [std:: bind1st](../../standard-library/functional-functions.md#bind1st) ve [std:: mem_fun](../../standard-library/functional-functions.md#mem_fun) işlevlerini kullanır.

Bir `call` veya `transformer` nesnesini, işlev çağrısı işleci `operator()`yerine belirli bir sınıf yöntemine bağlamanız gerekiyorsa bu tekniği kullanın.

[!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]

Ayrıca, aşağıdaki örnekte gösterildiği gibi `bind1st` işlevinin sonucunu bir [std:: Function](../../standard-library/function-class.md) nesnesine atayabilir veya `auto` anahtar sözcüğünü kullanabilirsiniz.

[!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `call.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Call. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Nasıl yapılır: Veri İşlem Hattında transformer Kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
[call Sınıfı](../../parallel/concrt/reference/call-class.md)<br/>
[transformer Sınıfı](../../parallel/concrt/reference/transformer-class.md)
