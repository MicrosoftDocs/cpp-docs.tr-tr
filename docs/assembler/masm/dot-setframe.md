---
title: .SETFRAME
ms.date: 12/17/2019
f1_keywords:
- .SETFRAME
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
ms.openlocfilehash: 8c491a811634995398a37aa001cc1c93f8434114
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318247"
---
# <a name="setframe"></a>.SETFRAME

Belirtilen yazmaç (*reg*) ve sapmayı (*konum*) kullanarak, çerçeve kaydı alanını ve geriye doğru izleme bilgilerini doldurur. Aralık 16 ' dan büyük ve 240 ' e eşit veya daha küçük olmalıdır. Bu yönerge Ayrıca, geçerli prolog sapmasını kullanarak belirtilen kayıt için bir `UWOP_SET_FPREG` bırakma kodu girişi oluşturur.

## <a name="syntax"></a>Sözdizimi

> **. SETFRAME** *reg*, *konum*

## <a name="remarks"></a>Açıklamalar

**. SETFRAME** , ml64. exe kullanıcılarına bir karenin nasıl bir kare işlevi olduğunu ve [işlem çerçevesi bildiriminden](proc.md) öğesine genişleten yalnızca prolog dahilinde izin verileceğini belirlemesine izin verir [. ENDPROLOG](dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca `.xdata` ve `.pdata`oluşturur. **. SETFRAME** önünde olmayan eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

Daha fazla bilgi için bkz. [for x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, bir çerçeve işaretçisinin nasıl kullanılacağını göstermektedir:

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

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
