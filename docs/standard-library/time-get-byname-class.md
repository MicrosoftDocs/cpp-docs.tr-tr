---
title: time_get_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_get_byname
helpviewer_keywords:
- time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
ms.openlocfilehash: 040d140fa4250ad33e20d1c2724b6f563e865e6b
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742664"
---
# <a name="time_get_byname-class"></a>time_get_byname Sınıfı

Türetilmiş sınıf şablonu, türünde bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlar `time_get` \<CharType, InputIterator> .

## <a name="syntax"></a>Söz dizimi

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

*_Locname*\
Adlandırılmış bir yerel ayar.

*_Refs*\
İlk başvuru sayısı.

## <a name="requirements"></a>Gereksinimler

Davranışı, adlandırılmış yerel ayar *_Locname*tarafından belirlenir. Her Oluşturucu temel nesnesini [time_get](../standard-library/time-get-class.md#time_get) \<CharType, InputIterator> () ile başlatır `_Refs` .

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
