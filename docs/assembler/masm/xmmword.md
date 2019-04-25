---
title: XMMWORD
ms.date: 08/30/2018
f1_keywords:
- XMMWORD
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
ms.openlocfilehash: 59d1ba71260ed08b761c332e887cf27517762303
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210111"
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