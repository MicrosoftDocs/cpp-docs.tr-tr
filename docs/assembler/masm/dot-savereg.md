---
title: .SAVEREG
ms.date: 08/30/2018
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: cac7aa7f2bdbf6b60831d2beb062f86559ec0358
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62178169"
---
# <a name="savereg"></a>.SAVEREG

Oluşturur ya da bir `UWOP_SAVE_NONVOL` veya `UWOP_SAVE_NONVOL_FAR` belirtilen kasa için kod girişi bırakma (`reg`) ve uzaklık (`offset`) geçerli başlangıç uzaklığını kullanarak. MASM en verimli kodlama seçersiniz.

## <a name="syntax"></a>Sözdizimi

> . SAVEREG yazmaç, offset

## <a name="remarks"></a>Açıklamalar

. SAVEREG ml64.exe kullanıcılara nasıl çerçeve işlevi geriye doğru izler belirtmek ve yalnızca gelen genişletir prolog içinde izin [PROC](../../assembler/masm/proc.md) çerçeve bildirimine [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeler, kodu üretmemesi; yalnızca hazırlanmasının `.xdata` ve `.pdata`. . Geriye doğru olması için eylemleri uygulayan yönergeleri ile SAVEREG gelmelidir. Bırakma yönergeleri hem anlaşma emin olmak için bunlar bir makroda geriye doğru şekilde tasarlanmıştır kodu kaydırmak için iyi bir uygulamadır.

Daha fazla bilgi için [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>