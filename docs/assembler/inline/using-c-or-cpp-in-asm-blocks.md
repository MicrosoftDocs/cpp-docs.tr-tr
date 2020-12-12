---
description: 'Hakkında daha fazla bilgi edinin: __asm bloklarında C veya C++ kullanma'
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
ms.openlocfilehash: 2fc1987339fcbabee07e2b626c3ae764c3d5e2e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121933"
---
# <a name="using-c-or-c-in-__asm-blocks"></a>__asm Bloklarında C veya C++ Kullanma

**Microsoft'a Özgü**

Satır içi derleme yönergeleri C veya C++ deyimleriyle karışabileceğinden, C veya C++ değişkenlerine ada göre başvurabilir ve bu dillerin diğer birçok öğesini kullanabilirsiniz.

Bir **`__asm`** blok aşağıdaki dil öğelerini kullanabilir:

- Simgeler, Etiketler ve değişken ve işlev adları dahil

- Sembolik sabitler ve Üyeler de dahil olmak üzere sabitler **`enum`**

- Makrolar ve Önişlemci yönergeleri

- Açıklamalar (hem __/ \* \* /__ hem de __//__ )

- Tür adları (bir masa türünün geçerli olacağı her yerde)

- **`typedef`** genellikle **PTR** ve **tür** gibi işleçlerle kullanılan adlar veya yapı ya da birleşim üyelerini belirtmek için

Bir **`__asm`** blok içinde, C gösterimi veya assembler taban gösterimi (örneğin, 0x100 ve 100h eşdeğerdir) ile tamsayı sabitleri belirtebilirsiniz. Bu, `#define` c 'de bir sabit değer tanımlamanızı (kullanarak) ve ardından programın hem c hem de C++ ve derleme bölümlerinde kullanmanıza olanak sağlar. Ayrıca, bu sabitleri 0 ' dan önce sekizlik olarak belirtebilirsiniz. Örneğin, 0777 sekizli sabiti belirtir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [__Asm bloklarında Işleçler kullanma](../../assembler/inline/using-operators-in-asm-blocks.md)

- [C veya C++ Symbols_in __asm blokları kullanma](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)

- [__Asm bloklarında C veya C++ verilerine erişme](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)

- [Satır Içi derlemeyle Işlevler yazma](../../assembler/inline/writing-functions-with-inline-assembly.md)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır içi assembler](../../assembler/inline/inline-assembler.md)<br/>
