---
title: "Yönetilen türler ve main işlevi (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- main function, in managed applications
- managed code, main() function
ms.assetid: 9d0e9620-58c4-4dac-a0e1-ffeb95f80fa5
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1a6d8b330108c5fba953567493551894036a7a5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="managed-types-and-the-main-function-ccli"></a>Yönetilen Türler ve main İşlevi (C++/CLI)
Bir uygulama kullanarak yazarken **/CLR**, bağımsız değişkenleri **main()** işlevi, bir yönetilen türü olamaz.  
  
 Uygun bir imza örneğidir:  
  
```  
// managed_types_and_main.cpp  
// compile with: /clr  
int main(int, char*[], char*[]) {}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen türler (C + +/ CLI)](../dotnet/managed-types-cpp-cli.md)