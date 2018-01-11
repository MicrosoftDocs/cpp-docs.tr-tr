---
title: "Derleyici Hatası C3351 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3351
dev_langs: C++
helpviewer_keywords: C3351
ms.assetid: c021bbbe-1067-4f51-af4f-940d2b792eb5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1d848ae18c4610b9f2078ce54532c392f489154f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3351"></a>Derleyici Hatası C3351
'object': temsilci Oluşturucu: adresini statik üye işlevi veya genel işlevi ikinci bağımsız değişkeni olmalıdır.  
  
 Bildirilen bir işlev adresi derleyici beklenen `static`.  
  
 Aşağıdaki örnek C3351 oluşturur:  
  
```  
// C3351a.cpp  
// compile with: /clr  
delegate int D(int, int);  
  
ref class C {  
public:  
   int mf(int, int) {  
      return 1;  
   }  
  
   static int mf2(int, int) {  
      return 1;  
   }  
};  
  
int main() {  
   System::Delegate ^pD = gcnew D(nullptr, &C::mf);   // C3351  
   System::Delegate ^pD2 = gcnew D(&C::mf2);  
}  
```  
