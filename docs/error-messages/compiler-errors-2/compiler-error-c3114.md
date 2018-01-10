---
title: "Derleyici Hatası C3114 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3114
dev_langs: C++
helpviewer_keywords: C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 509c0dd1d85187871e78cfa93a66bc4ef385bbb6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3114"></a>Derleyici Hatası C3114
'bağımsız değişkeni': öznitelik bağımsız değişkeni geçerli bir adlı  
  
 Geçerli bir adlandırılmış bağımsız değişkeni olarak bir öznitelik sınıfı veri üyesi için sırayla onu değil işaretlenmelidir `static`, `const`, veya `literal`. Bir özellik varsa, özelliği olmamalıdır `static` ve gerekir get ve set erişimcisi.  
  
 Daha fazla bilgi için bkz: [özelliği](../../windows/property-cpp-component-extensions.md) ve [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3114 oluşturur.  
  
```  
// C3114.cpp  
// compile with: /clr /c  
public ref class A : System::Attribute {  
public:  
   static property int StaticProp {  
      int get();  
   }  
  
   property int Prop2 {  
      int get();  
      void set(int i);  
   }  
};  
  
[A(StaticProp=123)]   // C3114  
public ref class R {};  
  
[A(Prop2=123)]   // OK  
public ref class S {};  
```