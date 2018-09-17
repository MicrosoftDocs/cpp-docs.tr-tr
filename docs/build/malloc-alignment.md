---
title: malloc hizalaması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa6e2748691eeb8a11834bcf8e6962252be7ab3f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712068"
---
# <a name="malloc-alignment"></a>malloc Hizalaması

[malloc](../c-runtime-library/reference/malloc.md) temel hizalama ve, olan herhangi bir nesneyi depolamak için ayrılan bellek miktarına uygun olabilecek için uygun şekilde hizalanmış belleğe dönmesi garanti edilir. A *temel hizalama* hizalama belirtimleri olmaksızın uygulamayla desteklenen en geniş hizalamadan küçük veya ona eşit olan hizalamadır. (Visual C++'da, bunun için gerekli olan hizalamadır bir `double`, veya 8 bayt. 64-bit platformları hedefleyen kodda, 16 bayttır.) Örneğin, dört baytlık bir atama dört bayt veya daha küçük bir nesne destekleyen bir sınır üzerinde hizalanabilir.

Visual C++ verir sahip türleri *genişletilmiş hizaya*, olarak da bilinen olduğu *aşırı hizalanmış* türleri. Örneğin SSE türleri [__m128](../cpp/m128.md) ve `__m256`ve kullanılarak bildirilen türler `__declspec(align( n ))` burada `n` 8'den büyükse, genişletilmiş hizaya sahiptir. Genişletilmiş hizalama gerektiren bir nesne için uygun olan bir sınır üzerinde bellek hizalama tarafından garanti edilmez `malloc`. Aşırı hizalanmış türlere bellek ayırmak için kullanmak [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) ve ilgili işlevleri.

## <a name="see-also"></a>Ayrıca Bkz.

[Yığın Kullanımı](../build/stack-usage.md)<br/>
[align](../cpp/align-cpp.md)<br/>
[__declspec](../cpp/declspec.md)