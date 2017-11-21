---
title: "Derleyici Hatası C2761 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2761
dev_langs: C++
helpviewer_keywords: C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7670c3fa67579c218024dfd3f1f585ad57cf37e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2761"></a>Derleyici Hatası C2761
'function': üye fonksiyonu yeniden bildirimi izin verilmiyor  
  
 Üye işlevi redeclare olamaz. Tanımlayabilirsiniz, ancak redeclare değil.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2761 oluşturur.  
  
```  
// C2761.cpp  
class a {  
   int t;  
   void test();  
};  
  
void a::a;     // C2761  
void a::test;  // C2761  
  
```  
  
## <a name="example"></a>Örnek  
 Bir sınıf veya yapı statik olmayan üye tanımlanamaz.  Aşağıdaki örnek C2761 oluşturur.  
  
```  
// C2761_b.cpp  
// compile with: /c  
struct C {  
   int s;  
   static int t;  
};  
  
int C::s;   // C2761  
int C::t;   // OK  
```