---
title: Yeni (vtable'da yeni yuva) (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5ac6b6401870e29ec10b17ff2c06fb970328af82
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612691"
---
# <a name="new-new-slot-in-vtable--c-component-extensions"></a>yeni (vtable'da yeni yuva) (C++ Bileşen Uzantıları)

**Yeni** anahtar sözcüğü, sanal üyenin vtable'da yeni yuva aldığını gösterir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliğinin tüm çalışma zamanları için geçerli olan açıklaması yoktur.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Windows çalışma zamanı'nda desteklenmiyor.

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

İçinde bir `/clr` derleme **yeni** sanal üyenin vtable'da yeni yuva alırsınız; işlev temel sınıf yöntemini geçersiz kılmaz gösterir.

**Yeni** işlevi için IL eklenecek newslot değiştiricisine neden olur.  Newslot hakkında daha fazla bilgi için bkz:

- [MethodInfo.getbasedefinition yöntemi](https://msdn.microsoft.com/library/system.reflection.methodinfo.getbasedefinition.aspx)

- [MethodAttributes numaralandırma](https://msdn.microsoft.com/library/system.reflection.methodattributes.aspx)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek etkisini gösterir **yeni**.

```cpp
// newslot.cpp
// compile with: /clr
ref class C {
public:
   virtual void f() {
      System::Console::WriteLine("C::f() called");
   }

   virtual void g() {
      System::Console::WriteLine("C::g() called");
   }
};

ref class D : public C {
public:
   virtual void f() new {
      System::Console::WriteLine("D::f() called");
   }

   virtual void g() override {
      System::Console::WriteLine("D::g() called");
   }
};

ref class E : public D {
public:
   virtual void f() override {
      System::Console::WriteLine("E::f() called");
   }
};

int main() {
   D^ d = gcnew D;
   C^ c = gcnew D;

   c->f();   // calls C::f
   d->f();   // calls D::f

   c->g();   // calls D::g
   d->g();   // calls D::g

   D ^ e = gcnew E;
   e->f();   // calls E::f
}
```

```Output
C::f() called

D::f() called

D::g() called

D::g() called

E::f() called
```

## <a name="see-also"></a>Ayrıca Bkz.

[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)  
[Geçersiz kılma tanımlayıcıları](../windows/override-specifiers-cpp-component-extensions.md)