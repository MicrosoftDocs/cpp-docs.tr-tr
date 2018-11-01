---
title: numpunct_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct_byname
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
ms.openlocfilehash: 64e8918b052b05088ff48aefb0f0f9ab8c6df586
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432879"
---
# <a name="numpunctbyname-class"></a>numpunct_byname Sınıfı

Türetilmiş bir şablon sınıfı olarak hizmet verebilen bir nesneyi tanımlayan bir `numpunct` biçimlendirmesi ve noktalama işaretleri sayısal ve Boolean ifadelerin etkinleştirme verili bir yerel ayar modeli.

## <a name="syntax"></a>Sözdizimi

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

Davranışını tarafından belirlenen [adlı](../standard-library/locale-class.md#name) yerel `_Locname`. Oluşturucu, temel nesnesiyle başlatır [numpunct](../standard-library/numpunct-class.md#numpunct)\<CharType > ( `_Refs`).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
