---
title: codecvt_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_base
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
ms.openlocfilehash: 1a32ba5e583fdb20118a3397f1ddb326302f2de1
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459385"
---
# <a name="codecvtbase-class"></a>codecvt_base Sınıfı

Bir dönüştürme sonucunu göstermek için model üye işlevleri için dönüş türü olarak kullanılan, olarak `result`adlandırılan bir numaralandırma türünü tanımlamak için kullanılan codecvt sınıfı için temel sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
    bool always_noconv() const;
    int max_length() const;
    int encoding() const;
    ~codecvt_base()

protected:
    virtual bool do_always_noconv() const;
    virtual int do_max_length() const;
    virtual int do_encoding() const;
};
```

## <a name="remarks"></a>Açıklamalar

Sınıfı, [codecvt](../standard-library/codecvt-class.md)şablon sınıfının tüm uzmanlıklarıyla ortak bir numaralandırma tanımlar. Numaralandırma sonucu, [do_in](../standard-library/codecvt-class.md#do_in) veya [do_out](../standard-library/codecvt-class.md#do_out)' den olası dönüş değerlerini açıklar:

- `ok`iç ve dış karakter kodlamaları arasında dönüştürme başarılı olursa.

- `partial`hedef dönüştürmenin başarılı olması için yeterince büyük değilse.

- `error`kaynak sırası hatalı biçimlendirilmişse.

- `noconv`işlev dönüştürme işlemi gerçekleştirmeyebilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
