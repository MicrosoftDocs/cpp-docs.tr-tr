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
ms.openlocfilehash: 9d5a0b24bb08a9485b2d212058fa8f0bd82e5842
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183680"
---
# <a name="ifexists-statement"></a>__if_exists Deyimi

**__İf_exists** deyimi belirtilen tanımlayıcı var olup olmadığını test eder. Tanımlayıcısı varsa, belirtilen deyim bloğu yürütülür.

## <a name="syntax"></a>Sözdizimi

```
__if_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*tanımlayıcı*|Test etmek istediğiniz varlığı tanımlayıcısı.|
|*Deyimleri*|Bir veya daha fazla deyimlerini *tanımlayıcı* bulunmaktadır.|

## <a name="remarks"></a>Açıklamalar

> [!CAUTION]
>  En güvenilir sonuçlar elde etmek için kullanın **__if_exists** deyiminin altında aşağıdaki kısıtlamalar geçerlidir.

- Uygulama **__if_exists** deyimi yalnızca basit türlere, şablon yok.

- Uygulama **__if_exists** deyimi içinde veya dışında bir sınıf tanımlayıcıları. Geçerli **__if_exists** yerel değişkenlere deyimi.

- Kullanım **__if_exists** deyimi yalnızca bir işlev gövdesinin içinde. Bir işlev gövdesinin dışında **__if_exists** deyimi tam olarak tanımlanmamış türlerden yalnızca test edebilirsiniz.

- Aşırı yüklenmiş işlevler için test ettiğinizde, belirli bir aşırı yükleme form için test edilemez.

Tamamlayan **__if_exists** deyimi [__if_not_exists](../cpp/if-not-exists-statement.md) deyimi.

## <a name="example"></a>Örnek

Bu örnekte, değil önerilir şablonları kullandığına dikkat edin.

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

## <a name="output"></a>Çıkış

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