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
ms.openlocfilehash: ea136ac0312b78519fe2d8ea88ace4d8b0d69946
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178424"
---
# <a name="__if_exists-statement"></a>__if_exists Deyimi

**__İf_exists** ifade, belirtilen tanımlayıcının mevcut olup olmadığını test eder. Tanımlayıcı varsa, belirtilen ifade bloğu yürütülür.

## <a name="syntax"></a>Sözdizimi

```
__if_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Tanımlayıcısını*|Varlığını test etmek istediğiniz tanımlayıcı.|
|*deyimler*|*Tanımlayıcı* varsa yürütülecek bir veya daha fazla deyim.|

## <a name="remarks"></a>Açıklamalar

> [!CAUTION]
>  En güvenilir sonuçlara ulaşmak için aşağıdaki kısıtlamalarda **__if_exists** ifadesini kullanın.

- **__İf_exists** deyiminizi şablonlara değil yalnızca basit türlere uygulayın.

- **__İf_exists** ifadesini, bir sınıfın içindeki veya dışındaki tanımlayıcılara uygulayın. **__İf_exists** ifadesini yerel değişkenlere uygulamayın.

- **__İf_exists** ifadesini yalnızca bir işlevin gövdesinde kullanın. Bir işlevin gövdesi dışında, **__if_exists** deyimleri yalnızca tam olarak tanımlanmış türleri test edebilir.

- Aşırı yüklenmiş işlevler için test ettiğinizde, belirli bir aşırı yükleme formu için test edilemez.

**__İf_exists** deyimin tamamlaması [__if_not_exists](../cpp/if-not-exists-statement.md) deyimidir.

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
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[__if_not_exists Deyimi](../cpp/if-not-exists-statement.md)
