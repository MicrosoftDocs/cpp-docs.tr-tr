---
title: Onaylama ve Kullanıcının Sağladığı İletiler (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- user-supplied messages [C++], run time
- user-supplied messages [C++], preprocessor time
- '#error%2C assert%2C static_assert [C++]'
- user-supplied messages [C++], compile time
ms.assetid: ebf7d885-61c8-4233-b0ae-1c9a38e0f385
ms.openlocfilehash: d76f0c2f7dc5a4202bff3f93e097a1c186f4601a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190566"
---
# <a name="assertion-and-user-supplied-messages-c"></a>Onaylama ve Kullanıcının Sağladığı İletiler (C++)

Dil, uygulamanızda hata ayıklamanıza yardımcı olan üç hata işleme mekanizmasını destekler: [#error yönergesi](../preprocessor/hash-error-directive-c-cpp.md), static_assert anahtar sözcüğü ve [onaylama makrosu, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu. [static_assert](../cpp/static-assert.md) C++ Üç mekanizmaların hepsi hata iletileri ve iki Ayrıca yazılım onaylamalarını da test edin. Yazılım onay belgesi, programınızda belirli bir noktada doğru olması beklenen bir koşulu belirtir. Derleme zamanı onaylama işlemi başarısız olursa, derleyici bir tanılama iletisi ve derleme hatası verir. Çalışma zamanı onayı başarısız olursa, işletim sistemi bir tanılama iletisi yayınlar ve uygulamanızı kapatır.

## <a name="remarks"></a>Açıklamalar

Uygulamanızın ömrü, ön işleme, derleme ve çalışma zamanı aşamasından oluşur. Her hata işleme mekanizması, bu aşamalardan biri sırasında kullanılabilen hata ayıklama bilgilerine erişir. Etkin bir şekilde hata ayıklamak için, bu aşama hakkında uygun bilgileri sağlayan mekanizmayı seçin:

- [#Error yönergesi](../preprocessor/hash-error-directive-c-cpp.md) ön işleme sırasında etkilidir. Kullanıcı tarafından belirtilen bir iletiyi koşulsuz olarak yayar ve derlemenin hata vererek başarısız olmasına neden olur. İleti, Önişlemci yönergeleri tarafından yönetilen bir metin içerebilir, ancak ortaya çıkan tüm ifadeler değerlendirilmez.

- [Static_assert](../cpp/static-assert.md) bildirimi, derleme zamanında geçerli olur. Boole değerine dönüştürülebilen, Kullanıcı tarafından belirtilen integral ifadesiyle temsil edilen bir yazılım onayını sınar. İfade sıfır (false) olarak değerlendirilirse, derleyici Kullanıcı tarafından belirtilen iletiyi yayınlar ve derleme hata vererek başarısız olur.

   `static_assert` bildirimi, şablon bağımsız değişkenleri Kullanıcı tarafından belirtilen ifadeye dahil olabileceğinden, özellikle hata ayıklama için yararlıdır.

- [Onaylama makrosu, _assert _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu çalışma zamanında etkilidir. Kullanıcı tarafından belirtilen bir ifadeyi değerlendirir ve sonuç sıfırsa, sistem bir tanılama iletisi yayınlar ve uygulamanızı kapatır. [_Assert](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) ve _ASSERTE gibi birçok farklı makro, bu makroya benzer ancak sistem tarafından tanımlanan veya Kullanıcı tanımlı tanılama iletileri verebilir.

## <a name="see-also"></a>Ayrıca bkz.

[#error Yönergesi (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[assert Makrosu, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[_ASSERT, _ASSERTE, _ASSERT_EXPR Makroları](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)<br/>
[static_assert](../cpp/static-assert.md)<br/>
[_STATIC_ASSERT Makrosu](../c-runtime-library/reference/static-assert-macro.md)<br/>
[Şablonlar](../cpp/templates-cpp.md)
