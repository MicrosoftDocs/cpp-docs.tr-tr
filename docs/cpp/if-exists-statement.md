---
description: 'Hakkında daha fazla bilgi edinin: __if_exists ekstresi'
title: __if_exists Deyimi
ms.date: 11/04/2016
f1_keywords:
- __if_exists_cpp
helpviewer_keywords:
- identifiers, testing for existence
- symbols, testing for existence
- __if_exists keyword [C++]
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
ms.openlocfilehash: d2edfc11d70e50d2e393938c108db9c425468003
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113967"
---
# <a name="__if_exists-statement"></a>__if_exists Deyimi

**`__if_exists`** İfade, belirtilen tanımlayıcının mevcut olup olmadığını test eder. Tanımlayıcı varsa, belirtilen ifade bloğu yürütülür.

## <a name="syntax"></a>Sözdizimi

```
__if_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>Parametreler

*Tanımlayıcısını*\
Varlığını test etmek istediğiniz tanımlayıcı.

*deyimler*\
*Tanımlayıcı* varsa yürütülecek bir veya daha fazla deyim.

## <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> En güvenilir sonuçlara ulaşmak için **`__if_exists`** aşağıdaki kısıtlamaların altındaki ifadesini kullanın.

- **`__if_exists`** İfadeyi şablonlara değil yalnızca basit türlere uygulayın.

- İfadeyi, **`__if_exists`** bir sınıfın içindeki veya dışındaki tanımlayıcılara uygulayın. **`__if_exists`** İfadeyi yerel değişkenlere uygulamayın.

- **`__if_exists`** Yalnızca bir işlevin gövdesinde ifadesini kullanın. Bir işlevin gövdesi dışında, **`__if_exists`** ifade yalnızca tam olarak tanımlanmış türleri test edebilir.

- Aşırı yüklenmiş işlevler için test ettiğinizde, belirli bir aşırı yükleme formu için test edilemez.

**`__if_exists`** Deyimden tamamlama [__if_not_exists](../cpp/if-not-exists-statement.md) deyimidir.

## <a name="example"></a>Örnek

Bu örnekte tavsiye edilen şablonları kullanan bir uyarı vardır.

```cpp
// the__if_exists_statement.cpp
// compile with: /EHsc
#include <iostream>

template<typename T>
class X : public T {
public:
   void Dump() {
      std::cout << "In X<T>::Dump()" << std::endl;

      __if_exists(T::Dump) {
         T::Dump();
      }

      __if_not_exists(T::Dump) {
         std::cout << "T::Dump does not exist" << std::endl;
      }
   }
};

class A {
public:
   void Dump() {
      std::cout << "In A::Dump()" << std::endl;
   }
};

class B {};

bool g_bFlag = true;

class C {
public:
   void f(int);
   void f(double);
};

int main() {
   X<A> x1;
   X<B> x2;

   x1.Dump();
   x2.Dump();

   __if_exists(::g_bFlag) {
      std::cout << "g_bFlag = " << g_bFlag << std::endl;
   }

   __if_exists(C::f) {
      std::cout << "C::f exists" << std::endl;
   }

   return 0;
}
```

## <a name="output"></a>Çıktı

```Output
In X<T>::Dump()
In A::Dump()
In X<T>::Dump()
T::Dump does not exist
g_bFlag = 1
C::f exists
```

## <a name="see-also"></a>Ayrıca bkz.

[Seçim Deyimleri](../cpp/selection-statements-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[__if_not_exists ekstresi](../cpp/if-not-exists-statement.md)
