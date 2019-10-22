---
title: time_put_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put_byname
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
ms.openlocfilehash: 4471c0df352a4d40d863ac36f0245cf8194f588c
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685460"
---
# <a name="time_put_byname-class"></a>time_put_byname Sınıfı

Türetilmiş sınıf şablonu, `time_put` \< CharType, OutputIterator > türünde bir yerel ayar modeli olarak işlev görebilecek bir nesne açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class OutIt = ostreambuf_iterator<CharType, char_traits<CharType>>>
class time_put_byname : public time_put<CharType, OutputIterator>
{
public:
    explicit time_put_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_put_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_put_byname();

};
```

### <a name="parameters"></a>Parametreler

*_Locname* \
Yerel ayar adı.

*_Refs* \
İlk başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Davranışı [adlandırılmış](../standard-library/locale-class.md#name) yerel ayar *_Locname*tarafından belirlenir. Her Oluşturucu temel nesnesini [time_put](../standard-library/time-put-class.md#time_put) \<CharType, OutputIterator > (`_Refs`) ile başlatır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
