---
title: MMWORD | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- MMWORD
dev_langs:
- C++
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7314c6d0861195e312c7f72481d2e195e041965d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679240"
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
    movq     mm0, mmword ptr [ebx]
```