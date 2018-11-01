---
title: malloc Hizalaması
ms.date: 11/04/2016
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
ms.openlocfilehash: 436033d4e99d42d0a1a9366377f928bc402ac974
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533555"
---
# <a name="malloc-alignment"></a>malloc Hizalaması

[malloc](../c-runtime-library/reference/malloc.md) temel hizalama ve, olan herhangi bir nesneyi depolamak için ayrılan bellek miktarına uygun olabilecek için uygun şekilde hizalanmış belleğe dönmesi garanti edilir. A *temel hizalama* hizalama belirtimleri olmaksızın uygulamayla desteklenen en geniş hizalamadan küçük veya ona eşit olan hizalamadır. (Visual C++'da, bunun için gerekli olan hizalamadır bir `double`, veya 8 bayt. 64-bit platformları hedefleyen kodda, 16 bayttır.) Örneğin, dört baytlık bir atama dört bayt veya daha küçük bir nesne destekleyen bir sınır üzerinde hizalanabilir.

Visual C++ verir sahip türleri *genişletilmiş hizaya*, olarak da bilinen olduğu *aşırı hizalanmış* türleri. Örneğin SSE türleri [__m128](../cpp/m128.md) ve `__m256`ve kullanılarak bildirilen türler `__declspec(align( n ))` burada `n` 8'den büyükse, genişletilmiş hizaya sahiptir. Genişletilmiş hizalama gerektiren bir nesne için uygun olan bir sınır üzerinde bellek hizalama tarafından garanti edilmez `malloc`. Aşırı hizalanmış türlere bellek ayırmak için kullanmak [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) ve ilgili işlevleri.

## <a name="see-also"></a>Ayrıca Bkz.

[Yığın Kullanımı](../build/stack-usage.md)<br/>
[align](../cpp/align-cpp.md)<br/>
[__declspec](../cpp/declspec.md)