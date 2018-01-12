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
ms.workload: cplusplus
ms.openlocfilehash: 8c3526eecbe125a1a76b637734fecc72785556b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3162"></a>Derleyici Hatası C3162
'type': yıkıcı olan bir başvuru türü statik veri üyesi 'member' türü olarak kullanılamaz  
  
 Ortak dil çalışma zamanı sınıfı statik üye işlevi de içerdiğinde, bir kullanıcı tarafından tanımlanan yıkıcı çalıştırmak ne zaman bilemezsiniz.  
  
 Nesne açıkça silinmedikçe yıkıcı asla çalışmaz.  
  
 Daha fazla bilgi için bkz:  
  
-   [/ CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Genel Visual C++ 64 Bit Geçiş Sorunları](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
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