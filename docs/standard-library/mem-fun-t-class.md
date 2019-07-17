---
title: mem_fun_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun_t
helpviewer_keywords:
- mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
ms.openlocfilehash: 19ccd4835c4257a7f409bcf0f7bda1a898567458
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245080"
---
# <a name="memfunt-class"></a>mem_fun_t Sınıfı

İzin veren bir bağdaştırıcı sınıfı bir `non_const` hiçbir bağımsız değişken bir işaretçi bağımsız değişkeni ile hazırlarken bir birli işlev nesnesi olarak çağrılacak üye işlevi. C ++ 17 sürümünde kaldırılmıştır C ++ 11'de kullanım dışı.

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
Bir sınıfın üye işlevi işaretçisi `Type` bir işlev nesnesi için dönüştürülecek.

*_Pleft*\
Nesne, *_Pm* üye işlevi çağrılır.

## <a name="return-value"></a>Dönüş Değeri

Bir uyarlanabilir birli işlevi.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir kopyasını depolar *_Pm*, bir sınıfın bir üye işlevi işaretçisi olmalıdır `Type`, özel üye nesnesinde. Onun üye işlevini tanımlar `operator()` döndüren olarak (`_Pleft`->* `_Pm`) ().

## <a name="example"></a>Örnek

Oluşturucusuna `mem_fun_t` genellikle kullanılmaz doğrudan; yardımcı işlevini `mem_fun` üye işlevleri uyum sağlamak için kullanılır. Bkz: [mem_fun](../standard-library/functional-functions.md#mem_fun) üye işlevi bağdaştırıcıları kullanmayı gösteren bir örnek.
