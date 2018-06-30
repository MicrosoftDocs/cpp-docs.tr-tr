---
title: __Asm bloklarında C veya C++ kullanma | Microsoft Docs
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96ed46cdf44ccacee806dd03bf7eacca26eec32d
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120956"
---
# <a name="using-c-or-c-in-asm-blocks"></a>__asm Bloklarında C veya C++ Kullanma

** Microsoft özel **

Satır içi derleme yönergeleri, C veya C++ deyimleri ile bir arada kullanılabilir olduğundan, ada göre C veya C++ değişkenlere başvurun ve diğer dillere birçok öğesini kullanın.

Bir `__asm` blok aşağıdaki dil öğeleri kullanabilirsiniz:

- Etiketleri ve değişken ve işlev adları dahil olmak üzere sembolleri

- Sembolik sabitler dahil olmak üzere sabitleri ve `enum` üyeleri

- Makrolar ve önişlemci yönergeleri

- Yorumlar (her ikisi de __/ \* \* /__ ve __//__ )

- (Yerde yasal MASM türü olur) adlarını yazın

- `typedef` genellikle işleçlerle gibi kullanılan adları, **PTR** ve **türü** veya yapısı veya birleşim üyeleri belirtin

İçinde bir `__asm` bloğu C gösterimi veya assembler taban gösterimi ile tamsayı sabitleri belirtebilirsiniz (0x100 ve 100 h eşdeğer, örneğin). Bu tanımlamanıza olanak verir (kullanarak `#define`) C sabitinde ve C veya C++ ve derleme program bölümlerinde kullanın. Sabitler de belirtebilirsiniz 0 ile önceki tarafından sekizli. Örneğin, bir sekizli sabiti 0777 belirtir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [__asm Bloklarında İşleçler Kullanma](../../assembler/inline/using-operators-in-asm-blocks.md)

- [__Asm bloklarını C veya C++ Symbols_in kullanarak](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)

- [__asm Bloklarında C veya C++ Verilerine Erişme](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)

- [Satır İçi Bütünleştirilmiş Kodla İşlevler Yazma](../../assembler/inline/writing-functions-with-inline-assembly.md)

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)
