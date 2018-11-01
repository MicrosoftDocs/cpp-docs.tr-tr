---
title: mem_fun_t Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::mem_fun_t
helpviewer_keywords:
- mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
ms.openlocfilehash: 32c66eb20215bc68efd0f0bb43c30f951da1bae9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456374"
---
# <a name="memfunt-class"></a>mem_fun_t Sınıfı

İzin veren bir bağdaştırıcı sınıfı bir `non_const` hiçbir bağımsız değişken bir işaretçi bağımsız değişkeni ile hazırlarken bir birli işlev nesnesi olarak çağrılacak üye işlevi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;

};
```

### <a name="parameters"></a>Parametreler

*_Pm*<br/>
Bir sınıfın üye işlevi işaretçisi `Type` bir işlev nesnesi için dönüştürülecek.

*_Pleft*<br/>
Nesne, *_Pm* üye işlevi çağrılır.

## <a name="return-value"></a>Dönüş Değeri

Bir uyarlanabilir birli işlevi.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir kopyasını depolar *_Pm*, bir sınıfın bir üye işlevi işaretçisi olmalıdır `Type`, özel üye nesnesinde. Onun üye işlevini tanımlar `operator()` döndüren olarak ( `_Pleft` ->*  `_Pm`) ().

## <a name="example"></a>Örnek

Oluşturucusuna `mem_fun_t` genellikle kullanılmaz doğrudan; yardımcı işlevini `mem_fun` üye işlevleri uyum sağlamak için kullanılır. Bkz: [mem_fun](../standard-library/functional-functions.md#mem_fun) üye işlevi bağdaştırıcıları kullanmayı gösteren bir örnek.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<işlev >](../standard-library/functional.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
