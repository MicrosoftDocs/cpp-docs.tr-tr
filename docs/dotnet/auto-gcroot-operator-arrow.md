---
title: auto_gcroot::operator -&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- auto_gcroot.operator->
- msclr::auto_gcroot::operator->
- auto_gcroot::operator->
- msclr.auto_gcroot.operator->
dev_langs:
- C++
helpviewer_keywords:
- operator->
ms.assetid: 2c77bc53-5f77-4544-9485-c950cd8e0bb1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 26157325e20fa834ed175b849d51c3858546b7ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105328"
---
# <a name="autogcrootoperator-gt"></a>auto_gcroot::operator-&gt;
Üye erişimi işleci.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_element_type operator->() const;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Tarafından Sarmalanan nesne `auto_gcroot`.  
  
## <a name="example"></a>Örnek  
  
```  
// msl_auto_gcroot_op_arrow.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:     
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {}  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
  
   int m_i;  
};  
  
int main() {  
   auto_gcroot<ClassA^> a( gcnew ClassA( "first" ) );  
   a->PrintHello();  
  
   a->m_i = 5;  
   Console::WriteLine( "a->m_i = {0}", a->m_i );  
}  
```  
  
```Output  
Hello from first A!  
a->m_i = 5  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [auto_gcroot üyeleri](../dotnet/auto-gcroot-members.md)   
 [auto_gcroot::get](../dotnet/auto-gcroot-get.md)