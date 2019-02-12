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
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152735"
---
# <a name="c-comments"></a>C Açıklamaları

Bir "Açıklama" İleri eğik çizgi/yıldız işareti birlikte başlayan bir karakter dizisidir (<strong>/\*</strong>) tek bir boşluk karakteri olarak derleyici tarafından kabul edilir ve aksi takdirde yok sayılır. Bir yorum yeni satır karakterleri dahil olmak üzere, ancak "açıklama sonu" sınırlayıcısı hariç olmak üzere temsil edilebilir karakter kümesindeki karakterlerin herhangi bir birleşimini içerebilir (<strong>\*/</strong>). Açıklamalar, birden fazla satır kaplayabilir, ancak iç içe geçemez.

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

Test amaçları için etkin olmayan bir kodun belirli satırlarını oluşturmak üzere açıklamaları kullanabilirsiniz; bununla birlikte, `#if` ve `#endif` önişlemci yönergeleri ve koşullu derleme bu görev için kullanışlı bir alternatif oluşturur. Daha fazla bilgi için [önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) içinde *önişlemci başvurusu*.

**Microsoft'a özgü**

Microsoft derleyicisi önünde iki eğik tek satırlık açıklamaları da destekler (__//__). /Za (ANSI standardı) ile derleme yaparsanız, bu açıklamalar hatalar oluşturur. Bu açıklamalar, ikinci satıra genişletilemez.

```C
// This is a valid comment
```

İki İleri eğik çizgi ile başlayan açıklamalar (__//__) bir kaçış karakteriyle öncesinde sonraki yeni satır karakteri tarafından sonlandırılır. Sonraki örnekte, yeni satır karakterini öncesinde bir ters eğik çizgi (**\\**), bir "kaçış dizisi" oluşturulmuştur. Bu kaçış dizisi, derleyicinin sonraki satırı önceki satırın bir parçası olarak değerlendirmesine neden olur. (Daha fazla bilgi için [kaçış dizileri](../c-language/escape-sequences.md).)

```C
// my comment \
    i++;
```

Bu nedenle, `i++;` deyimi açıklama dışında bırakılır.

Microsoft C için varsayılan Microsoft genişletmelerinin etkinleştirilmiş olduğu. Bu uzantıları devre dışı bırakmak için /Za kullanın.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Belirteçleri](../c-language/c-tokens.md)
