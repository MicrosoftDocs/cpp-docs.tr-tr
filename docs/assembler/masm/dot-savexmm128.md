---
description: Hakkında daha fazla bilgi edinin:. SAVEXMM128
title: .SAVEXMM128
ms.date: 12/17/2019
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: 697598aa5820b029d19da62a817c60455059865e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131124"
---
# <a name="savexmm128"></a>.SAVEXMM128

Geçerli başlangıç sapmasını `UWOP_SAVE_XMM128` `UWOP_SAVE_XMM128_FAR` kullanarak belirtilen XMM kaydı ve kayması için bir ya da bir geriye doğru izleme kodu girişi oluşturur. MASı, en verimli kodlamayı seçer.

## <a name="syntax"></a>Syntax

> **. SAVEXMM128** *xmmreg* , *konum*

## <a name="remarks"></a>Açıklamalar

**. SAVEXMM128** , ml64.exe kullanıcıların bir karenin nasıl bir kare işlevi olduğunu belirtmesini sağlar ve [işlem çerçevesi bildiriminden](proc.md) öğesine genişleten yalnızca prolog dahilinde izin verilir [. ENDPROLOG](dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca ve oluşturur `.xdata` `.pdata` . . SAVEXMM128 önünde olmayan eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

*Aralık* 16 ' dan fazla olmalıdır.

Daha fazla bilgi için bkz. [x64 Için ması (ml64.exe)](masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
