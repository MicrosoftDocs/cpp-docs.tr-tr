---
title: codecvt_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_base
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
ms.openlocfilehash: 6fca9b2130407b165a7a7bfb1fb2a9ec81774e20
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689884"
---
# <a name="codecvt_base-class"></a>codecvt_base Sınıfı

Bir dönüştürme sonucunu göstermek için model üye işlevleri için dönüş türü olarak kullanılan, `result` olarak adlandırılan bir numaralandırma türünü tanımlamak için kullanılan codecvt sınıfı için temel sınıf.

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

Sınıfı, [codecvt](../standard-library/codecvt-class.md)sınıf şablonunun tüm uzmanlıklarıyla ortak olan bir sabit listesini açıklar. Numaralandırma sonucu, [do_in](../standard-library/codecvt-class.md#do_in) veya [do_out](../standard-library/codecvt-class.md#do_out)' den olası dönüş değerlerini açıklar:

- iç ve dış karakter kodlamaları arasında dönüştürme başarılı olursa `ok`.

- hedef dönüştürmenin başarılı olması için yeterince büyük değilse `partial`.

- kaynak sırası hatalı biçimlendirilmişse `error`.

- işlev dönüştürme işlemi gerçekleştirmediğini `noconv`.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
