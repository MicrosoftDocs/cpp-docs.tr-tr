---
title: "Derleyici Hatası C2871 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2871
dev_langs: C++
helpviewer_keywords: C2871
ms.assetid: 44aeb84d-61f0-45e0-8dad-22a3cd46b7f8
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0003f04a32ff017234607a90162465549092a013
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2871"></a>Derleyici Hatası C2871
'name': Bu ada sahip bir ad alanı yok  
  
Bir ad değil bir tanımlayıcı geçirdiğinizde bu hata oluşur bir [kullanarak](../../cpp/namespaces-cpp.md#using_directives) yönergesi.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C2871 oluşturur:  
  
```cpp  
// C2871.cpp  
// compile with: /c
namespace a {
   int fn(int i) { return i; }
} 
namespace b { 
   using namespace d;   // C2871 because d is not a namespace  
   using namespace a;   // OK
}  
```