---
title: "Nasıl yapılır: geçersiz kılma tanımlayıcılarını bildirme (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 07d612e97a6aaf3ff53116415b8eedc7324f78ea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>Nasıl yapılır: Yerel Derlemelerde Geçersiz Kılma Tanımlayıcılarını Bildirme (C++/CLI)
[korumalı](../windows/sealed-cpp-component-extensions.md), [soyut](../windows/abstract-cpp-component-extensions.md), ve [geçersiz kılma](../windows/override-cpp-component-extensions.md) kullanmayın derlemeleri içinde kullanılabilir **/ZW** veya [/CLR](../build/reference/clr-common-language-runtime-compilation.md).  
  
> [!NOTE]
>  ISO C ++ 11 standart dil sahip [geçersiz kılma](../cpp/override-specifier.md) tanımlayıcısı ve [son](../cpp/final-specifier.md) tanımlayıcısı ve her ikisi de Visual Studio kullanımda desteklenir `final` yerine `sealed` amaçlanmıştır kodu yalnızca yerel olarak derlenmiş.  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnekte gösterilir `sealed` yerel derlemeleri içinde geçerlidir.  
  
### <a name="code"></a>Kod  
  
```cpp  
// sealed_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
   virtual void g();  
};  
  
class X : public I1 {  
public:  
   virtual void g() sealed {}  
};  
  
class Y : public X {  
public:  
  
   // the following override generates a compiler error  
   virtual void g() {}   // C3248 X::g is sealed!  
};  
```  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Sonraki örnekte gösterildiği `override` yerel derlemeleri içinde geçerlidir.  
  
### <a name="code"></a>Kod  
  
```cpp  
// override_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
};  
  
class X : public I1 {  
public:  
   virtual void f() override {}   // OK  
   virtual void g() override {}   // C3668 I1::g does not exist  
};  
```  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Bu örnekte gösterilir `abstract` yerel derlemeleri içinde geçerlidir.  
  
### <a name="code"></a>Kod  
  
```cpp  
// abstract_native_keyword.cpp  
class X abstract {};  
  
int main() {  
   X * MyX = new X;   // C3622 cannot instantiate abstract class  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Geçersiz kılma tanımlayıcıları](../windows/override-specifiers-cpp-component-extensions.md)