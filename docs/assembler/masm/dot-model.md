---
title: .MODEL
ms.date: 11/05/2019
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: b341cfaec35c08f5ac16447890c85570e9c9c0df
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703577"
---
# <a name="model-32-bit-masm"></a>. MODEL (32-bit masa)

Program bellek modelini başlatır. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Sözdizimi

> . MODEL MemoryModel [[, langtype]] [[, stackoption]]

### <a name="parameters"></a>Parametreler

*MemoryModel*<br/>
Kod ve veri işaretçilerinin boyutunu belirleyen gerekli parametre.

*langtype*<br/>
Yordamlar ve genel semboller için çağrı ve adlandırma kurallarını ayarlayan isteğe bağlı parametre.

*yığın*<br/>
İsteğe bağlı parametre.

*MemoryModel* `FLAT`ise *stackoption* kullanılmaz.

`NEARSTACK` belirtme yığın segmentini verilerle birlikte tek bir fiziksel kesime (`DGROUP`) gruplandırır. Yığın segmentinin (`SS`), veri segmenti kaydetme (`DS`) ile aynı adresi tutan varsayılır. `FARSTACK`, `DGROUP`ile yığını gruplandırmaz; Bu nedenle `SS` `DS`eşit değildir.

## <a name="remarks"></a>Açıklamalar

.`MODEL` , [x64 (ml64. exe) Için Masd](../../assembler/masm/masm-for-x64-ml64-exe.md)'de kullanılmaz.

Aşağıdaki tabloda, 16 bit ve 32-bit platformları hedeflenirken her bir parametre için olası değerler listelenmektedir:

|Parametre|32 bit değerleri|16 bit değerler (önceki 16 bit geliştirme desteği)|
|---------------|--------------------|----------------------------------------------------------------|
|*MemoryModel*|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|
|*langtype*|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|
|*yığın*|Kullanılan değil|`NEARSTACK`, `FARSTACK`|

## <a name="code"></a>Kod

Mase ile ilgili örnekler için, Visual [Studio 2010 Için Visual C++ örneklerden ve ilgili belgelerden](https://go.microsoft.com/fwlink/p/?linkid=178749)derleyici örneklerini indirin.

Aşağıdaki örnek, `.MODEL` yönergesinin kullanımını gösterir.

## <a name="example"></a>Örnek

```asm
; file simple.asm
; For x86 (32-bit), assemble with debug information:
;   ml -c -Zi simple.asm
; For x64 (64-bit), assemble with debug information:
;   ml64 -c -DX64 -Zi simple.asm
;
; In this sample, the 'X64' define excludes source not used
;  when targeting the x64 architecture

ifndef X64
.686p
.XMM
.model flat, C
endif

.data
; user data

.code
; user code

fxn PROC public
  xor eax, eax ; zero function return value
  ret
fxn ENDP

end
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>
