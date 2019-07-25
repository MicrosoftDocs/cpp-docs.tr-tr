---
title: numpunct_byname Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct_byname
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
ms.openlocfilehash: 0c9eb565c2dbf54da449411aa11a4c5661debf1d
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452313"
---
# <a name="numpunctbyname-class"></a>numpunct_byname Sınıfı

Türetilmiş şablon sınıfı, sayısal ve Boolean ifadelerin biçimlendirmesini ve noktalama işaretlerini `numpunct` etkinleştirerek, belirtilen bir yerel ayarın bir modeli olarak işlev görebilecek bir nesne tanımlar.

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

Davranışı, [adlandırılmış](../standard-library/locale-class.md#name) yerel ayar `_Locname`tarafından belirlenir. Oluşturucu kendi temel nesnesini, [sayısal tuş takımı olmayan](../standard-library/numpunct-class.md#numpunct)\<> ( `_Refs`) ile başlatır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
