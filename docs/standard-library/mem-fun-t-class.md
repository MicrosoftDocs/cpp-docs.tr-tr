---
description: 'Hakkında daha fazla bilgi edinin: mem_fun_t sınıfı'
title: mem_fun_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun_t
helpviewer_keywords:
- mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
ms.openlocfilehash: 53c3103c8f2c855d8d6ff9a2861ace4f2c69c787
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149155"
---
# <a name="mem_fun_t-class"></a>mem_fun_t Sınıfı

`non_const`Bir işaretçi bağımsız değişkeniyle başlatıldığında bir birli işlev nesnesi olarak çağrılması için bağımsız değişken alan bir üye işlevine izin veren bir bağdaştırıcı sınıfı. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;
};
```

### <a name="parameters"></a>Parametreler

*_Pm*\
İşlev nesnesine dönüştürülecek sınıfın üye işlevine yönelik bir işaretçi `Type` .

*_Pleft*\
*_Pm* member işlevinin çağrıldığı nesne.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir birli işlev.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir  `Type` özel üye nesnesinde, sınıfının üye işlevine bir işaretçi olması gereken _Pm kopyasını depolar. Üye işlevini `operator()` döndüren ( `_Pleft` ->*  `_Pm` ) () olarak tanımlar.

## <a name="example"></a>Örnek

Oluşturucusu `mem_fun_t` genellikle doğrudan kullanılmaz; yardımcı işlevi `mem_fun` üye işlevlerini uyarlamak için kullanılır. Üye işlev bağdaştırıcılarını nasıl kullanacağınızı gösteren bir örnek için bkz. [mem_fun](../standard-library/functional-functions.md#mem_fun) .
