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
ms.openlocfilehash: 39db2ead78a123c3274405e3560bca1c67cf1f5c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854148"
---
# <a name="timeputbyname-class"></a>time_put_byname Sınıfı

Türetilen Şablon sınıfı türü bir yerel ayar model hizmet verebilir bir nesneyi tanımlayan `time_put` \< CharType, OutputIterator >.

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

`_Locname` Yerel ayar adı.

`_Refs` Bir başlangıç başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Davranışını tarafından belirlenen [adlı](../standard-library/locale-class.md#name) yerel ayar `_Locname`. Her oluşturucu temel nesnesiyle başlatır [time_put](../standard-library/time-put-class.md#time_put)\<CharType, OutputIterator > ( `_Refs`).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
