---
title: .SAVEXMM128
ms.date: 12/17/2019
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: 6402b75c10b1400d56923116621f00b4d0908822
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318260"
---
# <a name="savexmm128"></a>.SAVEXMM128

Belirtilen XMM kaydı için bir `UWOP_SAVE_XMM128` veya `UWOP_SAVE_XMM128_FAR` geriye doğru izleme kodu girdisi ya da geçerli prolog sapmasını kullanarak bir konum üretir. MASı, en verimli kodlamayı seçer.

## <a name="syntax"></a>Sözdizimi

> **. SAVEXMM128** *xmmreg* , *konum*

## <a name="remarks"></a>Açıklamalar

**. SAVEXMM128** , ml64. exe kullanıcılarına bir karenin nasıl bir kare işlevi olduğunu ve [işlem çerçevesi bildiriminden](proc.md) öğesine genişleten yalnızca prolog dahilinde izin verileceğini belirlemesine izin verir [. ENDPROLOG](dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca `.xdata` ve `.pdata`oluşturur. . SAVEXMM128 önünde olmayan eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

*Aralık* 16 ' dan fazla olmalıdır.

Daha fazla bilgi için bkz. [for x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
