---
title: "Nasıl yapılır: kapatmanın başlayıp başlamadığını belirleme (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- .NET Framework, shutdown
- shutdown
- termination
- applications [C++], shutdown
ms.assetid: a8d39731-dea8-4f0a-96b7-2a5de09b21d7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7f4575f212752a43df2b130fbde9aa7264186d6f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-determine-if-shutdown-has-started-ccli"></a>Nasıl yapılır: Kapatmanın Başlayıp Başlamadığını Belirleme (C++/CLI)
Aşağıdaki kod örneği, uygulama veya .NET Framework şu anda sonlandırıyor olup olmadığını belirlemek gösterilmiştir. Bu, kapatma sırasında bu yapıları sistem tarafından sonlandırılır ve güvenilir bir şekilde kullanılamaz olduğundan, .NET Framework'teki statik öğeler erişmek için kullanışlıdır. Denetleyerek <xref:System.Environment.HasShutdownStarted%2A> özelliği ilk olarak, bu öğeleri erişilmemesi olası hatalarını önlemek.  
  
## <a name="example"></a>Örnek  
  
```  
// check_shutdown.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   if (Environment::HasShutdownStarted)  
      Console::WriteLine("Shutting down.");  
   else  
      Console::WriteLine("Not shutting down.");  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows işlemleri (C + +/ CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)