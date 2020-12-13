---
description: Hakkında daha fazla bilgi edinin:. SETFRAME
title: .SETFRAME
ms.date: 12/17/2019
f1_keywords:
- .SETFRAME
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
ms.openlocfilehash: b3554da14344293f00c499bc3084e6ddfd93c2ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131085"
---
# <a name="setframe"></a>.SETFRAME

Belirtilen yazmaç (*reg*) ve sapmayı (*konum*) kullanarak, çerçeve kaydı alanını ve geriye doğru izleme bilgilerini doldurur. Aralık 16 ' dan büyük ve 240 ' e eşit veya daha küçük olmalıdır. Bu yönerge ayrıca geçerli giriş `UWOP_SET_FPREG` sapmasını kullanarak belirtilen kayıt için bir geriye doğru izleme kodu girişi oluşturur.

## <a name="syntax"></a>Syntax

> **. SETFRAME** *reg*, *konum*

## <a name="remarks"></a>Açıklamalar

**. SETFRAME** , ml64.exe kullanıcıların bir karenin nasıl bir kare işlevi olduğunu belirtmesini ve [işlem çerçevesi bildiriminden](proc.md) öğesine genişleten yalnızca prolog içinde nasıl izin verileceğini belirlemesine izin verir [. ENDPROLOG](dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca ve oluşturur `.xdata` `.pdata` . **. SETFRAME** önünde olmayan eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

Daha fazla bilgi için bkz. [x64 Için ması (ml64.exe)](masm-for-x64-ml64-exe.md).

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
