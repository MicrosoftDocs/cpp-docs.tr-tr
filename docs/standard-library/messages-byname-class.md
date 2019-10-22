---
title: messages_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_byname
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
ms.openlocfilehash: 56d8931cb404d9c0f3f5113f8b2ca0f1158209f2
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689337"
---
# <a name="messages_byname-class"></a>messages_byname Sınıfı

Türetilmiş sınıf şablonu, yerelleştirilmiş iletilerin alınmasını etkinleştirerek, belirli bir yerel ayarın ileti modeli olarak işlev görebilecek bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class messages_byname : public messages<CharType> {
public:
    explicit messages_byname(
    const char *_Locname,
    size_t _Refs = 0);

    explicit messages_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~messages_byname();

};
```

### <a name="parameters"></a>Parametreler

*_Locname* \
Adlandırılmış bir yerel ayar.

*_Refs* \
İlk başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Davranışı adlandırılmış yerel ayar *_Locname*tarafından belirlenir. Her Oluşturucu kendi temel nesnesini \<CharType > (`_Refs`) [iletileriyle](../standard-library/messages-class.md#messages) başlatır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
