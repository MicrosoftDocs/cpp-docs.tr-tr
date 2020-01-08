---
title: PROC
ms.date: 12/06/2019
f1_keywords:
- PROC
helpviewer_keywords:
- PROC directive
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
ms.openlocfilehash: 85d9a1e82eebcd83cb0f12f5ca751ec9415af18d
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318676"
---
# <a name="proc"></a>PROC

*Etiket*adlı bir yordam bloğunun başlangıcını ve sonunu işaretler. Bloktaki deyimler **Call** yönergesi veya [Invoke](invoke.md) yönergesi ile çağrılabilir.

## <a name="syntax"></a>Sözdizimi

> *etiket* **proc** ⟦*Distance*⟧ ⟦*Language-Type*⟧ ⟦ **PUBLIC** | **PRIVATE** | **Export** ⟧ ⟦ __\<__ *prologuearg* __>__ ⟧ ⟦, *reglist*⟧ ⟦ __,__ *parametre* ⟦ __:__ *Tag*⟧**kullanır** ... ⟧\
> ⟦**Frame** ⟦ __:__ *ehandler-Address*⟧ ⟧ \
> *deyimler*\
> *etiket* **endp**

## <a name="remarks"></a>Açıklamalar

⟦*Distance*⟧ ve ⟦*Language-Type*⟧ bağımsız değişkenleri yalnızca 32-bit Masd 'de geçerlidir.

⟦**Frame** ⟦ __:__ *ehandler-Address*⟧ ⟧ yalnızca ml64. exe ile geçerlidir ve bir işlevin yapılandırılmış özel durum işleme geriye doğru izleme davranışı için. xdata içinde. pdata ve bırakma bilgilerinde bir işlev tablosu girişi oluşturulmasına neden olur.

**Çerçeve** özniteliği kullanıldığında, arkasından bir gelmelidir [. ENDPROLOG](dot-endprolog.md) yönergesi.

Ml64. exe kullanma hakkında daha fazla bilgi için bkz. [for x64 (ml64. exe)](masm-for-x64-ml64-exe.md) .

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

Yukarıdaki kod, aşağıdaki işlev tablosu ve geriye doğru izleme bilgilerini yayacaktır:

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

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
