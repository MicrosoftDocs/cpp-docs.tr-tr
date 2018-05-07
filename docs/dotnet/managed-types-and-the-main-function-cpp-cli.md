---
title: Yönetilen türler ve main işlevi (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- main function, in managed applications
- managed code, main() function
ms.assetid: 9d0e9620-58c4-4dac-a0e1-ffeb95f80fa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6024f4b6e72fa997f816f7fee0b76778c5ebfc4f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
 [Yönetilen Türler (C++/CLI)](../dotnet/managed-types-cpp-cli.md)