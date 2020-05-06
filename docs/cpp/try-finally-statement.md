---
title: try-finally Deyimi
ms.date: 11/19/2018
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
ms.openlocfilehash: 17f7fb415303ab74f588a2205bc9430127091e96
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825902"
---
# <a name="try-finally-statement"></a>try-finally Deyimi

**Microsoft'a Özgü**

Aşağıdaki sözdizimi, **try-finally** ifadesini açıklar:

> **\_\_almaya**<br/>
> {\
> &nbsp;&nbsp;&nbsp;&nbsp;korunan kod \
> }\
> **\_\_son olarak**\
> {\
> &nbsp;&nbsp;&nbsp;&nbsp;sonlandırma kodu \
> }

## <a name="grammar"></a>Dilbilgisi

*try-finally-deyimin*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;bileşik- *deyimin* *compound-statement* ** \_ \_** son Birleşik ifadesini deneyin ** \_ \_**

**Try-finally** , C ve C++ dillerinin bir kod bloğunun yürütülmesi kesintiye uğradığında temizleme kodunun yürütülmesini Garantilemesini sağlayan bir Microsoft uzantısıdır. Temizleme, bellek ayırmayı, dosyaları kapatmayı ve dosya tutamaçlarını serbest bırakmayı, bu görevlerden oluşur. **Try-finally** ekstresi, özellikle de zamanından önce geri dönebileceği bir hata için bir denetim yapıldığı birkaç yere sahip yordamlar için yararlıdır.

İlgili bilgi ve kod örneği için bkz. [try-except deyimleri](../cpp/try-except-statement.md). Genel olarak yapılandırılmış özel durum işleme hakkında daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme](../cpp/structured-exception-handling-c-cpp.md). C++/CLı ile yönetilen uygulamalarda özel durumları işleme hakkında daha fazla bilgi için bkz. [/clr altında özel durum işleme](../extensions/exception-handling-cpp-component-extensions.md).

> [!NOTE]
> Yapılandırılmış özel durum işlemi, hem C hem de C++ kaynak dosyaları için Win32 ile çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme her türden özel durumu işleyebildiği için daha esnektir. C++ programları için, C++ özel durum işleme mekanizmasını ([try, catch ve throw](../cpp/try-throw-and-catch-statements-cpp.md) deyimlerini) kullanmanız önerilir.

**__Try** yan tümcesinden sonraki bileşik ifade, korunan bölümdür. **__Finally** yan tümcesinden sonraki bileşik ifade sonlandırma işleyicisidir. İşleyici, korunan bölüm bir özel durum (olağan dışı sonlandırma) veya standart Fall (normal sonlandırma) tarafından çıkış yapılıp olmamasından bağımsız olarak, korunan bölüme çıkıldığında yürütülen bir eylem kümesini belirtir.

Denetim, basit sıralı yürütme (karşı) ile bir **__try** ifadesine ulaşır. Denetim **__try**girdiğinde, ilişkili işleyicisi etkin hale gelir. Denetim akışı try bloğunun sonuna ulaşırsa, yürütme aşağıdaki gibi devam eder:

1. Sonlandırma işleyicisi çağrılır.

1. Sonlandırma işleyicisi tamamlandığında, **__finally** deyiminden sonra yürütme devam eder. Korunan bölümün bitiş şeklinden bağımsız olarak (örneğin, korumalı gövdeden veya bir **dönüş** ifadesiyle bir **goto** aracılığıyla), denetim akışı korunan bölümden ayrılmadan *önce* sonlandırma işleyicisi yürütülür.

   **__Finally** bir ifade, uygun bir özel durum işleyicisi aramasını engellemez.

**__Try** bloğunda bir özel durum oluşursa, işletim sistemi özel durum için bir işleyici bulmalıdır veya program başarısız olur. Bir işleyici bulunursa, tüm **__finally** blokları yürütülür ve yürütme işleyicide sürdürülür.

Örneğin, aşağıdaki şekilde gösterildiği gibi bir dizi işlevin, A işlevini D işlevine çağırdığı hakkında düşünün. Her işlevde bir sonlandırma işleyicisi vardır. Bir özel durum D işlevinde ve içinde işlenirse, Sistem yığını kaldırmasından sonra sonlandırma işleyicileri bu sırada çağrılır: D, C, B.

![Sonlandırma&#45;işleyicisi yürütme sırası](../cpp/media/vc38cx1.gif "Sonlandırma&#45;işleyicisi yürütme sırası") <br/>
Sonlandırma Işleyicisi yürütme sırası

> [!NOTE]
> Try-finally davranışı, C# gibi **son olarak**kullanılması desteklenen diğer dillerden farklıdır.  Tek bir **__try** , **__finally** ve **__except**olamaz, ancak ikisini birden içeremez.  Her ikisi birlikte kullanılacaksa, bir dış try-except ifadesinin INNER try-finally ifadesini içermesi gerekir.  Her bir bloğun ne zaman yürütüldüğünü belirten kurallar da farklıdır.

Önceki sürümlerle uyumluluk için, **_try**, **_finally**ve **_leave** **__try**, **__finally**ve **__leave** için eş anlamlılardır, [/za \(Disable dil uzantıları devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtilmemiş

## <a name="the-__leave-keyword"></a>__leave Anahtar Sözcüğü

**__Leave** anahtar sözcüğü yalnızca **try-finally** ifadesinin korunan bölümünde geçerlidir ve etkisi, korunan bölümün sonuna atlayın. Yürütme, sonlandırma işleyicisindeki ilk ifadede devam eder.

Bir **goto** ifadesine ayrıca korunan bölüm de atlayabilir, ancak yığın geri sarma özelliğini çağırdığı için performans düşer. **__Leave** deyimleri, yığın geri sarma nedeniyle daha etkilidir.

## <a name="abnormal-termination"></a>Olağan dışı sonlandırma

[Longjmp](../c-runtime-library/reference/longjmp.md) çalışma zamanı işlevini kullanarak bir **try-finally** ifadesinden çıkmak olağan dışı sonlandırma olarak değerlendirilir. **__Try** ifadeye geçmek geçersizdir, ancak bunlardan biri atlanmak için geçerli değildir. Ayrılma noktası ( **__try** bloğunun normal sonlandırması) ve hedef (özel durumu işleyen **__except** bloğu) arasında etkin olan tüm **__finally** deyimleri çalıştırılmalıdır. Buna yerel geriye doğru izleme denir.

Bir **TRY** bloğu herhangi bir nedenden dolayı erken sonlandırıldıysa, bloğu geri alma işleminin bir parçası olarak sistem ilişkili **finally** bloğunu yürütür. Bu gibi durumlarda, bir, **finally** bloğu içinden çağrılırsa, [abnormalsonlandırma](/windows/win32/Debug/abnormaltermination) işlevi **true** değerini döndürür; Aksi takdirde, **false**döndürür.

Bir işlem bir **try-finally** ifadesinin ortasında sonlandırılabilmesi için sonlandırma işleyicisi çağrılmaz.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[Sonlandırma-Işleyici sözdizimi](/windows/win32/Debug/termination-handler-syntax)
