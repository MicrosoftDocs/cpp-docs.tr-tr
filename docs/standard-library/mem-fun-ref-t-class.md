---
title: mem_fun_ref_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun_ref_t
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
ms.openlocfilehash: d8f5ef05d1bdeec694cdf22d7e7a163478127dfc
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687769"
---
# <a name="mem_fun_ref_t-class"></a>mem_fun_ref_t Sınıfı

Bir başvuru bağımsız değişkeniyle başlatıldığında bir birli işlev nesnesi olarak çağrılması için bağımsız değişken alan `non_const` üye işlevine izin veren bir bağdaştırıcı sınıfı. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

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

*_Pm* \
İşlev nesnesine dönüştürülecek `Type` sınıfının üye işlevine yönelik bir işaretçi.

*sol* \
*_Pm* üye işlevinin çağrıldığı nesne.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir birli işlev.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir özel üye nesnesinde `Type` sınıfının üye işlevine bir işaretçi olması gereken *_Pm*öğesinin bir kopyasını depolar. @No__t_0 üye işlevini, döndüren (**Left**. * `_Pm`) () olarak tanımlar.

## <a name="example"></a>Örnek

@No__t_0 Oluşturucusu genellikle doğrudan kullanılmaz; `mem_fun_ref` yardımcı işlevi, üye işlevlerini uyarlamak için kullanılır. Üye işlev bağdaştırıcılarını nasıl kullanacağınızı gösteren bir örnek için bkz. [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) .
