---
title: auto_handle::operator = | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- auto_handle::operator=
- msclr.auto_handle.operator=
- msclr::auto_handle::operator=
- auto_handle.operator=
dev_langs:
- C++
helpviewer_keywords:
- auto_handle::operator=
ms.assetid: 503ca172-e766-4a78-af98-36fd48c931ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f41eff9659fd85b21b46560be4c1141152f748f1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103626"
---
# <a name="autohandleoperator"></a>auto_handle::operator=
Atama işleci.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
auto_handle<_element_type> % operator=(  
   auto_handle<_element_type> % _right  
);  
template<typename _other_type>  
auto_handle<_element_type> % operator=(  
   auto_handle<_other_type> % _right  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*_right*<br/>
`auto_handle` Geçerli atanacak `auto_handle`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli `auto_handle`, artık sahip olan `_right`.  
  
## <a name="example"></a>Örnek  
  
```  
// msl_auto_handle_op_assign.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
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
   auto_handle<ClassA> a;  
   auto_handle<ClassA> a2(gcnew ClassA( "first" ) );  
   a = a2; // assign from same type  
   a->PrintHello();  
  
   auto_handle<ClassB> b(gcnew ClassB( "second" ) );     
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
Hello from second B!  
in ClassA destructor: first  
Hello from second A!  
done  
in ClassA destructor: second  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Üst bilgi dosyası** \<msclr\auto_handle.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [auto_handle Members](../dotnet/auto-handle-members.md)