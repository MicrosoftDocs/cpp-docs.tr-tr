---
title: MMWORD
ms.date: 12/17/2019
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: fd3b9f40b7ff9fa4dae570e0ed906c13a9456424
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75311929"
---
# <a name="mmword"></a>MMWORD

MMX ve SSE (XMM) yönergeleriyle 64 bitlik multimedya işlenenleri için kullanılır.

## <a name="syntax"></a>Sözdizimi

> **MMWORD**

## <a name="remarks"></a>Açıklamalar

**MMWORD** bir türdür.  Mase 'ye eklenen **MMWORD** öncesinde, ile eşdeğer işlevler elde edilebilir:

```asm
    mov mm0, qword ptr [ebx]
```

Her iki yönerge de 64 bitlik işlenenler üzerinde çalışırken, **QWORD** , 64 bit işaretsiz tamsayılar türüdür ve **MMWORD** , bir 64-bit multimedya değeri türüdür.

**MMWORD** , [__m64](../../cpp/m64.md)ile aynı türü temsil etmek üzere tasarlanmıştır.

## <a name="example"></a>Örnek

```asm
    movq     mm0, mmword ptr [ebx]
```

## <a name="see-also"></a>Ayrıca Bkz.

[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
