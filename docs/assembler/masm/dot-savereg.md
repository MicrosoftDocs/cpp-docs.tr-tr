---
title: . SAVEREG | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAVEREG
dev_langs:
- C++
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7010664cd2e80841d9e35d8fcf72d195cecf796
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688995"
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