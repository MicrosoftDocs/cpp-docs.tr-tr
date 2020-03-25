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
ms.openlocfilehash: 3254fb6b750466de0a38230c5e1cfa067c476f5e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169519"
---
# <a name="debugging-and-listings-for-inline-assembly"></a>Satır İçi Derleme için Hata Ayıklama ve Listeleme

**Microsoft 'a özgü**

Satır içi derleme kodu içeren programlar, [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) seçeneğiyle derlerseniz kaynak düzeyinde bir hata ayıklayıcı ile hata ayıklanabilir.

Hata ayıklayıcı içinde, hem C C++ hem de derleme dili satırlarında kesme noktaları ayarlayabilirsiniz. Karışık derleme ve kaynak modunu etkinleştirirseniz, derleme kodunun hem kaynak hem de ayrıştırılmış formunu görüntüleyebilirsiniz.

Birden çok derleme yönergelerinin veya kaynak dili deyimlerinin tek bir satıra yerleştirilmesi, hata ayıklamanın ayıklanmadığını unutmayın. Kaynak modunda, hata ayıklayıcıyı, tek bir satırda kesme noktaları ayarlamak için kullanabilirsiniz, ancak aynı satırdaki tek tek deyimlerde kullanılamaz. Aynı prensibi, tek bir mantıksal satıra genişleyen C makrosu olarak tanımlanan bir `__asm` bloğu için geçerlidir.

[/Fas](../../build/reference/fa-fa-listing-file.md) derleyici seçeneğiyle bir karma kaynak ve derleme listesi oluşturursanız, listede her derleme dili satırının hem kaynak hem de derleme formları bulunur. Makrolar listelerde genişletilmez, ancak derleme sırasında genişletilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
