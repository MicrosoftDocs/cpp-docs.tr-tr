---
title: PROC | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- PROC
dev_langs:
- C++
helpviewer_keywords:
- PROC directive
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ee26e181f0f40126c86a36889c43405f0b40f5e
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680852"
---
# <a name="proc"></a>PROC

Başlangıç ve bitiş adlı bir yordam bloğunun işaretler *etiket*. Bloğu içindeki deyimler ile çağrılabilir **çağrı** yönerge veya [INVOKE](../../assembler/masm/invoke.md) yönergesi.

## <a name="syntax"></a>Sözdizimi

> *Etiket* PROC [[*uzaklık*]] [[*langtype*]] [[*görünürlük*]] [[\<*prologuearg*>]] [[ KULLANAN *reglist*]] [[, *parametre* [[:*etiketi*]]]...<br/>
> [[Çerçeve [[:*ehandler adresi*]]]]<br/>
> *Deyimleri*<br/>
> *Etiket* ENDP

## <a name="remarks"></a>Açıklamalar

[[Çerçeve [[:*ehandler adresi*]]]] yalnızca ml64.exe ile geçerlidir ve .pdata işlev bir tablo girişi oluşturun ve bir işlevin yapılandırılmış bilgiler sanal işlem bulunur, geriye doğru izleme MASM neden olan özel durum işleme geriye doğru davranışı.

Zaman **çerçeve** özniteliği kullanılır, bu gelmelidir bir [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi.

Bkz: [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md) ml64.exe kullanma hakkında daha fazla bilgi için.

## <a name="example"></a>Örnek

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

Yukarıdaki kod, aşağıdaki işlev tablosu yayma ve geriye doğru izleme bilgilerini:

```Output
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

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>