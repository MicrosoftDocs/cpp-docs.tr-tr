---
title: ctype_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- locale/std::ctype_base
helpviewer_keywords:
- ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
ms.openlocfilehash: 83ef35f9fac438cfa217decf222abd365ff84269
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531137"
---
# <a name="ctypebase-class"></a>ctype_base Sınıfı

Sınıfı şablon sınıfı modelleri için temel bir sınıf olarak hizmet verir [ctype](../standard-library/ctype-class.md). Karakterleri tek tek veya aralığın tamamında sınıflandırmak veya sınamak için kullanılan numaralandırma türleri tanımlamak için kullanılan ctype sınıfı için temel sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
struct ctype_base : public locale::facet
{
    enum
    {
        alnum,
        alpha,
        cntrl,
        digit,
        graph,
        lower,
        print,
        punct,
        space,
        upper,
        xdigit
    };
    typedef short mask;

    ctype_base( size_t _Refs = 0 );
    ~ctype_base();
};
```

## <a name="remarks"></a>Açıklamalar

Bu, bir numaralandırma maskesi tanımlar. Benzer adlarla üstbilgisinde bildirilen işlevler tarafından tanımlandığı şekilde, karakterleri sınıflandırmak için farklı bir şekilde her bir numaralandırma sabiti belirtir \<ctype.h >. Sabittir:

- **alanı** (işlev [isspace](../standard-library/locale-functions.md#isspace))

- **Yazdırma** (işlev [isprint](../standard-library/locale-functions.md#isprint))

- **CTRL** (işlev [iscntrl](../standard-library/locale-functions.md#iscntrl))

- **üst** (işlev [isupper](../standard-library/locale-functions.md#isupper))

- **daha düşük** (işlev [islower](../standard-library/locale-functions.md#islower))

- **basamak** (işlev [isdigit](../standard-library/locale-functions.md#isdigit))

- **noktalama işareti** (işlev [ispunct](../standard-library/locale-functions.md#ispunct))

- **xdigit** (işlev [isxdigit](../standard-library/locale-functions.md#isxdigit))

- **alfa** (işlev [isalpha](../standard-library/locale-functions.md#isalpha))

- **alnum'la** (işlev [isalnum](../standard-library/locale-functions.md#isalnum))

- **graf** (işlev [isgraph](../standard-library/locale-functions.md#isgraph))

Bu sabit bir birleşimi tarafından ORing sınıflandırmaları ayırt edebilirsiniz. Özellikle, her zaman, doğru olduğu **alnum'la** == ( **alfa** &#124; **basamak** \) ve **grafik** \= \= \( **alnum'la** &#124; **noktalama işareti**).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
