---
title: "Derleyici Uyarısı (düzey 4) C4623 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4623
dev_langs: C++
helpviewer_keywords: C4623
ms.assetid: e630d8d0-f6ea-469c-a74f-07b027587225
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d9a47f0cc967011465286329461abc72eccb8c80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4623"></a>Derleyici Uyarısı (düzey 4) C4623
'`derived class`': varsayılan oluşturucu temel sınıf varsayılan bir oluşturucu erişilemez veya silinmiş olduğundan silindi olarak örtük olarak tanımlanmıştı  
  
 Bir oluşturucu bir taban sınıf içinde erişilebilir değil ve türetilen sınıf için oluşturulmamış. Yığında bu türde bir nesne oluşturma girişimi herhangi bir derleyici hatasına neden olur.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4623 oluşturur.  
  
```  
// C4623.cpp  
// compile with: /W4  
#pragma warning(default : 4623)  
class B {  
   B();  
};  
  
class C {  
public:  
   C();  
};  
  
class D : public B {};   // C4623 - to fix, make B's constructor public  
class E : public C {};   // OK - class C constructor is public  
  
int main() {  
   // D d;  will cause an error  
}  
```