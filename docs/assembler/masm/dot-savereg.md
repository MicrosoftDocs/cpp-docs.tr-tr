---
title: .SAVEREG
ms.date: 08/30/2018
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: 324cf0e70a7ad619e5741c9acc18c24a72f54d13
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397963"
---
# <a name="savereg"></a>.SAVEREG

Geçerli başlangıç sapmasını kullanarak belirtilen yazmaç (*reg*) ve konum (*konum*) için bir `UWOP_SAVE_NONVOL` ya da `UWOP_SAVE_NONVOL_FAR` bırakma kodu girişi oluşturur. MASı, en verimli kodlamayı seçer.

## <a name="syntax"></a>Sözdizimi

> **. Savereg** *reg* __,__ *konum*

## <a name="remarks"></a>Açıklamalar

**. SAVEREG**, ml64. exe kullanıcılarına, bir çerçeve işlevinin yük dışı bırakma ve [işlem çerçevesi bildiriminden](../../assembler/masm/proc.md) öğesine genişleyen yalnızca prolog içinde nasıl izin verileceğini belirlemesine izin verir [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca `.xdata` ve `.pdata`oluşturur. **. SAVEREG** öncesinde eylemleri gerçekten uygulayan yönergelerden kaçınılmalıdır. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

Daha fazla bilgi için bkz. [for x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)
