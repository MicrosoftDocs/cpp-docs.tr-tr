---
title: "Derleyici Uyarısı (düzey 1) C4944 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4944
dev_langs: C++
helpviewer_keywords: C4944
ms.assetid: e2905eb1-2e3b-4fab-a48b-c0cae0fd997f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 896a84df35d3fd71fae8a519146eee1db5a004c7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4944"></a>Derleyici Uyarısı (düzey 1) C4944
'simgesi': 'assembly1' simgesini alınamıyor: 'simgesi' geçerli kapsamda zaten mevcut olduğundan  
  
 Bir simge bir kaynak kod dosyasında tanımlanan ve ardından bir #using başvurulan simgenin tanımlanmış derleme. Derlemesindeki sembolü göz ardı edilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir bileşen ClassA adlı bir türü ile oluşturur.  
  
```  
// C4944.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler C4944 oluşturur.  
  
```  
// C4944b.cpp  
// compile with: /clr /W1  
class ClassA {  
public:  
   int u;  
};  
  
#using "C4944.dll"   // C4944 ClassA also defined C4944.dll  
  
int main() {  
   ClassA * x = new ClassA();  
   x->u = 9;  
   System::Console::WriteLine(x->u);  
}  
```