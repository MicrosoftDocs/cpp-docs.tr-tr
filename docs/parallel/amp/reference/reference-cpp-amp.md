---
title: "Başvuru (C++ AMP) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: amp/Concurrency::Reference (C++ AMP)
dev_langs: C++
helpviewer_keywords: C++ Accelerated Massive Parallelism, reference
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 84b68f4fa5ba207a9cb615877936ca08bdc2259b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="reference-c-amp"></a>Başvuru (C++ AMP)
Bu bölüm, C++ hızlandırılmış yoğun paralellik (C++ AMP) çalışma zamanı için başvuru bilgileri içerir.  
  
> [!NOTE]
>  Standart C++ dili bir alt çizgi ile başlayan tanımlayıcıları kullanımını ayırır (`_`) karakteri kitaplıklar gibi uygulamaları için. Kodunuzda bir alt çizgi ile başlayan adları kullanmayın. Bu kural, adları izleyen öğeleri garanti edilmez ve değiştirilebilir gelecek olan kod davranışını serbest bırakır. Bu nedenlerle, bu kod öğeler bu belgelerden göz ardı edilir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Eşzamanlılık Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)  
 Sınıfları ve verileri paralel donanımda C++ kodu ivmesini etkinleştirmek işlevleri sağlar.  
  
 [CONCURRENCY::Direct3D Namespace](concurrency-direct3d-namespace.md)  
 D3D birlikte çalışabilirlik desteği işlevleri sağlar. İşlem AMP kodda D3D kaynaklarının sorunsuz kullanımını ve Ara yedek kopya oluşturmak zorunda kalmadan D3D kodda AMP içinde oluşturulan kaynaklarının kullanımını etkinleştirir. Artımlı olarak DirectX uygulamalarınızı işlem yoğunluklu bölümlerini hızlandırmak ve AMP hesaplamalar üretilen veriler üzerinde D3D API kullanmak için C++ AMP kullanabilirsiniz.  
  
 [CONCURRENCY::fast_math Namespace](concurrency-fast-math-namespace.md)  
 İşlevlerini `fast_math` ad alanı C99 uyumlu değildir. Yalnızca tek duyarlıklı sürümleri her işlev sağlanır. Bu işlevler karşılık gelen işlevlerde daha hızlıdır DirectX iç işlevleri kullanmak `precise_math` ad alanı ve Hızlandırıcı genişletilmiş çift duyarlıklı desteği gerektirmez, ancak daha az kesin. Her işlev C99 koduyla kaynak düzeyi uyumluluk için iki sürümü vardır; Her iki sürümünü alın ve tek duyarlıklı değerleri döndürür.  
  
 [CONCURRENCY::Graphics Namespace](concurrency-graphics-namespace.md)  
 Türler ve tasarlanmış işlevler için grafik programlamaya sağlar.  
  
 [CONCURRENCY::precise_math Namespace](concurrency-precise-math-namespace.md)  
 İşlevlerini `precise_math` ad alanı olan C99 uyumlu. Her işlevi tek duyarlıklı ve çift duyarlıklı sürümleri dahil edilir. Bu işlevler — bu tek duyarlıklı işlevler içerir — Hızlandırıcı genişletilmiş çift duyarlıklı desteğini gerektirir.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [C++ AMP (C++ hızlandırılmış yoğun paralellik)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 C++ AMP ayrı grafik kart üzerinde bir grafik işlemci birimi (GPU) yaygın olarak mevcut verileri paralel donanım yararlanarak, C++ kod yürütmeyi hızlandırır.





