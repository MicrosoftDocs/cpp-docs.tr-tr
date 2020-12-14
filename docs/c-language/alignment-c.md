---
title: Hizalama (C11)
description: Microsoft Visual C tür hizalamasını açıklar
ms.date: 12/10/2020
helpviewer_keywords:
- _Alignof keyword [C]
- _Alignas keyword [C]
- memory, alignment
ms.openlocfilehash: 051987ae705f84d7d4972398f742143f14b53e2b
ms.sourcegitcommit: be469dd87453255b0e35e333712c8207b09b3dd4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2020
ms.locfileid: "97440663"
---
# <a name="alignment-c11"></a>Hizalama (C11)

C 'nin alt düzey özelliklerinden biri, donanım mimarisinden en yüksek avantajdan yararlanmak için bellekteki nesnelerin kesin hizalamasını belirtme yeteneğidir.

Veriler veri boyutunun birden çok katı olan bir adreste depolandığında belleği okur ve daha verimli bir şekilde yazar. Örneğin, 4 baytlık bir tamsayı, 4 ' ün katı olan bir adreste depolanıyorsa daha verimli bir şekilde erişilir. Veriler hizalanmıyorsa, CPU verilere erişmek için daha fazla çalışma yapar.

Varsayılan olarak, derleyici verileri boyutuna göre hizalar: 1 baytlık bir sınırında, 2 baytlık bir sınırında,, **`char`** **`short`** **`int`** **`long`** , ve **`float`** 4 baytlık bir sınırında, **`double`** 8 baytlık sınırında vb.

Ayrıca, sık kullanılan verileri işlemcinin önbellek satırı boyutuyla hizalayarak, önbellek performansını geliştirebilirsiniz. Örneğin, boyutu 32 bayttan daha az olan bir yapı tanımlarsanız, yapının örneklerinin etkin bir şekilde önbelleğe alınmasını sağlamak için 32 baytlık hizalama yapmak isteyebilirsiniz.

Genellikle hizalama konusunda endişelenmeniz gerekmez. Derleyici, verileri, hedef işlemciyi ve verilerin boyutunu temel alan doğal sınırlara göre genellikle hizalar. Veriler, 32 bitlik işlemcilerde 4 baytlık sınırlara ve 64 bit işlemcilerde 8 baytlık sınırlara göre hizalanır. Ancak bazı durumlarda, veri yapılarınız için özel bir hizalama belirterek performans iyileştirmeleri veya bellek tasarrufları elde edebilirsiniz.

**`_Alignof`** Bir tür veya değişkenin tercih edilen hizalamasını almak ve **`_Alignas`** bir değişken veya Kullanıcı tanımlı tür için özel bir hizalama belirtmek için C11 anahtar sözcüğünü kullanın.

Kolay makrolar **`alignof`** ve **`alignas`** içinde tanımlanmıştır, `<stdalign.h>` sırasıyla doğrudan **`_Alignof`** ve ile eşlenir **`_Alignas`** . Bu makrolar C++ ' da kullanılan anahtar sözcüklerle eşleşir. Bu nedenle, iki dil arasında kod paylaşırsanız kod taşınabilirliği için C anahtar kelimeleri yerine makroları kullanmak yararlı olabilir.

## <a name="alignas-and-_alignas-c11"></a>`alignas` ve `_Alignas` (C11)

**`alignas`** **`_Alignas`** Bir değişken veya Kullanıcı tanımlı tür için özel hizalama belirtmek üzere veya kullanın. Yapı, birleşim, numaralandırma veya değişkene uygulanabilir.

### <a name="alignas-syntax"></a>`alignas` sözdizimi

```c
alignas(type)
alignas(constant-expression)
_Alignas(type)
_Alignas(constant-expression)
```

### <a name="remarks"></a>Açıklamalar

`_Alignas` TypeDef, bit alanı, işlev, işlev parametresi veya belirticiyle belirtilen bir nesne bildiriminde kullanılamaz `register` .

1, 2, 4, 8, 16, vb. gibi iki üssü olan bir hizalama belirtin. Türün boyutundan küçük bir değer kullanmayın.

