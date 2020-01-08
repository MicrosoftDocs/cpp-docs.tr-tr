---
title: .ALLOCSTACK
ms.date: 12/17/2019
f1_keywords:
- .ALLOCSTACK
helpviewer_keywords:
- .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
ms.openlocfilehash: bcc94619dfa24ab5c8b5d23a60825641290ef176
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75314191"
---
# <a name="allocstack"></a>.ALLOCSTACK

Prolog 'daki geçerli fark için belirtilen boyuta sahip bir **UWOP_ALLOC_SMALL** veya **UWOP_ALLOC_LARGE** oluşturur.

## <a name="syntax"></a>Sözdizimi

> **. ALLOCSTACK** *boyutu*

## <a name="remarks"></a>Açıklamalar

MASı, belirli bir boyut için en verimli kodlamayı seçer.

**. ALLOCSTACK** , ml64. exe kullanıcılarına bir çerçeve işlevinin yük dışı bırakma ve [işlem çerçevesi bildiriminden](proc.md) öğesine genişleyen yalnızca prolog içinde nasıl izin verileceğini belirlemesine izin verir [. ENDPROLOG](dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca `.xdata` ve `.pdata`oluşturur. **. ALLOCSTACK** öncesinde, eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

*Boyut* işleneni 8 ' in katı olmalıdır.

Daha fazla bilgi için bkz. [for x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Örnek

Aşağıdaki örnek, bir geriye doğru izleme/özel durum işleyicisinin nasıl ekleneceğini göstermektedir:

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

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
