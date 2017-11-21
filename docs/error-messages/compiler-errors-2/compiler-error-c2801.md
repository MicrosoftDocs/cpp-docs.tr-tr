---
title: "Derleyici Hatası C2801 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2801
dev_langs: C++
helpviewer_keywords: C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 41e7956ace6c54cd55a2ed9f68f18c867bc80ad9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2801"></a>Derleyici Hatası C2801
Statik olmayan üye 'işleci işleci' olmalıdır  
  
 Statik olmayan üye olarak yalnızca aşağıdaki işleçleri aşırı yüklenebilir:  
  
-   Atama`=`  
  
-   Sınıf üye erişimi`->`  
  
-   Alt simge oluşturma`[]`  
  
-   İşlev çağrısı`()`  
  
 Olası C2801 nedenler:  
  
-   Aşırı yüklenmiş işleci bir sınıf, yapı veya bileşim üyesi değil.  
  
-   Aşırı yüklenmiş işleci bildirilen `static`.  
  
-   Aşağıdaki örnek C2801 oluşturur:  
  
```  
// C2801.cpp  
// compile with: /c  
operator[]();   // C2801 not a member  
class A {  
   static operator->();   // C2801 static  
   operator()();   // OK  
};  
```