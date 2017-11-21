---
title: "Standart dönüştürmeler ve örtük kutulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: boxing, implicit
ms.assetid: 33f7fc7d-5674-44a2-a859-0e6a04fae519
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 69e95168ce68200d24415302f7c87ce63d3858c8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="standard-conversions-and-implicit-boxing"></a>Standart Dönüştürmeler ve Örtük Kutulama
Standart dönüştürme kutulama gerektiren dönüştürme derleyici tarafından seçilir.  
  
## <a name="example"></a>Örnek  
  
```  
// clr_implicit_boxing_Std_conversion.cpp  
// compile with: /clr  
int f3(int ^ i) {   // requires boxing  
   return 1;  
}  
  
int f3(char c) {   // no boxing required, standard conversion  
   return 2;  
}  
  
int main() {  
   int i = 5;  
   System::Console::WriteLine(f3(i));  
}  
```  
  
```Output  
2  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kutulama](../windows/boxing-cpp-component-extensions.md)