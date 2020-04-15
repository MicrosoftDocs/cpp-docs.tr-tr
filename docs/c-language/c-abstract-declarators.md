---
title: C Soyut Bildirimciler
ms.date: 11/04/2016
helpviewer_keywords:
- declarators, abstract
- abstract declarations
ms.assetid: 6a556ad7-0555-421a-aa02-294d77cda8b5
ms.openlocfilehash: 196eb39d901b38ab7b005b03a933827ec4288218
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335062"
---
# <a name="c-abstract-declarators"></a>C Soyut Bildirimciler

Soyut bildirimci, tanımlayıcısı olmayan, bir veya daha fazla işaretçiden, diziden veya işlev değiştiricisinden oluşan bir bildirimcidir. İşaretçi değiştirici<strong>\*</strong>( ) her zaman bir bildirimde tanımlayıcıdan önce gelir; dizi (**[ ]**) ve fonksiyon ( **( )** ) tanımlayıcıyı izler. Bu bilgiyle; tanımlayıcının, soyut bildirimcinin neresinde görüneceğini belirleyebilir ve ona göre bildiriciyi yorumlayabilirsiniz. Bkz. Ek bilgi ve karmaşık bildirimcilerin örnekleri için [Daha Karmaşık Bildirimcileri Yorumlama.](../c-language/interpreting-more-complex-declarators.md) Bildirimciler basitleştirmek için genellikle `typedef` kullanılabilir. [Bkz. Typedef Bildirimleri](../c-language/typedef-declarations.md).

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
> Boş parantez kümesinden oluşan soyut bildirimciye belirsiz **( )** olduğu için izin verilmez. İma edilen tanımlayıcının parantez içinde mi (bu durumda, değiştirilmemiş bir türdür) yoksa parantezlerden önce mi (bu durumda, bir işlev türüdür) olduğunu belirlemek mümkün değildir.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)
