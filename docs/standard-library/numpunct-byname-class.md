---
description: 'Hakkında daha fazla bilgi edinin: numpunct_byname sınıfı'
title: numpunct_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct_byname
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
ms.openlocfilehash: e4e6352f9f65b2a726acf3f8f5f8ede9bffe54f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338037"
---
# <a name="numpunct_byname-class"></a>numpunct_byname Sınıfı

Türetilmiş sınıf şablonu, `numpunct` sayısal ve Boolean ifadelerin biçimlendirmesini ve noktalama işaretlerini etkinleştirerek, belirtilen bir yerel ayarın bir modeli olarak işlev görebilecek bir nesne tanımlar.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType>
class numpunct_byname : public numpunct<Elem> {
public:
    explicit numpunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit numpunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~numpunct_byname();

};
```

## <a name="remarks"></a>Açıklamalar

Davranışı, [adlandırılmış](../standard-library/locale-class.md#name) yerel ayar tarafından belirlenir `_Locname` . Oluşturucu kendi temel nesnesini bir [sayısal tuş takımı](../standard-library/numpunct-class.md#numpunct) \<CharType> () ile başlatır `_Refs` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
