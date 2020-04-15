---
title: __if_exists Deyimi
ms.date: 11/04/2016
f1_keywords:
- __if_exists_cpp
helpviewer_keywords:
- identifiers, testing for existence
- symbols, testing for existence
- __if_exists keyword [C++]
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
ms.openlocfilehash: 609d576c6ab3eddca569ed4f19a4024b47b6a1d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374147"
---
# <a name="__if_exists-statement"></a>__if_exists Deyimi

**__if_exists** deyimi belirtilen tanımlayıcının var olup olmadığını sınar. Tanımlayıcı varsa, belirtilen deyim bloğu yürütülür.

## <a name="syntax"></a>Sözdizimi

```
__if_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Tanımlayıcı*|Varlığını test etmek istediğiniz tanımlayıcı.|
|*Ifa -de*|Tanımlayıcı *varsa* yürütülecek bir veya daha fazla deyim.|

## <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> En güvenilir sonuçları elde etmek için aşağıdaki kısıtlamalar altında **__if_exists** ifadesini kullanın.

- **__if_exists** deyimini şablonlara değil, yalnızca basit türlere uygulayın.

- **__if_exists** ifadesini sınıf içinde veya dışında tanımlayıcılara uygulayın. **__if_exists** deyimini yerel değişkenlere uygulamayın.

- **__if_exists** ifadesini yalnızca bir işlevin gövdesinde kullanın. Bir işlevin gövdesi dışında, **__if_exists** deyimi yalnızca tam olarak tanımlanmış türleri sınayabilir.

- Aşırı yüklü işlevleri test ettiğinizde, aşırı yüklemenin belirli bir formunu test edemezsiniz.

**__if_exists** deyiminin tamamlayıcısı [__if_not_exists](../cpp/if-not-exists-statement.md) ifadesidir.

## <a name="example"></a>Örnek

Bu örnekte tavsiye edilen şablonlar kullandığına dikkat edin.

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
[__if_not_exists Deyimi](../cpp/if-not-exists-statement.md)
