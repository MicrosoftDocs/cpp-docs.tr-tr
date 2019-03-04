---
title: 'Nasıl yapılır: Veri ardışık düzeninde transformer kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- transformer class, example
- data pipelines, using transformer [Concurrency Runtime]
- using transformer in data pipelines [Concurrency Runtime]
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
ms.openlocfilehash: 59c4854eea985b3c91fad6e7dc6c47ca9b07d333
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291477"
---
# <a name="how-to-use-transformer-in-a-data-pipeline"></a>Nasıl yapılır: Veri ardışık düzeninde transformer kullanma

Bu konu nasıl kullanılacağını gösteren temel bir örnek içeren [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) veri ardışık düzeninde sınıfı. Görüntü işleme gerçekleştirmek için veri işlem hattı kullanan daha eksiksiz bir örnek için bkz. [izlenecek yol: Görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

*Veri ardışık* yaygın eş zamanlı programlama modelidir. Veri işlem hattı bir dizi burada her bir aşama işini gerçekleştirir ve ardından o iş sonucu sonraki aşamaya geçirir aşamadan oluşur. `transformer` Önemli bileşenlerinden veri işlem hatları bir giriş değeri aldığından sınıfı bu değeri temel çalışma gerçekleştirir ve ardından başka bir bileşeni kullanmak için bir sonuç üretir.

## <a name="example"></a>Örnek

Bu örnek, bir dizi ilk giriş değerini verilen dönüştürmeler gerçekleştirmek için aşağıdaki veri işlem hattı kullanır:

1. İlk aşamada, girdi mutlak değerini hesaplar.

1. İkinci aşamada, girdi karekökünü hesaplar.

1. Üçüncü aşaması, girdi karesini hesaplar.

1. İleri aşama, girdi geçersiz hale getirir.

1. Beşinci aşama nihai sonucu bir iletiyi arabelleğe yazar.

Son olarak, örnek konsola işlem hattının sonucu yazdırır.

[!code-cpp[concrt-data-pipeline#1](../../parallel/concrt/codesnippet/cpp/how-to-use-transformer-in-a-data-pipeline_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
The result is -42.
```

Çıkış türü giriş değerinden farklı bir değer için veri ardışık düzeninde bir aşama için yaygındır. Bu örnekte, ikinci aşaması türünde bir değer alır. `int` , girdi olarak bu değeri kare kökünü oluşturur (bir `double`) çıktısını olarak.

> [!NOTE]
>  Bu örnekteki veri işlem hattı için bir örnektir. Her dönüştürme işlemi çok az iş gerçekleştirdiğinden, ileti geçirme gerçekleştirmek için gerekli ek yükü veri işlem hattı kullanmanın avantajları daha fazla olabilir.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `data-pipeline.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc veri pipeline.cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İzlenecek yol: Görüntü İşleme Ağı Oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)
