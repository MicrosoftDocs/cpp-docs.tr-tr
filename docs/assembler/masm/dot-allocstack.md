---
title: . ALLOCSTACK | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .ALLOCSTACK
dev_langs:
- C++
helpviewer_keywords:
- .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 292a7fcdb0a1d7c4ecccab895c643479397b4a98
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681937"
---
# <a name="allocstack"></a>.ALLOCSTACK

Oluşturur bir **UWOP_ALLOC_SMALL** veya **UWOP_ALLOC_LARGE** prolog geçerli uzaklığı için belirtilen boyut ile.

## <a name="syntax"></a>Sözdizimi

> . ALLOCSTACK boyutu

## <a name="remarks"></a>Açıklamalar

MASM için verilen boyuta en verimli kodlama seçersiniz.

. ALLOCSTACK ml64.exe kullanıcılara nasıl çerçeve işlevi geriye doğru izler belirtmek ve yalnızca gelen genişletir prolog içinde izin [PROC](../../assembler/masm/proc.md) çerçeve bildirimine [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeler, kodu üretmemesi; yalnızca hazırlanmasının `.xdata` ve `.pdata`. . Geriye doğru olması için eylemleri uygulayan yönergeleri ile ALLOCSTACK gelmelidir. Bırakma yönergeleri hem anlaşma emin olmak için bunlar bir makroda geriye doğru şekilde tasarlanmıştır kodu kaydırmak için iyi bir uygulamadır.

`size` İşlenen 8'in katı olmalıdır.

Daha fazla bilgi için bkz. [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Örnek

Aşağıdaki örnek, bir geriye doğru izleme/özel durum işleyicisi belirteceğiniz gösterilmektedir:

```asm
; ml64 ex3.asm /link /entry:Example1  /SUBSYSTEM:Console
text SEGMENT
PUBLIC Example3
PUBLIC Example3_UW
Example3_UW PROC NEAR
   ; exception/unwind handler body

   ret 0

Example3_UW ENDP

Example3 PROC FRAME : Example3_UW

   sub rsp, 16
.allocstack 16

.endprolog

   ; function body
    add rsp, 16
   ret 0

Example3 ENDP
text ENDS
END
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>