Yapılar ve birleşimler herhangi bir üyenin en büyük hizalamasına eşittir. Tek tek üye hizalama gereksinimlerinin karşılanmasını sağlamak için yapılar içine Doldurma baytları eklenir.

Bir bildirimde birden fazla tanımlayıcı varsa **`alignas`**  (örneğin, farklı belirticilerine sahip çeşitli üyelere sahip bir yapı **`alignas`** ), yapının hizalaması en büyük bir olur.

### <a name="alignas-example"></a>`alignas` örneğinde

Bu örnek, **`alignof`** C++ ' ta taşınabileceğinden kolaylık makrosunu kullanır. Kullanıyorsanız, davranış aynıdır `_Alignof` .

```c
// Compile with /std:c11

#include <stdio.h>
#include <stdalign.h>

typedef struct 
{
    int value; // aligns on a 4-byte boundary. There will be 28 bytes of padding between value and alignas
    alignas(32) char alignedMemory[32]; // assuming a 32 byte friendly cache alignment
} cacheFriendly; // this struct will be 32-byte aligned because alignedMemory is 32-byte alligned and is the largest alignment specified in the struct

int main()
{
    printf("sizeof(cacheFriendly): %d\n", sizeof(cacheFriendly)); // 4 bytes for int value + 32 bytes for alignedMemory[] + padding to ensure  alignment
    printf("alignof(cacheFriendly): %d\n", alignof(cacheFriendly)); // 32 because alignedMemory[] is aligned on a 32-byte boundary

    /* output
        sizeof(cacheFriendly): 64
        alignof(cacheFriendly): 32
    */
}
```

## <a name="alignof-and-_alignof-c11"></a>`alignof` ve `_Alignof` (C11)

`_Alignof` belirtilen türün bayt cinsinden hizalamasını döndürür. Türünde bir değer döndürür `size_t` .

### <a name="alignof-syntax"></a>`alignof` sözdizimi

```cpp
alignof(type)
_Alignof(type)
```

### <a name="alignof-example"></a>`alignof` örneğinde

Bu örnek, **`alignof`** C++ ' ta taşınabileceğinden kolaylık makrosunu kullanır. Kullanıyorsanız, davranış aynıdır `_Alignof` .

```c
// Compile with /std:c11

#include <stdalign.h>
#include <stdio.h>

int main()
{
    size_t alignment = alignof(short);
    printf("alignof(short) = %d\n", alignment); // 2
    printf("alignof(int) = %d\n", alignof(int)); // 4
    printf("alignof(long) = %d\n", alignof(long)); // 4
    printf("alignof(float) = %d\n", alignof(float)); // 4
    printf("alignof(double) = %d\n", alignof(double)); // 8

    typedef struct
    {
        int a;
        double b;
    } test;

    printf("alignof(test) = %d\n", alignof(test)); // 8 because that is the alignment of the largest element in the structure

    /* output
        
       alignof(short) = 2
       alignof(int) = 4
       alignof(long) = 4
       alignof(float) = 4
       alignof(double) = 8
       alignof(test) = 8
    */
}
```

## <a name="requirements"></a>Gereksinimler

[std: c++ 11](../build/reference/std-specify-language-standard-version.md) veya üzeri gereklidir.

Windows SDK sürüm 10.0.20201.0 veya üzeri. Bu sürüm, şu anda [Windows Insider Preview Indirilenler](https://www.microsoft.com/software-download/windowsinsiderpreviewSDK)aracılığıyla indirebileceğiniz bir Insider derlemesi. Bkz. [C11 and C17:](https://devblogs.microsoft.com/cppblog/c11-and-c17-standard-support-arriving-in-msvc/#c11-and-c17-getting-started) Bu SDK 'yı yükleme ve kullanma hakkında yönergeler için Başlarken.

## <a name="see-also"></a>Ayrıca bkz.

[`/std` (Dil standart sürümünü belirt)](../build/reference/std-specify-language-standard-version.md)\
[C++ `alignof` ve `alignas`](../cpp/alignment-cpp-declarations.md#alignof-and-alignas)\
[Veri hizalamasını derleyici işleme](../cpp/alignment-cpp-declarations.md#compiler-handling-of-data-alignment)