---
title: Derleyici Hatası C3675 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3675
dev_langs:
- C++
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b4aaa53ae1d92364fad143f127ee3e7b504acdd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273650"
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