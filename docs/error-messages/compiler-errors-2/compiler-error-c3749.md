---
title: "Derleyici Hatası C3749 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3749
dev_langs: C++
helpviewer_keywords: C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 49c231ed1337b683e501dd145055775867f6e2fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3749"></a>Derleyici Hatası C3749
'öznitelik': özel bir öznitelik bir işlev içinde kullanılamaz.  
  
 Özel bir öznitelik, bir işlev içinde kullanılamaz. Özel öznitelikler hakkında daha fazla bilgi için Ek Yardım konusuna [özniteliği](../../windows/attribute.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3749 oluşturur:  
  
```  
// C3749a.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
public ref struct ABC : public Attribute {  
   ABC() {}  
};  
  
void f1() { [ABC]; };  // C3749  
```  
