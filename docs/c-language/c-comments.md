---
title: C Açıklamaları
ms.date: 06/25/2018
helpviewer_keywords:
- code comments, C code
- comments, documenting code
- comments, C code
- /* */ comment delimiters
- comments
ms.assetid: 0f5f2825-e673-49e7-8669-94e2f5294989
ms.openlocfilehash: fd2c08855bcc3ef3b4068f3841ce177d8162ff5b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326293"
---
# <a name="c-comments"></a>C Açıklamaları

"Açıklama", derleyici tarafından tek bir boşluk karakteri olarak değerlendirilen ve aksi durumda Yoksayılmış eğik<strong>/</strong>çizgi/yıldız bileşimi () ile başlayan bir karakter dizisidir. Bir yorum, yeni satır karakterleri de dahil olmak üzere, gösterilebilir tablo karakter kümesindeki karakterlerin herhangi bir birleşimini içerebilir, ancak "End Comment" sınırlayıcısı (<strong>\*</strong>) hariç olabilir. Açıklamalar, birden fazla satır kaplayabilir, ancak iç içe geçemez.

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

Test amaçları için etkin olmayan bir kodun belirli satırlarını oluşturmak üzere açıklamaları kullanabilirsiniz; bununla birlikte, `#if` ve `#endif` önişlemci yönergeleri ve koşullu derleme bu görev için kullanışlı bir alternatif oluşturur. Daha fazla bilgi için bkz. *Önişlemci Başvurusu*Içindeki [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) .

**Microsoft'a Özgü**

Microsoft derleyicisi Ayrıca, önünde iki eğik çizgi (__//__) ile tek satırlık açıklamaları destekler. /Za (ANSI standardı) ile derleme yaparsanız, bu açıklamalar hatalar oluşturur. Bu açıklamalar, ikinci satıra genişletilemez.

```C
// This is a valid comment
```

İki eğik çizgi (__//__) ile başlayan yorumlar, öncesinde bir kaçış karakteri olmayan sonraki yeni satır karakteri tarafından sonlandırılır. Sonraki örnekte, yeni satır karakterinin önünde bir ters eğik çizgi (**\\**), "kaçış sırası" oluşturuluyor. Bu kaçış dizisi, derleyicinin sonraki satırı önceki satırın bir parçası olarak değerlendirmesine neden olur. (Daha fazla bilgi için bkz. [kaçış dizileri](../c-language/escape-sequences.md).)

```C
// my comment \
    i++;
```

Bu nedenle, `i++;` deyimi açıklama dışında bırakılır.

Microsoft C için varsayılan değer, Microsoft uzantılarının etkinleştirilme içindir. Bu uzantıları devre dışı bırakmak için /Za kullanın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C belirteçleri](../c-language/c-tokens.md)
