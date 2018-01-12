---
title: "Nasıl yapılır: kullanıcı etkileşimli durumunu belirleme (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++, user interactive state
- user interactive state
ms.assetid: 9f52323e-38b8-4a41-9b1d-052012ad839b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a2cb3ffb8e0bfd8eba04555286894b6f1e58cfd7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-determine-the-user-interactive-state-ccli"></a>Nasıl yapılır: Kullanıcı Etkileşimli Durumunu Belirleme (C++/CLI)
Aşağıdaki kod örneğinde, kodu bir etkileşimli kullanıcı bağlamında çalışacak olup olmadığını belirlemek gösterilmiştir. Varsa <xref:System.Environment.UserInteractive%2A> kod hizmet işlemi olarak çalışıyordur veya gelen bir Web uygulamasının içinde bu durumda, kullanıcıyla etkileşim çalışmamalıdır sonra yanlış.  
  
## <a name="example"></a>Örnek  
  
```  
// user_interactive.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   if ( Environment::UserInteractive )  
      Console::WriteLine("User interactive");  
   else  
      Console::WriteLine("Noninteractive");  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows işlemleri (C + +/ CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)