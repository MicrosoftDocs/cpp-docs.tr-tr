---
title: C++ AMP (C++ Accelerated Massive Parallelism)
ms.date: 11/04/2016
helpviewer_keywords:
- C++ AMP (see C++ Accelerated Massive Parallelism)
- C++ Accelerated Massive Parallelism, getting started
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
ms.openlocfilehash: f8ac71023f66868a66fb8c54a5e86678225378a1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400701"
---
# <a name="c-amp-c-accelerated-massive-parallelism"></a>C++ AMP (C++ Accelerated Massive Parallelism)

C++ AMP (C++ Accelerated Massive Parallelism) ayrı ekran kartı üzerindeki grafik işlemci birimi (GPU) gibi veri-paralel donanımlardan yararlanarak C++ kod yürütülmesini hızlandırır. C++ AMP programlama modeli çok boyutlu diziler, dizin oluşturma, bellek aktarımı ve döşeme için destek içerir. Ayrıca, bir matematiksel işlev kitaplığını içerir. C++ AMP dil uzantılarını verilerin CPU'dan GPU'ya nasıl taşınır denetlemek için kullanın ve yedekleyin.

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[C++ AMP'ye Genel Bakış](../../parallel/amp/cpp-amp-overview.md)|C++ AMP ve matematik kitaplığının anahtar özelliklerini açıklar.|
|[Lambda'lar, İşlev Nesneleri ve Kısıtlanmış İşlevler Kullanma](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|Çağrıları lambda ifadeleri, işlev nesneleri ve kısıtlanmış işlevler kullanma açıklanmaktadır [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) yöntemi.|
|[Döşemeleri Kullanma](../../parallel/amp/using-tiles.md)|Kutucukları C++ AMP kodunuzu hızlandırmak için nasıl kullanılacağını açıklar.|
|[Hızlandırıcı ve accelerator_view Nesnelerini Kullanma](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|Kodunuzun GPU üzerinde yürütülmesini özelleştirmek için Hızlandırıcıları kullanmayı açıklar.|
|[UWP Uygulamalarında C++ AMP Kullanma](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|Windows çalışma zamanı türlerini kullanan Evrensel Windows Platformu (UWP) uygulamaları C++ AMP kullanmayı açıklar.|
|[Grafikler (C++ AMP)](../../parallel/amp/graphics-cpp-amp.md)|C++ AMP grafik kitaplığının nasıl kullanılacağını açıklar.|
|[İzlenecek yol: Matris Çarpımı](../../parallel/amp/walkthrough-matrix-multiplication.md)|C++ AMP kodu kullanarak ve döşemek matris çarpım göstermektedir.|
|[İzlenecek yol: C++ AMP Uygulamasında Hata Ayıklama](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|Oluşturun ve büyük bir tamsayı dizisi toplamak için paralel azaltma kullanan bir uygulamanın hatalarını ayıklama işlemleri açıklanmaktadır.|

## <a name="reference"></a>Başvuru

[Başvuru (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)<br/>
[tile_static Anahtar Sözcüğü](../../cpp/tile-static-keyword.md)<br/>
[restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)

## <a name="other-resources"></a>Diğer Kaynaklar

[Yerel kod Blog içinde paralel programlama](http://go.microsoft.com/fwlink/p/?linkid=238472)<br/>
[Yükleme için C++ AMP örnek projeleri](http://go.microsoft.com/fwlink/p/?linkid=248508)<br/>
[Eşzamanlılık görselleştiricisi ile C++ AMP kodunu analiz etme](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/03/09/analyzing-c-amp-code-with-the-concurrency-visualizer/)