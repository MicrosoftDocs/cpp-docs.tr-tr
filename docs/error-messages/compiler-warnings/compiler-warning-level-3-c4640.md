---
title: "Derleyici Uyarısı (Düzey 3) C4640 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4640
dev_langs:
- C++
helpviewer_keywords:
- C4640
ms.assetid: f76871f6-e436-4c35-9793-d2f22f7e1c7f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2510a74301486c26afcf7499b1f5920d84bab644
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4640"></a>Derleyici Uyarısı (Düzey 3) C4640
'Instance': yerel statik nesne yapımı iş parçacığı açısından güvenli değil  
  
 Bir statik bir nesnenin örneğine iş parçacığı içinde korumalı değil.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4640 oluşturur:  
  
```  
// C4640.cpp  
// compile with: /W3  
#pragma warning(default:4640)  
  
class X {  
public:  
   X() {  
   }  
};  
  
void f() {  
   static X aX;   // C4640  
}  
  
int main() {  
   f();  
}  
```