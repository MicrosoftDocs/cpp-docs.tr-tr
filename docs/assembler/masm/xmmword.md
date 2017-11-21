---
title: XMMWORD | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: XMMWORD
dev_langs: C++
helpviewer_keywords: XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 34bed9288320a5a8eadca88c67da72dd6ee2094d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="xmmword"></a>XMMWORD
128-bit multimedya işlenenleri MMX ve SSE (XMM) yönergeleri ile birlikte kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
XMMWORD  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `XMMWORD`aynı türde temsil etmek üzere tasarlanmıştır [__m128](../../cpp/m128.md).  
  
## <a name="example"></a>Örnek  
  
```  
movdqa   xmm0, xmmword ptr [ebx]  
```