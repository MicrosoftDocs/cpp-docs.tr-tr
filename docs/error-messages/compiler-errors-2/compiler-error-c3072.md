---
title: "Derleyici Hatası C3072 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3072
dev_langs: C++
helpviewer_keywords: C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3334edd6f297a61ca62a5fe5a0f8b6cddfef7f80
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3072"></a>Derleyici Hatası C3072
operator 'işleci' ref sınıfının bir örneği için uygulanamaz  
  
 birli kullanmak '`operator` ' ref sınıfının bir örneği için bir tanıtıcı türü dönüştürmek için işleci  
  
 Bir CLR türü CLR işleçleri, yerel (veya standart) işleçleri gerektirir.  Daha fazla bilgi için bkz: [izleme başvurusu işleci](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3072 oluşturur.  
  
```  
// C3072.cpp  
// compile with: /clr  
ref class R {};  
  
int main() {  
   R r1;  
   R^ r2 = &r1;   // C3072  
   R^ r3 = %r1;   // OK  
}  
```