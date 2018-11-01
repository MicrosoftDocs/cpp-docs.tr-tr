---
title: C Soyut Bildirimciler
ms.date: 11/04/2016
helpviewer_keywords:
- declarators, abstract
- abstract declarations
ms.assetid: 6a556ad7-0555-421a-aa02-294d77cda8b5
ms.openlocfilehash: 5dc58b71c8b2032342b6604112673086dc94649b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429828"
---
# <a name="c-abstract-declarators"></a>C Soyut Bildirimciler

Soyut bildirimci, tanımlayıcısı olmayan, bir veya daha fazla işaretçiden, diziden veya işlev değiştiricisinden oluşan bir bildirimcidir. İşaretçi değiştirici (<strong>\*</strong>) her zaman bir bildirimcide; tanımlayıcısından önce gelir dizi (**[]**) ve işlev ( **()** ) değiştiriciler tanımlayıcıyı izler. Bu bilgiyle; tanımlayıcının, soyut bildirimcinin neresinde görüneceğini belirleyebilir ve ona göre bildiriciyi yorumlayabilirsiniz. Bkz: [daha karmaşık Bildirimcileri yorumlama](../c-language/interpreting-more-complex-declarators.md) ek bilgi ve örnekler. Bildirimciler basitleştirmek için genellikle `typedef` kullanılabilir. Bkz: [Typedef bildirimleri](../c-language/typedef-declarations.md).

Soyut bildirimciler karmaşık olabilir. Bir karmaşık soyut bildirimcideki parantezler belirli bir yorumu belirtir (bildirimler içindeki karmaşık bildirimciler için olduğu gibi).

Bu örneklerde soyut bildirimciler gösterilmektedir:

```
int *         // The type name for a pointer to type int:

int *[3]      // An array of three pointers to int

int (*) [5]   // A pointer to an array of five int

int *()       // A function with no parameter specification
              // returning a pointer to int

// A pointer to a function taking no arguments and
// returning an int

int (*) ( void )

// An array of an unspecified number of constant pointers to
// functions each with one parameter that has type unsigned int
// and an unspecified number of other parameters returning an int

int (*const []) ( unsigned int, ... )
```

> [!NOTE]
>  Bir boş ayraç kümesi içeren soyut bildirimciye **()**, belirsiz olduğu için izin verilmiyor. İma edilen tanımlayıcının parantez içinde mi (bu durumda, değiştirilmemiş bir türdür) yoksa parantezlerden önce mi (bu durumda, bir işlev türüdür) olduğunu belirlemek mümkün değildir.

## <a name="see-also"></a>Ayrıca Bkz.

[Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)