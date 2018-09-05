---
title: . PUSHFRAME | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .PUSHFRAME
dev_langs:
- C++
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c86ba043eb185e9cc5697f236b907ae8177d6824
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689495"
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