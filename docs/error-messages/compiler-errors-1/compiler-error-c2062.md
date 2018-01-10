---
title: "Derleyici Hatası C2062 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2062
dev_langs: C++
helpviewer_keywords: C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4a006bed55f16e6ed94c3b5ed9415320acb86fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2062"></a>Derleyici Hatası C2062
türü 'type' beklenmeyen  
  
 Derleyici bir tür adı beklediğiniz değil.  
  
 Aşağıdaki örnek C2062 oluşturur:  
  
```  
// C2062.cpp  
// compile with: /c  
struct A {  : int l; };   // C2062  
struct B { private: int l; };   // OK  
```  
  
 C2062 tanıtıcıları tanımlanmamış bir oluşturucu ait parametre listesi türlerinde derleyici yöntemi nedeniyle ortaya çıkabilir. Derleyici tanımsız (yanlış yazılmış?) tür karşılaşırsa Oluşturucusu ifade olan ve C2062 sorunları varsayar. Çözmek için yalnızca bir oluşturucu parametre listesinde tanımlı türler kullanın.