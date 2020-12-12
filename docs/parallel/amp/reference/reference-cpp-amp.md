---
description: 'Daha fazla bilgi edinin: başvuru (C++ AMP)'
title: Başvuru (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::Reference (C++ AMP)
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, reference
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
ms.openlocfilehash: 043522d7524078c3c7fec956021fdd7a86347169
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327629"
---
# <a name="reference-c-amp"></a>Başvuru (C++ AMP)

Bu bölüm C++ Accelerated Massive Parallelism (C++ AMP) çalışma zamanına ilişkin başvuru bilgilerini içerir.

> [!NOTE]
> C++ dil standardı, kitaplıklar gibi uygulamalar için bir alt çizgi () karakteriyle başlayan tanımlayıcıların kullanımını saklı tutar `_` . Kodunuzda bir alt çizgi ile başlayan adları kullanmayın. Adları bu kuralı izleyen kod öğelerinin davranışı garanti edilmez ve gelecek sürümlerde değiştirilebilir. Bu nedenlerden dolayı bu tür kod öğeleri bu belgelerden çıkarılır.

## <a name="in-this-section"></a>Bu Bölümde

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)<br/>
Veri paralel donanımlarda C++ kodu hızlandırmayı etkinleştiren sınıfları ve işlevleri sağlar.

[Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)<br/>
D3D birlikte çalışabilirliği destekleyen işlevler sağlar. , Ek ara kopyalar oluşturmadan,, AMP kodunda işlem için D3D kaynaklarının ve D3D kodunda AMP 'da oluşturulan kaynakların kullanımı için sorunsuz bir şekilde kullanılmasını mümkün. DirectX uygulamalarınızın yoğun işlem yoğunluklu bölümlerini artımlı olarak hızlandırmak ve AMP hesaplamalarından üretilen verilerde D3D API 'sini kullanmak için C++ AMP kullanabilirsiniz.

[Concurrency::fast_math Ad Alanı](concurrency-fast-math-namespace.md)<br/>
`fast_math`Ad alanındaki Işlevler C99 uyumlu değildir. Her bir işlevin yalnızca tek duyarlıklı sürümleri sağlanır. Bu işlevler, ad alanındaki karşılık gelen işlevlerden daha hızlı olan DirectX iç işlevlerini kullanır `precise_math` ve hızlandırıcıda genişletilmiş çift duyarlıklı destek gerektirmez, ancak daha az doğru olur. C99 Code ile kaynak düzeyinde uyumluluk için her bir işlevin iki sürümü vardır. Her iki sürüm de tek duyarlıklı değerler alır ve döndürür.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)<br/>
Grafik programlama için tasarlanmış türleri ve işlevleri sağlar.

[Eşzamanlılık::p recise_math ad alanı](concurrency-precise-math-namespace.md)<br/>
`precise_math`Ad alanındaki Işlevler C99 uyumludur. Her bir işlevin hem tek duyarlıklı hem de çift duyarlıklı sürümleri dahil edilmiştir. Bu işlevler, tek duyarlıklı işlevleri içerir — hızlandırıcı üzerinde genişletilmiş çift duyarlıklı destek gerektirir.

## <a name="related-sections"></a>İlgili Bölümler

[C++ AMP (C++ Accelerated Massive Parallelism)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
, Ayrı bir grafik kartında grafik işleme birimi (GPU) olarak da bulunan veri paralel donanımlarından yararlanarak C++ kodunuzun yürütülmesini hızlandırır C++ AMP.
