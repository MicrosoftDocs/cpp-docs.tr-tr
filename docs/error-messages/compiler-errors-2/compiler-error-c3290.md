---
title: "Derleyici Hatası C3290 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3290
dev_langs: C++
helpviewer_keywords: C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c3dceac5102936bbb86f5c103fb0c9240f5ee2d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3290"></a>Derleyici Hatası C3290
'type': başvuru türü bir önemsiz özelliğine sahip olamaz  
  
 Bir özellik yanlış bildirildi. Önemsiz bir özelliği bildirme, derleyici özelliği güncelleştirileceğini belirten bir değişken oluşturur ve izleme başvurusu olması olası değil değişken bir sınıf.  
  
 Bkz: [özelliği](../../windows/property-cpp-component-extensions.md) ve [izleme başvurusu işleci](../../windows/tracking-reference-operator-cpp-component-extensions.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3290 oluşturur.  
  
```  
// C3290.cpp  
// compile with: /clr /c  
ref struct R {};  
  
ref struct X {  
   R^ mr;  
  
   property R % y;   // C3290  
   property R ^ x;   // OK  
  
   // OK  
   property R% prop {  
      R% get() {   
         return *mr;   
      }  
  
      void set(R%) {}  
   }  
};  
  
int main() {  
   X x;  
   R% xp = x.prop;  
}  
```