---
title: XMMWORD | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- XMMWORD
dev_langs:
- C++
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7fbb578c5e168f53bc1b4e217713efa1ea329743
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689220"
---
# <a name="xmmword"></a>XMMWORD

128-bit MMX ve (XMM) SSE yönergeleri ile multimedya işlenenleri için kullanılır.

## <a name="syntax"></a>Sözdizimi

> XMMWORD

## <a name="remarks"></a>Açıklamalar

`XMMWORD` aynı tür olarak temsil etmek üzere tasarlanmıştır [__m128](../../cpp/m128.md).

## <a name="example"></a>Örnek

```asm
    movdqa   xmm0, xmmword ptr [ebx]
```