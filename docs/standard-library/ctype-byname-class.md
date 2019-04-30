---
title: ctype_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype_byname
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
ms.openlocfilehash: d998747045ece765269ddb013b525b8c06fcdf8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394175"
---
# <a name="ctypebyname-class"></a>ctype_byname Sınıfı

Türetilmiş bir şablon sınıfı bir karakterlerin sınıflandırılmasını ve çalışması arasında ve yerel karakter dönüştürme sağlayarak verili bir yerel ayarın ctype modeli olarak hizmet verebilen bir nesneyi tanımlayan ve yerel karakter kümesi belirtildi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```

## <a name="remarks"></a>Açıklamalar

Davranışını adlandırılmış yerel ayar tarafından belirlenir `_Locname`. Her Oluşturucu, temel nesnesiyle başlatır [ctype](../standard-library/ctype-class.md)\<CharType > ( `_Refs`) veya temel sınıf için eşdeğer `ctype<char>`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
