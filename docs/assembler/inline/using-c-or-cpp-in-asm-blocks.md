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
ms.openlocfilehash: 16b298b92a4ba40d9091499a1821ad4f3c413d6c
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74854530"
---
# <a name="using-c-or-c-in-__asm-blocks"></a>__asm Bloklarında C veya C++ Kullanma

**Microsoft 'a özgü**

Satır içi derleme yönergeleri C veya C++ deyimleri ile karışabileceğinden, bu diller, c veya C++ değişkenlere ada göre başvurabilir ve bu dillerin diğer birçok öğesini kullanabilir.

`__asm` bloğu aşağıdaki dil öğelerini kullanabilir:

- Simgeler, Etiketler ve değişken ve işlev adları dahil

- Sembolik sabitler ve `enum` üyeleri dahil sabitler

- Makrolar ve Önişlemci yönergeleri

- Açıklamalar ( __/\* \*/__ ve __//__ )

- Tür adları (bir masa türünün geçerli olacağı her yerde)

- genellikle **PTR** ve **tür** gibi işleçlerle kullanılan ve yapı ya da birleşim üyelerini belirtmek için `typedef` adları.

`__asm` bloğu içinde, C gösterimi veya assembler taban gösterimi (örneğin, 0x100 ve 100h) ile tamsayı sabitleri belirtebilirsiniz. Bu, C 'de bir sabit değer tanımlamanızı (`#define`kullanarak) ve ardından bunu programın hem C C++ 'de hem de derleme bölümlerinde kullanmanıza olanak sağlar. Ayrıca, bu sabitleri 0 ' dan önce sekizlik olarak belirtebilirsiniz. Örneğin, 0777 sekizli sabiti belirtir.

## <a name="what-do-you-want-to-know-more-about"></a>Hangi konu hakkında daha fazla bilgi edinmek istiyorsunuz?

- [__asm Bloklarında İşleçler Kullanma](../../assembler/inline/using-operators-in-asm-blocks.md)

- [C veya C++ Symbols_in __asm bloklarını kullanma](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)

- [__asm Bloklarında C veya C++ Verilerine Erişme](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)

- [Satır İçi Bütünleştirilmiş Kodla İşlevler Yazma](../../assembler/inline/writing-functions-with-inline-assembly.md)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>
