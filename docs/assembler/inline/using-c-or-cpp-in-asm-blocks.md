---
title: __asm Bloklarında C veya C++ Kullanma
ms.date: 08/30/2018
helpviewer_keywords:
- inline assembly, mixing instructions with C/C++ statements
- symbols, in __asm blocks
- macros, __asm blocks
- preprocessor directives, used in __asm blocks
- type names, used in __asm blocks
- preprocessor directives
- preprocessor, directives
- constants, in __asm blocks
- comments, in __asm blocks
- typedef names, used in __asm blocks
- __asm keyword [C++], C/C++ elements in
ms.assetid: ae8b2b52-6b75-42e3-ac0c-ad02d922ed97
ms.openlocfilehash: 0949eba769bed33da8fe39bb41500a2ba02af224
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602156"
---
# <a name="using-c-or-c-in-asm-blocks"></a>__asm Bloklarında C veya C++ Kullanma

** Microsoft'a özgü **

Satır içi derleme yönergelerini C veya C++ deyimleri ile karma olabilir çünkü C veya C++ değişkenlere adıyla başvurun ve diğer birçok dillere öğesini kullanın.

Bir `__asm` blok aşağıdaki dil öğelerini kullanabilirsiniz:

- Etiketleri ve değişken ve işlev adları da dahil, sembollerin

- Sembolik sabit değerler dahil olmak üzere, sabitleri ve `enum` üyeleri

- Makrolar ve ön işlemci yönergeleri

- Açıklama (her ikisi de __/ \* \* /__ ve __//__ )

- (Her yerde yasal MASM türü olacaktır) adlarını yazın

- `typedef` işleçlerle gibi genel olarak kullanılan adları **PTR** ve **türü** veya yapı veya birleşim üyelerini belirtmek için

İçinde bir `__asm` blok, C gösterimi veya derleyici taban gösterimi ile tamsayı sabitlerini belirtmek (0x100 ve 100 h eşdeğer olan, örneğin). Bu tanımlamanızı sağlar (kullanarak `#define`) bir sabit c ve C veya C++ ve derleme program bölümlerinde kullanabilirsiniz. Sabitler (c++) belirtebilirsiniz bunları 0 ile önceki tarafından sekizlik. Örneğin, 0777 sekizlik sabiti belirtir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [__asm Bloklarında İşleçler Kullanma](../../assembler/inline/using-operators-in-asm-blocks.md)

- [__Asm bloklarında C veya C++ Symbols_in kullanma](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)

- [__asm Bloklarında C veya C++ Verilerine Erişme](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)

- [Satır İçi Bütünleştirilmiş Kodla İşlevler Yazma](../../assembler/inline/writing-functions-with-inline-assembly.md)

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>
