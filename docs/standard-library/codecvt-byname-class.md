---
description: 'Hakkında daha fazla bilgi edinin: codecvt_byname sınıfı'
title: codecvt_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_byname
helpviewer_keywords:
- codecvt_byname class
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
ms.openlocfilehash: 526988f46b729e1a3d4ab6892d2c8f1fecba78a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234078"
---
# <a name="codecvt_byname-class"></a>codecvt_byname Sınıfı

Dönüşümlere ilişkin bir kültürel alanına özgü bilgilerin alınmasını sağlayan, verili bir yerel ayarın harmanlama modeli olarak işlev yapabilecek bir nesneyi tanımlayan türetilmiş bir sınıf şablonu.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class Byte, class StateType>
class codecvt_byname: public codecvt<CharType, Byte, StateType> {
public:
    explicit codecvt_byname(
    const char* _Locname,
    size_t _Refs = 0);
```

```cpp
explicit codecvt_byname(
    const string& _Locname,
    size_t _Refs = 0);
```

```cpp
protected:
    virtual ~codecvt_byname();

};
```

### <a name="parameters"></a>Parametreler

*_Locname*\
Adlandırılmış bir yerel ayar.

*_Refs*\
İlk başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Adlandırılmış bir yerel ayar oluşturulduğunda, byname modelleri otomatik olarak oluşturulur.

Davranışı, adlandırılmış yerel ayar *_Locname* tarafından belirlenir. Her Oluşturucu temel nesnesini [codecvt](../standard-library/codecvt-class.md) \<CharType, Byte, StateType> () ile başlatır `_Refs` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
