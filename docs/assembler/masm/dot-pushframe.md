---
title: .PUSHFRAME
ms.date: 08/30/2018
f1_keywords:
- .PUSHFRAME
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
ms.openlocfilehash: 9ea506e25435c5d6f1b10eab8c4f25f72bf88791
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468334"
---
# <a name="pushframe"></a>.PUSHFRAME

Oluşturur bir `UWOP_PUSH_MACHFRAME` kod girişi geriye doğru izleme. İsteğe bağlı `code` belirtilirse, geriye doğru izleme kodu giriş 1 değiştiricisi verilmiştir. Aksi takdirde değiştirici 0'dır.

## <a name="syntax"></a>Sözdizimi

> . PUSHFRAME [kod]

## <a name="remarks"></a>Açıklamalar

. PUSHFRAME ml64.exe kullanıcılara nasıl çerçeve işlevi geriye doğru izler belirtmek ve yalnızca gelen genişletir prolog içinde izin [PROC](../../assembler/masm/proc.md) çerçeve bildirimine [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeler, kodu üretmemesi; yalnızca hazırlanmasının `.xdata` ve `.pdata`. . Geriye doğru olması için eylemleri uygulayan yönergeleri ile PUSHFRAME gelmelidir. Bırakma yönergeleri hem anlaşma emin olmak için bunlar bir makroda geriye doğru şekilde tasarlanmıştır kodu kaydırmak için iyi bir uygulamadır.

Daha fazla bilgi için [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>