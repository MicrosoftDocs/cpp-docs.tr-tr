---
title: C açıklamaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- code comments, C code
- comments, documenting code
- comments, C code
- /* */ comment delimiters
- comments
ms.assetid: 0f5f2825-e673-49e7-8669-94e2f5294989
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3a6c2d32596aa8205d02ee5cddb28b5ba3c8166
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="c-comments"></a>C Açıklamaları
Bir iletme eğik çizgi/yıldız birleşimi ile başlayan bir karakter dizisi "comment" olan (<b>/\*</b>), tek bir boşluk karakteri olarak derleyici tarafından kabul edilir ve aksi halde yoksayılır. Bir yorum yeni satır karakterleri dahil olmak üzere, ancak "açıklama bitiş" sınırlayıcı hariç gösterilebilir karakter kümesinden karakter herhangi bir birleşimini içerebilir (<b>\*/</b>). Açıklamalar, birden fazla satır kaplayabilir, ancak iç içe geçemez.  
  
 Açıklamalar, boşluk karakterine izin verilen her yerde görünebilir. Derleyici bir yorumu tek bir boşluk karakteri olarak değerlendirdiği için belirteçlere sahip açıklamaları dahil edemezsiniz. Derleyici, açıklamadaki karakterleri yoksayar.  
  
 Kodunuzu belgelemek için açıklamaları kullanabilirsiniz. Bu örnek, derleyici tarafından kabul edilen bir açıklamadır:  
  
```  
/* Comments can contain keywords such as  
   for and while without generating errors. */  
```  
  
 Yorumlar, kod deyimi ile aynı satırda görünebilir:  
  
```  
printf( "Hello\n" );  /* Comments can go here */  
```  
  
 İşlevlerin veya program modüllerinin önüne tanımlayıcı bir açıklama bloğu yerleştirebilirsiniz:  
  
```  
/* MATHERR.C illustrates writing an error routine   
 * for math functions.   
 */   
```  
  
 Açıklamalar iç içe açıklamalar içeremeyeceği için bu örnek bir hataya neden olur:  
  
```  
/* Comment out this routine for testing   
  
   /* Open file */  
    fh = _open( "myfile.c", _O_RDONLY );  
    .  
    .  
    .  
 */  
```  
  
 Hatanın nedeni, derleyicinin `*/` sözcüğünden sonra gelen ilk `Open file` dizisini açıklama sonu olarak algılamasıdır. Kalan metni işlemeye çalışır ve açıklamanın dışında `*/` bulduğunda bir hata oluşturur.  
  
 Test amaçları için etkin olmayan bir kodun belirli satırlarını oluşturmak üzere açıklamaları kullanabilirsiniz; bununla birlikte, `#if` ve `#endif` önişlemci yönergeleri ve koşullu derleme bu görev için kullanışlı bir alternatif oluşturur. Daha fazla bilgi için bkz: [önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) içinde *önişlemci başvurusu*.  
  
 **Microsoft özel**  
  
 Microsoft derleyici tarafından iki eğik öncesinde tek satırlı yorumlar da destekler (**//**). /Za (ANSI standardı) ile derleme yaparsanız, bu açıklamalar hatalar oluşturur. Bu açıklamalar, ikinci satıra genişletilemez.  
  
```  
// This is a valid comment  
```  
  
 İki eğik çizgi ile başlayan yorumları (**//**) bir kaçış karakteriyle öncesinde sonraki yeni satır karakteri tarafından sonlandırıldı. Sonraki örnekte yeni satır karakteri bir ters eğik çizgi (**\\**), bir "kaçış sırası." oluşturma Bu kaçış dizisi, derleyicinin sonraki satırı önceki satırın bir parçası olarak değerlendirmesine neden olur. (Daha fazla bilgi için bkz: [kaçış sıraları](../c-language/escape-sequences.md).)  
  
```  
// my comment \  
    i++;   
```  
  
 Bu nedenle, `i++;` deyimi açıklama dışında bırakılır.  
  
 Microsoft C için Microsoft uzantıları etkinleştirildiğini varsayılandır. Bu uzantıları devre dışı bırakmak için /Za kullanın.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Belirteçleri](../c-language/c-tokens.md)
