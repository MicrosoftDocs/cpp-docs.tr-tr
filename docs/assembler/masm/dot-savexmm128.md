---
title: .SAVEXMM128 | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAVEXMM128
dev_langs:
- C++
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d44855d3449000c588f7e840753bd734af4b1af
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689913"
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