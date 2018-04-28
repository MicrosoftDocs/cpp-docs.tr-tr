---
title: XMMWORD | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: f8fd8e6c82a3275161e519eeead490473e8d64ab
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="xmmword"></a>XMMWORD
128-bit multimedya işlenenleri MMX ve SSE (XMM) yönergeleri ile birlikte kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
XMMWORD  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `XMMWORD` aynı türde temsil etmek üzere tasarlanmıştır [__m128](../../cpp/m128.md).  
  
## <a name="example"></a>Örnek  
  
```  
movdqa   xmm0, xmmword ptr [ebx]  
```