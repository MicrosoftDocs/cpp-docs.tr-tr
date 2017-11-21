---
title: "Derleyici Hatası C3171 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3171
dev_langs: C++
helpviewer_keywords: C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ebd64aa2c80f6e21b1e5c1829d8e165d46207718
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3171"></a>Derleyici Hatası C3171
'module': bir projede farklı modül öznitelikleri belirtilemez  
  
 [Modül](../../windows/module-cpp.md) farklı parametre listeleri özniteliklerle iki bir derleme dosyalarında bulundu. Yalnızca bir benzersiz `module` derlemesi başına özniteliği belirtilebilir.  
  
 Aynı `module` öznitelikleri birden fazla kaynak kodu dosyasına belirtilebilir.  
  
 Örneğin, aşağıdaki `module` öznitelikleri bulundu:  
  
```  
// C3171.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];  
int main() {}  
```  
  
 Ardından,  
  
```  
// C3171b.cpp  
// compile with: C3171.cpp  
// C3171 expected  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];  
```  
  
 Derleyici C3171 oluşturur (farklı sürüm değerleri unutmayın).