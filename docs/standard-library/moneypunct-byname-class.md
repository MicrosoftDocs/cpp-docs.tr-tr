---
title: moneypunct_byname sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/std::moneypunct_byname
dev_langs:
- C++
helpviewer_keywords:
- moneypunct_byname class
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e4720ac87884a079bbc2ede6b625658adb9c29c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="moneypunctbyname-class"></a>moneypunct_byname Sınıfı

Olarak hizmet verebilir bir nesneyi tanımlayan bir türetilmiş Şablon sınıfı bir `moneypunct` para biçimlendirme etkinleştirme, belirli bir yerel güvenliğin giriş alanı veya parasal çıktı alanları.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, bool Intl = false>
class moneypunct_byname : public moneypunct<CharType, Intl>
{
public:
    explicit moneypunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit moneypunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~moneypunct_byname();

};
```

## <a name="remarks"></a>Açıklamalar

Davranışını adlandırılmış bölgeye göre belirlenir `_Locname`. Her oluşturucu temel nesnesiyle başlatır [moneypunct](../standard-library/moneypunct-class.md#moneypunct)\<CharType, uluslararası > ( `_Refs`).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
