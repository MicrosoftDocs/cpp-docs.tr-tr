---
title: "Derleyici Uyarısı (Düzey 3) C4073 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4073
dev_langs: C++
helpviewer_keywords: C4073
ms.assetid: 50081a6e-6acd-45ff-8484-9b1ea926cc5c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e30c8439ed146658b3d1fcf258d3b13c37f3dd10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4073"></a>Derleyici Uyarısı (Düzey 3) C4073
Kitaplık başlatma alanına yerleştirir başlatıcıları  
  
 Üçüncü taraf kitaplığı geliştiriciler tarafından belirtilen kitaplığı başlatma alanı kullanmalıdır yalnızca [#pragma init_seg](../../preprocessor/init-seg.md). Aşağıdaki örnek C4073 oluşturur:  
  
```  
// C4073.cpp  
// compile with: /W3  
#pragma init_seg(lib)   // C4073  
  
// try this line to resolve the warning  
// #pragma init_seg(user)  
  
int main() {  
}  
```