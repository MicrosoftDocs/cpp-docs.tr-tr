---
description: ': Sealed (C++/CLı ve C++/CX) hakkında daha fazla bilgi'
title: sealed (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- sealed_cpp
- sealed
helpviewer_keywords:
- sealed keyword [C++]
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
ms.openlocfilehash: a1ec201f9b03d1f2cf4d11eb71ba166f48bc6cea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341054"
---
# <a name="sealed--ccli-and-ccx"></a>sealed (C++/CLI ve C++/CX)

**Sealed** , bir sanal üyenin geçersiz kılınamayacağını veya bir türün temel tür olarak kullanılamayacağını belirten ref sınıfları için bağlama duyarlı bir anahtar sözcüktür.

> [!NOTE]
> ISO C++ 11 standart dili [final](../cpp/final-specifier.md) anahtar sözcüğünü sunmuştur. Standart sınıflarda **son** ' u kullanın ve ref sınıflarında **mühürlü** kullanın.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

## <a name="syntax"></a>Sözdizimi

```cpp
ref class identifier sealed {...};
virtual return-type identifier() sealed {...};
```

### <a name="parameters"></a>Parametreler

*Tanımlayıcısını*<br/>
İşlevin veya sınıfın adı.

*dönüş türü*<br/>
Bir işlev tarafından döndürülen tür.

## <a name="remarks"></a>Açıklamalar

İlk sözdizimi örneğinde, bir sınıf mühürlenmiş olur. İkinci örnekte, bir sanal işlev korumalıdır.

Ref sınıfları ve bunların sanal üye işlevleri için **Sealed** anahtar sözcüğünü kullanın. Daha fazla bilgi için bkz. [geçersiz kılma belirticileri ve yerel derlemeler](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

Bir türün nitelik türünü kullanarak korumalı olup olmadığını derleme zamanında tespit edebilirsiniz `__is_sealed(type)` . Daha fazla bilgi için bkz. [tür nitelikleri Için derleyici desteği](compiler-support-for-type-traits-cpp-component-extensions.md).

**Sealed** , bağlama duyarlı bir anahtar sözcüktür.  Daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](context-sensitive-keywords-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Bkz. [başvuru sınıfları ve yapıları](../cppcx/ref-classes-and-structs-c-cx.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

(Bu dil özelliği için yalnızca ortak dil çalışma zamanına uygulanan bir açıklama yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, sanal üye üzerinde **Sealed** efektinin etkisini gösterir.

```cpp
// sealed_keyword.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
   virtual void g();
};

ref class X : I1 {
public:
   virtual void f() {
      System::Console::WriteLine("X::f override of I1::f");
   }

   virtual void g() sealed {
      System::Console::WriteLine("X::f override of I1::g");
   }
};

ref class Y : public X {
public:
   virtual void f() override {
      System::Console::WriteLine("Y::f override of I1::f");
   }

   /*
   // the following override generates a compiler error
   virtual void g() override {
      System::Console::WriteLine("Y::g override of I1::g");
   }
   */
};

int main() {
   I1 ^ MyI = gcnew X;
   MyI -> f();
   MyI -> g();

   I1 ^ MyI2 = gcnew Y;
   MyI2 -> f();
}
```

```Output
X::f override of I1::f
X::f override of I1::g
Y::f override of I1::f
```

Sonraki kod örneği, bir sınıfın nasıl korumalı olarak işaretleneceğini gösterir.

```cpp
// sealed_keyword_2.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

ref class X sealed : I1 {
public:
   virtual void f() override {}
};

ref class Y : public X {   // C3246 base class X is sealed
public:
   virtual void f() override {}
};
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
