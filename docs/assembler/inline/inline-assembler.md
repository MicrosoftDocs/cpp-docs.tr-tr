---
description: Daha fazla bilgi için bkz. satır Içi assembler
title: Satır İçi Derleyicisi
ms.date: 08/30/2018
helpviewer_keywords:
- assembler [C++]
- assembler [C++], inline
- assembly language [C++], inline
- inline assembler [C++]
- inline assembly [C++]
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
ms.openlocfilehash: 67ae8c40dee71f693dd6641dd81e8f61b8536a1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117776"
---
# <a name="inline-assembler"></a>Satır İçi Derleyicisi

**Microsoft'a Özgü**

Derleme dili; program hızını geliştirmek, bellek ihtiyaçlarını azaltmak ve donanımı denetlemek gibi pek çok amaca hizmet eder. Derleme dili talimatlarını ek derleme ve bağlama adımı olmadan doğrudan C ve C++ kaynaklı programlarınıza katıştırmak için satır içi derleyiciyi kullanabilirsiniz. Satır içi assembler derleyici içinde yerleşik olarak bulunur, böylece, Microsoft Makro Çevirici (MASM) gibi ayrı bir derleyici gerekmez.

> [!NOTE]
> Satır içi derleme kodu içeren programlar diğer donanım platformlarına tamamen taşınamaz. Taşınabilirlik için tasarlıyorsanız, satır içi derleyici kullanmaktan kaçının.

Satır içi derleme ARM ve x64 işlemcilerde desteklenmez.  Aşağıdaki konular, Visual C/C++ satır içi birleştirici/ayırıcı ile x86 işlemcilerin nasıl kullanıldığını açıklar:

- [Satır içi assembler genel bakış](../../assembler/inline/inline-assembler-overview.md)

- [Satır Içi derlemenin avantajları](../../assembler/inline/advantages-of-inline-assembly.md)

- [__asm](../../assembler/inline/asm.md)

- [__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)

- [__Asm bloklarında C veya C++ kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)

- [Satır Içi derlemede kayıtları kullanma ve koruma](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)

- [Satır Içi derlemede etiketlere atlama](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)

- [Satır Içi derlemede C Işlevlerini çağırma](../../assembler/inline/calling-c-functions-in-inline-assembly.md)

- [Satır Içi derlemede C++ Işlevlerini çağırma](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)

- [__Asm bloklarını C makroları olarak tanımlama](../../assembler/inline/defining-asm-blocks-as-c-macros.md)

- [Satır Içi derlemeyi iyileştirme](../../assembler/inline/optimizing-inline-assembly.md)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Iç bilgileri ve derleme dili](../../intrinsics/compiler-intrinsics-and-assembly-language.md)<br/>
[C++ dil başvurusu](../../cpp/cpp-language-reference.md)<br/>
