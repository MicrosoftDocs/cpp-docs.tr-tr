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
ms.openlocfilehash: 855f2c18423fd6c1ca708034214e6f5c7048d6d8
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605567"
---
# <a name="override--c-component-extensions"></a>geçersiz kılma (C++ Bileşen Uzantıları)
**Geçersiz kılma** bağlama duyarlı anahtar sözcüğü bir tür üyesi bir temel sınıf veya temel arabirim üyesi kıldığını gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 **Geçersiz kılma** (varsayılan derleyici seçeneği), yerel hedefler için derleme yaparken anahtar sözcüğü geçerli Windows çalışma zamanı hedefleri (`/ZW` derleyici seçeneği), veya ortak dil çalışma zamanı hedefleri (`/clr` derleyici seçeneği).  
  
 Geçersiz kılma tanımlayıcıları hakkında daha fazla bilgi için bkz. [geçersiz kılma belirticisi](../cpp/override-specifier.md) ve [geçersiz kılma tanımlayıcıları ve yerel derlemeler](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Bağlama duyarlı anahtar sözcükler hakkında daha fazla bilgi için bkz. [Context-Sensitive Keywords](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## <a name="examples"></a>Örnekler  
  
 Aşağıdaki kod örneği gösteren **geçersiz kılma** yerel derlemelerde de kullanılabilir.  
  
```cpp  
// override_keyword_1.cpp  
// compile with: /c  
struct I1 {  
   virtual void f();  
};  
  
struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
### <a name="example"></a>Örnek

 Aşağıdaki kod örneği gösteren **geçersiz kılma** Windows çalışma zamanı derlemeleri kullanılabilir.  
  
```cpp 
// override_keyword_2.cpp  
// compile with: /ZW /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
#### <a name="requirements"></a>Gereksinimler  
  
 Derleyici seçeneği: `/ZW`  
    
### <a name="example"></a>Örnek

 Aşağıdaki kod örneği gösteren **geçersiz kılma** ortak dil çalışma zamanı derlemeleri kullanılabilir.  
  
```cpp  
// override_keyword_3.cpp  
// compile with: /clr /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
#### <a name="requirements"></a>Gereksinimler  
  
 Derleyici seçeneği: `/clr`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [geçersiz kılma belirticisi](../cpp/override-specifier.md)   
 [Geçersiz kılma tanımlayıcıları](../windows/override-specifiers-cpp-component-extensions.md)