---
title: .SAVEXMM128
ms.date: 08/30/2018
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: c29ec47170c5e0f46f02d53f23ab477a79bbdc32
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205231"
---
# <a name="savexmm128"></a>.SAVEXMM128

Oluşturur ya da bir `UWOP_SAVE_XMM128` veya `UWOP_SAVE_XMM128_FAR` belirtilen XMM kaydı için kod girişi bırakma ve geçerli başlangıç uzaklığını kullanarak uzaklığı. MASM en verimli kodlama seçersiniz.

## <a name="syntax"></a>Sözdizimi

> .SAVEXMM128 xmmreg, offset

## <a name="remarks"></a>Açıklamalar

. SAVEXMM128 sağlayan nasıl çerçeve işlevi geriye doğru izler ve yalnızca gelen genişletir prolog içinde izin ml64.exe kullanıcıların [PROC](../../assembler/masm/proc.md) çerçeve bildirimine [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeler, kodu üretmemesi; yalnızca hazırlanmasının `.xdata` ve `.pdata`. . Geriye doğru olması için eylemleri uygulayan yönergeleri ile SAVEXMM128 gelmelidir. Bırakma yönergeleri hem anlaşma emin olmak için bunlar bir makroda geriye doğru şekilde tasarlanmıştır kodu kaydırmak için iyi bir uygulamadır.

*uzaklık* 16 katı olmalıdır.

Daha fazla bilgi için [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>