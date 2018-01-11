---
title: auto_gcroot::Release | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot::release
- auto_gcroot::release
- auto_gcroot.release
- msclr.auto_gcroot.release
dev_langs: C++
helpviewer_keywords: release method
ms.assetid: 40b253f0-154e-4d79-80a4-ff13199c3ff0
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ea93fa37ab895bd1b96c4955a3edc8fd773f4a86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="autogcrootrelease"></a>auto_gcroot::release
Nesneden serbest `auto_gcroot` yönetimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_element_type release();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yayımlanan nesnesi.  
  
## <a name="example"></a>Örnek  
  
```  
// msl_auto_gcroot_release.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {  
      Console::WriteLine( "ClassA constructor: " + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "ClassA destructor: " + m_s );  
   }  
  
   void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );     
   }  
};  
  
int main()  
{  
   ClassA^ a;  
  
   // create a new scope:  
   {  
      auto_gcroot<ClassA^> agc1 = gcnew ClassA( "first" );  
      auto_gcroot<ClassA^> agc2 = gcnew ClassA( "second" );  
      a = agc1.release();  
   }  
   // agc1 and agc2 go out of scope here  
  
   a->PrintHello();  
  
   Console::WriteLine( "done" );  
}  
```  
  
```Output  
ClassA constructor: first  
ClassA constructor: second  
ClassA destructor: second  
Hello from first A!  
done  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [auto_gcroot üyeleri](../dotnet/auto-gcroot-members.md)   
 [auto_gcroot::~auto_gcroot](../dotnet/auto-gcroot-tilde-auto-gcroot.md)