---
title: ctype_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- locale/std::ctype_base
helpviewer_keywords:
- ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
ms.openlocfilehash: f23b9528cf9a921e1d005756aa82751f3fdb745e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449355"
---
# <a name="ctypebase-class"></a>ctype_base Sınıfı

Sınıfı, [CType](../standard-library/ctype-class.md)şablon sınıfı modelleri için bir temel sınıf işlevi görür. Karakterleri tek tek veya aralığın tamamında sınıflandırmak veya sınamak için kullanılan numaralandırma türleri tanımlamak için kullanılan ctype sınıfı için temel sınıf.

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

Bir numaralandırma maskesini tanımlar. Her numaralandırma sabiti,, CType. h > üst bilgisinde \<bildirildiği benzer adlara sahip işlevler tarafından tanımlanan karakterleri sınıflandırmaya yönelik farklı bir yol biçimlendirir. Sabitler şunlardır:

- **boşluk** (işlev [ısspace](../standard-library/locale-functions.md#isspace))

- **Yazdır** (işlev [ısprint](../standard-library/locale-functions.md#isprint))

- **cni** (işlev [SCC](../standard-library/locale-functions.md#iscntrl))

- **büyük** (işlev [ıupper](../standard-library/locale-functions.md#isupper))

- **daha düşük** (işlev [IsLower](../standard-library/locale-functions.md#islower))

- **basamak** (işlev [IsDigit](../standard-library/locale-functions.md#isdigit))

- **punct** (işlev [ispunct](../standard-library/locale-functions.md#ispunct))

- **xdigit** (işlev [ısxdigit](../standard-library/locale-functions.md#isxdigit))

- **Alfa** (işlev [ısalpha](../standard-library/locale-functions.md#isalpha))

- **alnum** (işlev [ısalnum](../standard-library/locale-functions.md#isalnum))

- **grafik** (işlev [isgraf](../standard-library/locale-functions.md#isgraph))

Sınıflandırmaların bir bileşimini bu sabitlerle ayırarak ayırdetmek için kullanabilirsiniz. Özellikle, **alnum** = = ( **Alfa** &#124; **basamağı** \) ve **Graf** \= \= \( &#124; **alnum** **punct**) ile her zaman doğrudur.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
