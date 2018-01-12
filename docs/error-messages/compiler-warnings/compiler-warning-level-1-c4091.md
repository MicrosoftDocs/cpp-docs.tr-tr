---
title: "Derleyici Uyarısı (düzey 1) C4091 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4091
dev_langs: C++
helpviewer_keywords: C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9be40d65b657a7ac34fb105a2b1b16c702e4922c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4091"></a>Derleyici Uyarısı (düzey 1) C4091
'anahtar sözcüğü': 'type' sol tarafta hiçbir değişken bildirilmişse yoksayıldı  
  
 Derleyici burada kullanıcı büyük olasılıkla bildirilmesi için bir değişken hedeflenen, ancak derleyici değişkeni bildirme bırakamıyor bir durum algıladı.  
  
## <a name="example"></a>Örnek  
 A `__declspec` özniteliği kullanıcı tanımlı tür bildirimi başındaki türü değişkenine uygular. Hiçbir değişken bildirilmiş C4091 gösterir. Aşağıdaki örnek C4091 oluşturur.  
  
```  
// C4091.cpp  
// compile with: /W1 /c  
__declspec(dllimport) class X {}; // C4091  
  
// __declspec attribute applies to varX  
__declspec(dllimport) class X2 {} varX;  
  
// __declspec attribute after the class or struct keyword   
// applies to user defined type  
class __declspec(dllimport) X3 {};  
```  
  
## <a name="example"></a>Örnek  
 Tanımlayıcı bir typedef ise, ayrıca bir değişken adı olamaz. Aşağıdaki örnek C4091 oluşturur.  
  
```  
// C4091_b.cpp  
// compile with: /c /W1 /WX  
#define LIST 4  
typedef struct _LIST {} LIST;   // C4091  
```