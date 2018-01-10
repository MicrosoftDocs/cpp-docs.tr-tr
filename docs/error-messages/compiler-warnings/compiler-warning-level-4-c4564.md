---
title: "Derleyici Uyarısı (düzey 4) C4564 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4564
dev_langs: C++
helpviewer_keywords: C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25f9f8755acafd71a9ac75a68f601660b781746a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4564"></a>Derleyici Uyarısı (düzey 4) C4564
desteklenmeyen varsayılan parametre 'parametresi' yöntemi 'sınıfı' sınıfının ' yöntemi' tanımlar  
  
 Derleyici bir veya daha fazla parametre varsayılan değerlerine sahip olan bir yöntem algıladı. Yöntem çağrıldığında parametreler için varsayılan değerler göz ardı edilir; açıkça bu parametrelerin değerlerini belirtin. Bu parametreler için değerler açıkça belirtmezseniz, C++ derleyicisi bir hata oluşturur.  
  
 Visual Basic ile oluşturulan aşağıdaki .dll yöntemi bağımsız değişkenler üzerinde varsayılan parametreleri sağlayan:  
  
```  
' C4564.vb  
' compile with: vbc /t:library C4564.vb  
Public class TestClass  
   Public Sub MyMethod (a as Integer, _  
                        Optional c as Integer=1)  
   End Sub  
End class  
```  
  
 Ve Visual Basic ile oluşturulan .dll öğesini kullanan aşağıdaki C++ örnek,  
  
```  
// C4564.cpp  
// compile with: /clr /W4 /WX  
#using <C4564.dll>  
  
int main() {  
   TestClass ^ myx = gcnew TestClass();   // C4564  
   myx->MyMethod(9);  
   // try the following line instead, to avoid an error  
   // myx->MyMethod(9, 1);  
}  
```