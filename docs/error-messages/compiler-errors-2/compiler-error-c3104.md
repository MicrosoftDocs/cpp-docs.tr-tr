---
title: Derleyici Hatası C3104
ms.date: 11/04/2016
f1_keywords:
- C3104
helpviewer_keywords:
- C3104
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
ms.openlocfilehash: 71a5943f65f4bd490ecb02824fef7a96741709f1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540329"
---
# <a name="compiler-error-c3104"></a>Derleyici Hatası C3104

Geçersiz öznitelik bağımsız değişkeni

Bir öznitelik için geçersiz bir bağımsız değişken belirtildi.

Bkz: [öznitelik parametre türleri](../../windows/attribute-parameter-types-cpp-component-extensions.md) daha fazla bilgi için.

Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulan: yönetilen diziler için özel öznitelikler geçirirken, dizi türü artık toplama başlatma listeden çıkarılır. Derleyici artık başlatıcı listesi yanı sıra, dizi türü belirtmenizi gerektirir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3104 oluşturur.

```
// C3104a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::Class)]
public ref struct ABC : public Attribute {
   ABC(array<int>^){}
   array<double> ^ param;
};

[ABC( {1,2,3}, param = {2.71, 3.14})]   // C3104
// try the following line instead
// [ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]
ref struct AStruct{};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3104 oluşturur.

```
// C3104b.cpp
// compile with: /clr /c
// C3104 expected
using namespace System;

int func() {
   return 0;
}

[attribute(All)]
ref class A {
public:
   A(int) {}
};

// Delete the following 2 lines to resolve.
[A(func())]
ref class B {};

// OK
[A(0)]
ref class B {};
```
