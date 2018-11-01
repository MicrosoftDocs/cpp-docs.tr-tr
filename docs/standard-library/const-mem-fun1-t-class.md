---
title: const_mem_fun1_t Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::const_mem_fun1_t
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
ms.openlocfilehash: 53724c3d9b795d8cbde7a4bcda3531e43d41c4a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548795"
---
# <a name="constmemfun1t-class"></a>const_mem_fun1_t Sınıfı

İzin veren bir bağdaştırıcı sınıfı bir **const** bir işaretçi bağımsız değişkeni ile hazırlarken bir ikili fonksiyon nesnesi olarak çağrılan tek bir bağımsız değişken alan üye işlevi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_t : public binary_function<const Type *, Arg, Result>
{
    explicit const_mem_fun1_t(Result (Type::* _Pm)(Arg) const);
    Result operator()(const Type* _Pleft, Arg right) const;
};
```

### <a name="parameters"></a>Parametreler

*_Pm*<br/>
Bir sınıfın üye işlevi işaretçisi `Type` bir işlev nesnesi için dönüştürülecek.

*_Pleft*<br/>
**Const** nesnesinin *_Pm* üye işlevi çağrılır.

*sağ*<br/>
Bağımsız değişkeni için verilen *_Pm*.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili fonksiyon.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir kopyasını depolar *_Pm*, bir sınıfın bir üye işlevi işaretçisi olmalıdır `Type`, özel üye nesnesinde. Onun üye işlevini tanımlar `operator()` döndüren olarak ( *_Pleft*->\*<em>Pm</em>) ( *doğru* ) **const**.

## <a name="example"></a>Örnek

Oluşturucusuna `const_mem_fun1_t` genellikle kullanılmaz doğrudan; yardımcı işlevini `mem_fun` üye işlevleri uyum sağlamak için kullanılır. Bkz: [mem_fun](../standard-library/functional-functions.md#mem_fun) üye işlevi bağdaştırıcıları kullanmayı gösteren bir örnek.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
