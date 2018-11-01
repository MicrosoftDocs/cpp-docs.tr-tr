---
title: mem_fun1_t Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::mem_fun1_t
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
ms.openlocfilehash: 9a1fe26e66eb2ad20e6889b95640fadd2b3c45a0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613217"
---
# <a name="memfun1t-class"></a>mem_fun1_t Sınıfı

İzin veren bir bağdaştırıcı sınıfı bir `non_const` bir işaretçi bağımsız değişkeni ile hazırlarken bir ikili fonksiyon nesnesi olarak çağrılan tek bir bağımsız değişken alan üye işlevi.

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

*_Pm*<br/>
Bir sınıfın üye işlevi işaretçisi `Type` bir işlev nesnesi için dönüştürülecek.

*_Pleft*<br/>
Nesne, *_Pm* üye işlevi çağrılır.

*sağ*<br/>
Bağımsız değişkeni için verilen *_Pm*.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili fonksiyon.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir kopyasını depolar *_Pm*, bir sınıfın bir üye işlevi işaretçisi olmalıdır `Type`, özel üye nesnesinde. Onun üye işlevini tanımlar `operator()` döndüren olarak ( **_Pleft** -> \* `_Pm`) ( **doğru**).

## <a name="example"></a>Örnek

Oluşturucusuna `mem_fun1_t` genellikle kullanılmaz doğrudan; yardımcı işlevini `mem_fun` üye işlevleri uyum sağlamak için kullanılır. Bkz: [mem_fun](../standard-library/functional-functions.md#mem_fun) üye işlevi bağdaştırıcıları kullanmayı gösteren bir örnek.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
