---
title: "Nasıl yapılır: Dönüştür char * dizesini System::Byte dizisine | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- examples [C++], strings
- arrays [C++], character
- character arrays, converting to System::Byte arrays
- examples [C++], arrays
ms.assetid: de9bc4eb-773c-4796-a496-9b90ca986503
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4d0750884c9d7d5bfb1b9566b26cdce5c8c1962c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-convert-char--string-to-systembyte-array"></a>Nasıl yapılır: char * Dizesini System::Byte Dizisine Dönüştürme
Dönüştürülecek en verimli şekilde bir `char *` dizesinden bir <xref:System.Byte> dizi kullanmaktır <xref:System.Runtime.InteropServices.Marshal> sınıfı.  
  
## <a name="example"></a>Örnek  
  
```  
// convert_native_string_to_Byte_array.cpp  
// compile with: /clr  
#include <string.h>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
int main() {  
   char buf[] = "Native String";  
   int len = strlen(buf);  
  
   array< Byte >^ byteArray = gcnew array< Byte >(len + 2);  
  
   // convert native pointer to System::IntPtr with C-Style cast  
   Marshal::Copy((IntPtr)buf,byteArray, 0, len);  
  
   for ( int i = byteArray->GetLowerBound(0); i <= byteArray->GetUpperBound(0); i++ ) {  
      char dc =  *(Byte^)   byteArray->GetValue(i);  
      Console::Write((Char)dc);  
   }  
  
   Console::WriteLine();  
}  
```  
  
```  
Native String  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ birlikte çalışması (örtük PInvoke) kullanarak](../dotnet/using-cpp-interop-implicit-pinvoke.md)