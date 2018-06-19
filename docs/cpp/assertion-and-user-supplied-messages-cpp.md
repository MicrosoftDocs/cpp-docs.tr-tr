---
title: Onaylama ve kullanıcının sağladığı iletiler (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- user-supplied messages [C++], run time
- user-supplied messages [C++], preprocessor time
- '#error%2C assert%2C static_assert [C++]'
- user-supplied messages [C++], compile time
ms.assetid: ebf7d885-61c8-4233-b0ae-1c9a38e0f385
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e93798dadee3e4270d82eac84a794c6133c05c07
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411711"
---
# <a name="assertion-and-user-supplied-messages-c"></a>Onaylama ve Kullanıcının Sağladığı İletiler (C++)
Yardımcı C++ dili destekler üç hata işleme mekanizmaları uygulamanızda hata ayıklama: [#error yönergesi](../preprocessor/hash-error-directive-c-cpp.md), [static_assert](../cpp/static-assert.md) anahtar sözcüğü ve [assert makrosu, _assert, _ wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu. Hata iletileri üç mekanizma vermek ve ayrıca test iki yazılım onaylar. Bir yazılım onaylama programınızdaki belirli bir noktada doğru olması için beklediğiniz bir koşulu belirtir. Derleme zamanı onaylama başarısız olursa, derleyici bir tanılama iletisi ve derleme hatası verir. Çalışma zamanı onaylama başarısız olursa, işletim sisteminin bir tanılama iletisi yayınlar ve uygulamanızı kapatır.  
  
## <a name="remarks"></a>Açıklamalar  
 Ön işleme uygulamanızın ömrünü oluşur, derleyin ve zaman aşaması çalıştırın. Her hata mekanizması işleme Bu aşamalar biri sırasında hata ayıklama bilgileri erişir. Etkili bir şekilde hata ayıklamak için bu aşamada ilgili bilgileri sağlayan mekanizması seçin:  
  
-   [#Error yönergesi](../preprocessor/hash-error-directive-c-cpp.md) zaman ön işleme sırasında etkili olur. Koşulsuz olarak bir kullanıcı tarafından belirtilen ileti yayar ve derlemesinin bir hata ile başarısız olmasına neden olur. Önişlemci yönergeleri tarafından yönetilebilir metin iletisi içerebilir ancak herhangi bir sonuç ifade değerlendirilmez.  
  
-   [Static_assert](../cpp/static-assert.md) bildirimidir yürürlükte derleme zamanında. Kullanıcı tarafından belirtilen ve bir Boolean değerine dönüştürülebilir bir tamsayı ifade tarafından temsil edilen bir yazılım onaylama sınar. Sıfır (false) ifadeyi hesaplar, kullanıcı tanımlı iletinin derleyici sorunları ve derleme bir hata ile başarısız olur.  
  
     `static_assert` Bildirimi, bağımsız şablon kullanıcı tarafından belirtilen ifade eklenebilir olduğundan, şablonları hata ayıklama için özellikle yararlıdır.  
  
-   [Assert makrosu, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu olduğundan geçerli çalışma zamanında. Bir kullanıcı tarafından belirtilen ifadeyi değerlendirir ve sonuç sıfır ise, sistem bir tanılama iletisi yayınlar ve uygulamanızı kapatır. Diğer birçok makrolar gibi[_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) ve `_ASSERTE`, bu makrosu benzer ancak farklı sistem tanımlı veya kullanıcı tanımlı tanılama iletileri sorun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#error yönergesi (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)   
 [Assert makrosu, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [_ASSERT, _ASSERTE, _ASSERT_EXPR makroları](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)   
 [static_assert](../cpp/static-assert.md)   
 [_Statıc_assert makrosu](../c-runtime-library/reference/static-assert-macro.md)   
 [Şablonlar](../cpp/templates-cpp.md)