---
title: Açık geçersiz kılmalarC++(/CLI C++ve/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- overriding, override [C++]
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
ms.openlocfilehash: c199301794daaa140ede2fd99b0ae755cea70f97
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172379"
---
# <a name="explicit-overrides--ccli-and-ccx"></a>Açık geçersiz kılmalarC++(/CLI C++ve/CX)

Bu konu, bir temel sınıfın veya arabirimin bir üyesini açıkça geçersiz kılmayı açıklar. Adlandırılmış (açık) geçersiz kılma yalnızca, farklı bir ada sahip türetilmiş bir yöntemle bir yöntemi geçersiz kılmak için kullanılmalıdır.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="syntax"></a>Sözdizimi

```cpp
overriding-function-declarator = type::function [,type::function] { overriding-function-definition }
overriding-function-declarator = function { overriding-function-definition }
```

### <a name="parameters"></a>Parametreler

*geçersiz kılma işlevi-bildirimci*<br/>
Geçersiz kılma işlevinin dönüş türü, adı ve bağımsız değişken listesi.  Geçersiz kılma işlevinin, geçersiz kılınan işlevle aynı ada sahip olması gerekmediğini unutmayın.

*type*<br/>
Geçersiz kılınacak bir işlev içeren temel tür.

*çalışmayacaktır*<br/>
Geçersiz kılınacak bir veya daha fazla işlev adının virgülle ayrılmış listesi.

*geçersiz kılma işlevi-tanımı*<br/>
Geçersiz kılma işlevini tanımlayan işlev gövdesi deyimleri.

### <a name="remarks"></a>Açıklamalar

Bir yöntem imzası için bir diğer ad oluşturmak veya aynı imzaya sahip yöntemler için farklı uygulamalar sağlamak üzere açık geçersiz kılmalar kullanın.

Devralınan türlerin ve devralınan tür üyelerinin davranışını değiştirme hakkında daha fazla bilgi için bkz. [geçersiz kılma belirticileri](override-specifiers-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

Yerel koddaki veya `/clr:oldSyntax`Derlenmiş koddaki açık geçersiz kılmalar hakkında daha fazla bilgi için bkz. [Açık geçersiz kılmalar](../cpp/explicit-overrides-cpp.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneğinde, açık geçersiz kılmalar kullanılarak değil, temel arabirimdeki bir üyenin basit, örtük bir şekilde geçersiz kılınması ve uygulanması gösterilmektedir.

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

Aşağıdaki kod örneği, açık bir geçersiz kılma söz dizimini kullanarak tüm arabirim üyelerinin ortak bir imzayla nasıl uygulanacağını gösterir.

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

Aşağıdaki kod örneği, bir işlev geçersiz kılmanın uyguladığı işlevden farklı bir ada sahip olabilir.

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

Aşağıdaki kod örneği, türü güvenli bir koleksiyon uygulayan açık bir arabirim uygulamasını gösterir.

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

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)
