---
title: "Nasıl yapılır: geçerli kullanıcı adını alma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- current user names
- user names, retrieving
- UserName string
ms.assetid: 91679571-d029-41f5-b657-1460c81c608a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c4738c829f346126dfed7990c50186a7c267df1a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-retrieve-the-current-username-ccli"></a>Nasıl yapılır: Geçerli Kullanıcı Adını Alma (C++/CLI)
Aşağıdaki kod örneğinde geçerli kullanıcı adını (Windows'ta oturum açmış kullanıcı adı) alınmasını gösterilmektedir. Adı depolanan <xref:System.Environment.UserName%2A> tanımlanan dize <xref:System.Environment> ad alanı.  
  
## <a name="example"></a>Örnek  
  
```  
// username.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nCurrent user: {0}", Environment::UserName);  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows işlemleri (C + +/ CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)