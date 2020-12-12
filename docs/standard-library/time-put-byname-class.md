---
description: 'Hakkında daha fazla bilgi edinin: time_put_byname sınıfı'
title: time_put_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put_byname
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
ms.openlocfilehash: b519b28b7af8f5b54f9150d1d84f68cd6695bc49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167259"
---
# <a name="time_put_byname-class"></a>time_put_byname Sınıfı

Türetilmiş sınıf şablonu, türünde bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlar `time_put` \< CharType, OutputIterator > .

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

Davranışı, [adlandırılmış](../standard-library/locale-class.md#name) yerel ayar *_Locname* tarafından belirlenir. Her Oluşturucu temel nesnesini [time_put](../standard-library/time-put-class.md#time_put) \<CharType, OutputIterator> () ile başlatır `_Refs` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
