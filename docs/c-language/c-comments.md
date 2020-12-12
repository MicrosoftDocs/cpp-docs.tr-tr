---
description: 'Daha fazla bilgi edinin: C açıklamaları'
title: C Açıklamaları
ms.date: 06/25/2018
helpviewer_keywords:
- code comments, C code
- comments, documenting code
- comments, C code
- /* */ comment delimiters
- comments
ms.assetid: 0f5f2825-e673-49e7-8669-94e2f5294989
ms.openlocfilehash: 64ce3dea188e75545953b3427cd508dac5420a83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284583"
---
# <a name="c-comments"></a>C Açıklamaları

"Açıklama", <strong>/\*</strong> derleyici tarafından tek bir boşluk karakteri olarak değerlendirilen ve aksi durumda Yoksayılmış eğik çizgi/yıldız bileşimi () ile başlayan bir karakter dizisidir. Bir yorum, yeni satır karakterleri de dahil olmak üzere, gösterilebilir tablo karakter kümesindeki karakterlerin herhangi bir birleşimini içerebilir, ancak "End Comment" sınırlayıcısı ( <strong>\*/</strong> ) hariç olabilir. Açıklamalar, birden fazla satır kaplayabilir, ancak iç içe geçemez.

Açıklamalar, boşluk karakterine izin verilen her yerde görünebilir. Derleyici bir yorumu tek bir boşluk karakteri olarak değerlendirdiği için belirteçlere sahip açıklamaları dahil edemezsiniz. Derleyici, açıklamadaki karakterleri yoksayar.

Kodunuzu belgelemek için açıklamaları kullanabilirsiniz. Bu örnek, derleyici tarafından kabul edilen bir açıklamadır:

```C
/* Comments can contain keywords such as
   for and while without generating errors. */
```

Yorumlar, kod deyimi ile aynı satırda görünebilir:

```C
printf( "Hello\n" );  /* Comments can go here */
```

İşlevlerin veya program modüllerinin önüne tanımlayıcı bir açıklama bloğu yerleştirebilirsiniz:

```C
/* MATHERR.C illustrates writing an error routine
* for math functions.
*/
```

Açıklamalar iç içe açıklamalar içeremeyeceği için bu örnek bir hataya neden olur:

```C
/* Comment out this routine for testing

   /* Open file */
    fh = _open( "myfile.c", _O_RDONLY );
    .
    .
    .
*/
```

Hatanın nedeni, derleyicinin `*/` sözcüğünden sonra gelen ilk `Open file` dizisini açıklama sonu olarak algılamasıdır. Kalan metni işlemeye çalışır ve açıklamanın dışında `*/` bulduğunda bir hata oluşturur.

Test amaçları için etkin olmayan bir kodun belirli satırlarını oluşturmak üzere açıklamaları kullanabilirsiniz; bununla birlikte, `#if` ve `#endif` önişlemci yönergeleri ve koşullu derleme bu görev için kullanışlı bir alternatif oluşturur. Daha fazla bilgi için bkz. *Önişlemci Başvurusu* Içindeki [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) .

**Microsoft'a Özgü**

Microsoft derleyicisi Ayrıca, önünde iki eğik çizgi () ile tek satırlık açıklamaları destekler __//__ . /Za (ANSI standardı) ile derleme yaparsanız, bu açıklamalar hatalar oluşturur. Bu açıklamalar, ikinci satıra genişletilemez.

```C
// This is a valid comment
```

İki eğik çizgi () ile başlayan yorumlar, __//__ öncesinde bir kaçış karakteri olmayan sonraki yeni satır karakteri tarafından sonlandırılır. Sonraki örnekte, yeni satır karakterinin önünde bir ters eğik çizgi ( **\\** ), "kaçış sırası" oluşturuluyor. Bu kaçış dizisi, derleyicinin sonraki satırı önceki satırın bir parçası olarak değerlendirmesine neden olur. (Daha fazla bilgi için bkz. [kaçış dizileri](../c-language/escape-sequences.md).)

```C
// my comment \
    i++;
```

Bu nedenle, `i++;` deyimi açıklama dışında bırakılır.

Microsoft C için varsayılan değer, Microsoft uzantılarının etkinleştirilme içindir. Bu uzantıları devre dışı bırakmak için /Za kullanın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C belirteçleri](../c-language/c-tokens.md)
