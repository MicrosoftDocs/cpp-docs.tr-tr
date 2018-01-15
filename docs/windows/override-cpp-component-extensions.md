---
title: "geçersiz kılma (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 88138001a9767bbe9752c1de0577910fca8bc914
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="override--c-component-extensions"></a>geçersiz kılma (C++ Bileşen Uzantıları)
`override` Bağlama duyarlı anahtar sözcüğü bir türünün bir üyesi bir taban sınıf veya temel arabirim üye kıldığını gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 `override` (Varsayılan derleyici seçeneği), yerel hedefler için derlerken anahtar sözcüğü geçerli Windows çalışma zamanı hedefleri (**/ZW** derleyici seçeneği), ya da ortak dil çalışma zamanı hedefleri (**/CLR** derleyici seçenek).  
  
 Geçersiz kılma tanımlayıcıları hakkında daha fazla bilgi için bkz: [override tanımlayıcısı](../cpp/override-specifier.md) ve [geçersiz kılma tanımlayıcıları ve yerel derleme](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Bağlama duyarlı anahtar sözcükler hakkında daha fazla bilgi için bkz: [Context-Sensitive anahtar sözcükleri](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneğinde gösterir `override` içinde yerel derlemeleri de kullanılabilir.  
  
```cpp#  
// override_keyword_1.cpp  
// compile with: /c  
struct I1 {  
   virtual void f();  
};  
  
struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Örnek**  
  
 Aşağıdaki kod örneğinde gösterir `override` Windows çalışma zamanı derlemeleri içinde kullanılabilir.  
  
```cpp#  
// override_keyword_2.cpp  
// compile with: /ZW /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Gereksinimler**  
  
 Derleyici seçeneği: **/ZW**  
  
 **Örnek**  
  
 Aşağıdaki kod örneğinde gösterir `override` ortak dil çalışma zamanı derlemeleri kullanılabilir.  
  
```cpp#  
// override_keyword_3.cpp  
// compile with: /clr /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Gereksinimler**  
  
 Derleyici seçeneği:   **/CLR**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [override tanımlayıcısı](../cpp/override-specifier.md)   
 [Geçersiz kılma tanımlayıcıları](../windows/override-specifiers-cpp-component-extensions.md)