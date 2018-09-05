---
title: Satır içi Assembler | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assembler [C++]
- assembler [C++], inline
- assembly language [C++], inline
- inline assembler [C++]
- inline assembly [C++]
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 277ba0aab4f2e756fcf9b5eb1f3a9765b8da3a7b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683456"
---
# <a name="inline-assembler"></a>Satır İçi Derleyicisi

**Microsoft'a özgü**

Derleme dili; program hızını geliştirmek, bellek ihtiyaçlarını azaltmak ve donanımı denetlemek gibi pek çok amaca hizmet eder. Derleme dili talimatlarını ek derleme ve bağlama adımı olmadan doğrudan C ve C++ kaynaklı programlarınıza katıştırmak için satır içi derleyiciyi kullanabilirsiniz. Satır içi assembler derleyici içinde yerleşik olarak bulunur, böylece, Microsoft Makro Çevirici (MASM) gibi ayrı bir derleyici gerekmez.

> [!NOTE]
>  Satır içi derleme kodu içeren programlar diğer donanım platformlarına tamamen taşınamaz. Taşınabilirlik için tasarlıyorsanız, satır içi derleyici kullanmaktan kaçının.

Satır içi derleme ARM ve x64 desteklenmiyor işlemci.  Aşağıdaki konular, Visual C/C++ satır içi birleştirici/ayırıcı ile x86 işlemcilerin nasıl kullanıldığını açıklar:

- [Satır İçi Assembler’a Genel Bakış](../../assembler/inline/inline-assembler-overview.md)

- [Satır İçi Bütünleştirilmiş Kod Avantajları](../../assembler/inline/advantages-of-inline-assembly.md)

- [__asm](../../assembler/inline/asm.md)

- [__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)

- [__asm Bloklarında C veya C++ Kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)

- [Bir Satır İçi Bütünleştirilmiş Kodda Kayıtları Kullanma ve Koruma](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)

- [İç Bütünleştirilmiş Kodda Etiketlere Atlama](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)

- [Satır İçi Bütünleştirilmiş Kodda C İşlevlerini Çağırma](../../assembler/inline/calling-c-functions-in-inline-assembly.md)

- [Satır İçi Bütünleştirilmiş Kodda C İşlevlerini Çağırma](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)

- [__asm Bloklarını C Makroları olarak tanımlama](../../assembler/inline/defining-asm-blocks-as-c-macros.md)

- [Satır İçi Bütünleştirilmiş Kodu En İyi Duruma Getirme](../../assembler/inline/optimizing-inline-assembly.md)

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri ve Derleme Dili](../../intrinsics/compiler-intrinsics-and-assembly-language.md)<br/>
[C++ Dil Başvurusu](../../cpp/cpp-language-reference.md)<br/>