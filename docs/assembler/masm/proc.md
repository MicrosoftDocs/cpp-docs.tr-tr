---
title: PROC
ms.date: 08/30/2018
f1_keywords:
- PROC
helpviewer_keywords:
- PROC directive
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
ms.openlocfilehash: e7931c97570c0fefcacb0123d75934867793fba4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210540"
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