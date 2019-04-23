---
title: korumalı (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- sealed_cpp
- sealed
helpviewer_keywords:
- sealed keyword [C++]
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
ms.openlocfilehash: 493f6597d146480714848b37154cc8bacd37113a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030455"
---
# <a name="sealed--ccli-and-ccx"></a>korumalı (C++/CLI ve C++/CX)

**korumalı** sanal üyesi geçersiz kılınamaz gösteren bir bağlama duyarlı anahtar sözcük başvuru sınıfları için veya bir türü temel tür olarak kullanılamaz.

> [!NOTE]
> Tanıtılan ISO C ++ 11 standart dil [son](../cpp/final-specifier.md) anahtar sözcüğü. Kullanım **son** standart sınıfları ve **korumalı** ref sınıfları.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

## <a name="syntax"></a>Sözdizimi

```cpp
ref class identifier sealed {...};
virtual return-type identifier() sealed {...};
```

### <a name="parameters"></a>Parametreler

*tanımlayıcı*<br/>
İşlev veya sınıf adı.

*dönüş türü*<br/>
İşlev tarafından döndürülen tür.

## <a name="remarks"></a>Açıklamalar

İlk söz dizimi örnekte, bir sınıfın korumalı. İkinci örnekte, korumalı bir sanal işlev.

Kullanım **korumalı** başvuru sınıfları ve bunların sanal üye işlevleri için anahtar sözcüğü. Daha fazla bilgi için [geçersiz kılma tanımlayıcıları ve yerel derlemeler](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

Bir tür kullanarak korumalı olmadığını derleme zamanında algılayabilir `__is_sealed(type)` türü niteliğine. Daha fazla bilgi için [tür özellikleri için derleyici desteği](compiler-support-for-type-traits-cpp-component-extensions.md).

**korumalı** bağlama duyarlı bir anahtar sözcüktür.  Daha fazla bilgi için [Context-Sensitive Keywords](context-sensitive-keywords-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Bkz: [başvuru sınıfları ve yapıları](../cppcx/ref-classes-and-structs-c-cx.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

(Bu dil özelliğinin yalnızca ortak dil çalışma zamanı için geçerli olan açıklaması yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Bu aşağıdaki kod örneğinde etkilerini gösterir **korumalı** üzerinde bir sanal üye.

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

Sonraki kod örneğinde, bir sınıf sealed olarak işaretlemek gösterilmektedir.

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

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)