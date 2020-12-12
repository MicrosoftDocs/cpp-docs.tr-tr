---
description: Hakkında daha fazla bilgi edinin:. MODEL (32-bit masa)
title: .MODEL
ms.date: 11/05/2019
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: f4f69b88a2041a13a0b92445c61c4a84d43e442f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131436"
---
# <a name="model-32-bit-masm"></a>. MODEL (32-bit masa)

Program bellek modelini başlatır. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Syntax

> **. Model** *bellek-model* ⟦__,__ *dil türü*⟧ ⟦__,__ *Stack-Option*⟧

### <a name="parameters"></a>Parametreler

*bellek modeli*\
Kod ve veri işaretçilerinin boyutunu belirleyen gerekli parametre.

*dil türü*\
Yordamlar ve genel semboller için çağrı ve adlandırma kurallarını ayarlayan isteğe bağlı parametre.

*Stack-seçenek*\
İsteğe bağlı parametre.

*bellek-model* **düz** ise *yığın seçeneği* kullanılmaz.

Her bir fiziksel kesime (**DGROUP**) veri ile birlikte, daha önce **bir yığın segmenti belirtme.** Yığın segmenti yazmacı (**SS**), veri segmenti kayıt (**DS**) ile aynı adresi tutan varsayılır. **Farstack** , yığını **DGROUP** ile gruplandırmaz; Bu nedenle **SS** , **DS 'ye** eşit değildir.

## <a name="remarks"></a>Açıklamalar

**. MODEL** , [x64 (ml64.exe) Için Masd](masm-for-x64-ml64-exe.md)'de kullanılmaz.

Aşağıdaki tabloda, 16 bit ve 32-bit platformları hedeflenirken her bir parametre için olası değerler listelenmektedir:

|Parametre|32 bit değerleri|16 bit değerler (önceki 16 bit geliştirme desteği)|
|---------------|--------------------|----------------------------------------------------------------|
|*bellek modeli*|**DÜZ**|küçük, **küçük**, **kompakt**, **Orta**, **büyük, çok** **büyük,** **düz**|
|*dil türü*|**C**, **stdcall**|**C**, **temel**, **FORTRAN**, **Pascal**, **syscall**, **stdcall**|
|*Stack-seçenek*|Kullanılmıyor|**yaklaştığında yığın**, **farstack**|

## <a name="code"></a>Kod

MASı ile ilgili örnekler için, [Visual Studio 2010 Visual C++ örnekleri ve Ilgili belgelerden](https://go.microsoft.com/fwlink/p/?linkid=178749)derleyici örneklerini indirin.

Aşağıdaki örnek, yönergesinin kullanımını gösterir `.MODEL` .

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

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
