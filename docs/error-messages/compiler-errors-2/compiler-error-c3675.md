---
title: "Derleyici Hatası C3675 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3675
dev_langs:
- C++
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6545b7cfa8232ba8b48df104ce848eb34c0e108c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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