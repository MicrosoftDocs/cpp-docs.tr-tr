---
title: time_get_byname sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xloctime/std::time_get_byname
dev_langs:
- C++
helpviewer_keywords:
- time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9858bfe4dc1d2451e4cd5054c5909aab27ef86c3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710014"
---
# <a name="timegetbyname-class"></a>time_get_byname Sınıfı

Türetilmiş bir şablon sınıfı türü bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan `time_get` \<CharType, Inputıterator >.

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

*_Locname*<br/>
Adlandırılmış bir yerel ayar.

*_Refs*<br/>
Bir ilk başvuru sayısı.

## <a name="requirements"></a>Gereksinimler

Davranışını adlandırılmış yerel ayar tarafından belirlenir *_Locname*. Her Oluşturucu, temel nesnesiyle başlatır [time_get](../standard-library/time-get-class.md#time_get)\<CharType, Inputıterator > ( `_Refs`).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
