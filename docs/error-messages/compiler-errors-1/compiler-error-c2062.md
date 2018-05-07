---
title: Derleyici Hatası C2062 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2062
dev_langs:
- C++
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d11151a8e842796e4a5a8d45956782421daa1c70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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