---
title: .ALLOCSTACK
ms.date: 08/30/2018
f1_keywords:
- .ALLOCSTACK
helpviewer_keywords:
- .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
ms.openlocfilehash: 6d9d86371503992d1bebe738fb6e6773581b10e3
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398624"
---
# <a name="allocstack"></a>.ALLOCSTACK

Prolog 'daki geçerli fark için belirtilen boyuta sahip bir **UWOP_ALLOC_SMALL** veya **UWOP_ALLOC_LARGE** oluşturur.

## <a name="syntax"></a>Sözdizimi

> **. ALLOCSTACK** *boyutu*

## <a name="remarks"></a>Açıklamalar

MASı, belirli bir boyut için en verimli kodlamayı seçer.

**. ALLOCSTACK** , ml64. exe kullanıcılarına bir çerçeve işlevinin yük dışı bırakma ve [işlem çerçevesi bildiriminden](../../assembler/masm/proc.md) öğesine genişleyen yalnızca prolog içinde nasıl izin verileceğini belirlemesine izin verir [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca `.xdata` ve `.pdata`oluşturur. **. ALLOCSTACK** öncesinde, eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

*Boyut* işleneni 8 ' in katı olmalıdır.

Daha fazla bilgi için bkz. [for x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

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

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)
