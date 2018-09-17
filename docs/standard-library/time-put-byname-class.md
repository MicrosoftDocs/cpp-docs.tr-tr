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
ms.openlocfilehash: 62d78fb7c2b9cbaee62baf59636303f90177cf7b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699601"
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

*_Locname*<br/>
Bir yerel ayar adı.

*_Refs*<br/>
Bir ilk başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Davranışını tarafından belirlenen [adlı](../standard-library/locale-class.md#name) yerel *_Locname*. Her Oluşturucu, temel nesnesiyle başlatır [time_put](../standard-library/time-put-class.md#time_put)\<CharType, Outputıterator > (`_Refs`).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
