---
title: ctype_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype_byname
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
ms.openlocfilehash: 0b0f33781cc9f1f54661a44a5434c94316432a45
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457892"
---
# <a name="ctypebyname-class"></a>ctype_byname Sınıfı

Türetilmiş şablon sınıfı, belirli bir yerel ayarın CType modeli olarak işlev görebilecek bir nesne tanımlar, bu da karakterlerin sınıflandırılmasını ve büyük/küçük harf ve yerel olarak belirtilen karakter kümeleri arasında karakter dönüştürülmesini etkinleştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```

## <a name="remarks"></a>Açıklamalar

Davranışı, adlandırılmış yerel ayar `_Locname`tarafından belirlenir. Her Oluşturucu kendi temel nesnesini [CType](../standard-library/ctype-class.md)\<CharType > ( `_Refs`) veya temel sınıf `ctype<char>`için eşdeğer ile başlatır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
