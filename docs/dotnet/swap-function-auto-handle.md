---
title: "swap işlevi (auto_handle) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::swap
- msclr.swap
dev_langs: C++
helpviewer_keywords: swap function
ms.assetid: 7dd91b5c-f0de-4634-a2e2-642626706e27
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dfa449e16e6f2f28a857150220b4b710f7a75bc9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="swap-function-autohandle"></a>swap İşlevi (auto_handle)
Değiştirir biri arasında nesneleri `auto_handle` ve başka bir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename _element_type>  
void swap(  
   auto_handle<_element_type> % _left,  
   auto_handle<_element_type> % _right  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `_left`  
 Bir `auto_handle`.  
  
 `_right`  
 Başka bir `auto_handle`.  
  
## <a name="example"></a>Örnek  
  
```  
// msl_swap_auto_handle.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_handle<String> s1 = "string one";  
   auto_handle<String> s2 = "string two";  
  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
   swap( s1, s2 );  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
}  
```  
  
```Output  
s1 = 'string one', s2 = 'string two'  
s1 = 'string two', s2 = 'string one'  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası** \<msclr\auto_handle.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [auto_handle](../dotnet/auto-handle.md)   
 [auto_handle::Swap](../dotnet/auto-handle-swap.md)