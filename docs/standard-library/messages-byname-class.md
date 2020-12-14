---
description: 'Hakkında daha fazla bilgi edinin: messages_byname sınıfı'
title: messages_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_byname
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
ms.openlocfilehash: 960db9dd411e4ac42f81a0027e91ae1001b7877d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230529"
---
# <a name="messages_byname-class"></a>messages_byname Sınıfı

Türetilmiş sınıf şablonu, yerelleştirilmiş iletilerin alınmasını etkinleştirerek, belirli bir yerel ayarın ileti modeli olarak işlev görebilecek bir nesne tanımlar.

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

*_Locname*\
Adlandırılmış bir yerel ayar.

*_Refs*\
İlk başvuru sayısı.

## <a name="remarks"></a>Açıklamalar

Davranışı, adlandırılmış yerel ayar *_Locname* tarafından belirlenir. Her Oluşturucu kendi temel nesnesini [iletilerle](../standard-library/messages-class.md#messages) \<CharType> () başlatır `_Refs` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
