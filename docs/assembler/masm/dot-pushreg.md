---
title: .PUSHREG
ms.date: 08/30/2018
f1_keywords:
- .PUSHREG
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
ms.openlocfilehash: 2190bd05667de82dada34a63f11647c653f97247
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398031"
---
# <a name="pushreg"></a>.PUSHREG

Belirtilen kayıt numarası için, prolog 'deki geçerli sapmayı kullanarak bir `UWOP_PUSH_NONVOL` bırakma kodu girişi oluşturur.

## <a name="syntax"></a>Sözdizimi

> . PUSHREG kaydı

## <a name="remarks"></a>Açıklamalar

**. PUSHREG** , ml64. exe kullanıcılarına bir çerçeve işlevinin yük dışı bırakma şeklini belirtmesini sağlar ve işlem [](../../assembler/masm/proc.md) **çerçevesi** bildiriminden öğesine genişleten yalnızca prolog dahilinde izin verilir [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca `.xdata` ve `.pdata`oluşturur. **. PUSHREG** öncesinde eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

Daha fazla bilgi için bkz. [for x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

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

[Yönergeler başvurusu](directives-reference.md)
