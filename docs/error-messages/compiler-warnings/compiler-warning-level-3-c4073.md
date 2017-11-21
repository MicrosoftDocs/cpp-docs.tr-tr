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
ms.openlocfilehash: f9c53b9d5a5efb1b60c680543a2072bc4f148330
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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