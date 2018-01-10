---
title: "Derleyici Hatası C3737 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3737
dev_langs: C++
helpviewer_keywords: C3737
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0fc7a1314462c7a62bdece0b20c959e34ad39fb1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3737"></a>Derleyici Hatası C3737
'temsilci': bir temsilci açık bir çağrı kuralı olmayabilir  
  
 Belirtemeyeceğiniz [çağırma](../../cpp/calling-conventions.md) için bir `delegate`.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3737 oluşturur:  
  
```  
// C3737a.cpp  
// compile with: /clr  
delegate void __stdcall MyFunc();   // C3737  
// Try the following line instead.  
// delegate void MyFunc();  
  
int main() {  
}  
```  
