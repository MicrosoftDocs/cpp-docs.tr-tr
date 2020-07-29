---
title: Onaylama ve Kullanıcının Sağladığı İletiler (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- user-supplied messages [C++], run time
- user-supplied messages [C++], preprocessor time
- '#error%2C assert%2C static_assert [C++]'
- user-supplied messages [C++], compile time
ms.assetid: ebf7d885-61c8-4233-b0ae-1c9a38e0f385
ms.openlocfilehash: a4861b3e1d17835f11f5e148d6b62051a6747f80
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226027"
---
# <a name="assertion-and-user-supplied-messages-c"></a>Onaylama ve Kullanıcının Sağladığı İletiler (C++)

C++ dili, uygulamanızda hata ayıklamanıza yardımcı olan üç hata işleme mekanizmasını destekler: [#error yönergesi](../preprocessor/hash-error-directive-c-cpp.md), [static_assert](../cpp/static-assert.md) anahtar sözcüğü ve [onaylama makrosu, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu. Üç mekanizmaların hepsi hata iletileri ve iki Ayrıca yazılım onaylamalarını da test edin. Yazılım onay belgesi, programınızda belirli bir noktada doğru olması beklenen bir koşulu belirtir. Derleme zamanı onaylama işlemi başarısız olursa, derleyici bir tanılama iletisi ve derleme hatası verir. Çalışma zamanı onayı başarısız olursa, işletim sistemi bir tanılama iletisi yayınlar ve uygulamanızı kapatır.

## <a name="remarks"></a>Açıklamalar

Uygulamanızın ömrü, ön işleme, derleme ve çalışma zamanı aşamasından oluşur. Her hata işleme mekanizması, bu aşamalardan biri sırasında kullanılabilen hata ayıklama bilgilerine erişir. Etkin bir şekilde hata ayıklamak için, bu aşama hakkında uygun bilgileri sağlayan mekanizmayı seçin:

- [#Error yönergesi](../preprocessor/hash-error-directive-c-cpp.md) ön işleme sırasında etkilidir. Kullanıcı tarafından belirtilen bir iletiyi koşulsuz olarak yayar ve derlemenin hata vererek başarısız olmasına neden olur. İleti, Önişlemci yönergeleri tarafından yönetilen bir metin içerebilir, ancak ortaya çıkan tüm ifadeler değerlendirilmez.

- [Static_assert](../cpp/static-assert.md) bildirimi, derleme zamanında geçerli olur. Boole değerine dönüştürülebilen, Kullanıcı tarafından belirtilen integral ifadesiyle temsil edilen bir yazılım onayını sınar. İfade sıfır (false) olarak değerlendirilirse, derleyici Kullanıcı tarafından belirtilen iletiyi yayınlar ve derleme hata vererek başarısız olur.

   **`static_assert`** Bildirim özellikle, şablon bağımsız değişkenleri Kullanıcı tarafından belirtilen ifadeye dahil olabileceğinden, bu durum, şablonlarda hata ayıklama için yararlıdır.

- [Onaylama makrosu, _assert _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu çalışma zamanında etkilidir. Kullanıcı tarafından belirtilen bir ifadeyi değerlendirir ve sonuç sıfırsa, sistem bir tanılama iletisi yayınlar ve uygulamanızı kapatır. [_Assert](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) ve _ASSERTE gibi birçok farklı makro, bu makroya benzer ancak sistem tarafından tanımlanan veya Kullanıcı tanımlı tanılama iletileri verebilir.

## <a name="see-also"></a>Ayrıca bkz.

[#error yönergesi (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[onaylama makrosu, _assert _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[_ASSERT, _ASSERTE _ASSERT_EXPR makrolar](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)<br/>
[static_assert](../cpp/static-assert.md)<br/>
[_STATIC_ASSERT makro](../c-runtime-library/reference/static-assert-macro.md)<br/>
[Şablonlar](../cpp/templates-cpp.md)
