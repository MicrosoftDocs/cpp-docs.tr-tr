---
title: Derleyici Uyarısı (düzey 1) C4486 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4486
dev_langs:
- C++
helpviewer_keywords:
- C4486
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91ad3659660dbe17552dc46caa66afe274ace9cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4486"></a>Derleyici Uyarısı (düzey 1) C4486
'function': özel sanal bir yöntem ref sınıfı veya değer sınıfı 'Kapalı' olarak işaretlenmelidir  
  
 Özel sanal üye işlevi bir yönetilen sınıf veya yapı geçersiz veya erişilemiyor beri işaretlenmelidir [korumalı](../../windows/sealed-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4486 oluşturur.  
  
```  
// C4486.cpp  
// compile with: /clr /c /W1  
ref class B {  
private:  
   virtual void f() {}   // C4486  
   virtual void f1() sealed {}   // OK  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, özel korumalı, sanal işlev bir olası kullanımını göstermektedir.  
  
```  
// C4486_b.cpp  
// compile with: /clr /c  
ref class B {};  
  
ref class D : B {};  
  
interface class I {  
   B^ mf();  
};  
  
ref class E : I {  
private:  
   virtual B^ g() sealed = I::mf {  
      return gcnew B;  
   }  
  
public:  
   virtual D^ mf() {  
      return gcnew D;  
   }  
};  
```