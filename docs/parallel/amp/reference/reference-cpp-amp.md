---
title: Başvuru (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::Reference (C++ AMP)
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, reference
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
ms.openlocfilehash: a334c7873675183dc06abfc2fe51472190996bf3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351176"
---
# <a name="reference-c-amp"></a>Başvuru (C++ AMP)

Bu bölüm, C++ Accelerated Massive Parallelism (C++ AMP) çalışma zamanı için başvuru bilgileri içerir.

> [!NOTE]
>  C++ dil standardı bir alt çizgiyle başlayan tanımlayıcılar kullanımını ayırır (`_`) karakteri, kütüphane gibi uygulamalar için. Kodunuzda altı çizili ile başlayan adları kullanmayın. Öğe adları bu kurala uymayan garantili değildir ve gelecekte değişikliğe tabi olduğu kodun çalışma biçiminin serbest bırakır. Bu nedenlerden dolayı bu tür kod öğeleri bu belgelerden çıkarılır.

## <a name="in-this-section"></a>Bu Bölümde

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)<br/>
Sınıflar ve veri paralel donanımlarda C++ kodu hızlandırılmasını olanak sağlayan işlevler sunar.

[Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)<br/>
D3D birlikte çalışabilirlik destekleyen işlevleri sağlar. AMP kodunda hesaplamak için D3D kaynaklarını sorunsuz kullanımını ve gereksiz Ara kopyalar oluşturmadan, AMP D3D kodunda oluşturulan kaynakların kullanımını etkinleştirir. DirectX uygulamalarınızın işlem yoğunluklu bölümlerini kademeli olarak hızlandırmak ve AMP hesaplamalarıyla üretilen verilerde D3D API'sini kullanmak için C++ AMP'ı kullanabilirsiniz.

[Concurrency::fast_math Ad Alanı](concurrency-fast-math-namespace.md)<br/>
İçindeki işlevler `fast_math` ad alanı, C99 uyumlu değildir. Her işlevin yalnızca tek duyarlıklı sürümleri sağlanır. Bu işlevler karşılık gelen işlevlerden daha hızlı DirectX iç işlevler kullanan `precise_math` ad alanı ve hızlandırıcıda genişletilmiş çift duyarlıklı destek gerektirmeyen, ancak daha az doğru olur. C99 kodu ile kaynak düzeyinde uyumluluk için her işlevin iki sürümü vardır; Her iki sürümü, alır ve tek duyarlıklı değerler döndürür.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)<br/>
Grafik programlama için türleri ve tasarlanmış işlevleri sağlar.

[Concurrency::precise_math Ad Alanı](concurrency-precise-math-namespace.md)<br/>
İçindeki işlevler `precise_math` ad alanı olan C99 uyumludur. Her işlevin hem tek duyarlık hem çift duyarlık sürümleri dahil edilir. Bu işlevler — Bu, tek duyarlıklı işlevler içerir — hızlandırıcıda genişletilmiş çift duyarlıklı desteği gerektirir.

## <a name="related-sections"></a>İlgili Bölümler

[C++ AMP (C++ Accelerated Massive Parallelism)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
C++ AMP ayrı ekran kartı üzerindeki grafik işlemci birimi (GPU) gibi veri-paralel donanımlardan yararlanarak C++ kod yürütülmesini hızlandırır.
