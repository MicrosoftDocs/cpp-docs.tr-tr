---
title: Hata ayıklama ve listeleme satır içi derleme için | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- source level debugger
- __asm keyword [C++], debugging
- inline assembly, listings
- bugs, __asm blocks
- debugging [C++], inline assembly code
- inline assembly, debugging
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6cca954ae15252b97d883ba8491fdb98e506f68
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689295"
---
# <a name="debugging-and-listings-for-inline-assembly"></a>Satır İçi Derleme için Hata Ayıklama ve Listeleme

**Microsoft'a özgü**

Satır içi derleme kodu içeren programlar ile derleme yaparsanız bir kaynak düzey hata ayıklayıcı ile ayıklanabilir [/zi](../../build/reference/z7-zi-zi-debug-information-format.md) seçeneği.

Hata ayıklayıcısı içinde C veya C++ ve derleme dili satırlarda kesme noktaları ayarlayabilirsiniz. Karışık derleme ve kaynak modu etkinleştirirseniz, hem kaynak hem de ayrıştırılmış form derleme kodu görüntüleyebilirsiniz.

Birden çok derleme yönergeleri veya kaynak dili ifadelerini bir satıra koyarak hata ayıklama engel olabilir olduğunu unutmayın. Kaynak modunda hata ayıklayıcı, tek bir satırda ancak ayrı deyimler aynı satıra bir kesme noktası ayarlamak için kullanabilirsiniz. İçin de aynı ilke geçerlidir bir `__asm` bloğu tek bir mantıksal satırına genişletir C makro olarak tanımlanır.

Karışık kaynak ve derleme ile listeleme oluşturursanız [/Fas](../../build/reference/fa-fa-listing-file.md) derleyici seçeneği, listenin her derleme dili satırın hem kaynak hem de derleme formları içerir. Makrolar listelerinde genişletilir değil, ancak derleme sırasında genişletilmiş.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>