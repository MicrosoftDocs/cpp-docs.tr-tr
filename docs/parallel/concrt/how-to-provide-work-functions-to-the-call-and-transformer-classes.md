---
description: 'Daha fazla bilgi edinin: nasıl yapılır: çağrı ve transformatör sınıflarına çalışma Işlevleri sağlama'
title: 'Nasıl yapılır: call ve transformer Sınıflarına İş İşlevleri Sağlama'
ms.date: 11/04/2016
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
ms.openlocfilehash: 05def4dcc8357e73a8606fbc4ce741eebb647d37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197367"
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>Nasıl yapılır: call ve transformer Sınıflarına İş İşlevleri Sağlama

Bu konuda [concurrency:: Call](../../parallel/concrt/reference/call-class.md) ve [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) sınıflarına çalışma işlevleri sağlamanın birkaç yolu gösterilmektedir.

İlk örnek bir nesnesine lambda ifadesinin nasıl geçirileceğini gösterir `call` . İkinci örnek, bir işlev nesnesinin bir nesnesine nasıl geçirileceğini gösterir `call` . Üçüncü örnek bir nesne için bir sınıf yönteminin nasıl bağlanacağını gösterir `call` .

Çizimde, bu konudaki her örnek `call` sınıfını kullanır. Sınıfını kullanan bir örnek için `transformer` bkz. [nasıl yapılır: bir veri ardışık düzeninde transformatör kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).

## <a name="example-call-class"></a>Örnek: Call sınıfı

Aşağıdaki örnek, sınıfını kullanmanın yaygın bir yolunu gösterir `call` . Bu örnek, bir Lambda işlevini oluşturucuya geçirir `call` .

[!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
13 squared is 169.
```

## <a name="example-call-class-with-function-object"></a>Örnek: Function nesnesi ile Call sınıfı

Aşağıdaki örnek, bir `call` işlev nesnesiyle (functor) birlikte sınıfını kullanması dışında, önceki bir örneğe benzer.

[!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]

## <a name="example-functions-to-bind-call-object"></a>Örnek: çağrı nesnesini bağlama Işlevleri

Aşağıdaki örnek öncekine benzer, ancak bir nesneyi bir sınıf yöntemine bağlamak için [std:: bind1st](../../standard-library/functional-functions.md#bind1st) ve [std:: mem_fun](../../standard-library/functional-functions.md#mem_fun) işlevlerini kullanır `call` .

`call` `transformer` İşlev çağrısı işleci yerine belirli bir sınıf yöntemine bir veya nesnesini bağlamanız gerekiyorsa bu tekniği kullanın `operator()` .

[!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]

Ayrıca, `bind1st` Aşağıdaki örnekte gösterildiği gibi, işlevinin sonucunu bir [std:: Function](../../standard-library/function-class.md) nesnesine atayabilir veya **`auto`** anahtar sözcüğünü kullanabilirsiniz.

[!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `call.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Call. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Nasıl yapılır: bir veri ardışık düzeninde transformatör kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
[Call sınıfı](../../parallel/concrt/reference/call-class.md)<br/>
[Transformatör sınıfı](../../parallel/concrt/reference/transformer-class.md)
