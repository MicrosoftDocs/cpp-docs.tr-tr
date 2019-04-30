---
title: codecvt_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_base
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
ms.openlocfilehash: 6f957c39f9c78fd182b7ba2a14bdab7f27db56ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405306"
---
# <a name="codecvtbase-class"></a>codecvt_base Sınıfı

Bir numaralandırma türü tanımlamak için kullanılan codecvt sınıfının bir temel sınıf denir `result`bir dönüştürmenin sonucunu belirtmek için model üye işlevleri için dönüş türü olarak kullanılır.

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

Sınıfı için şablon sınıfın tüm uzmanlıkları ortak bir numaralandırma açıklar [codecvt](../standard-library/codecvt-class.md). Sabit listesi sonucu olası dönüş değerleri açıklar [do_in](../standard-library/codecvt-class.md#do_in) veya [do_out](../standard-library/codecvt-class.md#do_out):

- `ok` İç ve dış karakter kodlamaları arasında dönüştürme başarılı olursa.

- `partial` Hedef dönüştürme başarılı olması için yeterince büyük değilse.

- `error` Kaynak sırası olgu ise oluşturulmuş.

- `noconv` herhangi bir dönüştürme işlevi uyguluyorsa.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
