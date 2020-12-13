---
description: 'Hakkında daha fazla bilgi edinin: mem_fun1_t sınıfı'
title: mem_fun1_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_t
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
ms.openlocfilehash: a0fd8f060757c7dc5004ad753fd168c9e644e1b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149090"
---
# <a name="mem_fun1_t-class"></a>mem_fun1_t Sınıfı

`non_const`Bir işaretçi bağımsız değişkeniyle başlatıldığında bir ikili işlev nesnesi olarak çağrılması için tek bir bağımsız değişken alan bir üye işlevine izin veren bir bağdaştırıcı sınıfı. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Result, class Type, class Arg>
class mem_fun1_t : public binary_function<Type *, Arg, Result> {
    explicit mem_fun1_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type* _Pleft,
    Arg right) const;
};
```

### <a name="parameters"></a>Parametreler

*_Pm*\
İşlev nesnesine dönüştürülecek sınıfın üye işlevine yönelik bir işaretçi `Type` .

*_Pleft*\
*_Pm* member işlevinin çağrıldığı nesne.

*Right*\
*_Pm* için verilen bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili işlev.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir  `Type` özel üye nesnesinde, sınıfının üye işlevine bir işaretçi olması gereken _Pm kopyasını depolar. Üye işlevini `operator()` döndüren (**_Pleft** -> \* `_Pm` ) (**sağdaki**) olarak tanımlar.

## <a name="example"></a>Örnek

Oluşturucusu `mem_fun1_t` genellikle doğrudan kullanılmaz; yardımcı işlevi `mem_fun` üye işlevlerini uyarlamak için kullanılır. Üye işlev bağdaştırıcılarını nasıl kullanacağınızı gösteren bir örnek için bkz. [mem_fun](../standard-library/functional-functions.md#mem_fun) .
