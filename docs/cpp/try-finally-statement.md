---
title: try-finally deyimi
description: __Try ve yapılandırılmış özel durum işleme deyimlerinin __finally Microsoft C++ başvurusu.
ms.date: 08/25/2020
f1_keywords:
- __try
- _try
- __leave_cpp
- __leave
- __finally_cpp
- __try_cpp
- __finally
- _finally
helpviewer_keywords:
- __try keyword [C++]
- __finally keyword [C++]
- __leave keyword [C++]
- try-catch keyword [C++], try-finally keyword
- try-finally keyword [C++]
- __finally keyword [C++], try-finally statement syntax
- __leave keyword [C++], try-finally statement
- structured exception handling [C++], try-finally
ms.assetid: 826e0347-ddfe-4f6e-a7bc-0398e0edc7c2
ms.openlocfilehash: edabbbe35c86f0305e31f36584c4dfe01f2f88cd
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898639"
---
# <a name="try-finally-statement"></a>`try-finally` Ekstre

`try-finally`Bu ifade, C ve C++ dillerinde yapılandırılmış özel durum işlemeyi destekleyen, **Microsoft 'a özgü** bir uzantıdır.

## <a name="syntax"></a>Syntax

Aşağıdaki sözdizimi, ifadesini açıklar `try-finally` :

```cpp
    // . . .
    __try {
        // guarded code
    }
    __finally {
        // termination code
    }
    // . . .
```

## <a name="grammar"></a>Dilbilgisi

> *`try-finally-statement`*:\
> &emsp;**`__try`** *`compound-statement`* **`__finally`** *`compound-statement`*

`try-finally`Bu ifade, bir kod bloğunun yürütülmesi kesintiye uğradığında, hedef uygulamaların Temizleme kodunun yürütülmesini garanti etmesini sağlayan C ve C++ dillerinin Microsoft uzantısıdır. Temizleme, bellek ayırmayı, dosyaları kapatmayı ve dosya tutamaçlarını serbest bırakmayı, bu görevlerden oluşur. Bu `try-finally` ifade özellikle, bir hatanın, zamanından önce geri dönememesine neden olabilecek birkaç yere sahip yordamlar için yararlıdır.

İlgili bilgi ve kod örneği için [ `try-except` bkz..](../cpp/try-except-statement.md) Genel olarak yapılandırılmış özel durum işleme hakkında daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme](../cpp/structured-exception-handling-c-cpp.md). C++/CLı ile yönetilen uygulamalarda özel durumları işleme hakkında daha fazla bilgi için, bkz. [özel `/clr` durum işleme ](../extensions/exception-handling-cpp-component-extensions.md).

> [!NOTE]
> Yapılandırılmış özel durum işlemi, hem C hem de C++ kaynak dosyaları için Win32 ile çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme her türden özel durumu işleyebildiği için daha esnektir. C++ programları için, c++ özel durum işleme mekanizmasını ([ `try` , `catch` ve `throw` ](../cpp/try-throw-and-catch-statements-cpp.md) deyimlerini) kullanmanız önerilir.

Yan tümcesinden sonraki bileşik ifade, **`__try`** korunan bölümdür. Yan tümcesinden sonraki bileşik ifade **`__finally`** sonlandırma işleyicisidir. İşleyici, korunan bölüm çıkıldığında, korunan bölümü bir özel durum (olağan dışı sonlandırma) veya standart Fall (normal sonlandırma) ile sonlandırıp sonlandırdığı zaman yürütülen bir eylem kümesini belirtir.

Denetim, **`__try`** basit sıralı yürütme (geçiş) ile bir ifadeye ulaşır. Denetim öğesine girdiğinde **`__try`** , ilişkili işleyicisi etkin hale gelir. Denetim akışı try bloğunun sonuna ulaşırsa, yürütme aşağıdaki gibi devam eder:

1. Sonlandırma işleyicisi çağrılır.

