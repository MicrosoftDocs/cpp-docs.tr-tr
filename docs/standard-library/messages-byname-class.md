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
ms.openlocfilehash: e03cb627e7e9db40d56a69112977d87141626696
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100450"
---
# <a name="messagesbyname-class"></a>messages_byname Sınıfı

Türetilmiş bir şablon sınıfı yerelleştirilmiş iletilerin alınmasını sağlayan verili bir yerel ayar, bir ileti modeli olarak hizmet verebilen bir nesneyi tanımlar.

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

*_Locname*<br/>
Adlandırılmış bir yerel ayar.

*_Refs*<br/>
Bir ilk başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Davranışını adlandırılmış yerel ayar tarafından belirlenir *_Locname*. Her Oluşturucu, temel nesnesiyle başlatır [iletileri](../standard-library/messages-class.md#messages)\<CharType > ( `_Refs`).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
