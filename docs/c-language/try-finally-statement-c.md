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

Bu `try-finally` ifade, bir kod bloğunun yürütülmesi kesintiye uğradığında uygulamaların Temizleme kodunu yürütmeyi garanti etmesini sağlayan C diline yönelik bir Microsoft uzantısıdır. Temizleme, bellek ayırmayı, dosyaları kapatmayı ve dosya tutamaçlarını serbest bırakmayı, bu görevlerden oluşur. Bu `try-finally` ifade özellikle, bir hatanın, zamanından önce geri dönememesine neden olabilecek birkaç yere sahip yordamlar için yararlıdır.

*try-finally-deyimin*: **__try**  *bileşik ifade*

**__finally**  *bileşik ifade*

`__try` Yan tümcesinden sonraki bileşik ifade, korunan bölümdür. `__finally` Yan tümcesinden sonraki bileşik ifade sonlandırma işleyicisidir. İşleyici, korunan bölüm çıkıldığında, korunan bölümün bir özel durum (olağan dışı sonlandırma) veya standart Fall (normal sonlandırma) tarafından çıkış yapıldığında yürütülen bir eylem kümesini belirtir.

Denetim, basit `__try` sıralı yürütme (geçiş) ile bir ifadeye ulaşır. Denetim `__try` ifadeye girdiğinde, ilişkili işleyicisi etkin hale gelir. Yürütme aşağıdaki gibi devam eder:

1. Korunan bölüm yürütülür.

1. Sonlandırma işleyicisi çağrılır.

1. Sonlandırma işleyicisi tamamlandığında, yürütme `__finally` deyimden sonra devam eder. Korunan bölümün bitiş şeklinden bağımsız olarak (örneğin, korumalı `goto` gövdeden veya bir `return` deyimden bir deyimle), sonlandırma işleyicisi denetim akışı korunan bölümden ayrılmadan önce yürütülür.

`__leave` Anahtar sözcüğü bir `try-finally` ekstre bloğunda geçerlidir. Öğesinin `__leave` etkisi, `try-finally` bloğun sonuna atlamanız. Sonlandırma işleyicisi hemen yürütülür. Aynı sonucu `goto` elde etmek için bir ifade kullanılabilse de, bir `goto` ifade yığın geri sarma oluşmasına neden olur. İfade `__leave` , yığın geri sarma içermediğinden daha etkilidir.

Bir `try-finally` `return` deyimin veya `longjmp` çalışma zamanı işlevinin kullanıldığı bir deyimden çıkmak olağan dışı sonlandırma olarak değerlendirilir. Bir `__try` ifadeye geçmek geçersizdir, ancak bunlardan biri atlanmak için geçerli değildir. Ayrılma `__finally` noktası ve hedefin hedefi arasında etkin olan tüm deyimler çalıştırılmalıdır. Buna "yerel geriye doğru izleme" adı verilir.

Bir işlem, bir `try-finally` deyimin yürütüldüğü sırada sonlandırılabilmesi durumunda sonlandırma işleyicisi çağrılmaz.

> [!NOTE]
> Yapılandırılmış özel durum işleme C ve C++ kaynak dosyalarıyla birlikte çalışmaktadır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme mekanizması, herhangi bir türdeki özel durumları işleyebilmek için çok daha esnektir.

> [!NOTE]
> C++ programları için, yapılandırılmış özel durum işleme yerine C++ özel durum işleme kullanılmalıdır. Daha fazla bilgi için bkz. *C++ dil başvurusunda* [özel durum işleme](../cpp/exception-handling-in-visual-cpp.md) .

`try-finally` Deyimin nasıl çalıştığını görmek için [try-except ifadesinin](../c-language/try-except-statement-c.md) örneğine bakın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[try-finally Deyimi](../cpp/try-finally-statement.md)
