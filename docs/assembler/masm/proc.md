---
title: PROC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROC
dev_langs: C++
helpviewer_keywords: PROC directive
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2567099c26682bd7d448175b1283aeab56054516
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="proc"></a>PROC
Başlangıç ve bitiş adlı bir yordam bloğunun işaretler *etiket*. Blok ifadeler ile çağrılabilir **ÇAĞRISI** yönergesi veya [INVOKE](../../assembler/masm/invoke.md) yönergesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
   label PROC [[distance]] [[langtype]] [[visibility]] [[<prologuearg>]]   
[[USES reglist]] [[, parameter [[:tag]]]]...  
[FRAME [:ehandler-address] ]  
statements  
label ENDP  
```  
  
## <a name="remarks"></a>Açıklamalar  
 [Çerçeve [:*ehandler adresi*]] yalnızca ml64.exe ile geçerli olduğundan ve bir işlevin tablo girişi ve.xdata'yı oluşturmak ve bir işlevin yapılandırılmış xdata'daki bilgileri bırakma MASM neden olan özel durum işleme bırakma davranışı.  
  
 Zaman **çerçeve** özniteliği kullanılır, bu tarafından uyulması gereken bir [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi.  
  
 Bkz: [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md) ml64.exe kullanma hakkında daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
  
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
  
 Yukarıdaki kod, aşağıdaki işlev tablosu yayma ve geriye doğru izleme bilgilerini:  
  
```  
FileHeader->Machine 34404  
Dumping Unwind Information for file ex2.exe  
  
.pdata entry 1 0x00001000 0x00001023  
  
  Unwind data: 0x00002000  
  
    Unwind version: 1  
    Unwind Flags: None  
    Size of prologue: 0x08  
    Count of codes: 3  
    Frame register: rbp  
    Frame offset: 0x0  
    Unwind codes:  
  
      Code offset: 0x08, SET_FPREG, register=rbp, offset=0x00  
      Code offset: 0x05, ALLOC_SMALL, size=0x10  
      Code offset: 0x01, PUSH_NONVOL, register=rbp  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler başvurusu](../../assembler/masm/directives-reference.md)