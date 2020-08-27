---
title: try-finally deyimi (C)
description: Microsoft C/C++, bir try-finally deyimin dili uzantısı kullanarak yapılandırılmış özel durum Işleme (SEH) uygular.
ms.date: 08/24/2020
helpviewer_keywords:
- try-finally keyword [C]
- __finally keyword [C], try-finally statement syntax
- __finally keyword [C]
- structured exception handling, try-finally
ms.assetid: 514400c1-c322-4bf3-9e48-3047240b8a82
ms.openlocfilehash: 6f9cf901ed0a82b355880225c902ec4fc3e1082b
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898707"
---
# <a name="try-finally-statement-c"></a>try-finally deyimi (C)

**Microsoft'a özgü**

Bu `try-finally` ifade, bir kod bloğunun yürütülmesi kesintiye uğradığında uygulamaların Temizleme kodunu yürütmeyi garanti etmesini sağlayan C diline yönelik bir Microsoft uzantısıdır. Temizleme, bellek ayırmayı, dosyaları kapatmayı ve dosya tutamaçlarını serbest bırakmayı, bu görevlerden oluşur. Bu `try-finally` ifade özellikle, bir hatanın, zamanından önce geri dönememesine neden olabilecek birkaç yere sahip yordamlar için yararlıdır.

> *`try-finally-statement`*:\
> &emsp;**`__try`** *`compound-statement`* **`__finally`** *`compound-statement`*

Yan tümcesinden sonraki bileşik ifade, **`__try`** korunan bölümdür. Yan tümcesinden sonraki bileşik ifade **`__finally`** sonlandırma işleyicisidir. İşleyici, korunan bölüm çıkıldığında yürütülen bir eylem kümesi belirtir. Korunan bölümün bir özel durum (olağan dışı sonlandırma) veya standart Fall (normal sonlandırma) tarafından mı çıkış olduğuna bakılmaksızın.

Denetim, **`__try`** basit sıralı yürütme (geçiş) ile bir ifadeye ulaşır. Denetim **`__try`** ifadeye girdiğinde, ilişkili işleyicisi etkin hale gelir. Yürütme aşağıdaki gibi devam eder:

1. Korunan bölüm yürütülür.

1. Sonlandırma işleyicisi çağrılır.

1. Sonlandırma işleyicisi tamamlandığında, yürütme deyimden sonra devam eder **`__finally`** . Korunan bölümün nasıl bitdiğine bakılmaksızın (örneğin, **`goto`** korunan gövdeden veya bir **`return`** deyimden bir deyimle), sonlandırma işleyicisi denetim akışı korunan bölümden geçmeden önce yürütülür.

**`__leave`** Anahtar sözcüğü bir `try-finally` Ekstre bloğunda geçerlidir. Öğesinin etkisi, **`__leave`** bloğun sonuna atlamanız `try-finally` . Sonlandırma işleyicisi hemen yürütülür. **`goto`** Aynı sonucu elde etmek için bir ifade kullanılabilse de, bir **`goto`** ifade yığın geri sarma oluşmasına neden olur. **`__leave`** İfade, yığın geri sarma içermediğinden daha etkilidir.

Bir deyimin `try-finally` veya çalışma zamanı işlevinin kullanıldığı bir deyimden çıkmak **`return`** `longjmp` olağan dışı sonlandırma olarak değerlendirilir. Bir ifadeye geçmek yasal değildir **`__try`** , ancak bunlardan biri atlanamaz. **`__finally`** Ayrılma noktası ve hedefin hedefi arasında etkin olan tüm deyimler çalıştırılmalıdır. Bu, yerel bir *geriye doğru izleme*olarak adlandırılır.

Bir işlem, bir deyimin yürütüldüğü sırada sonlandırılabilmesi durumunda sonlandırma işleyicisi çağrılmaz `try-finally` .

> [!NOTE]
> Yapılandırılmış özel durum işleme C ve C++ kaynak dosyalarıyla birlikte çalışmaktadır. Ancak, özellikle C++ için tasarlanmamıştır. Taşınabilir C++ programları için, yapılandırılmış özel durum işleme yerine C++ özel durum işleme kullanılmalıdır. Ayrıca, C++ özel durum işleme mekanizması, herhangi bir türdeki özel durumları işleyebilmek için çok daha esnektir. Daha fazla bilgi için bkz. *C++ dil başvurusunda* [özel durum işleme](../cpp/exception-handling-in-visual-cpp.md) .

Deyimin nasıl çalıştığını görmek için [ `try-except` deyimin](../c-language/try-except-statement-c.md) örneğine bakın `try-finally` .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[`try-finally` ifade (C++)](../cpp/try-finally-statement.md)
