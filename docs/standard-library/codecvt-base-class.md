---
description: 'Hakkında daha fazla bilgi edinin: codecvt_base Sınıfı'
title: codecvt_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_base
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
ms.openlocfilehash: d0fb5a56a163ba80cee89eb6f37200243e6c08e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325107"
---
# <a name="codecvt_base-class"></a>codecvt_base Sınıfı

`result`Bir dönüştürme sonucunu göstermek için model üye işlevleri için dönüş türü olarak kullanılan, olarak adlandırılan bir numaralandırma türünü tanımlamak için kullanılan codecvt sınıfı için temel sınıf.

## <a name="syntax"></a>Syntax

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

Sınıfı, [codecvt](../standard-library/codecvt-class.md)sınıf şablonunun tüm uzmanlıklarıyla ortak olan bir sabit listesini açıklar. Numaralandırma sonucu [do_in](../standard-library/codecvt-class.md#do_in) veya [do_out](../standard-library/codecvt-class.md#do_out)ait olası dönüş değerlerini açıklar:

- `ok` iç ve dış karakter kodlamaları arasında dönüştürme başarılı olursa.

- `partial` hedef dönüştürmenin başarılı olması için yeterince büyük değilse.

- `error` kaynak sırası hatalı biçimlendirilmişse.

- `noconv` işlev dönüştürme işlemi gerçekleştirmeyebilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
