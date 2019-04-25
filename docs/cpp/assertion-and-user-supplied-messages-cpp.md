---
title: Onaylama ve Kullanıcının Sağladığı İletiler (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- user-supplied messages [C++], run time
- user-supplied messages [C++], preprocessor time
- '#error%2C assert%2C static_assert [C++]'
- user-supplied messages [C++], compile time
ms.assetid: ebf7d885-61c8-4233-b0ae-1c9a38e0f385
ms.openlocfilehash: 913aa199b4acd2ceb6daf7a24d8c50c28234b74a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184367"
---
# <a name="assertion-and-user-supplied-messages-c"></a>Onaylama ve Kullanıcının Sağladığı İletiler (C++)

C++ Yardımcı dili destekleyen üç hata işleme düzenekleri uygulamanızı hata ayıklama: [#error yönergesi](../preprocessor/hash-error-directive-c-cpp.md), [static_assert](../cpp/static-assert.md) anahtar sözcüğü ve [assert makrosu, _ Assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu. Hata iletileri üç mekanizma vermek ve iki Ayrıca yazılım onaylar test edin. Yazılım onaylama programınızda belirli bir noktada doğru olması beklenen bir koşulu belirtir. Bir derleme zamanı onaylama işlemi başarısızsa, derleyici bir tanılama iletisi ve bir derleme hatası verir. Bir çalışma zamanı onaylama başarısız olursa, işletim sisteminin bir tanılama iletisi yayınlar ve uygulamanızı kapatır.

## <a name="remarks"></a>Açıklamalar

Zaman aşamayı çalıştırmak ve derleme veya ön işleme uygulamanızın ömrünü oluşur. Her bir hata işleme mekanizması biri bu aşamaları sırasında kullanılabilir hata ayıklama bilgileri erişir. Etkili bir şekilde hata ayıklamak için bu aşamada ilgili bilgileri sağlayan mekanizma seçin:

- [#Error yönergesi](../preprocessor/hash-error-directive-c-cpp.md) zaman ön işleme sırasında yürürlükte olur. Koşulsuz olarak bir kullanıcı tarafından belirtilen iletiyi yayar ve derlemesinin bir hata ile başarısız olmasına neden olur. Önişlemci yönergeleri tarafından yönetilen bir metin iletisi içerebilir, ancak herhangi bir sonuç ifade değerlendirilmez.

- [Static_assert](../cpp/static-assert.md) bildirimi yürürlükte olan derleme zamanında. Bu kullanıcı tarafından belirtilen ve bir Boolean değerine dönüştürülebilir bir integral ifadesi tarafından temsil edilen bir yazılım onayını sınar. İfade sıfır (false) olarak değerlendirilirse, kullanıcı tarafından belirtilen ileti derleyici verir ve derleme bir hata ile başarısız olur.

   `static_assert` Bildirimi, şablon bağımsız değişkenleri, kullanıcı tarafından belirtilen ifade eklenebilir olduğundan, şablonları hata ayıklama için özellikle kullanışlıdır.

- [Assert makrosu, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu yürürlükte olan çalışma zamanında. Bir kullanıcı tarafından belirtilen ifadeyi değerlendirir ve sonucu sıfır ise, sistem bir tanılama iletisi yayınlar ve uygulamanızı kapatır. Diğer birçok makrolar gibi[_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) ve _ASSERTE, bu makroyu benzer ancak farklı sistem tanımlı veya kullanıcı tanımlı tanılama iletileri yayınlar.

## <a name="see-also"></a>Ayrıca bkz.

[#error Yönergesi (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[assert Makrosu, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[_ASSERT, _ASSERTE, _ASSERT_EXPR Makroları](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)<br/>
[static_assert](../cpp/static-assert.md)<br/>
[_STATIC_ASSERT Makrosu](../c-runtime-library/reference/static-assert-macro.md)<br/>
[Şablonlar](../cpp/templates-cpp.md)