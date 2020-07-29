---
title: try-finally Deyimi (C)
ms.date: 11/04/2016
helpviewer_keywords:
- try-finally keyword [C]
- __finally keyword [C], try-finally statement syntax
- __finally keyword [C]
- structured exception handling, try-finally
ms.assetid: 514400c1-c322-4bf3-9e48-3047240b8a82
ms.openlocfilehash: b800daa7689cef769ce3a3b070c957f18e8794c9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213716"
---
# <a name="try-finally-statement-c"></a>try-finally Deyimi (C)

**Microsoft'a Özgü**

Bu `try-finally` ifade, bir kod bloğunun yürütülmesi kesintiye uğradığında uygulamaların Temizleme kodunu yürütmeyi garanti etmesini sağlayan C diline yönelik bir Microsoft uzantısıdır. Temizleme, bellek ayırmayı, dosyaları kapatmayı ve dosya tutamaçlarını serbest bırakmayı, bu görevlerden oluşur. Bu `try-finally` ifade özellikle, bir hatanın, zamanından önce geri dönememesine neden olabilecek birkaç yere sahip yordamlar için yararlıdır.

*try-finally-deyimin*: **__try**  *bileşik ifade*

**`__finally`**  *bileşik ifade*

Yan tümcesinden sonraki bileşik ifade, `__try` korunan bölümdür. Yan tümcesinden sonraki bileşik ifade **`__finally`** sonlandırma işleyicisidir. İşleyici, korunan bölüm çıkıldığında, korunan bölümün bir özel durum (olağan dışı sonlandırma) veya standart Fall (normal sonlandırma) tarafından çıkış yapıldığında yürütülen bir eylem kümesini belirtir.

Denetim, `__try` basit sıralı yürütme (geçiş) ile bir ifadeye ulaşır. Denetim `__try` ifadeye girdiğinde, ilişkili işleyicisi etkin hale gelir. Yürütme aşağıdaki gibi devam eder:

1. Korunan bölüm yürütülür.

1. Sonlandırma işleyicisi çağrılır.

1. Sonlandırma işleyicisi tamamlandığında, yürütme deyimden sonra devam eder **`__finally`** . Korunan bölümün bitiş şeklinden bağımsız olarak (örneğin, **`goto`** korumalı gövdeden veya bir **`return`** deyimden bir deyimle), sonlandırma işleyicisi denetim akışı korunan bölümden ayrılmadan önce yürütülür.

** `__leave** keyword is valid within a ` Try-finally ` statement block. The effect of **` __leave bloğun sonuna atlayacaksınız** `try-finally` . Sonlandırma işleyicisi hemen yürütülür. **`goto`** Aynı sonucu elde etmek için bir ifade kullanılabilse de, bir **`goto`** ifade yığın geri sarma oluşmasına neden olur. Yığın geri sarma içermediğinden **' __leave** deyimin daha etkilidir.

Bir deyimin `try-finally` veya çalışma zamanı işlevinin kullanıldığı bir deyimden çıkmak **`return`** `longjmp` olağan dışı sonlandırma olarak değerlendirilir. Bir ifadeye geçmek geçersizdir `__try` , ancak bunlardan biri atlanmak için geçerli değildir. **`__finally`** Ayrılma noktası ve hedefin hedefi arasında etkin olan tüm deyimler çalıştırılmalıdır. Buna "yerel geriye doğru izleme" adı verilir.

Bir işlem, bir deyimin yürütüldüğü sırada sonlandırılabilmesi durumunda sonlandırma işleyicisi çağrılmaz `try-finally` .

> [!NOTE]
> Yapılandırılmış özel durum işleme C ve C++ kaynak dosyalarıyla birlikte çalışmaktadır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme mekanizması, herhangi bir türdeki özel durumları işleyebilmek için çok daha esnektir.

> [!NOTE]
> C++ programları için, yapılandırılmış özel durum işleme yerine C++ özel durum işleme kullanılmalıdır. Daha fazla bilgi için bkz. *C++ dil başvurusunda* [özel durum işleme](../cpp/exception-handling-in-visual-cpp.md) .

Deyimin nasıl çalıştığını görmek için [try-except ifadesinin](../c-language/try-except-statement-c.md) örneğine bakın `try-finally` .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[try-finally ekstresi](../cpp/try-finally-statement.md)
