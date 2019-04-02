---
title: Açık geçersiz kılmalar (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- overriding, override [C++]
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
ms.openlocfilehash: 64b50505104b2f4ee9e5aade4f9bca104c1d5565
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787653"
---
# <a name="explicit-overrides--ccli-and-ccx"></a>Açık geçersiz kılmalar (C + +/ CLI ve C + +/ CX)

Bu konu, temel sınıfta veya arabirimde üye açıkça geçersiz kılma anlatılmaktadır. (Açık) adlandırılmış bir geçersiz kılma, farklı bir ada sahip bir türetilmiş yöntemi ile bir yöntemi geçersiz kılmak için yalnızca kullanılmalıdır.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="syntax"></a>Sözdizimi

```cpp
overriding-function-declarator = type::function [,type::function] { overriding-function-definition }
overriding-function-declarator = function { overriding-function-definition }
```

### <a name="parameters"></a>Parametreler

*geçersiz kılma-işlevi-declarator*<br/>
Geçersiz kılma işlev dönüş türü, adı ve bağımsız değişken listesi.  Geçersiz kılma işlevi geçersiz kılınmasını işlevi aynı ada sahip olmadığını unutmayın.

*type*<br/>
Geçersiz kılmak için bir işlevi içeren temel türü.

*İşlevi*<br/>
Geçersiz kılmak için bir veya daha fazla işlev adlarının virgülle ayrılmış listesi.

*geçersiz kılma-işlevi-definition*<br/>
Geçersiz kılma işlevi tanımlayan işlev gövdesi deyimleri.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılmalar için bir yöntem imzası bir diğer ad oluşturmak veya yöntemleri witht aynı imzaya için farklı uygulamalarını sağlamak için açık kullanın.

Devralınan türlerin ve devralınan tür üyeleri davranışını değiştirme hakkında daha fazla bilgi için bkz: [geçersiz kılma tanımlayıcıları](override-specifiers-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

Açık hakkında bilgi yerel kodda geçersiz kılar veya derlenmiş kodu `/clr:oldSyntax`, bkz: [açık geçersiz kılmalar](../cpp/explicit-overrides-cpp.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği basit, örtük geçersiz kılma ve üye uygulaması temel bir arabirimde açık geçersiz kılmalar kullanmayan gösterir.

```cpp
// explicit_override_1.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

ref class X : public I1 {
public:
   virtual void f() {
      System::Console::WriteLine("X::f override of I1::f");
   }
};

int main() {
   I1 ^ MyI = gcnew X;
   MyI -> f();
}
```

```Output
X::f override of I1::f
```

Aşağıdaki kod örneği, ortak bir imzaya sahip tüm arabirim üyelerini açık geçersiz kılma sözdiziminin uygulamak gösterilmektedir.

```cpp
// explicit_override_2.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

interface struct I2 {
   virtual void f();
};

ref struct X : public I1, I2 {
   virtual void f() = I1::f, I2::f {
      System::Console::WriteLine("X::f override of I1::f and I2::f");
   }
};

int main() {
   I1 ^ MyI = gcnew X;
   I2 ^ MyI2 = gcnew X;
   MyI -> f();
   MyI2 -> f();
}
```

```Output
X::f override of I1::f and I2::f
X::f override of I1::f and I2::f
```

Aşağıdaki kod örneği, nasıl bir işlevi geçersiz kılma uyguladığı işlevden farklı bir ad olabilir gösterir.

```cpp
// explicit_override_3.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

ref class X : public I1 {
public:
   virtual void g() = I1::f {
      System::Console::WriteLine("X::g");
   }
};

int main() {
   I1 ^ a = gcnew X;
   a->f();
}
```

```Output
X::g
```

Aşağıdaki kod örneği, türü güvenli koleksiyonu uygulayan açık arabirim uygulaması gösterir.

```cpp
// explicit_override_4.cpp
// compile with: /clr /LD
using namespace System;
ref class R : ICloneable {
   int X;

   virtual Object^ C() sealed = ICloneable::Clone {
      return this->Clone();
   }

public:
   R() : X(0) {}
   R(int x) : X(x) {}

   virtual R^ Clone() {
      R^ r = gcnew R;
      r->X = this->X;
      return r;
   }
};
```

## <a name="see-also"></a>Ayrıca Bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)