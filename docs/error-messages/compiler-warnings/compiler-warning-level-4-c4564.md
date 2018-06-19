---
title: Derleyici Uyarısı (düzey 4) C4564 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4564
dev_langs:
- C++
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f0cf68eb75d420a0d23c04687d4f9492910b53f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293679"
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