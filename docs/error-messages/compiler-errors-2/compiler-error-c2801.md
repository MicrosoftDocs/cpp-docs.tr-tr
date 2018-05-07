---
title: Derleyici Hatası C2801 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2801
dev_langs:
- C++
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f68b3f575fcb8b909f58ac2ffbcaca26580279da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2801"></a>Derleyici Hatası C2801
Statik olmayan üye 'işleci işleci' olmalıdır  
  
 Statik olmayan üye olarak yalnızca aşağıdaki işleçleri aşırı yüklenebilir:  
  
-   Atama `=`  
  
-   Sınıf üye erişimi `->`  
  
-   Alt simge oluşturma `[]`  
  
-   İşlev çağrısı `()`  
  
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