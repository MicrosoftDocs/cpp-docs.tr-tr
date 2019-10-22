---
title: moneypunct_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::moneypunct_byname
helpviewer_keywords:
- moneypunct_byname class
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
ms.openlocfilehash: c687bc870e4d78cfe9174eb04ea09c34d6a9c955
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687665"
---
# <a name="moneypunct_byname-class"></a>moneypunct_byname Sınıfı

Verilen bir yerel ayarın `moneypunct` modeli olarak işlev görebilecek, parasal giriş alanı veya parasal çıkış alanlarını biçimlendirmeyi sağlayan bir nesneyi tanımlayan türetilmiş bir sınıf şablonu.

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

Davranışı, adlandırılmış yerel ayar `_Locname` tarafından belirlenir. Her Oluşturucu kendi temel nesnesini [moneypunct](../standard-library/moneypunct-class.md#moneypunct) \<CharType, Intl > (`_Refs`) ile başlatır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
