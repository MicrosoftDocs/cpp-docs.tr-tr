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
ms.openlocfilehash: 708b69bc63e59d8ba6ba882d894d6f17b59d8237
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592375"
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

[override Tanımlayıcısı](../cpp/override-specifier.md)  
[Geçersiz kılma tanımlayıcıları](../windows/override-specifiers-cpp-component-extensions.md)