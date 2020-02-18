---
title: Yapıları ve Sınıfları Yorumlama
ms.date: 06/28/2019
ms.topic: conceptual
f1_keywords:
- _Field_size_bytes_part_
- _Field_size_bytes_full_opt_
- _Field_size_bytes_
- _Field_size_opt_
- _Field_size_part_
- _Field_size_bytes_part_opt_
- _Field_range_
- _Field_size_part_opt_
- _Field_size_
- _Field_size_bytes_opt_
- _Struct_size_bytes_
- _Field_size_bytes_full_
- _Field_size_full_
- _Field_size_full_opt_
- _Field_z_
ms.assetid: b8278a4a-c86e-4845-aa2a-70da21a1dd52
ms.openlocfilehash: e6b08c18d2524f1240eed99dd45320a7f4c00ac3
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77417481"
---
# <a name="annotating-structs-and-classes"></a>Yapıları ve Sınıfları Yorumlama

Struct ve Class üyelerine, ınvarıant gibi davranan ek açıklamaları kullanarak açıklama ekleyebilirsiniz — bir parametre çağrısı veya bir sonuç değeri olarak kapsayan yapıyı içeren herhangi bir işlev çağrısında ya da işlev girişinde/çıkışta doğru olarak kabul edilir.

## <a name="struct-and-class-annotations"></a>Struct ve sınıf ek açıklamaları

- `_Field_range_(low, high)`

     Alan, `high``low` aralığında (kapsamlı).  İlgili ön koşul veya gönderi koşulları kullanılarak açıklamalı nesneye uygulanan `_Satisfies_(_Curr_ >= low && _Curr_ <= high)` eşdeğerdir.

- `_Field_size_(size)`, `_Field_size_opt_(size)`, `_Field_size_bytes_(size)`, `_Field_size_bytes_opt_(size)`

     `size`tarafından belirtilen öğeler (veya bayt) içinde yazılabilir boyutu olan bir alan.

- `_Field_size_part_(size, count)`, `_Field_size_part_opt_(size, count)`, `_Field_size_bytes_part_(size, count)`, `_Field_size_bytes_part_opt_(size, count)`

     `size`tarafından belirtilen öğeler (veya bayt) ve okunabilir olan öğelerin (bayt) `count`.

- `_Field_size_full_(size)`, `_Field_size_full_opt_(size)`, `_Field_size_bytes_full_(size)`, `_Field_size_bytes_full_opt_(size)`

     `size`tarafından belirtilen öğeler (veya bayt) içinde hem okunabilir hem de yazılabilir boyuta sahip bir alan.

- `_Field_z_`

     Null ile sonlandırılmış bir dizeye sahip alan.

- `_Struct_size_bytes_(size)`

     Struct veya Class bildirimi için geçerlidir.  Bu türdeki geçerli bir nesnenin, `size`tarafından belirtilen bayt sayısıyla, tanımlanan türden daha büyük olabileceğini gösterir.  Örnek:

    ```cpp

    typedef _Struct_size_bytes_(nSize)
    struct MyStruct {
        size_t nSize;
        ...
    };

    ```

     `MyStruct *` türündeki bir parametre `pM` arabellek boyutu daha sonra şu şekilde alınır:

    ```cpp
    min(pM->nSize, sizeof(MyStruct))
    ```

## <a name="example"></a>Örnek

```cpp
#include <sal.h>

// This _Struct_size_bytes_ is equivalent to what below _Field_size_ means.
_Struct_size_bytes_(__builtin_offsetof(MyBuffer, buffer) + bufferSize * sizeof(int))
struct MyBuffer
{
    static int MaxBufferSize;

    _Field_z_
    const char* name;

    int firstField;

    // ... other fields

    _Field_range_(1, MaxBufferSize)
    int bufferSize;

    _Field_size_(bufferSize)        // Prefered way - easier to read and maintain.
    int buffer[]; // Using C99 Flexible array member
};
```

Bu örneğe ilişkin notlar:

- `_Field_z_` `_Null_terminated_`eşdeğerdir.  ad alanı için `_Field_z_`, ad alanının null ile sonlandırılmış bir dize olduğunu belirtir.
- `bufferSize` için `_Field_range_`, `bufferSize` değerinin 1 ve `MaxBufferSize` (her ikisi de dahil) arasında olması gerektiğini belirtir.
- `_Struct_size_bytes_` ve `_Field_size_` ek açıklamaların nihai sonuçları eşdeğerdir. Benzer düzeni olan yapılar veya sınıflar için `_Field_size_` daha kolay bir şekilde daha `_Struct_size_bytes_` fazla başvuru ve hesaplamalar içerdiğinden, daha kolay okunabilir ve bakımı vardır. `_Field_size_` bayt boyutuna dönüştürme gerektirmez. Bayt boyutu tek seçenektir, örneğin, void işaretçi alanı için `_Field_size_bytes_` kullanılabilir. Hem `_Struct_size_bytes_` hem de `_Field_size_` varsa, her ikisi de araçlar tarafından kullanılabilir. Bu, iki ek açıklama kabul eterif durumunda ne yapmanız gerektiğini araca kadar olur.

## <a name="see-also"></a>Ayrıca bkz.

- [C/C++ Kod Hatalarını Azaltmak için SAL Ek Açıklamalarını Kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL'yi Anlama](../code-quality/understanding-sal.md)
- [İşlev Parametrelerini ve Dönüş Değerlerini Açıklama](../code-quality/annotating-function-parameters-and-return-values.md)
- [İşlev Davranışını Yorumlama](../code-quality/annotating-function-behavior.md)
- [Kilitlenme Davranışını Yorumlama](../code-quality/annotating-locking-behavior.md)
- [Açıklamanın Ne Zaman ve Nereye Uygulanacağını Belirtme](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [İç İşlevler](../code-quality/intrinsic-functions.md)
- [En İyi Yöntemler ve Örnekler](../code-quality/best-practices-and-examples-sal.md)
