---
description: 'Hakkında daha fazla bilgi edinin: mem_fun1_ref_t sınıfı'
title: mem_fun1_ref_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_ref_t
helpviewer_keywords:
- mem_fun1_ref_t class
ms.assetid: 7d6742f6-19ba-4523-b3c8-0e5b8f11464f
ms.openlocfilehash: 6418812fb4c924c8d67ba4fc09d4595455ad73c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149129"
---
# <a name="mem_fun1_ref_t-class"></a>mem_fun1_ref_t Sınıfı

`non_const`Bir başvuru bağımsız değişkeniyle başlatıldığında bir ikili işlev nesnesi olarak çağrılması için tek bir bağımsız değişken alan bir üye işlevine izin veren bir bağdaştırıcı sınıfı. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Result, class Type, class Arg>
class mem_fun1_ref_t : public binary_function<Type, Arg, Result> {
    explicit mem_fun1_ref_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type& left,
    Arg right) const;
};
```

### <a name="parameters"></a>Parametreler

*_Pm*\
İşlev nesnesine dönüştürülecek sınıfın üye işlevine yönelik bir işaretçi `Type` .

*tarafta*\
*_Pm* member işlevinin çağrıldığı nesne.

*Right*\
*_Pm* için verilen bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili işlev.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir  `Type` özel üye nesnesinde, sınıfının üye işlevine bir işaretçi olması gereken _Pm kopyasını depolar. Üye işlevini `operator()` döndürülen (**soldaki** \* ) olarak tanımlar. `_Pm` (**sağ**).

## <a name="example"></a>Örnek

Oluşturucusu `mem_fun1_ref_t` genellikle doğrudan kullanılmaz; yardımcı işlevi `mem_fun_ref` üye işlevlerini uyarlamak için kullanılır. Üye işlev bağdaştırıcılarını nasıl kullanacağınızı gösteren bir örnek için bkz. [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) .
