---
title: Yeni (vtable'da yeni yuva) (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
ms.openlocfilehash: c5446e5e84491ff7d736ce3b3af49dacd471c010
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025792"
---
# <a name="new-new-slot-in-vtable--ccli-and-ccx"></a>Yeni (vtable'da yeni yuva) (C++/CLI ve C++/CX)

**Yeni** anahtar sözcüğü, sanal üyenin vtable'da yeni yuva aldığını gösterir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliğinin tüm çalışma zamanları için geçerli olan açıklaması yoktur.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Windows çalışma zamanı'nda desteklenmiyor.

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

İçinde bir `/clr` derleme **yeni** sanal üyenin vtable'da yeni yuva alırsınız; işlev temel sınıf yöntemini geçersiz kılmaz gösterir.

**Yeni** işlevi için IL eklenecek newslot değiştiricisine neden olur.  Newslot hakkında daha fazla bilgi için bkz:

- <xref:System.Reflection.MethodInfo.GetBaseDefinition?displayProperty=nameWithType>

- <xref:System.Reflection.MethodAttributes?displayProperty=nameWithType>

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

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)<br/>

[Geçersiz Kılma Tanımlayıcıları](override-specifiers-cpp-component-extensions.md)