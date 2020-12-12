---
description: 'Hakkında daha fazla bilgi edinin: ctype_byname sınıfı'
title: ctype_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype_byname
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
ms.openlocfilehash: cc5f44e1c544d2088030621b684c9e070175d695
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233142"
---
# <a name="ctype_byname-class"></a>ctype_byname Sınıfı

Türetilmiş sınıf şablonu, belirli bir yerel ayarın CType modeli olarak işlev görebilecek bir nesne tanımlar, bu durum, büyük/küçük harf ve yerel olarak belirtilen karakter kümeleri arasında karakterlerin sınıflandırılmasını ve karakter dönüştürülmesini etkinleştirir.

## <a name="syntax"></a>Syntax

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

Davranışı, adlandırılmış yerel ayar tarafından belirlenir `_Locname` . Her Oluşturucu kendi temel nesnesini [CType](../standard-library/ctype-class.md) \<CharType> ( `_Refs` ) veya temel sınıf için eşdeğer olarak başlatır `ctype<char>` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
