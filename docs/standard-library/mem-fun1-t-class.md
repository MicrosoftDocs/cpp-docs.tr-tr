---
title: mem_fun1_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_t
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
ms.openlocfilehash: 00d9322a8f0530da2e48b3f16fb52c00f9d1b075
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687742"
---
# <a name="mem_fun1_t-class"></a>mem_fun1_t Sınıfı

Bir işaretçi bağımsız değişkeniyle başlatıldığında bir ikili işlev nesnesi olarak çağrılması için tek bir bağımsız değişken alan `non_const` üye işlevine izin veren bir bağdaştırıcı sınıfı. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

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

*_Pm* \
İşlev nesnesine dönüştürülecek `Type` sınıfının üye işlevine yönelik bir işaretçi.

*_Pleft* \
*_Pm* üye işlevinin çağrıldığı nesne.

*sağ* \
*_Pm*'ye verilen bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili işlev.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir özel üye nesnesinde `Type` sınıfının üye işlevine bir işaretçi olması gereken *_Pm*öğesinin bir kopyasını depolar. Üye işlevini döndüren `operator()` tanımlar ( **_Pleft** -> \* `_Pm`) (**sağ**).

## <a name="example"></a>Örnek

@No__t_0 Oluşturucusu genellikle doğrudan kullanılmaz; `mem_fun` yardımcı işlevi, üye işlevlerini uyarlamak için kullanılır. Üye işlev bağdaştırıcılarını nasıl kullanacağınızı gösteren bir örnek için bkz. [mem_fun](../standard-library/functional-functions.md#mem_fun) .
