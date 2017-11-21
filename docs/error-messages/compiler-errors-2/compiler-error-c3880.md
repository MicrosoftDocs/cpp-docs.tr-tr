---
title: "Derleyici Hatası C3880 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3880
dev_langs: C++
helpviewer_keywords: C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5e86108e0ab2608f7f59f160d9f7a849b83ef71a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3880"></a>Derleyici Hatası C3880
'var': değişmez değer veri üyesi olamaz  
  
 Türü bir [değişmez değer](../../windows/literal-cpp-component-extensions.md) özniteliği olmalıdır, veya derleme zamanı dönüştürülebilir, aşağıdaki türlerden biri:  
  
-   tam sayı türü  
  
-   dize  
  
-   Enum bir tam sayı veya temel alınan türü ile  
  
 Aşağıdaki örnek C3880 oluşturur:  
  
```  
// C3880.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal System::Decimal staticConst1 = 10;   // C3880  
   literal int staticConst2 = 10;   // OK  
};  
```