---
title: messages_byname sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xlocmes/std::messages_byname
dev_langs:
- C++
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 075c708260886c45c3850062671969bc331c6343
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="messagesbyname-class"></a>messages_byname Sınıfı

Türetilen Şablon sınıfı yerelleştirilmiş iletileri alma etkinleştirme belirli bir yerel bir ileti modeli kullanılabileceği bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class messages_byname : public messages<CharType> {
public:
    explicit messages_byname(
    const char *_Locname,
    size_t _Refs = 0);

    explicit messages_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~messages_byname();

};
```

### <a name="parameters"></a>Parametreler

`_Locname` Adlandırılmış bir yerel ayar.

`_Refs` Bir başlangıç başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Davranışını adlandırılmış bölgeye göre belirlenir `_Locname`. Her oluşturucu temel nesnesiyle başlatır [iletileri](../standard-library/messages-class.md#messages)\<CharType > ( `_Refs`).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
