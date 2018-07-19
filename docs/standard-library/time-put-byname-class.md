---
title: time_put_byname sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xloctime/std::time_put_byname
dev_langs:
- C++
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10c01fcc7c75fb3ea9abf5803f5f17d3bd378333
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953907"
---
# <a name="timeputbyname-class"></a>time_put_byname Sınıfı

Türetilmiş bir şablon sınıfı türü bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan `time_put` \< CharType, Outputıterator >.

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

*_Locname*  
 Bir yerel ayar adı.

*_Refs*  
 Bir ilk başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Davranışını tarafından belirlenen [adlı](../standard-library/locale-class.md#name) yerel *_Locname*. Her Oluşturucu, temel nesnesiyle başlatır [time_put](../standard-library/time-put-class.md#time_put)\<CharType, Outputıterator > (`_Refs`).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
