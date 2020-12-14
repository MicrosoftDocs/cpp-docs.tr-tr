---
description: "Daha fazla bilgi edinin: yeni (vtable 'da yeni yuva) (C++/CLı ve C++/CX)"
title: new (vtable'da yeni yuva) (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
ms.openlocfilehash: ccc6adbd29eca82b44d34b981803a88332a8784a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257686"
---
# <a name="new-new-slot-in-vtable--ccli-and-ccx"></a>new (vtable'da yeni yuva) (C++/CLI ve C++/CX)

**`new`** Anahtar sözcüğü, sanal bir üyenin vtable 'da yeni bir yuva aldığını gösterir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliği için tüm çalışma zamanları için uygulanan bir açıklama yoktur.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Windows Çalışma Zamanı desteklenmez.

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

Bir `/clr` derlemede, **`new`** sanal bir üyenin vtable 'da yeni bir yuva aldığını ve işlevin bir temel sınıf yöntemini geçersiz kılmadığını gösterir.

**`new`** , NewSlot değiştiricisinin işlev için Il 'ye eklenmesine neden olur.  NewSlot hakkında daha fazla bilgi için bkz.

- <xref:System.Reflection.MethodInfo.GetBaseDefinition?displayProperty=nameWithType>

- <xref:System.Reflection.MethodAttributes?displayProperty=nameWithType>

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek öğesinin etkisini gösterir **`new`** .

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

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)<br/>
[Geçersiz kılma belirticileri](override-specifiers-cpp-component-extensions.md)
