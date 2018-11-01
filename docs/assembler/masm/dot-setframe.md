---
title: .SETFRAME
ms.date: 08/30/2018
f1_keywords:
- .SETFRAME
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
ms.openlocfilehash: c2c35cdb2889350b27e9fb11c397b684506972c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506892"
---
# <a name="setframe"></a>.SETFRAME

Çerçeve doldurur, geriye doğru izleme bilgilerinde belirtilen yazmaç kullanarak alan ve uzaklık kaydetme (`reg`) ve uzaklık (`offset`). Uzaklık 16 olmalıdır ve 240 küçüktür veya eşittir. Bu yönerge ayrıca oluşturur bir `UWOP_SET_FPREG` belirtilen geçerli başlangıç uzaklığını kullanarak kaydetmek için kod girişi geriye doğru izleme.

## <a name="syntax"></a>Sözdizimi

> . SETFRAME yazmaç, offset

## <a name="remarks"></a>Açıklamalar

. SETFRAME sağlayan nasıl çerçeve işlevi geriye doğru izler ve yalnızca gelen genişletir prolog içinde izin ml64.exe kullanıcıların [PROC](../../assembler/masm/proc.md) çerçeve bildirimine [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeler, kodu üretmemesi; yalnızca hazırlanmasının `.xdata` ve `.pdata`. . Geriye doğru olması için eylemleri uygulayan yönergeleri ile SETFRAME gelmelidir. Bırakma yönergeleri hem anlaşma emin olmak için bunlar bir makroda geriye doğru şekilde tasarlanmıştır kodu kaydırmak için iyi bir uygulamadır.

Daha fazla bilgi için [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, bir çerçeve işaretçisi kullanma işlemini gösterir:

### <a name="code"></a>Kod

```asm
; ml64 frmex2.asm /link /entry:frmex2 /SUBSYSTEM:CONSOLE
_text SEGMENT
frmex2 PROC FRAME
   push rbp
.pushreg rbp
   sub rsp, 010h
.allocstack 010h
   mov rbp, rsp
.setframe rbp, 0
.endprolog
   ; modify the stack pointer outside of the prologue (similar to alloca)
   sub rsp, 060h

   ; we can unwind from the following AV because of the frame pointer
   mov rax, 0
   mov rax, [rax] ; AV!

   add rsp, 060h
   add rsp, 010h
   pop rbp
   ret
frmex2 ENDP
_text ENDS
END
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>