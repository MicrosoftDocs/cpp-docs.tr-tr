---
title: "Derleyici Uyarısı (düzey 1) C4691 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4691
dev_langs:
- C++
helpviewer_keywords:
- C4691
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17673ee3e65d2e0cd0d989c56759b62de38f5fdc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4691"></a>Derleyici Uyarısı (düzey 1) C4691
'type': başvuru türü başvurulmayan derlemesi 'dosya', bunun yerine kullanılan geçerli çeviri biriminde tanımlanan türü bekleniyordu  
  
 Orijinal türü tanımını içeren meta veri dosyası başvurulmayan ve derleyici yerel tür tanımı kullanıyor.  
  
 Burada yeniden durumda *dosya*, C4691 göz ardı ya da pragma ile kapalı [uyarı](../../preprocessor/warning.md).  Diğer bir deyişle, oluşturmakta olduğunuz dosya burada tür tanımı bulmak için derleyici bekliyor dosya ile aynı olduğunda, C4691 yoksayabilirsiniz.  
  
 Ancak, meta verilerde başvurulan aynı derlemeden olmayan bir tanım derleyici kullanıyorsa, beklenmeyen davranışları oluşabilir; CLR türleri yalnızca türünün adı, ancak aynı zamanda tarafından derleme yazılmalıdır.  Diğer bir deyişle, derleme z.dll bir türden Z derleme y.dll bir türden Z farklıdır.  
  
## <a name="example"></a>Örnek  
 Bu örnek, orijinal türü tanımını içerir.  
  
```  
// C4691_a.cpp  
// compile with: /clr /LD /W1  
public ref class Original_Type {};  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek C4691_a.dll başvuruyor ve Original_Type türünde bir alan bildirir.  
  
```  
// C4691_b.cpp  
// compile with: /clr /LD  
#using "C4691_a.dll"  
public ref class Client {  
public:  
   Original_Type^ ot;  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4691 oluşturur.  Bu örnek için Original_Type bir tanım içeriyor ve C4691a.dll başvurmuyor dikkat edin.  
  
 Çözümlemek için özgün türü tanımını içeren meta veri dosyası başvuru ve yerel bildirim ve tanımı kaldırın.  
  
```  
// C4691_c.cpp  
// compile with: /clr /LD /W1  
// C4691 expected  
  
// Uncomment the following line to resolve.  
// #using "C4691_a.dll"  
#using "C4691_b.dll"  
  
// Delete the following line to resolve.  
ref class Original_Type;  
  
public ref class MyClass : Client {};  
```