---
description: 'Hakkında daha fazla bilgi edinin: pointer_to_binary_function sınıfı'
title: pointer_to_binary_function Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_binary
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
ms.openlocfilehash: 5cdecc297ff5c55c9b6c57b5b6ab029636f3958c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340716"
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

*pFunc*\
Dönüştürülecek ikili işlev.

*tarafta*\
*\* PFunc* 'ın çağrıldığı sol nesne.

*Right*\
*\* PFunc* 'ın çağrıldığı doğru nesne.

## <a name="return-value"></a>Dönüş Değeri

Sınıf şablonu bir kopyasını depolar `pfunc` . Üye işlevini `operator()` iade olarak tanımlar `(* pfunc)(Left, right)` .

## <a name="remarks"></a>Açıklamalar

Bir ikili işlev işaretçisi bir işlev nesnesidir ve bir parametre olarak ikili işlev bekleyen C++ standart kitaplık algoritmasına geçirilebilir, ancak uyumlu değil. Bir değeri kendisine bağlama veya bir negatifle ile birlikte kullanma gibi bir bağdaştırıcı ile kullanmak için, iç içe geçmiş türleriyle birlikte sağlanmalı `first_argument_type` `second_argument_type` ve `result_type` Bu tür bir uyarlama mümkün hale gelmelidir. Tarafından dönüştürme, `pointer_to_binary_function` işlev bağdaştırıcılarını ikili işlev işaretçileriyle çalışmasına izin verir.

## <a name="example"></a>Örnek

Oluşturucusu `pointer_to_binary_function` nadiren doğrudan kullanılır. Bağdaştırıcı koşulunu bildirme ve kullanma hakkında bir örnek için bkz. yardımcı işlevi [ptr_fun](../standard-library/functional-functions.md#ptr_fun) `pointer_to_binary_function` .
