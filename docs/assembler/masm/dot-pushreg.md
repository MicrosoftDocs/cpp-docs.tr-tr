---
title: . PUSHREG | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .PUSHREG
dev_langs:
- C++
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4b9f4a7189d2dbe3717535a95a1816e5fd0de3b
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="pushreg"></a>.PUSHREG
Oluşturan bir `UWOP_PUSH_NONVOL` belirtilen numarasını başlangıç uzaklığı geçerli kullanarak kaydetmek için kod girişi bırakma.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.PUSHREG register  
```  
  
## <a name="remarks"></a>Açıklamalar  
 . PUSHREG ml64.exe kullanıcıların nasıl çerçeve işlevi unwinds ve yalnızca gelen genişletir giriş içinde izin belirtmesine izin verir [PROC](../../assembler/masm/proc.md) çerçeve bildirimine [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeleri kod oluşturmaz; yalnızca oluşturdukları `.xdata` ve `.pdata`. . PUSHREG gerçekten unwound olmasını eylemlerini uygulamak yönergeleri ile gelmelidir. Bırakma yönergeleri ve bunlar makro bırakma sözleşmesi emin olmak için değiştirmemektir kodu sarmalamak için iyi bir uygulamadır.  
  
 Daha fazla bilgi için bkz: [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="sample"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, geçici olmayan tegisters anında gösterilmektedir.  
  
### <a name="code"></a>Kod  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)