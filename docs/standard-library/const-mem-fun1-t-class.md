---
title: const_mem_fun1_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_t
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
ms.openlocfilehash: 8ccd9d7e58b9cadec83b64df5553564db20a5745
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244523"
---
# <a name="constmemfun1t-class"></a>const_mem_fun1_t Sınıfı

İzin veren bir bağdaştırıcı sınıfı bir **const** bir işaretçi bağımsız değişkeni ile hazırlarken bir ikili fonksiyon nesnesi olarak çağrılan tek bir bağımsız değişken alan üye işlevi. C ++ 17 sürümünde kaldırılmıştır C ++ 11'de kullanım dışı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_t : public binary_function<const Type *, Arg, Result>
{
    explicit const_mem_fun1_t(Result (Type::* member_ptr)(Arg) const);
    Result operator()(const Type* left, Arg right) const;
};
```

### <a name="parameters"></a>Parametreler

*member_ptr*\
Bir sınıfın üye işlevi işaretçisi `Type` bir işlev nesnesi için dönüştürülecek.

*Sol*\
**Const** nesnesinin *member_ptr* üye işlevi çağrılır.

*sağ*\
Bağımsız değişkeni için verilen *member_ptr*.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili fonksiyon.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir kopyasını depolar *member_ptr*, bir sınıfın bir üye işlevi işaretçisi olmalıdır `Type`, özel üye nesnesinde. Onun üye işlevini tanımlar `operator()` döndüren olarak `(left->member_ptr)(right) const`.

## <a name="example"></a>Örnek

Oluşturucusuna `const_mem_fun1_t` doğrudan nadiren kullanılır. `mem_fn` üye işlevleri uyum sağlamak için kullanılır. Bkz: [mem_fn](../standard-library/functional-functions.md#mem_fn) üye işlevi bağdaştırıcıları kullanmayı gösteren bir örnek.
