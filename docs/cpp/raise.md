---
title: __raise
description: Yerel olay işleme için Microsoft C++ uzantısı anahtar sözcüğünü nasıl kullanacağınızı öğrenin `__raise` .
ms.date: 11/20/2020
f1_keywords:
- __raise
- __raise_cpp
helpviewer_keywords:
- __raise keyword [C++]
ms.openlocfilehash: c9df602803062bc51b8c0cee13f17263cdc91786
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483158"
---
# <a name="__raise-keyword"></a>`__raise` sözcükle

Bir olayın çağrı sitesini vurgular.

> [!NOTE]
> Yerel C++ içindeki olay öznitelikleri standart C++ ile uyumsuzdur. Uyumluluk modunu belirttiğinizde derlenirler [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

## <a name="syntax"></a>Syntax

> **`__raise`** *`method-declarator`* **`;`**

## <a name="remarks"></a>Açıklamalar

Yönetilen koddan bir olay yalnızca tanımlandığı sınıf içinden oluşturulabilir. Daha fazla bilgi için bkz. [`event`](../extensions/event-cpp-component-extensions.md).

**`__raise`** Bir olay olmayan bir çağrı yaparsanız anahtar sözcüğü bir hata oluşturulmasına neden olur.

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="example"></a>Örnek

```cpp
// EventHandlingRef_raise.cpp
struct E {
   __event void func1();
   void func1(int) {}

   void func2() {}

   void b() {
      __raise func1();
      __raise func1(1);  // C3745: 'int Event::bar(int)':
                         // only an event can be 'raised'
      __raise func2();   // C3745
   }
};

int main() {
   E e;
   __raise e.func1();
   __raise e.func1(1);  // C3745
   __raise e.func2();   // C3745
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lerimi](../cpp/keywords-cpp.md)\
[Olay işleme](../cpp/event-handling.md)\
[`__event`](../cpp/event.md)\
[`__hook`](../cpp/hook.md)\
[`__unhook`](../cpp/unhook.md)\
[.NET ve UWP için bileşen uzantıları](../extensions/component-extensions-for-runtime-platforms.md)
