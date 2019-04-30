---
title: moneypunct_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::moneypunct_byname
helpviewer_keywords:
- moneypunct_byname class
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
ms.openlocfilehash: 003ba2136e779c444c7edad9b1759a861a8b0803
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383561"
---
# <a name="moneypunctbyname-class"></a>moneypunct_byname Sınıfı

Olarak hizmet verebilen bir nesneyi tanımlayan türetilmiş bir şablon sınıfı bir `moneypunct` parasal biçimlendirme etkinleştirme verili bir yerel ayar modeli giriş alanını veya parasal çıkış alanları.

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

Davranışını adlandırılmış yerel ayar tarafından belirlenir `_Locname`. Her Oluşturucu, temel nesnesiyle başlatır [moneypunct](../standard-library/moneypunct-class.md#moneypunct)\<CharType, uluslararası > ( `_Refs`).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
