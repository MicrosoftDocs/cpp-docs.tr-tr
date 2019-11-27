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
