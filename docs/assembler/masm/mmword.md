---
description: 'Daha fazla bilgi edinin: MMWORD'
title: MMWORD
ms.date: 12/17/2019
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: f0e888efcfea7c1ca94129ff3e4cd2f40644ae13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128244"
---
# <a name="mmword"></a>MMWORD

MMX ve SSE (XMM) yönergeleriyle 64 bitlik multimedya işlenenleri için kullanılır.

## <a name="syntax"></a>Syntax

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
