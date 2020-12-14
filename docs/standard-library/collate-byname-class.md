---
description: 'Hakkında daha fazla bilgi edinin: collate_byname sınıfı'
title: collate_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- locale/std::collate_byname
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
ms.openlocfilehash: 8e5ee60a2415fe6fede6db387c774151b97396dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233961"
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

*_Locname*\
Adlandırılmış bir yerel ayar.

*_Refs*\
İlk başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, [harmanlama](../standard-library/collate-class.md#collate)türünde bir [yerel ayar modeli](../standard-library/locale-class.md#facet_class) olarak kullanılabilecek bir nesneyi tanımlar \<CharType> . Davranışı, [adlandırılmış](../standard-library/locale-class.md#name) yerel ayar *_Locname* tarafından belirlenir. Her Oluşturucu kendi temel nesnesini [COLLATE](../standard-library/collate-class.md#collate) \<CharType> () ile başlatır `_Refs` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
