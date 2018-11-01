---
title: __asm Bloklarında C veya C++ Simgelerini Kullanma
ms.date: 08/30/2018
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
ms.openlocfilehash: fc22af8ec04d616eb8f5566b118e19c405605401
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552522"
---
# <a name="using-c-or-c-symbols-in-asm-blocks"></a>__asm Bloklarında C veya C++ Simgelerini Kullanma

**Microsoft'a özgü**

Bir `__asm` blok herhangi bir C veya C++ sembol blok göründüğü kapsamda başvurabilir. (C ve C++ simgeler şunlardır: değişken adları, işlev adlarını ve etiketleri; sembolik sabit olmayan adları veya `enum` üyeleri. C++ üye işlevleri çağıramazsınız.)

C ve C++ sembolleri kullanımını bazı kısıtlamalar:

- Her bir çevirici dil ifadesi yalnızca bir C veya C++ sembol içerebilir. Birden çok simgeleri yalnızca aynı derleme yönergesinin görünebilen **UZUNLUĞU**, **türü**, ve **BOYUTU** ifadeler.

- Başvurulan işlevler bir `__asm` blok bildirilmesi gerekir (daha önce programda prototipli). Aksi halde, derleyici işlev adlarını ve Etiketler arasında ayrım yapamaz `__asm` blok.

- Bir `__asm` blok MASM ayrılmış sözcük (büyük) bağımsız olarak aynı yazım denetimi ile C veya C++ simgeleri kullanamaz. MASM ayrılmış sözcükler yönerge adları gibi dahil **anında İLETME** ve sı gibi adlarını kaydedin.

- Yapı ve birleşim etiketleri tanınmıyor `__asm` engeller.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında C veya C++ Kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>