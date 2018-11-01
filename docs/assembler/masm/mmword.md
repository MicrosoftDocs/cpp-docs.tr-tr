---
title: MMWORD
ms.date: 08/30/2018
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: 1205338f9140c74a3a6e0b4bce57983edc80862e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541130"
---
# <a name="mmword"></a>MMWORD

64-bit MMX ve (XMM) SSE yönergeleri ile multimedya işlenenleri için kullanılır.

## <a name="syntax"></a>Sözdizimi

> MMWORD

## <a name="remarks"></a>Açıklamalar

`MMWORD` bir türdür.  MASM için eklenen MMWORD önce eşdeğer işlev ile elde edildiğini:

```asm
    mov mm0, qword ptr [ebx]
```

Her iki yönerge 64-bit işlenenler üzerinde çalışırken `QWORD` için 64-bit işaretsiz tamsayı türü ve `MMWORD` için 64-bit multimedya bir değer türüdür.

`MMWORD` aynı tür olarak temsil etmek üzere tasarlanmıştır [__m64](../../cpp/m64.md).

## <a name="example"></a>Örnek

```asm
    movq     mm0, mmword ptr [ebx]
```