---
description: Hakkında daha fazla bilgi edinin:. PUSHREG
title: .PUSHREG
ms.date: 12/16/2019
f1_keywords:
- .PUSHREG
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
ms.openlocfilehash: b9316cebad76747c69cb577fcae71f28b6bd9530
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131267"
---
# <a name="pushreg"></a>.PUSHREG

`UWOP_PUSH_NONVOL`Belirtilen kayıt numarası için, prolog 'deki geçerli sapmayı kullanarak bir bırakma kodu girişi oluşturur.

## <a name="syntax"></a>Syntax

> . PUSHREG *kaydı*

## <a name="remarks"></a>Açıklamalar

**. PUSHREG** , ml64.exe kullanıcıların bir çerçeve işlevinin yük dışı bırakma şeklini belirtmesini ve işlem [](proc.md) **çerçevesi** bildiriminden öğesine genişleten yalnızca prolog içinde nasıl izin verileceğini belirlemesine izin verir [. ENDPROLOG](dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca ve oluşturur `.xdata` `.pdata` . **. PUSHREG** öncesinde eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

*yazmaç* aşağıdakilerden biri olabilir: \
VAX | RCX | RDX | RBX | RDı | RSı | RBP | R8 | R9 | R10 | R11 | R12 | R13 | R14 | R15.

Daha fazla bilgi için bkz. [x64 Için ması (ml64.exe)](masm-for-x64-ml64-exe.md).

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
