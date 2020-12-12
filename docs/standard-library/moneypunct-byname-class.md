---
description: 'Hakkında daha fazla bilgi edinin: moneypunct_byname sınıfı'
title: moneypunct_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::moneypunct_byname
helpviewer_keywords:
- moneypunct_byname class
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
ms.openlocfilehash: b20293ac6788156f25f95878a5ab0098c178edec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277472"
---
# <a name="moneypunct_byname-class"></a>moneypunct_byname Sınıfı

`moneypunct`Parasal giriş alanını veya parasal çıkış alanlarını biçimlendirmeyi etkinleştirerek, belirli bir yerel ayarın bir modeli olarak işlev yapabilecek bir nesneyi tanımlayan türetilmiş bir sınıf şablonu.

## <a name="syntax"></a>Syntax

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

Davranışı, adlandırılmış yerel ayar tarafından belirlenir `_Locname` . Her Oluşturucu kendi temel nesnesini [moneypunct](../standard-library/moneypunct-class.md#moneypunct) \<CharType, Intl> () ile başlatır `_Refs` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
