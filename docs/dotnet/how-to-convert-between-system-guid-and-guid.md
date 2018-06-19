---
title: 'Nasıl yapılır: System::Guid ve GUID arasında dönüştürme | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- System::GUID
- GUID, converting to System::GUID
- System::GUID, converting to GUID
ms.assetid: 022c934c-3395-4f04-b498-85ad9bf8c646
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7986fb615f8d57de63a1f50a8ca844e208e5907e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127449"
---
# <a name="how-to-convert-between-systemguid-and-guid"></a>Nasıl yapılır: System::Guid ve GUID Arasında Dönüştürme
Aşağıdaki kod örneği arasında dönüştürme gösterilmektedir bir <xref:System.Guid> ve `_GUID`.  
  
## <a name="example"></a>Örnek  
  
```  
// convert_guids.cpp  
// compile with: /clr  
#include <windows.h>  
#include <stdio.h>  
  
using namespace System;  
  
Guid FromGUID( _GUID& guid ) {  
   return Guid( guid.Data1, guid.Data2, guid.Data3,   
                guid.Data4[ 0 ], guid.Data4[ 1 ],   
                guid.Data4[ 2 ], guid.Data4[ 3 ],   
                guid.Data4[ 4 ], guid.Data4[ 5 ],   
                guid.Data4[ 6 ], guid.Data4[ 7 ] );  
}  
  
_GUID ToGUID( Guid& guid ) {  
   array<Byte>^ guidData = guid.ToByteArray();  
   pin_ptr<Byte> data = &(guidData[ 0 ]);  
  
   return *(_GUID *)data;  
}  
  
int main() {  
   _GUID ng = {0x11111111,0x2222,0x3333,0x44,0x55,0x55,0x55,0x55,0x55,0x55,0x55};  
   Guid mg;  
  
   Console::WriteLine( (mg = FromGUID( ng )).ToString() );  
   _GUID ng2 = ToGUID( mg );  
  
   printf_s(  "%x-%x-%x-", ng2.Data1, ng2.Data2, ng2.Data3 );  
   for (int i = 0 ; i < 8 ; i++) {  
      if (i == 2)  
         printf_s("-");  
      printf_s("%x", ng2.Data4[i]);  
   }  
   printf_s("\n");  
}  
```  
  
```Output  
11111111-2222-3333-4455-555555555555  
11111111-2222-3333-4455-555555555555  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)