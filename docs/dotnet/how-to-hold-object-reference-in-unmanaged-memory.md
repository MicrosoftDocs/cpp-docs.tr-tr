---
title: "Nasıl yapılır: yönetilmeyen bellekte nesne başvurusunu tutma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- object references, in native functions
- objects [C++], reference in native functions
- references, to objects in native functions
- gcroot keyword [C++], object reference in native function
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2d4f5a54d71a49d76b1fbc2ba31a0ffe42738b92
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-hold-object-reference-in-unmanaged-memory"></a>Nasıl yapılır: Yönetilmeyen Bellekte Nesne Başvurusunu Tutma
Saran gcroot.h kullanabilirsiniz <xref:System.Runtime.InteropServices.GCHandle>, yönetilmeyen bellekte bir CLR nesnesi başvurusu tutmak için. Alternatif olarak, kullanabileceğiniz `GCHandle` doğrudan.  
  
## <a name="example"></a>Örnek  
  
```  
// hold_object_reference.cpp  
// compile with: /clr  
#include "gcroot.h"  
using namespace System;  
  
#pragma managed  
class StringWrapper {  
  
private:  
   gcroot<String ^ > x;  
  
public:  
   StringWrapper() {  
      String ^ str = gcnew String("ManagedString");  
      x = str;  
   }  
  
   void PrintString() {  
      String ^ targetStr = x;  
      Console::WriteLine("StringWrapper::x == {0}", targetStr);  
   }  
};  
#pragma unmanaged  
int main() {  
   StringWrapper s;  
   s.PrintString();  
}  
```  
  
```Output  
StringWrapper::x == ManagedString  
```  
  
## <a name="example"></a>Örnek  
 `GCHandle`bir yönetilen nesne başvurusunu yönetilmeyen bellekte tutmak için bir yol sağlar.  Kullandığınız <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> yönetilen bir nesne için donuk bir tutamaç oluşturmak için yöntemi ve <xref:System.Runtime.InteropServices.GCHandle.Free%2A> bunu serbest bırakmak için. Ayrıca, <xref:System.Runtime.InteropServices.GCHandle.Target%2A> yöntemi, yönetilen kod işleyiciyi nesne başvurusu geri almak olanak sağlar.  
  
```  
// hold_object_reference_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
class StringWrapper {  
   IntPtr m_handle;  
public:  
   StringWrapper() {  
      String ^ str = gcnew String("ManagedString");  
      m_handle = static_cast<IntPtr>(GCHandle::Alloc(str));  
   }  
   ~StringWrapper() {  
      static_cast<GCHandle>(m_handle).Free();  
   }  
  
   void PrintString() {  
      String ^ targetStr = safe_cast< String ^ >(static_cast<GCHandle>(m_handle).Target);  
      Console::WriteLine("StringWrapper::m_handle == {0}", targetStr);  
   }  
};  
  
#pragma unmanaged  
int main() {  
   StringWrapper s;   
   s.PrintString();  
}  
```  
  
```Output  
StringWrapper::m_handle == ManagedString  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ birlikte çalışması (örtük PInvoke) kullanarak](../dotnet/using-cpp-interop-implicit-pinvoke.md)