---
description: 'Daha fazla bilgi edinin: satır Içi derleme için hata ayıklama ve dökümler'
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
ms.openlocfilehash: b4608a0176de5e061d7dc7f15b8758d9bd3a94b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117876"
---
# <a name="debugging-and-listings-for-inline-assembly"></a>Satır İçi Derleme için Hata Ayıklama ve Listeleme

**Microsoft'a Özgü**

Satır içi derleme kodu içeren programlar, [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) seçeneğiyle derlerseniz kaynak düzeyinde bir hata ayıklayıcı ile hata ayıklanabilir.

Hata ayıklayıcı içinde, hem C hem de C++ ve derleme dili satırlarında kesme noktaları ayarlayabilirsiniz. Karışık derleme ve kaynak modunu etkinleştirirseniz, derleme kodunun hem kaynak hem de ayrıştırılmış formunu görüntüleyebilirsiniz.

Birden çok derleme yönergelerinin veya kaynak dili deyimlerinin tek bir satıra yerleştirilmesi, hata ayıklamanın ayıklanmadığını unutmayın. Kaynak modunda, hata ayıklayıcıyı, tek bir satırda kesme noktaları ayarlamak için kullanabilirsiniz, ancak aynı satırdaki tek tek deyimlerde kullanılamaz. Aynı ilke, **`__asm`** tek bir mantıksal satıra genişleyen C makrosu olarak tanımlanan bir blok için geçerlidir.

[/Fas](../../build/reference/fa-fa-listing-file.md) derleyici seçeneğiyle bir karma kaynak ve derleme listesi oluşturursanız, listede her derleme dili satırının hem kaynak hem de derleme formları bulunur. Makrolar listelerde genişletilmez, ancak derleme sırasında genişletilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
