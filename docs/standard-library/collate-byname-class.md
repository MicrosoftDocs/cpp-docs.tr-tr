---
title: collate_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- locale/std::collate_byname
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
ms.openlocfilehash: 46eb139bafcf7368688f32cce37e38362c158c91
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569607"
---
# <a name="collatebyname-class"></a>collate_byname Sınıfı

Dize sıralama kurallarıyla ilgili kültürel bir alana özgü bilgilerin alınmasını sağlayan, verili yerel ayarın bir harmanlama modeli olarak hizmet verebilen bir nesneyi tanımlayan türetilmiş bir şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class collate_byname : public collate<CharType> {
public:
    explicit collate_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit collate_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~collate_byname();

};
```

### <a name="parameters"></a>Parametreler

*_Locname*<br/>
Adlandırılmış bir yerel ayar.

*_Refs*<br/>
Bir ilk başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı olarak hizmet verebilen bir nesneyi tanımlayan bir [yerel ayar modeli](../standard-library/locale-class.md#facet_class) türü [collate](../standard-library/collate-class.md#collate)\<CharType >. Davranışını tarafından belirlenen [adlı](../standard-library/locale-class.md#name) yerel *_Locname*. Her Oluşturucu, temel nesnesiyle başlatır [collate](../standard-library/collate-class.md#collate)\<CharType > ( `_Refs`).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
