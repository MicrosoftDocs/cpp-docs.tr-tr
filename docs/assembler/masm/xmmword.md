---
description: 'Daha fazla bilgi edinin: XMMWORD'
title: XMMWORD
ms.date: 12/17/2019
f1_keywords:
- XMMWORD
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
ms.openlocfilehash: 304ac53a29fa7912107d6d4e87ee6efd3924ac3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124988"
---
# <a name="xmmword"></a>XMMWORD

MMX ve SSE (XMM) yönergeleriyle 128 bitlik multimedya işlenenleri için kullanılır.

## <a name="syntax"></a>Syntax

> **XMMWORD**

## <a name="remarks"></a>Açıklamalar

**Xmmword** , [__m128](../../cpp/m128.md)ile aynı türü temsil etmek üzere tasarlanmıştır.

## <a name="example"></a>Örnek

```asm
    movdqa   xmm0, xmmword ptr [ebx]
```

## <a name="see-also"></a>Ayrıca Bkz.

[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
