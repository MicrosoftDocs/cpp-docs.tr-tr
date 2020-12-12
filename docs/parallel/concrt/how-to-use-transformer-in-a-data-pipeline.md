---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: bir veri ardışık düzeninde transformatör kullanma'
title: 'Nasıl yapılır: Veri Ardışık Düzeninde transformer Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- transformer class, example
- data pipelines, using transformer [Concurrency Runtime]
- using transformer in data pipelines [Concurrency Runtime]
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
ms.openlocfilehash: 97b0af16a3ce89b940952117bb8639d281363a23
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205622"
---
# <a name="how-to-use-transformer-in-a-data-pipeline"></a>Nasıl yapılır: Veri Ardışık Düzeninde transformer Kullanma

Bu konu, bir veri işlem hattında [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) sınıfının nasıl kullanılacağını gösteren temel bir örnek içerir. Görüntü işleme gerçekleştirmek için veri işlem hattı kullanan daha kapsamlı bir örnek için bkz. [Izlenecek yol: Image-Processing ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

*Veri ardışık düzen* oluşturma, eşzamanlı programlamada ortak bir modeldir. Bir veri işlem hattı, her aşamanın iş yaptığı ve sonra o çalışmanın sonucunu sonraki aşamaya ileten bir dizi aşamadan oluşur. `transformer`Bir giriş değeri aldığından, bu değerde iş gerçekleştirdiğinden ve sonra başka bir bileşenin kullanması için bir sonuç üreten veri işlem hatlarında bir anahtar bileşen sınıfı.

## <a name="example"></a>Örnek

Bu örnek, bir ilk giriş değeri verilen bir dizi dönüştürme gerçekleştirmek için aşağıdaki veri ardışık düzenini kullanır:

1. İlk aşama, girişinin mutlak değerini hesaplar.

1. İkinci aşama, girişinin kare kökünü hesaplar.

1. Üçüncü aşama, girişinin karesini hesaplar.

1. İleri aşama, girişini geçersiz kılar.

1. Beşinci aşama nihai sonucu bir ileti arabelleğine yazar.

Son olarak, örnek işlem hattının sonucunu konsola yazdırır.

[!code-cpp[concrt-data-pipeline#1](../../parallel/concrt/codesnippet/cpp/how-to-use-transformer-in-a-data-pipeline_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
The result is -42.
```

Bir veri işlem hattının, türü giriş değerinden farklı olan bir değeri çıktısının çıkışı yaygındır. Bu örnekte, ikinci aşama, giriş olarak türünde bir değer alır **`int`** ve çıkış olarak bu değerin (a) kare kökünü üretir **`double`** .

> [!NOTE]
> Bu örnekteki veri ardışık düzeni, illüstrasyon amaçlıdır. Her dönüştürme işlemi çok az iş gerçekleştirdiğinden, ileti geçişini gerçekleştirmek için gerekli olan ek yük, bir veri işlem hattı kullanmanın avantajlarını engelleyebilir.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `data-pipeline.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Data-Pipeline. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İzlenecek yol: Image-Processing ağ oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)
