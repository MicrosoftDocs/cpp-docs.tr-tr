---
title: collate_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- locale/std::collate_byname
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
ms.openlocfilehash: 3e9a256ac7bdb5f6d077746fe2a08990ed41e931
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688265"
---
# <a name="collate_byname-class"></a>collate_byname Sınıfı

Belirli bir yerel ayarın bir harmanlama modeli olarak işlev yapabilecek bir nesneyi tanımlayan, dize sıralama kurallarıyla ilgili bir kültürel alanına özgü bilgilerin alınmasını sağlayan türetilmiş bir sınıf şablonu.

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

*_Locname* \
Adlandırılmış bir yerel ayar.

*_Refs* \
İlk başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, > \<CharType [harmanlama](../standard-library/collate-class.md#collate) türünde bir [yerel ayar modeli](../standard-library/locale-class.md#facet_class) olarak kullanılabilecek bir nesneyi tanımlar. Davranışı [adlandırılmış](../standard-library/locale-class.md#name) yerel ayar *_Locname*tarafından belirlenir. Her Oluşturucu temel nesnesini [collate](../standard-library/collate-class.md#collate) \<CharType > (`_Refs`) ile başlatır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
