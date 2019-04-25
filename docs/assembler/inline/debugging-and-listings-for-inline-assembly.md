---
title: Satır İçi Derleme için Hata Ayıklama ve Listeleme
ms.date: 08/30/2018
helpviewer_keywords:
- source level debugger
- __asm keyword [C++], debugging
- inline assembly, listings
- bugs, __asm blocks
- debugging [C++], inline assembly code
- inline assembly, debugging
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
ms.openlocfilehash: 1b2ec146daf450c4302be9fea8fdd117ec6398da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167212"
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