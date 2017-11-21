---
title: "Derleyici Hatası C2521 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2521
dev_langs: C++
helpviewer_keywords: C2521
ms.assetid: 6042821b-e345-4a54-a7e9-a2c9019ea016
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: debe1e52637ea705996d2f787792b3691de34e23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2521"></a>Derleyici Hatası C2521
işlev herhangi bir bağımsız değişken almaz  
  
 Bir yıkıcı veya sonlandırıcıyı bağımsız değişkenleri kullanma girişiminde bulunuldu.  
  
 Daha fazla bilgi için bkz: [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2521 oluşturur.  
  
```  
// C2521.cpp  
// compile with: /clr  
ref class R {  
protected:  
   !R() {}  
  
public:  
   void CleanUp() {  
      this->!R(4);   // C2521  
      this->!R();   // OK  
   }  
};  
  
int main() {  
   R^ r = gcnew R();  
   r->CleanUp();  
}  
```