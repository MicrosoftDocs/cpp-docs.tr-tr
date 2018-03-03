---
title: auto_gcroot::operator = | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- auto_gcroot.operator=
- msclr::auto_gcroot::operator=
- msclr.auto_gcroot.operator=
- auto_gcroot::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator=
ms.assetid: 99eba5eb-5a2c-4edf-b3d5-c903f818233d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b924c3596d1f381d42c711e42e93fd9ae6d037e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="autogcrootoperator"></a>auto_gcroot::operator=
Atama işleci.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
auto_gcroot<_element_type> & operator=(  
   _element_type _right  
);  
auto_gcroot<_element_type> & operator=(  
   auto_gcroot<_element_type> & _right  
);  
template<typename _other_type>  
auto_gcroot<_element_type> & operator=(  
   auto_gcroot<_other_type> & _right  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `_right`  
 Nesne veya `auto_gcroot` geçerli atanacak `auto_gcroot`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli `auto_gcroot`, şimdi sahibi olan `_right`.  
  
## <a name="example"></a>Örnek  
  
```  
// msl_auto_gcroot_operator_equals.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:  
   String^ m_s;     
public:  
   ClassA(String^ s) : m_s(s) {  
      Console::WriteLine( "in ClassA constructor: " + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "in ClassA destructor: " + m_s );  
   }  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
ref class ClassB : ClassA {  
public:     
   ClassB( String^ s ) : ClassA( s ) {}  
   virtual void PrintHello() new {  
      Console::WriteLine( "Hello from {0} B!", m_s );  
   }  
};  
  
int main()  
{  
   auto_gcroot<ClassA^> a;  
   auto_gcroot<ClassA^> a2(gcnew ClassA( "first" ) );  
   a = a2; // assign from same type  
   a->PrintHello();  
  
   ClassA^ ha = gcnew ClassA( "second" );  
   a = ha; // assign from raw handle  
  
   auto_gcroot<ClassB^> b(gcnew ClassB( "third" ) );     
   b->PrintHello();  
   a = b; // assign from derived type     
   a->PrintHello();  
  
   Console::WriteLine("done");  
}  
```  
  
```Output  
in ClassA constructor: first  
Hello from first A!  
in ClassA constructor: second  
in ClassA destructor: first  
in ClassA constructor: third  
Hello from third B!  
in ClassA destructor: second  
Hello from third A!  
done  
in ClassA destructor: third  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [auto_gcroot üyeleri](../dotnet/auto-gcroot-members.md)   
 [auto_gcroot::attach](../dotnet/auto-gcroot-attach.md)