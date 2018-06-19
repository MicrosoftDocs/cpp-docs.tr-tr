---
title: 'Nasıl yapılır: kullanıcı etkileşimli durumunu belirleme (C + +/ CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, user interactive state
- user interactive state
ms.assetid: 9f52323e-38b8-4a41-9b1d-052012ad839b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4649a6e7ce4833b55f38e636b87bb53f646e85cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127311"
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