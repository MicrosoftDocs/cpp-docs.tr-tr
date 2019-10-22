---
title: numpunct_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct_byname
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
ms.openlocfilehash: da9259df8c527e44a4adea3a53be31b3c3ffc10b
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687602"
---
# <a name="numpunct_byname-class"></a>numpunct_byname Sınıfı

Türetilmiş sınıf şablonu, sayısal ve Boolean ifadelerin biçimlendirmesini ve noktalama işaretlerini etkinleştirerek, belirli bir yerel ayarın `numpunct` modeli olarak işlev görebilecek bir nesne tanımlar.

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

Davranışı, [adlandırılmış](../standard-library/locale-class.md#name) yerel ayar `_Locname` tarafından belirlenir. Oluşturucu kendi temel nesnesini bir [ana \<CharType >](../standard-library/numpunct-class.md#numpunct) (`_Refs`) olarak başlatır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
