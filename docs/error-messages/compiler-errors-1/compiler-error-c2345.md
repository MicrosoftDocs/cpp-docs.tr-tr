---
title: "Derleyici Hatası C2345 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2345
dev_langs: C++
helpviewer_keywords: C2345
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 372012b970ae277f3bb6854224bf4e432167abb3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2345"></a>Derleyici Hatası C2345
align(Value): Geçersiz hizalama değeri  
  
 Bir değere geçirilen [Hizala](../../cpp/align-cpp.md) izin verilen aralığın dışında olan anahtar sözcük.  
  
 Aşağıdaki kod C2345 oluşturur  
  
```  
// C2345.cpp  
// compile with: /c  
__declspec(align(0)) int a;   // C2345  
__declspec(align(1)) int a;   // OK  
```