---
title: moneypunct_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::moneypunct_byname
helpviewer_keywords:
- moneypunct_byname class
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
ms.openlocfilehash: 47c9d2281973cb57288bfdcf865926fb6dd9ed0e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460204"
---
# <a name="moneypunctbyname-class"></a>moneypunct_byname Sınıfı

Parasal giriş alanını veya parasal çıkış alanlarını biçimlendirmeyi etkinleştirerek, belirli bir yerel `moneypunct` ayarın modeli olarak işlev yapabilecek bir nesneyi tanımlayan türetilmiş bir şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, bool Intl = false>
class moneypunct_byname : public moneypunct<CharType, Intl>
{
public:
    explicit moneypunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit moneypunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~moneypunct_byname();

};
```

## <a name="remarks"></a>Açıklamalar

Davranışı, adlandırılmış yerel ayar `_Locname`tarafından belirlenir. Her Oluşturucu kendi temel nesnesini [moneypunct](../standard-library/moneypunct-class.md#moneypunct)\<CharType, Intl > ( `_Refs`) ile başlatır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
