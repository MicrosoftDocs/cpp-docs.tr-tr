---
title: .PUSHREG
ms.date: 12/16/2019
f1_keywords:
- .PUSHREG
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
ms.openlocfilehash: de6ffd3668f47732144e8c632410f6dfde6b2f31
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318299"
---
# <a name="pushreg"></a>.PUSHREG

Belirtilen kayıt numarası için, prolog 'deki geçerli sapmayı kullanarak bir `UWOP_PUSH_NONVOL` bırakma kodu girişi oluşturur.

## <a name="syntax"></a>Sözdizimi

> . PUSHREG *kaydı*

## <a name="remarks"></a>Açıklamalar

**. PUSHREG** , ml64. exe kullanıcılarına bir çerçeve işlevinin yük dışı bırakma şeklini belirtmesini sağlar ve işlem [](proc.md) **çerçevesi** bildiriminden öğesine genişleten yalnızca prolog dahilinde izin verilir [. ENDPROLOG](dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca `.xdata` ve `.pdata`oluşturur. **. PUSHREG** öncesinde eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

*yazmaç* aşağıdakilerden biri olabilir: \
VAX | RCX | RDX | RBX | RDı | RSı | RBP | R8 | R9 | R10 | R11 | R12 | R13 | R14 | R15.

Daha fazla bilgi için bkz. [for x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, geçici olmayan yazmaçların nasıl göndermeli olduğunu gösterir.

### <a name="code"></a>Kod

```asm
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE
_text SEGMENT
Example1 PROC FRAME
   push r10
.pushreg r10
   push r15
.pushreg r15
   push rbx
.pushreg rbx
   push rsi
.pushreg rsi
.endprolog
   ; rest of function ...
   ret
Example1 ENDP
_text ENDS
END
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
