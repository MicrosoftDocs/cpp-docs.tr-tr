---
title: Başvuru (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::Reference (C++ AMP)
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, reference
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
ms.openlocfilehash: ff7c2b0894a2fa3de7674a72bc93dd3f781398b9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126415"
---
# <a name="reference-c-amp"></a>Başvuru (C++ AMP)

Bu bölüm, C++ hızlandırılmış büyük paralellik (C++ amp) çalışma zamanına ilişkin başvuru bilgilerini içerir.

> [!NOTE]
> Dil C++ standardı, kitaplıklar gibi uygulamalar için bir alt çizgi (`_`) karakteriyle başlayan tanımlayıcıların kullanımını saklı tutar. Kodunuzda bir alt çizgi ile başlayan adları kullanmayın. Adları bu kuralı izleyen kod öğelerinin davranışı garanti edilmez ve gelecek sürümlerde değiştirilebilir. Bu nedenlerden dolayı bu tür kod öğeleri bu belgelerden çıkarılır.

## <a name="in-this-section"></a>Bu Bölümde

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)<br/>
Veri paralel donanımındaki C++ kod hızlandırmasını etkinleştiren sınıflar ve işlevler sağlar.

[Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)<br/>
D3D birlikte çalışabilirliği destekleyen işlevler sağlar. , Ek ara kopyalar oluşturmadan,, AMP kodunda işlem için D3D kaynaklarının ve D3D kodunda AMP 'da oluşturulan kaynakların kullanımı için sorunsuz bir şekilde kullanılmasını mümkün. Amp kullanarak C++ , DirectX uygulamalarınızın yoğun işlem yoğunluğu olan bölümlerini kademeli olarak HıZLANDıRıR ve amp hesaplamalarından ÜRETILEN VERILERDE D3D API 'sini kullanabilirsiniz.

[Concurrency::fast_math Ad Alanı](concurrency-fast-math-namespace.md)<br/>
`fast_math` ad alanındaki işlevler C99 uyumlu değildir. Her bir işlevin yalnızca tek duyarlıklı sürümleri sağlanır. Bu işlevler, `precise_math` ad alanındaki karşılık gelen işlevlerden daha hızlı olan DirectX iç işlevlerini kullanır ve hızlandırıcıda genişletilmiş çift duyarlıklı destek gerektirmez, ancak daha az doğru olur. C99 Code ile kaynak düzeyinde uyumluluk için her bir işlevin iki sürümü vardır. Her iki sürüm de tek duyarlıklı değerler alır ve döndürür.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)<br/>
Grafik programlama için tasarlanmış türleri ve işlevleri sağlar.

[Concurrency::precise_math Ad Alanı](concurrency-precise-math-namespace.md)<br/>
`precise_math` ad alanındaki işlevler C99 uyumludur. Her bir işlevin hem tek duyarlıklı hem de çift duyarlıklı sürümleri dahil edilmiştir. Bu işlevler, tek duyarlıklı işlevleri içerir — hızlandırıcı üzerinde genişletilmiş çift duyarlıklı destek gerektirir.

## <a name="related-sections"></a>İlgili Bölümler

[C++ AMP (C++ Accelerated Massive Parallelism)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
C++AMP, ayrı bir grafik kartında C++ grafik işleme BIRIMI (GPU) olarak kullanılan veri paralel donanımlarından yararlanarak kodunuzun yürütülmesini hızlandırır.
