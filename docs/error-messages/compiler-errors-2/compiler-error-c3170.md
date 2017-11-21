---
title: "Derleyici Hatası C3170 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3170
dev_langs: C++
helpviewer_keywords: C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aa11ac93ab7e5637153a063a892d99e127b80f54
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3170"></a>Derleyici Hatası C3170
farklı modül tanımlayıcıları projede sahip olamaz  
  
 [Modül](../../windows/module-cpp.md) öznitelikleri farklı adlara sahip bir derleme dosyalarında iki bulundu. Yalnızca bir benzersiz `module` derlemesi başına özniteliği belirtilebilir.  
  
 Aynı `module` öznitelikleri birden fazla kaynak kodu dosyasına belirtilebilir.  
  
 Örneğin aşağıdaki modül öznitelik bulunamadı:  
  
```  
// C3170.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
int main() {}  
```  
  
 Ardından,  
  
```  
// C3170b.cpp  
// compile with: C3170.cpp  
// C3170 expected  
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
```  
  
 Derleyici C3170 oluşturur (farklı adlar unutmayın).