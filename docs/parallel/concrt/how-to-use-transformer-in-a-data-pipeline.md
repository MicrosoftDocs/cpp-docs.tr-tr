---
title: "Nasıl yapılır: veri ardışık düzeninde transformer kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- transformer class, example
- data pipelines, using transformer [Concurrency Runtime]
- using transformer in data pipelines [Concurrency Runtime]
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76c8a50bd5a58d9fe6e4a68f05d9732e50fd04e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-transformer-in-a-data-pipeline"></a>Nasıl yapılır: Veri Ardışık Düzeninde transformer Kullanma
Bu konu, nasıl kullanılacağını gösteren temel bir örnek içerir [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) veri ardışık düzeninde sınıfı. Veri ardışık görüntü işleme gerçekleştirmek için kullandığı daha eksiksiz bir örnek için bkz: [izlenecek yol: görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
 *Veri ardışık düzen* eşzamanlı programlarındaki ortak bir deseni. Veri ardışık burada her aşamanın çalışma gerçekleştirir ve sonra o iş sonucunu sonraki aşamaya iletir aşamaları bir dizi oluşur. `transformer` Kilit bir bileşeni veri ardışık düzenleri bir giriş değerinin aldığından sınıfı bu değeri çalışma gerçekleştirir ve bir sonuç almak için kullanılacak başka bir bileşen üretir.  
  
## <a name="example"></a>Örnek  
 Bu örnek, bir dizi dönüşümleri ilk giriş değerini verilen gerçekleştirmek için aşağıdaki veri ardışık kullanır:  
  
1.  İlk aşamada, kendi giriş mutlak değerini hesaplar.  
  
2.  İkinci aşama, kendi giriş'in kare kökünü hesaplar.  
  
3.  Üçüncü aşaması, kendi giriş kare hesaplar.  
  
4.  İleri kendi giriş aşama üzerindeki geçersiz kılar.  
  
5.  Beşinci aşama son sonucu bir ileti arabelleğe yazar.  
  
 Son olarak, örnek konsoluna ardışık sonucunu yazdırır.  
  
 [!code-cpp[concrt-data-pipeline#1](../../parallel/concrt/codesnippet/cpp/how-to-use-transformer-in-a-data-pipeline_1.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
```Output  
The result is -42.  
```  
  
 Giriş değeri, türü farklı bir değer çıkarmak için veri ardışık düzeninde bir aşama için yaygın bir sorundur. Bu örnekte, İkinci aşama türünde bir değer alır. `int` giriş olarak ve bu değer'in kare kökünü üretir (bir `double`) çıktısını olarak.  
  
> [!NOTE]
>  Bu örnekte veri ardışık için çizimidir. Her dönüştürme işlemi için çok az iş gerçekleştirdiğinden, ileti geçirme gerçekleştirmek için gerekli ek yükü veri ardışık kullanmanın yararları daha ağır basar.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `data-pipeline.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc verileri-pipeline.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)   
 [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)   
 [İzlenecek yol: Görüntü İşleme Ağı Oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)

