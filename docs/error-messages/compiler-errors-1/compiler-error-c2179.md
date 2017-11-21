---
title: "Derleyici Hatası C2179 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2179
dev_langs: C++
helpviewer_keywords: C2179
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c0f311bcdbbdaa721e3897eae0a90ae892cf75d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2179"></a>Derleyici Hatası C2179
'type': öznitelik bağımsız değişkeni tür parametreleri kullanamaz  
  
 Genel tür parametresi, çalışma zamanında çözümlenir. Ancak, bir öznitelik parametre derleme zamanında giderilmesi gerekir. Bu nedenle, bir öznitelik bağımsız değişkeni olarak bir genel tür parametresi kullanılamaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2179 oluşturur.  
  
```  
// C2179.cpp  
// compile with: /clr  
using namespace System;  
  
public ref struct Attr : Attribute {  
   Attr(Type ^ a) {  
      x = a;  
   }  
  
   Type ^ x;  
};  
  
ref struct G {};  
  
generic<typename T>   
public ref class Z {   
public:  
   Type ^ d;  
   [Attr(T::typeid)]   // C2179  
   // try the following line instead  
   // [Attr(G::typeid)]  
   T t;  
};  
```