1. Sonlandırma işleyicisi tamamlandığında, yürütme deyimden sonra devam eder **`__finally`** . Ancak, korunan bölüm sonlanır (örneğin, **`goto`** korunan **`return`** gövdeden veya bir deyimin dışında), sonlandırma işleyicisi denetim akışı korunan bölümden *geçmeden önce* yürütülür.

   Bir **`__finally`** ifade uygun özel durum işleyicisini aramayı engellemez.

Blokta bir özel durum oluşursa **`__try`** , işletim sistemi özel durum için bir işleyici bulmalıdır veya program başarısız olur. Bir işleyici bulunursa, hiçbir ve tüm **`__finally`** blokları yürütülür ve yürütme işleyicide sürdürülür.

Örneğin, aşağıdaki şekilde gösterildiği gibi bir dizi işlevin, A işlevini D işlevine çağırdığı hakkında düşünün. Her işlevde bir sonlandırma işleyicisi vardır. Bir özel durum D işlevinde ve içinde işlenirse, Sistem yığını kaldırmasından sonra sonlandırma işleyicileri bu sırada çağrılır: D, C, B.

![Sonlandırma&#45;işleyicisi yürütme sırası](../cpp/media/vc38cx1.gif "Sonlandırma&#45;işleyicisi yürütme sırası") <br/>
Sonlandırma Işleyicisi yürütme sırası

> [!NOTE]
> Try-finally davranışı, C# gibi kullanımını destekleyen diğer dillerden farklıdır **`finally`** .  Tek biri **`__try`** , ve öğelerinin her ikisine de sahip olabilir **`__finally`** **`__except`** .  Her ikisi birlikte kullanılacaksa, bir dış try-except ifadesinin INNER try-finally ifadesini içermesi gerekir.  Her bir bloğun ne zaman yürütüldüğünü belirten kurallar da farklıdır.

,, Ve önceki sürümleriyle uyumluluk için,, ve, **`_try`** **`_finally`** **`_leave`** **`__try`** **`__finally`** **`__leave`** derleyici seçeneği [ `/Za` (dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md) belirtilmediyse, ve için eş anlamlılardır.

## <a name="the-__leave-keyword"></a>__leave Anahtar Sözcüğü

**`__leave`** Anahtar sözcüğü, yalnızca bir deyimin korunan bölümünde geçerlidir `try-finally` ve etkisi, korunan bölümün sonuna atlamanız olur. Yürütme, sonlandırma işleyicisindeki ilk ifadede devam eder.

Bir **`goto`** deyim ayrıca korunan bölümden de geçebilir, ancak yığın geri sarma 'yı çağırdığı için performansı düşürür. **`__leave`** İfade, yığın geri sarma nedeniyle daha etkilidir.

## <a name="abnormal-termination"></a>Olağan dışı sonlandırma

`try-finally` [Longjmp](../c-runtime-library/reference/longjmp.md) çalışma zamanı işlevini kullanarak bir deyimden çıkmak olağan dışı sonlandırma olarak değerlendirilir. Bir deyime geçmek yasal değildir **`__try`** , ancak bir ifadeye geçmek yasal değildir. **`__finally`** Ayrılma noktası (bloğun normal sonlandırması **`__try`** ) ve hedef ( **`__except`** özel durumu işleyen blok) arasında etkin olan tüm deyimler çalıştırılmalıdır. Bu, yerel bir *geriye doğru izleme*olarak adlandırılır.

Bir **`__try`** blok, bloğa bir geç dahil olmak üzere herhangi bir nedenle erken sonlandırıldıysa, sistem, **`__finally`** yığını geriye doğru izleme işleminin bir parçası olarak ilişkili bloğu yürütür. Bu gibi durumlarda, [`AbnormalTermination`](/windows/win32/Debug/abnormaltermination) işlev **`true`** bloğunun içinden çağrıldığında döndürür **`__finally`** ; Aksi takdirde, döndürür **`false`** .

Sonlandırma işleyicisi, bir işlem bir deyimin yürütülmesi ortasında sonlandırılabilecek şekilde çağrılmaz `try-finally` .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[Sonlandırma-işleyici sözdizimi](/windows/win32/Debug/termination-handler-syntax)
