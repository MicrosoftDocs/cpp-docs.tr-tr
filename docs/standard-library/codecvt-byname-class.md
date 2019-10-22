---
title: codecvt_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_byname
helpviewer_keywords:
- codecvt_byname class
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
ms.openlocfilehash: b48f01126eba7082230fc5e19150d42d1dfad2f3
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688302"
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

*_Locname* \
Adlandırılmış bir yerel ayar.

*_Refs* \
İlk başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Adlandırılmış bir yerel ayar oluşturulduğunda, byname modelleri otomatik olarak oluşturulur.

Davranışı adlandırılmış yerel ayar *_Locname*tarafından belirlenir. Her Oluşturucu temel nesnesini [codecvt](../standard-library/codecvt-class.md) \<CharType, Byte, statetype > (`_Refs`) ile başlatır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
