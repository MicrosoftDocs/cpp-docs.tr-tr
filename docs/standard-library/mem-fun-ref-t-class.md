---
title: mem_fun_ref_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun_ref_t
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
ms.openlocfilehash: 0879736863a9b8052d19cc86dc5636ba14bcf993
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240603"
---
# <a name="memfunreft-class"></a>mem_fun_ref_t Sınıfı

İzin veren bir bağdaştırıcı sınıfı bir `non_const` hiçbir bağımsız değişken olarak bir başvuru bağımsız değişkeni ile hazırlarken bir birli işlev nesnesi çağrılacak üye işlevi. C ++ 17 sürümünde kaldırılmıştır C ++ 11'de kullanım dışı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Result, class Type>
class mem_fun_ref_t : public unary_function<Type, Result> {
    explicit mem_fun_ref_t(
    Result (Type::* _Pm)());

    Result operator()(Type& left) const;
};
```

### <a name="parameters"></a>Parametreler

*_Pm*\
Bir sınıfın üye işlevi işaretçisi `Type` bir işlev nesnesi için dönüştürülecek.

*Sol*\
Nesne, *_Pm* üye işlevi çağrılır.

## <a name="return-value"></a>Dönüş Değeri

Bir uyarlanabilir birli işlevi.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir kopyasını depolar *_Pm*, bir sınıfın bir üye işlevi işaretçisi olmalıdır `Type`, özel üye nesnesinde. Onun üye işlevini tanımlar `operator()` döndüren olarak (**sol**. * `_Pm`) ().

## <a name="example"></a>Örnek

Oluşturucusuna `mem_fun_ref_t` genellikle kullanılmaz doğrudan; yardımcı işlevini `mem_fun_ref` üye işlevleri uyum sağlamak için kullanılır. Bkz: [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) üye işlevi bağdaştırıcıları kullanmayı gösteren bir örnek.
