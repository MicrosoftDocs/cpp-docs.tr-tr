---
title: "Nasıl yapılır: yerel tür içinde değer türüne başvuruyu tutma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- value type reference in native type
- reference to value type in native type
ms.assetid: 1eabf8be-7d4f-4339-9027-48d5c4244483
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 17730011c8e13416ed84f7731fdf5469fc918c64
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-hold-reference-to-value-type-in-native-type"></a>Nasıl yapılır: Yerel Tür İçinde Değer Türüne Başvuruyu Tutma
Kullanım `gcroot` yerel tür içinde değer türüne bir başvuru tutmak için paketlenmiş türü.  
  
## <a name="example"></a>Örnek  
  
```  
// reference_to_value_in_native.cpp  
// compile with: /clr  
#using <mscorlib.dll>  
#include <vcclr.h>   
  
using namespace System;   
  
public value struct V {  
   String ^str;  
};  
  
class Native {  
public:  
   gcroot< V^ > v_handle;  
};  
  
int main() {  
   Native native;  
   V v;  
   native.v_handle = v;  
   native.v_handle->str = "Hello";  
   Console::WriteLine("String in V: {0}", native.v_handle->str);  
}  
```  
  
```Output  
String in V: Hello  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ birlikte çalışması (örtük PInvoke) kullanarak](../dotnet/using-cpp-interop-implicit-pinvoke.md)