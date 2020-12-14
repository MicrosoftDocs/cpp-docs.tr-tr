---
description: 'Daha fazla bilgi edinin: C soyut bildirimcileri'
title: C Soyut Bildirimciler
ms.date: 11/04/2016
helpviewer_keywords:
- declarators, abstract
- abstract declarations
ms.assetid: 6a556ad7-0555-421a-aa02-294d77cda8b5
ms.openlocfilehash: 9af51d96ac50222b9148060147812aecdf114b7d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211615"
---
# <a name="c-abstract-declarators"></a>C Soyut Bildirimciler

Soyut bildirimci, tanımlayıcısı olmayan, bir veya daha fazla işaretçiden, diziden veya işlev değiştiricisinden oluşan bir bildirimcidir. İşaretçi değiştiricisi ( <strong>\*</strong> ) her zaman bir bildirimci içindeki tanımlayıcıdan önce gelir; dizi (**[]**) ve işlev ( **()** ) değiştiriciler tanımlayıcıyı izler. Bu bilgiyle; tanımlayıcının, soyut bildirimcinin neresinde görüneceğini belirleyebilir ve ona göre bildiriciyi yorumlayabilirsiniz. Ek bilgi ve karmaşık bildirimcilerin örnekleri için [daha karmaşık Bildirimcilerin yorumlanması](../c-language/interpreting-more-complex-declarators.md) bölümüne bakın. Genel **`typedef`** olarak, bildirimcilerin basitleşmesi için kullanılabilir. Bkz. [typedef bildirimleri](../c-language/typedef-declarations.md).

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
> Boş parantezlerin **()** kümesinden oluşan soyut bildirimci, belirsiz olduğu için kullanılamaz. İma edilen tanımlayıcının parantez içinde mi (bu durumda, değiştirilmemiş bir türdür) yoksa parantezlerden önce mi (bu durumda, bir işlev türüdür) olduğunu belirlemek mümkün değildir.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimciler ve değişken bildirimleri](../c-language/declarators-and-variable-declarations.md)
