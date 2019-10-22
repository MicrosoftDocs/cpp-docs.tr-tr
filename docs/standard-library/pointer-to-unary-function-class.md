---
title: pointer_to_unary_function Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_unary
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
ms.openlocfilehash: 2b6bf82faa39e22c5af584a9fc3ebf68f5851463
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689135"
---
# <a name="pointer_to_unary_function-class"></a>pointer_to_unary_function Sınıfı

Birli işlev işaretçisini uyarlanabilir tablo birli işlevine dönüştürür. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```

### <a name="parameters"></a>Parametreler

*pFunc* \
Dönüştürülecek ikili işlev.

*sol* \
*@No__t_1pfunc* çağrılan nesne.

## <a name="return-value"></a>Dönüş Değeri

Sınıf şablonu `pfunc` bir kopyasını depolar. @No__t_0 üye işlevini, döndüren (\* **pFunc**) (_ *Left*) olarak tanımlar.

## <a name="remarks"></a>Açıklamalar

Birli işlev işaretçisi bir işlev nesnesidir ve parametre olarak birli bir işlev bekleyen C++ standart kitaplık algoritmasına geçirilebilir, ancak uyumlu değil. Bir değeri kendisine bağlama veya bir negatifle ile birlikte kullanma gibi bir bağdaştırıcı ile kullanmak için, bu tür bir uyarlama sağlayan `argument_type` ve `result_type` iç içe geçmiş türlerle sağlanmalıdır. @No__t_0 dönüşümü, işlev bağdaştırıcılarını ikili işlev işaretçileriyle çalışmasına izin verir.

## <a name="example"></a>Örnek

@No__t_0 Oluşturucusu nadiren doğrudan kullanılır. @No__t_1 bağdaştırıcı koşulunu bildirme ve kullanma hakkında bir örnek için bkz. [ptr_fun](../standard-library/functional-functions.md#ptr_fun) Helper function.
