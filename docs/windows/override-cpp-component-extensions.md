---
title: geçersiz kılma (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6818256aafc64702e5423a5560c251e6d46750fa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878885"
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