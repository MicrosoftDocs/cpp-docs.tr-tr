---
description: 'Hakkında daha fazla bilgi edinin: time_get_byname sınıfı'
title: time_get_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_get_byname
helpviewer_keywords:
- time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
ms.openlocfilehash: 056681782d0e8edcc3d99ccf2b414b2b93db9986
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180285"
---
# <a name="time_get_byname-class"></a>time_get_byname Sınıfı

Türetilmiş sınıf şablonu, türünde bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlar `time_get` \<CharType, InputIterator> .

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

*_Locname*\
Adlandırılmış bir yerel ayar.

*_Refs*\
İlk başvuru sayısı.

## <a name="requirements"></a>Gereksinimler

Davranışı, adlandırılmış yerel ayar *_Locname* tarafından belirlenir. Her Oluşturucu temel nesnesini [time_get](../standard-library/time-get-class.md#time_get) \<CharType, InputIterator> () ile başlatır `_Refs` .

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
