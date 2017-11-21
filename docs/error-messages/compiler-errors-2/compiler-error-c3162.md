---
title: "Derleyici Hatası C3162 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3162
dev_langs: C++
helpviewer_keywords: C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8bfde260ef0efe58ed70469a80a8bf7316eefa46
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3162"></a>Derleyici Hatası C3162
'type': yıkıcı olan bir başvuru türü statik veri üyesi 'member' türü olarak kullanılamaz  
  
 Ortak dil çalışma zamanı sınıfı statik üye işlevi de içerdiğinde, bir kullanıcı tarafından tanımlanan yıkıcı çalıştırmak ne zaman bilemezsiniz.  
  
 Nesne açıkça silinmedikçe yıkıcı asla çalışmaz.  
  
 Daha fazla bilgi için bkz:  
  
-   [/ CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Genel Visual C++ 64-bit geçiş sorunları](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3162 oluşturur.  
  
```  
// C3162.cpp  
// compile with: /clr /c  
ref struct A {  
   ~A() { System::Console::WriteLine("in destructor"); }  
   static A i;   // C3162  
   static A^ a = gcnew A;   // OK  
};  
  
int main() {  
   A ^ a = gcnew A;  
   delete a;  
}  
```