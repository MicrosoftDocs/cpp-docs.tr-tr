---
title: "Nasıl yapılır: yerel makine adını alma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- computer name, retrieving
- machine name, retrieving
- computer name
ms.assetid: 6c7acb9a-3f9b-43b2-a756-bd4fb859e697
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 30ac988240e32351a8659b5145bd621bc490aaba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-retrieve-the-local-machine-name-ccli"></a>Nasıl yapılır: Yerel Makine Adını Alma (C++/CLI)
Aşağıdaki kod örneğinde yerel makine adını alma gösterir (gibi bilgisayar adını, bir ağ üzerinde görünür). Bunu alarak gerçekleştirmek <xref:System.Environment.MachineName%2A> tanımlanan dize <xref:System.Environment> ad alanı.  
  
## <a name="example"></a>Örnek  
  
```  
// machine_name.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nMachineName: {0}", Environment::MachineName);  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows işlemleri (C + +/ CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)