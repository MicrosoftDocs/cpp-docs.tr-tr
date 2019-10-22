---
title: mem_fun1_ref_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_ref_t
helpviewer_keywords:
- mem_fun1_ref_t class
ms.assetid: 7d6742f6-19ba-4523-b3c8-0e5b8f11464f
ms.openlocfilehash: 238d6147b2afa5ca3e143bc57aa4892e17d2c869
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687750"
---
# <a name="mem_fun1_ref_t-class"></a>mem_fun1_ref_t Sınıfı

Bir başvuru bağımsız değişkeniyle başlatıldığında bir ikili işlev nesnesi olarak çağrılması için tek bir bağımsız değişken alan `non_const` üye işlevine izin veren bir bağdaştırıcı sınıfı. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

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

*_Pm* \
İşlev nesnesine dönüştürülecek `Type` sınıfının üye işlevine yönelik bir işaretçi.

*sol* \
*_Pm* üye işlevinin çağrıldığı nesne.

*sağ* \
*_Pm*'ye verilen bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili işlev.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir özel üye nesnesinde `Type` sınıfının üye işlevine bir işaretçi olması gereken *_Pm*öğesinin bir kopyasını depolar. Üye işlevini döndüren `operator()` tanımlar (**Left**. \* `_Pm`) (**sağ**).

## <a name="example"></a>Örnek

@No__t_0 Oluşturucusu genellikle doğrudan kullanılmaz; `mem_fun_ref` yardımcı işlevi, üye işlevlerini uyarlamak için kullanılır. Üye işlev bağdaştırıcılarını nasıl kullanacağınızı gösteren bir örnek için bkz. [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) .
