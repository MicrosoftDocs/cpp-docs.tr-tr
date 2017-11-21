---
title: "Derleyici Uyarısı (düzey 4) C4263 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4263
dev_langs: C++
helpviewer_keywords: C4263
ms.assetid: daabb05d-ab56-460f-ab6c-c74d222ef649
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c22441d23bcb6deec9b6bf437730920c664dd5f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4263"></a>Derleyici Uyarısı (düzey 4) C4263
'function': üye işlevini geçersiz bir temel sınıf sanal üye işlevi  
  
 Bir sınıf işlev tanımı aynı sayıda veya bağımsız değişken türü bir temel sınıf sanal işlevinde aynı ada sahiptir. Bu, temel sınıf sanal işlev etkili bir şekilde gizler.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4263 oluşturur:  
  
```  
// C4263.cpp  
// compile with: /W4  
#pragma warning(default:4263)  
#pragma warning(default:4264)  
class B {  
public:  
   virtual void func();  
};  
  
class D : public B {  
   void func(int);   // C4263  
};  
  
int main() {  
}  
```