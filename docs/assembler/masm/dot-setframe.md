---
title: . SETFRAME | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SETFRAME
dev_langs:
- C++
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c49d512534a11f01376deac41006e55c6b7b9d89
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="setframe"></a>.SETFRAME
Çerçeve doldurur bırakma bilgilerin belirtilen yazmaç kullanarak alan ve uzaklık kaydetmek (`reg`) ve uzaklık (`offset`). Uzaklık 16 katları olmalıdır ve 240 küçük veya buna eşit. Bu yönerge ayrıca oluşturur bir `UWOP_SET_FPREG` geçerli başlangıç sapmasını kullanarak belirtilen kaydetmek için kod girişi bırakma.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.SETFRAME reg, offset  
```  
  
## <a name="remarks"></a>Açıklamalar  
 . SETFRAME ml64.exe kullanıcıların nasıl çerçeve işlevi unwinds ve yalnızca gelen genişletir giriş içinde izin belirtmesine izin verir [PROC](../../assembler/masm/proc.md) çerçeve bildirimine [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeleri kod oluşturmaz; yalnızca oluşturdukları `.xdata` ve `.pdata`. . SETFRAME gerçekten unwound olmasını eylemlerini uygulamak yönergeleri ile gelmelidir. Bırakma yönergeleri ve bunlar makro bırakma sözleşmesi emin olmak için değiştirmemektir kodu sarmalamak için iyi bir uygulamadır.  
  
 Daha fazla bilgi için bkz: [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="sample"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, bir çerçeve işaretçisi kullanmayı gösterir:  
  
### <a name="code"></a>Kod  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)