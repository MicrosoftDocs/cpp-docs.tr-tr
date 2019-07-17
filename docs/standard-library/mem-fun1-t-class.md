---
title: mem_fun1_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_t
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
ms.openlocfilehash: 822de97849750a72948137ba8fe23beab8554ff5
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245094"
---
# <a name="memfun1t-class"></a>mem_fun1_t Sınıfı

İzin veren bir bağdaştırıcı sınıfı bir `non_const` bir işaretçi bağımsız değişkeni ile hazırlarken bir ikili fonksiyon nesnesi olarak çağrılan tek bir bağımsız değişken alan üye işlevi. C ++ 17 sürümünde kaldırılmıştır C ++ 11'de kullanım dışı.

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
Bir sınıfın üye işlevi işaretçisi `Type` bir işlev nesnesi için dönüştürülecek.

*_Pleft*\
Nesne, *_Pm* üye işlevi çağrılır.

*sağ*\
Bağımsız değişkeni için verilen *_Pm*.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili fonksiyon.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir kopyasını depolar *_Pm*, bir sınıfın bir üye işlevi işaretçisi olmalıdır `Type`, özel üye nesnesinde. Onun üye işlevini tanımlar `operator()` döndüren olarak ( **_Pleft** -> \* `_Pm`) (**doğru**).

## <a name="example"></a>Örnek

Oluşturucusuna `mem_fun1_t` genellikle kullanılmaz doğrudan; yardımcı işlevini `mem_fun` üye işlevleri uyum sağlamak için kullanılır. Bkz: [mem_fun](../standard-library/functional-functions.md#mem_fun) üye işlevi bağdaştırıcıları kullanmayı gösteren bir örnek.
