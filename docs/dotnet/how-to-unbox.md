---
title: "Nasıl yapılır: Unbox | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: unboxing
ms.assetid: 75794696-9275-47bf-9a7d-5abe6585ab91
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 27c778590b99c52cb8f8c0104af6f62a0a6898d5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-unbox"></a>Nasıl yapılır: Açma
Unbox ve değeri değiştirmek gösterilmiştir.  
  
## <a name="example"></a>Örnek  
  
```  
// vcmcppv2_unboxing.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   int ^ i = gcnew int(13);  
   int j;  
   Console::WriteLine(*i);   // unboxing  
   *i = 14;   // unboxing and assignment  
   Console::WriteLine(*i);  
   j = safe_cast<int>(i);   // unboxing and assignment  
   Console::WriteLine(j);  
}  
```  
  
```Output  
13  
14  
14  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kutulama](../windows/boxing-cpp-component-extensions.md)