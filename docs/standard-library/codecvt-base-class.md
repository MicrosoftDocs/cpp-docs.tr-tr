---
title: codecvt_base sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt_base
dev_langs:
- C++
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a471cdd63ed46e15c9ec41968ed341eefaf36963
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965398"
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
