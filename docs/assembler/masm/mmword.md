---
title: MMWORD | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: e97b1e58116d633519b1a780928e05862ac1771d
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32054786"
---
# <a name="mmword"></a>MMWORD
64-bit multimedya işlenenleri MMX ve SSE (XMM) yönergeleri ile birlikte kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
MMWORD  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `MMWORD` bir türüdür.  MASM için eklenmekte olan MMWORD önce eşdeğer işlevsellik ile elde edildiğini:  
  
```  
mov mm0, qword ptr [ebx]  
```  
  
 Her iki yönerge 64-bit işlenen üzerinde çalışırken `QWORD` 64-bit işaretsiz tamsayı türü ve `MMWORD` bir 64-bit multimedya değerin türü.  
  
 `MMWORD` aynı türde temsil etmek üzere tasarlanmıştır [__m64](../../cpp/m64.md).  
  
## <a name="example"></a>Örnek  
  
```  
movq     mm0, mmword ptr [ebx]  
```