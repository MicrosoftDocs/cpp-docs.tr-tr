---
title: try-finally Deyimi (C)
ms.date: 11/04/2016
helpviewer_keywords:
- try-finally keyword [C]
- __finally keyword [C], try-finally statement syntax
- __finally keyword [C]
- structured exception handling, try-finally
ms.assetid: 514400c1-c322-4bf3-9e48-3047240b8a82
ms.openlocfilehash: 61a6a9edd9faaf8afb06bb7bfdc619cddde3e6fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349610"
---
# <a name="try-finally-statement-c"></a>try-finally Deyimi (C)

**Microsoft'a Özgü**

İfade, `try-finally` bir kod bloğunun yürütülmesi kesintiye uğradığında uygulamaların temizleme kodunun yürütülmesini garanti etmesini sağlayan C dilinin Microsoft uzantısıdır. Temizleme, bellek ayırma, dosyaları kapatma ve dosya tutamaçları serbest bırakma gibi görevlerden oluşur. İfade, `try-finally` özellikle rutinden erken dönüşe neden olabilecek bir hata için çek yapıldığı birkaç yeri olan yordamlar için yararlıdır.

*try-finally-statement*: **__try**  *bileşik deyimi*

**__finally**  *bileşik deyimi*

Maddeden `__try` sonraki bileşik ifade korunan bölümdür. Yan tümceden `__finally` sonraki bileşik deyimi sonlandırma işleyicisidir. İşleyici, korunan bölüm çıkarKen, korunan bölümün bir özel durum (anormal sonlandırma) veya standart düşüş (normal sonlandırma) tarafından çıkarılıp çıkarılmadığını çalıştıran bir dizi eylem belirtir.

Denetim basit `__try` sıralı yürütme (üzerinden düşmek) tarafından bir ifadeulaşır. `__try` Denetim deyimi girdiğinde, ilişkili işleyicisi etkin olur. Yürütme aşağıdaki gibi devam eder:

1. Korunan bölüm yürütülür.

1. Sonlandırma işleyicisi çağrılır.

1. Sonlandırma işleyicisi tamamlandığında, yürütme `__finally` deyimden sonra devam eder. Korunan bölümün nasıl sona ererdiklerinden bağımsız `goto` olarak (örneğin, korunan gövdeden `return` çıkan bir ifade yoluyla veya bir deyim le), denetim akışı korunan bölümden çıkmadan önce sonlandırma işleyicisi yürütülür.

`__leave` Anahtar kelime bir `try-finally` deyim bloğu içinde geçerlidir. Etkisi `try-finally` bloğun `__leave` sonuna atlamaktır. Sonlandırma işleyicisi hemen yürütülür. Bir `goto` deyim aynı sonucu gerçekleştirmek için kullanılabilir, ancak bir `goto` deyim yığın gevşeme neden olur. Yığın `__leave` gevşeme içermediğinden deyim daha verimlidir.

Bir deyim `try-finally` veya `return` `longjmp` çalışma zamanı işlevi kullanarak bir deyim den çıkma anormal sonlandırma olarak kabul edilir. Bir `__try` açıklamaya atlamak yasadışı, ama birinden atlamak yasal. Kalkış `__finally` noktası ile hedef arasında etkin olan tüm ifadeler çalıştırılmalıdır. Buna "yerel gevşeme" denir.

Bir `try-finally` bildirim icra edilirken bir işlem öldürülürse sonlandırma işleyicisi çağrılmaz.

> [!NOTE]
> Yapılandırılmış özel durum işleme C ve C++ kaynak dosyalarıyla çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme mekanizması, her türlü özel durumları işleyebilir, çok daha esnektir.

> [!NOTE]
> C++ programları için yapılandırılmış özel durum işleme yerine C++ özel durum işleme kullanılmalıdır. Daha fazla bilgi için *C++ Dil Başvurusu'nda* [Özel Durum Kullanımı'na](../cpp/exception-handling-in-visual-cpp.md) bakın.

İfadenin nasıl çalıştığını görmek için [deneme dışı deyiminin](../c-language/try-except-statement-c.md) örneğine bakın. `try-finally`

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[try-finally Deyimi](../cpp/try-finally-statement.md)
