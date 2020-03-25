---
title: override (C++/CLI ve C++/CX)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
ms.openlocfilehash: 32c825539efe670528eab7416afefe07d4cb1b6c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172106"
---
# <a name="override--ccli-and-ccx"></a>override (C++/CLI ve C++/CX)

**Geçersiz kılma** bağlamı duyarlı anahtar sözcüğü, bir türün bir üyesinin temel sınıfı veya temel arabirim üyesini geçersiz kıldığını belirtir.

## <a name="remarks"></a>Açıklamalar

**Override** anahtar sözcüğü, yerel hedefler (varsayılan derleyici seçeneği), Windows çalışma zamanı hedefler (`/ZW` derleyici seçeneği) veya ortak dil çalışma zamanı hedefleri (`/clr` derleyici seçeneği) için derlenirken geçerlidir.

Geçersiz kılma belirticileri hakkında daha fazla bilgi için bkz. [geçersiz kılma belirticisi](../cpp/override-specifier.md) ve [geçersiz kılma tanımlayıcıları ve yerel derlemeler](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

Bağlama duyarlı anahtar sözcükler hakkında daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](context-sensitive-keywords-cpp-component-extensions.md).

## <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, **geçersiz kılma** 'nın yerel derlemelerde da kullanılabilir olduğunu gösterir.

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

Aşağıdaki kod örneği, **geçersiz kılmanın** Windows çalışma zamanı derlemelerinde kullanılabileceğini gösterir.

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

Aşağıdaki kod örneği, **geçersiz kılma** 'nın ortak dil çalışma zamanı derlemelerinde kullanılabileceğini gösterir.

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

## <a name="see-also"></a>Ayrıca bkz.

[override Tanımlayıcısı](../cpp/override-specifier.md)<br/>
[Geçersiz Kılma Tanımlayıcıları](override-specifiers-cpp-component-extensions.md)
