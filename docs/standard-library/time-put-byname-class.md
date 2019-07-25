---
title: time_put_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put_byname
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
ms.openlocfilehash: 2da2bf4ea1c709b820c1a82dc20e288634139a83
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460000"
---
# <a name="timeputbyname-class"></a>time_put_byname Sınıfı

Türetilmiş şablon sınıfı, CharType, OutputIterator > türünde `time_put` \< bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlar.

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

*_Locname*\
Yerel ayar adı.

*_Refs*\
İlk başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Davranışı [adlandırılmış](../standard-library/locale-class.md#name) yerel ayar *_Locname*tarafından belirlenir. Her Oluşturucu temel nesnesini [time_put](../standard-library/time-put-class.md#time_put)\<CharType, OutputIterator > (`_Refs`) ile başlatır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
