---
title: messages_byname sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmes/std::messages_byname
dev_langs:
- C++
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eab07f19f9d5025eba1ffe82c7e23066683b6267
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852985"
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
