---
title: time_get_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_get_byname
helpviewer_keywords:
- time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
ms.openlocfilehash: 9df3831e085f1dea1df45ff9368479fa516b944e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685767"
---
# <a name="time_get_byname-class"></a>time_get_byname Sınıfı

Türetilmiş sınıf şablonu, `time_get` \<CharType, InputIterator > türünde bir yerel ayar modeli olarak işlev görebilecek bir nesne açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class InputIterator =
    istreambuf_iterator<CharType, char_traits<CharType>>>
class time_get_byname : public time_get<CharType, InputIterator>
{
public:
    explicit time_get_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_get_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_get_byname()
};
```

### <a name="parameters"></a>Parametreler

*_Locname* \
Adlandırılmış bir yerel ayar.

*_Refs* \
İlk başvuru sayısı.

## <a name="requirements"></a>Gereksinimler

Davranışı adlandırılmış yerel ayar *_Locname*tarafından belirlenir. Her Oluşturucu temel nesnesini [time_get](../standard-library/time-get-class.md#time_get) \<CharType, InputIterator > (`_Refs`) ile başlatır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
