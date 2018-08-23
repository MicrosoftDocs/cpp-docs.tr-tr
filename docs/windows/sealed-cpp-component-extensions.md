---
title: Mühürlü (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- sealed_cpp
- sealed
dev_langs:
- C++
helpviewer_keywords:
- sealed keyword [C++]
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f9693e16695d7a8c755515b4dd5163e2688a1d29
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611295"
---
# <a name="sealed--c-component-extensions"></a>mühürlü (C++ Bileşen Uzantıları)

**korumalı** sanal üyesi geçersiz kılınamaz gösteren bir bağlama duyarlı anahtar sözcük başvuru sınıfları için veya bir türü temel tür olarak kullanılamaz.

> [!NOTE]
> ISO C ++ 11 standart dil sahip [son](../cpp/final-specifier.md) Visual Studio'da desteklendiğine anahtar sözcüğü. Kullanım **son** standart sınıfları ve **korumalı** ref sınıfları.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

## <a name="syntax"></a>Sözdizimi

```cpp
ref class identifier sealed {...};
virtual return-type identifier() sealed {...};
```

### <a name="parameters"></a>Parametreler

*tanımlayıcı*  
İşlev veya sınıf adı.

*dönüş türü*  
İşlev tarafından döndürülen tür.

## <a name="remarks"></a>Açıklamalar

İlk söz dizimi örnekte, bir sınıfın korumalı. İkinci örnekte, korumalı bir sanal işlev.

**Korumalı** anahtar sözcüğü, yerel hedefler için ve Windows çalışma zamanı ve ortak dil çalışma zamanı (CLR) için geçerli. Daha fazla bilgi için [geçersiz kılma tanımlayıcıları ve yerel derlemeler](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

Bir tür kullanarak korumalı olmadığını derleme zamanında algılayabilir `__is_sealed(type)` türü niteliğine. Daha fazla bilgi için [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

**korumalı** bağlama duyarlı bir anahtar sözcüktür.  Daha fazla bilgi için [Context-Sensitive Keywords](../windows/context-sensitive-keywords-cpp-component-extensions.md).

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

## <a name="see-also"></a>Ayrıca Bkz.

[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)