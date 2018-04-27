---
title: collate_byname sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- locale/std::collate_byname
dev_langs:
- C++
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41b5be0df93fcc5fcb1c1c18eddb0b051f1da8a8
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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

`_Locname` Adlandırılmış bir yerel ayar.

`_Refs` Bir başlangıç başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı olarak hizmet verebilir bir nesneyi tanımlayan bir [yerel model](../standard-library/locale-class.md#facet_class) türü [collate](../standard-library/collate-class.md#collate)\<CharType >. Davranışını tarafından belirlenen [adlı](../standard-library/locale-class.md#name) yerel ayar `_Locname`. Her oluşturucu temel nesnesiyle başlatır [collate](../standard-library/collate-class.md#collate)\<CharType > ( `_Refs`).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
