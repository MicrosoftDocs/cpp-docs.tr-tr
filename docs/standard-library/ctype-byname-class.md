---
title: ctype_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype_byname
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
ms.openlocfilehash: dcaaff45fb33155710f788af4ceb657eff97464e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689741"
---
# <a name="ctype_byname-class"></a>ctype_byname Sınıfı

Türetilmiş sınıf şablonu, belirli bir yerel ayarın CType modeli olarak işlev görebilecek bir nesne tanımlar, bu durum, büyük/küçük harf ve yerel olarak belirtilen karakter kümeleri arasında karakterlerin sınıflandırılmasını ve karakter dönüştürülmesini etkinleştirir.

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

Davranışı, adlandırılmış yerel ayar `_Locname` tarafından belirlenir. Her Oluşturucu temel nesnesini [CType](../standard-library/ctype-class.md) \<CharType > (`_Refs`) veya temel sınıf `ctype<char>` eşdeğerini ile başlatır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
