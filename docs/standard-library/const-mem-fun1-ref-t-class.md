---
title: const_mem_fun1_ref_t Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::const_mem_fun1_ref_t
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
ms.openlocfilehash: e90ac09543c0704cf900e0fc5448e295034dcb66
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516458"
---
# <a name="constmemfun1reft-class"></a>const_mem_fun1_ref_t Sınıfı

İzin veren bir bağdaştırıcı sınıfı bir **const** bir başvuru bağımsız değişkeni ile hazırlarken bir ikili fonksiyon nesnesi olarak çağrılan tek bir bağımsız değişken alan üye işlevi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_ref_t
: public binary_function<Type, Arg, Result>
{
    explicit const_mem_fun1_ref_t(Result (Type::* Pm)(Arg) const);
    Result operator()(const Type& left, Arg right) const;
};
```

### <a name="parameters"></a>Parametreler

*PM*<br/>
Bir sınıfın üye işlevi işaretçisi `Type` bir işlev nesnesi için dönüştürülecek.

*Sol*<br/>
**Const** nesnesinin *Pm* üye işlevi çağrılır.

*sağ*<br/>
Bağımsız değişkeni için verilen *Pm*.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili fonksiyon.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir kopyasını depolar *Pm*, bir sınıfın bir üye işlevi işaretçisi olmalıdır `Type`, özel üye nesnesinde. Onun üye işlevini tanımlar `operator()` döndüren olarak ( `left`.\* *PM*) ( `right`) **const**.

## <a name="example"></a>Örnek

Oluşturucusuna `const_mem_fun1_ref_t` genellikle kullanılmaz doğrudan; yardımcı işlevini `mem_fun_ref` üye işlevleri uyum sağlamak için kullanılır. Bkz: [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) üye işlevi bağdaştırıcıları kullanma örnekleri için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
