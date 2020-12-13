---
description: Hakkında daha fazla bilgi edinin:. ALLOCSTACK
title: .ALLOCSTACK
ms.date: 12/17/2019
f1_keywords:
- .ALLOCSTACK
helpviewer_keywords:
- .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
ms.openlocfilehash: 6075b0900df104ae5faeaaff1dc0de2d3727b437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132372"
---
# <a name="allocstack"></a>.ALLOCSTACK

Prolog 'daki geçerli fark için belirtilen boyuta sahip bir **UWOP_ALLOC_SMALL** veya **UWOP_ALLOC_LARGE** oluşturur.

## <a name="syntax"></a>Syntax

> **. ALLOCSTACK** *boyutu*

## <a name="remarks"></a>Açıklamalar

MASı, belirli bir boyut için en verimli kodlamayı seçer.

**. ALLOCSTACK** , ml64.exe kullanıcıların, bir çerçeve işlevinin yük dışı bırakma ve [işlem çerçevesi bildiriminden](proc.md) öğesine genişleyen yalnızca prolog içinde nasıl izin verileceğini belirlemesine izin verir [. ENDPROLOG](dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca ve oluşturur `.xdata` `.pdata` . **. ALLOCSTACK** öncesinde, eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

*Boyut* işleneni 8 ' in katı olmalıdır.

Daha fazla bilgi için bkz. [x64 Için ması (ml64.exe)](masm-for-x64-ml64-exe.md).

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
