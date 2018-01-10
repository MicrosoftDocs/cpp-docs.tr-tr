---
title: MMWORD | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MMWORD
dev_langs: C++
helpviewer_keywords: MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bbe20f842a97186071431cd73e7de65fa8170bd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mmword"></a>MMWORD
64-bit multimedya işlenenleri MMX ve SSE (XMM) yönergeleri ile birlikte kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
MMWORD  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `MMWORD`bir türüdür.  MASM için eklenmekte olan MMWORD önce eşdeğer işlevsellik ile elde edildiğini:  
  
```  
mov mm0, qword ptr [ebx]  
```  
  
 Her iki yönerge 64-bit işlenen üzerinde çalışırken `QWORD` 64-bit işaretsiz tamsayı türü ve `MMWORD` bir 64-bit multimedya değerin türü.  
  
 `MMWORD`aynı türde temsil etmek üzere tasarlanmıştır [__m64](../../cpp/m64.md).  
  
## <a name="example"></a>Örnek  
  
```  
movq     mm0, mmword ptr [ebx]  
```