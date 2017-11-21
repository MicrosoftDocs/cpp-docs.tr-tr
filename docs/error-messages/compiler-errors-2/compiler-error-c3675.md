---
title: "Derleyici Hatası C3675 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3675
dev_langs: C++
helpviewer_keywords: C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d45236fc32fd0d10e9617b6946683d8ebd73ef0e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3675"></a>Derleyici Hatası C3675
'function': 'property' tanımlı olduğu için ayrılmıştır  
  
 Basit bir özelliği bildirme olduğunda derleyici alma ve ayarlama erişimci yöntemleri ve bu oluşturur adlardır programınızı kapsamı içinde mevcut.  Derleyicinin ürettiği adları get_ ve SWbemObject özellik adının başına eklenerek oluşturulur.  Bu nedenle, derleyicinin ürettiği erişimciler aynı ada sahip işlevleri bildiremezsiniz.  
  
 Bkz: [özelliği](../../windows/property-cpp-component-extensions.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3675 oluşturur.  
  
```  
// C3675.cpp  
// compile with: /clr /c  
ref struct C {  
public:  
   property int Size;  
   int get_Size() { return 0; }   // C3675  
};  
```