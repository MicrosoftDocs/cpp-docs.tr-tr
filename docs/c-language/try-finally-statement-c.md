---
title: try-finally Deyimi (C)
ms.date: 11/04/2016
helpviewer_keywords:
- try-finally keyword [C]
- __finally keyword [C], try-finally statement syntax
- __finally keyword [C]
- structured exception handling, try-finally
ms.assetid: 514400c1-c322-4bf3-9e48-3047240b8a82
ms.openlocfilehash: 82cc5ffa3f50196fc5f518b8bb5b2080ff14fd8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345312"
---
# <a name="try-finally-statement-c"></a>try-finally Deyimi (C)

**Microsoft'a özgü**

`try-finally` Deyimi, uygulamaların kod bloğunun yürütülmesi kesintiye uğradığında temizleme kodu yürütme garanti sağlayan C diline yönelik bir Microsoft uzantısıdır. Temizleme gibi görevleri belleğini, dosyaları kapatma ve dosya tanıtıcıları bırakarak oluşur. `try-finally` Sahip olduğu bir onay yapılır neden olabilecek bir hata için erken çeşitli yerlerde yordamlarını yordamından döndürmek için deyimi özellikle yararlıdır.

*try-finally deyimi*: **__try** *bileşik deyim*  

**__finally** *bileşik deyim* 

Sonra gelen bileşik deyim `__try` yan tümcesi ise korunan bölümün. Sonra gelen bileşik deyim `__finally` yan tümcesi ise sonlandırma işleyicisi. İşleyici, korunan bölümün çıkıldı, standart fall (normal sonlandırması) üzerinden veya bir özel durum (olağan dışı sonlandırma) tarafından korunan bölümün çıkıldı olmadığını yürütme eylemleri kümesini belirtir.

Denetim ulaştığında bir `__try` deyimi tarafından basit sıralı yürütme (fall aracılığıyla). Denetim girdiğinde `__try` deyimi, kendi ilişkili işleyicisi etkin hale gelir. Yürütme aşağıdaki gibi çalışır:

1. Korunan bölüm yürütülür.

1. Sonlandırma işleyicisi çağrılır.

1. Sonlandırma işleyicisi tamamlandığında sonra yürütülmesine devam `__finally` deyimi. Bağımsız olarak nasıl korunan bölüm sona erer (örneğin, aracılığıyla bir `goto` deyimi korumalı gövdenin dışında veya aracılığıyla bir `return` deyimi), denetim akışı korumalı bölümün dışına taşınmadan önce sonlandırma işleyicisi yürütülür.

`__leave` Sözcüktür içinde geçerli bir `try-finally` deyim bloğu. Etkisini `__leave` sonuna başlayabiliriz `try-finally` blok. Sonlandırma işleyicisi hemen çalıştırılır. Ancak bir `goto` deyimi aynı sonuca ulaşmak için kullanılabilir bir `goto` deyimi, yığın geriye doğru izleme neden olur. `__leave` Deyimi olduğundan daha verimli yığın geriye doğru izleme gerektirmez.

Çıkmadan bir `try-finally` using deyimi bir `return` deyimi veya `longjmp` çalışma zamanı işlevi olağan dışı sonlandırma olarak kabul edilir. Bloğuna atlamak için geçersiz bir `__try` deyimi, ancak yasal birinden dışarı atlanabilir. Tüm `__finally` kalkış noktası ve hedef arasında etkin olan deyimleri çalıştırılmalıdır. Bu durum, bir "yerel geriye doğru izlemeyi." olarak adlandırılır.

Sonlandırma işleyicisi bir işlem yürütülürken sonlandırılırsa çağrılmaz bir `try-finally` deyimi.

> [!NOTE]
>  Yapılandırılmış özel durum işleme, C ve C++ kaynak dosyaları ile çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme mekanizmasını daha esnek, her türden özel durumları işleyebilir olmamasıdır.

> [!NOTE]
>  C++ programları için C++ özel durum işleme, yapılandırılmış özel durum işleme yerine kullanılmalıdır. Daha fazla bilgi için [özel durum işleme](../cpp/exception-handling-in-visual-cpp.md) içinde *C++ dil başvurusu*.

Örneğin bakın [deneyin-except deyimi](../c-language/try-except-statement-c.md) görmek için nasıl `try-finally` deyimi çalışır.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[try-finally Deyimi](../cpp/try-finally-statement.md)
