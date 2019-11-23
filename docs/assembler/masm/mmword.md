---
title: MMWORD
ms.date: 08/30/2018
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: d4378c1435df09f249fe7f55dabd4bd0f43f6100
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397168"
---
# <a name="mmword"></a>MMWORD

Used for 64-bit multimedia operands with MMX and SSE (XMM) instructions.

## <a name="syntax"></a>Sözdizimi

> **MMWORD**

## <a name="remarks"></a>Açıklamalar

**MMWORD** is a type.  Prior to **MMWORD** being added to MASM, equivalent functionality could have been achieved with:

```asm
    mov mm0, qword ptr [ebx]
```

While both instructions work on 64-bit operands, **QWORD** is the type for 64-bit unsigned integers and **MMWORD** is the type for a 64-bit multimedia value.

**MMWORD** is intended to represent the same type as [__m64](../../cpp/m64.md).

## <a name="example"></a>Örnek

```asm
    movq     mm0, mmword ptr [ebx]
```
