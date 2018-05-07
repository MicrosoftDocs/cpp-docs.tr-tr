---
title: 'Nasıl yapılır: C# tarafından kullanılması için yerel sınıfı sarmalama | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- native code [C++], Visual C# and
- classes [C++], Visual C# and
ms.assetid: 988819ae-cc6a-4453-8ff5-be369210d962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d12f922e6f20499aa5a231be244e62a826cb6aaf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-wrap-native-class-for-use-by-c"></a>Nasıl yapılır: C# Tarafından Kullanılması için Yerel Sınıfı Sarmalama
Bu örnek, C# veya diğer .NET dilinde yazılan kod tarafından kullanılabilecek şekilde yerel C++ sınıfı sarmalama gösterilmektedir.  
  
## <a name="example"></a>Örnek  
  
```  
// wrap_native_class_for_mgd_consumption.cpp  
// compile with: /clr /LD  
#include <windows.h>  
#include <vcclr.h>  
#using <System.dll>  
  
using namespace System;  
  
class UnmanagedClass {  
public:  
   LPCWSTR GetPropertyA() { return 0; }  
   void MethodB( LPCWSTR ) {}  
};  
  
public ref class ManagedClass {  
public:  
   // Allocate the native object on the C++ Heap via a constructor  
   ManagedClass() : m_Impl( new UnmanagedClass ) {}  
  
   // Deallocate the native object on a destructor  
   ~ManagedClass() {  
      delete m_Impl;  
   }  
  
protected:  
   // Deallocate the native object on the finalizer just in case no destructor is called  
   !ManagedClass() {  
      delete m_Impl;  
   }  
  
public:  
   property String ^  get_PropertyA {  
      String ^ get() {  
         return gcnew String( m_Impl->GetPropertyA());  
      }  
   }  
  
   void MethodB( String ^ theString ) {  
      pin_ptr<const WCHAR> str = PtrToStringChars(theString);  
      m_Impl->MethodB(str);  
   }  
  
private:  
   UnmanagedClass * m_Impl;  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)