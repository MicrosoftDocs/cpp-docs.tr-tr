---
title: time_get_byname sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xloctime/std::time_get_byname
dev_langs:
- C++
helpviewer_keywords:
- time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 004c35e3c09f8acc55980024e4752ab26a26afa1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="timegetbyname-class"></a>time_get_byname Sınıfı

Türetilen Şablon sınıfı türü bir yerel ayar model hizmet verebilir bir nesneyi tanımlayan `time_get` \<CharType, InputIterator >.

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

`_Locname` Adlandırılmış bir yerel ayar.

`_Refs` Bir başlangıç başvuru sayısı.

## <a name="requirements"></a>Gereksinimler

Davranışını adlandırılmış bölgeye göre belirlenir `_Locname`. Her oluşturucu temel nesnesiyle başlatır [time_get](../standard-library/time-get-class.md#time_get)\<CharType, InputIterator > ( `_Refs`).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
