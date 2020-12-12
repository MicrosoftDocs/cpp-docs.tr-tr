---
description: 'Hakkında daha fazla bilgi edinin: ctype_base sınıfı'
title: ctype_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- locale/std::ctype_base
helpviewer_keywords:
- ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
ms.openlocfilehash: 430e6fbf77842e61e662fd3024a54b418f487748
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324688"
---
# <a name="ctype_base-class"></a>ctype_base Sınıfı

Sınıfı, sınıf şablonu [CType](../standard-library/ctype-class.md)modelleri için bir temel sınıf işlevi görür. Karakterleri tek tek veya aralığın tamamında sınıflandırmak veya sınamak için kullanılan numaralandırma türleri tanımlamak için kullanılan ctype sınıfı için temel sınıf.

## <a name="syntax"></a>Syntax

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

Bir numaralandırma maskesini tanımlar. Her numaralandırma sabiti, üst bilgide belirtilen benzer adlara sahip işlevler tarafından tanımlanan şekilde karakterleri sınıflandırmakta farklı bir yol biçimlendirir \<ctype.h> . Sabitler şunlardır:

- **boşluk** (işlev [ısspace](../standard-library/locale-functions.md#isspace))

- **Yazdır** (işlev [ısprint](../standard-library/locale-functions.md#isprint))

- **cnini** (işlev [SCC](../standard-library/locale-functions.md#iscntrl))

- **Upper** (işlev [ıupper](../standard-library/locale-functions.md#isupper))

- **daha düşük** (işlev [IsLower](../standard-library/locale-functions.md#islower))

- **basamak** (işlev [IsDigit](../standard-library/locale-functions.md#isdigit))

- **punct** (işlev [ispunct](../standard-library/locale-functions.md#ispunct))

- **xdigit** (işlev [ısxdigit](../standard-library/locale-functions.md#isxdigit))

- **Alfa** (işlev [isalpha](../standard-library/locale-functions.md#isalpha))

- **alnum** (işlev [isalnum](../standard-library/locale-functions.md#isalnum))

- **Graf** (işlev [isgraf](../standard-library/locale-functions.md#isgraph))

Sınıflandırmaların bir bileşimini bu sabitlerle ayırarak ayırdetmek için kullanabilirsiniz. Özellikle, **alnum** = = ( **Alpha** &#124; **digit** \) ve **Graf** \= \= \( **alnum** &#124; **punct**) değeri her zaman doğrudur.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
