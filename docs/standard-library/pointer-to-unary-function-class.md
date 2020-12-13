---
description: 'Hakkında daha fazla bilgi edinin: pointer_to_unary_function sınıfı'
title: pointer_to_unary_function Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_unary
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
ms.openlocfilehash: 45a927add90915bcbd8791eeba5561027b7e9217
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340703"
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

*pFunc*\
Dönüştürülecek ikili işlev.

*tarafta*\
*\* PFunc* 'ın çağrıldığı nesne.

## <a name="return-value"></a>Dönüş Değeri

Sınıf şablonu bir kopyasını depolar `pfunc` . Üye işlevini `operator()` döndüren ( \* **pFunc**) (_ *Left*) olarak tanımlar.

## <a name="remarks"></a>Açıklamalar

Birli işlev işaretçisi bir işlev nesnesidir ve parametre olarak birli bir işlev bekleyen C++ standart kitaplık algoritmasına geçirilebilir, ancak uyumlu değil. Bir değer bağlamak veya bir negatifi ile kullanmak gibi bir bağdaştırıcı ile kullanmak için, iç içe geçmiş türleriyle birlikte sağlanmalı `argument_type` ve `result_type` Bu tür bir uyarlama olması gerekir. Tarafından dönüştürme, `pointer_to_unary_function` işlev bağdaştırıcılarını ikili işlev işaretçileriyle çalışmasına izin verir.

## <a name="example"></a>Örnek

Oluşturucusu `pointer_to_unary_function` nadiren doğrudan kullanılır. Bağdaştırıcı koşulunu bildirme ve kullanma hakkında bir örnek için bkz. yardımcı işlevi [ptr_fun](../standard-library/functional-functions.md#ptr_fun) `pointer_to_unary_function` .
