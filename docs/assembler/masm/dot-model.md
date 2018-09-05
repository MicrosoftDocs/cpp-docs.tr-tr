---
title: . MODEL | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .MODEL
dev_langs:
- C++
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2b9606fc849658181cda5067f396a270f0ee3bb
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678176"
---
# <a name="model"></a>.MODEL

Program bellek modeli başlatır.

## <a name="syntax"></a>Sözdizimi

> . MODEL memorymodel [[, langtype]] [[, stackoption]]

### <a name="parameters"></a>Parametreler

*memorymodel*<br/>
Kod ve veri işaretçileri boyutunu belirler gerekli parametre.

*langtype*<br/>
Arama ve adlandırma kuralları için yordamlar ve ortak semboller ayarlar isteğe bağlı parametre.

*stackoption*<br/>
İsteğe bağlı parametre.

*stackoption* kullanılmaz *memorymodel* olduğu `FLAT`.

Belirtme `NEARSTACK` yığın kesiminin tek bir fiziksel kesim içinde gruplar (`DGROUP`) verileriyle birlikte. Yığın segment kaydı (`SS`) veri segmenti kaydı aynı adresi tutacak varsayılır (`DS`). `FARSTACK` yığın ile gruplandırmaz `DGROUP`; bu nedenle `SS` eşit olmadığı `DS`.

## <a name="remarks"></a>Açıklamalar

.`MODEL` kullanılmaz [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).

Aşağıdaki tabloda, 16-bit ve 32-bit platformu hedeflerken her parametre için olası değerler listelenmiştir:

|Parametre|32-bit değerleri|16-bit değerleri (geliştirme desteği için önceki 16-bit)|
|---------------|--------------------|----------------------------------------------------------------|
|*memorymodel*|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|
|*langtype*|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|
|*stackoption*|Kullanılan değil|`NEARSTACK`, `FARSTACK`|

## <a name="code"></a>Kod

MASM ile ilgili örnekler için derleyici örneklerini indirin [Visual C++ örnekleri ve ilgili belgeler için Visual Studio 2010](http://go.microsoft.com/fwlink/p/?linkid=178749).

Aşağıdaki örnek, kullanımını gösterir `.MODEL` yönergesi.

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

