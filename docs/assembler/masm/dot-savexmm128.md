---
title: .SAVEXMM128
ms.date: 08/30/2018
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: 08bc5ab50e15aa59e0c49992d1810c7de20f364e
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397957"
---
# <a name="savexmm128"></a>.SAVEXMM128

Belirtilen XMM kaydı için bir `UWOP_SAVE_XMM128` veya `UWOP_SAVE_XMM128_FAR` geriye doğru izleme kodu girdisi ya da geçerli prolog sapmasını kullanarak bir konum üretir. MASı, en verimli kodlamayı seçer.

## <a name="syntax"></a>Sözdizimi

> **. SAVEXMM128** *xmmreg* , *konum*

## <a name="remarks"></a>Açıklamalar

**. SAVEXMM128** , ml64. exe kullanıcılarına bir karenin nasıl bir kare işlevi olduğunu ve [işlem çerçevesi bildiriminden](../../assembler/masm/proc.md) öğesine genişleten yalnızca prolog dahilinde izin verileceğini belirlemesine izin verir [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca `.xdata` ve `.pdata`oluşturur. . SAVEXMM128 önünde olmayan eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

*Aralık* 16 ' dan fazla olmalıdır.

Daha fazla bilgi için bkz. [for x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)
