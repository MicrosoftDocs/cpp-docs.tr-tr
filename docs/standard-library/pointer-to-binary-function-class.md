---
title: pointer_to_binary_function Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_binary
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
ms.openlocfilehash: 890ebb7d4c2b8fbd51a4460e21efba3e763ead7e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687185"
---
# <a name="pointer_to_binary_function-class"></a>pointer_to_binary_function Sınıfı

Bir ikili işlev işaretçisini uyarlanabilir tablo ikili işlevine dönüştürür. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```

### <a name="parameters"></a>Parametreler

*pFunc* \
Dönüştürülecek ikili işlev.

*sol* \
*@No__t_1pfunc* üzerinde çağrıldığı sol nesne.

*sağ* \
*@No__t_1pfunc* üzerinde çağrıldığı doğru nesne.

## <a name="return-value"></a>Dönüş Değeri

Sınıf şablonu `pfunc` bir kopyasını depolar. @No__t_1 döndüren `operator()` üye işlevini tanımlar.

## <a name="remarks"></a>Açıklamalar

İkili işlev işaretçisi bir işlev nesnesidir ve bir parametre olarak ikili işlev bekleyen C++ standart kitaplık algoritmasına geçirilebilir, ancak uyumlu değil. Bir değer bağlamak veya bir negatifle ile kullanmak gibi bir bağdaştırıcı ile kullanmak için, bu tür bir uyarlama yapan `first_argument_type`, `second_argument_type` ve `result_type` iç içe geçmiş türleriyle birlikte verilmelidir. @No__t_0 dönüşümü, işlev bağdaştırıcılarını ikili işlev işaretçileriyle çalışmasına izin verir.

## <a name="example"></a>Örnek

@No__t_0 Oluşturucusu nadiren doğrudan kullanılır. @No__t_1 bağdaştırıcı koşulunu bildirme ve kullanma hakkında bir örnek için bkz. [ptr_fun](../standard-library/functional-functions.md#ptr_fun) Helper function.
