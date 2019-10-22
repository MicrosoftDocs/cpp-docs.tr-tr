---
title: const_mem_fun1_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_t
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
ms.openlocfilehash: 1af44635400037c6359b13c4f2925c3ac7f2d9d5
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689744"
---
# <a name="const_mem_fun1_t-class"></a>const_mem_fun1_t Sınıfı

Bir işaretçi bağımsız değişkeniyle başlatıldığında bir ikili işlev nesnesi olarak çağrılması için tek bir bağımsız değişken alan bir **const** üye işlevine izin veren bir bağdaştırıcı sınıfı. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

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

*member_ptr* \
İşlev nesnesine dönüştürülecek `Type` sınıfının üye işlevine yönelik bir işaretçi.

*sol* \
*Member_ptr* member işlevinin çağrıldığı **const** nesnesi.

*sağ* \
*Member_ptr*öğesine verilen bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili işlev.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir özel üye nesnesinde `Type` sınıfının üye işlevine bir işaretçi olması gereken bir *member_ptr*kopyasını depolar. @No__t_1 döndüren `operator()` üye işlevini tanımlar.

## <a name="example"></a>Örnek

@No__t_0 Oluşturucusu nadiren doğrudan kullanılır. `mem_fn`, üye işlevlerini uyarlamak için kullanılır. Üye işlev bağdaştırıcılarını nasıl kullanacağınızı gösteren bir örnek için bkz. [mem_fn](../standard-library/functional-functions.md#mem_fn) .
