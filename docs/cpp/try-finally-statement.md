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
ms.openlocfilehash: c26b72f7c675a4130f38c515cf71ecc290328ccc
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2019
ms.locfileid: "69498601"
---
# <a name="try-finally-statement"></a>try-finally Deyimi

**Microsoft 'a özgü**

Aşağıdaki sözdizimi, **try-finally** ifadesini açıklar:

> **\_ \_try**<br/>
> {<br/>
> &nbsp; &nbsp; &nbsp; &nbsp;//korunan kod<br/>
> }<br/>
> **\_ \_finally**<br/>
> {<br/>
> &nbsp; &nbsp; &nbsp; &nbsp;//sonlandırma kodu<br/>
> }

## <a name="grammar"></a>Dilbilgisi

*try-finally-deyimin*:<br/>
&nbsp; &nbsp; &nbsp; &nbsp; **\_ \_try** *bileşik ifade* **\_** 0finally *bileşik-ekstresi*

**Try-finally** , bir kod bloğunun yürütülmesi kesintiye uğradığında, hedef uygulamaların C++ Temizleme kodunu yürütmeyi garanti etmesini sağlayan C ve dillerin Microsoft uzantısıdır. Temizleme, bellek ayırmayı, dosyaları kapatmayı ve dosya tutamaçlarını serbest bırakmayı, bu görevlerden oluşur. **Try-finally** ekstresi, özellikle de zamanından önce geri dönebileceği bir hata için bir denetim yapıldığı birkaç yere sahip yordamlar için yararlıdır.

İlgili bilgi ve kod örneği için bkz. [try-except deyimleri](../cpp/try-except-statement.md). Genel olarak yapılandırılmış özel durum işleme hakkında daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme](../cpp/structured-exception-handling-c-cpp.md). /CLI ile C++yönetilen uygulamalarda özel durumları işleme hakkında daha fazla bilgi için bkz. [/clr altında özel durum işleme](../extensions/exception-handling-cpp-component-extensions.md).

> [!NOTE]
> Yapılandırılmış özel durum işlemi, hem C hem de C++ kaynak dosyaları için Win32 ile çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme her türden özel durumu işleyebildiği için daha esnektir. Programlar C++ için, C++ özel durum işleme mekanizmasını ([try, catch ve throw](../cpp/try-throw-and-catch-statements-cpp.md) deyimlerini) kullanmanız önerilir.

**__Try** yan tümcesinden sonraki bileşik ifade, korunan bölümdür. **__Finally** yan tümcesinden sonraki bileşik ifade sonlandırma işleyicisidir. İşleyici, korunan bölüm bir özel durum (olağan dışı sonlandırma) veya standart Fall (normal sonlandırma) tarafından çıkış yapılıp olmamasından bağımsız olarak, korunan bölüme çıkıldığında yürütülen bir eylem kümesini belirtir.

Denetim, bir **__try** ifadesine basit sıralı yürütme (Fall) ile ulaşır. Denetim **__try**'a girdiğinde, ilişkili işleyicisi etkin hale gelir. Denetim akışı try bloğunun sonuna ulaşırsa, yürütme aşağıdaki gibi devam eder:

1. Sonlandırma işleyicisi çağrılır.

1. Sonlandırma işleyicisi tamamlandığında, yürütme **__finally** ifadesinden sonra devam eder. Korunan bölümün bitiş şeklinden bağımsız olarak (örneğin, korumalı gövdeden veya bir **dönüş** ifadesiyle bir **goto** aracılığıyla), denetim akışı korunan bölümden ayrılmadan *önce* sonlandırma işleyicisi yürütülür.

   Bir **__finally** açıklaması uygun özel durum işleyicisini aramayı engellemez.

**__Try** bloğunda bir özel durum oluşursa, işletim sistemi özel durum için bir işleyici bulmalıdır veya program başarısız olur. Bir işleyici bulunursa, tüm **__finally** blokları çalıştırılır ve yürütme işleyicide sürdürülür.

Örneğin, aşağıdaki şekilde gösterildiği gibi bir dizi işlevin, A işlevini D işlevine çağırdığı hakkında düşünün. Her işlevde bir sonlandırma işleyicisi vardır. Bir özel durum D işlevinde ve içinde işlenirse, Sistem yığını kaldırmasından sonra sonlandırma işleyicileri bu sırada çağrılır: D, C, B.

![Sonlandırma&#45;işleyicisi yürütme sırası](../cpp/media/vc38cx1.gif "Sonlandırma&#45;işleyicisi yürütme sırası") <br/>
Sonlandırma Işleyicisi yürütme sırası

> [!NOTE]
> Try-finally davranışı,, gibi **son**kullanılması desteklenen diğer dillerden farklıdır C#.  Tek bir **__try** , **__finally** ve **__except**öğelerinin her ikisine de sahip olabilir.  Her ikisi birlikte kullanılacaksa, bir dış try-except ifadesinin INNER try-finally ifadesini içermesi gerekir.  Her bir bloğun ne zaman yürütüldüğünü belirten kurallar da farklıdır.

Önceki sürümlerle uyumluluk için, **_try**, **_Finally**ve **_dene** , **__try**, **__finally**ve _, derleyici seçeneği [/za \(Disable Language Extensions)](../build/reference/za-ze-disable-language-extensions.md) olmadığı takdirde **__leave** için eş anlamlılar belirtilir.

## <a name="the-__leave-keyword"></a>__leave Anahtar Sözcüğü

**__Leave** anahtar sözcüğü yalnızca **try-finally** ifadesinin korunan bölümünde geçerlidir ve bu, etkisi korunan bölümün sonuna atlanmak olur. Yürütme, sonlandırma işleyicisindeki ilk ifadede devam eder.

Bir **goto** ifadesine ayrıca korunan bölüm de atlayabilir, ancak yığın geri sarma özelliğini çağırdığı için performans düşer. **__Leave** deyimleri, yığın geri sarma nedenine neden olmadığından daha etkilidir.

## <a name="abnormal-termination"></a>Olağan dışı sonlandırma

[Longjmp](../c-runtime-library/reference/longjmp.md) çalışma zamanı işlevini kullanarak bir **try-finally** ifadesinden çıkmak olağan dışı sonlandırma olarak değerlendirilir. Bir **__try** ifadesine geçmek geçersizdir, ancak bunlardan biri atlanmak için geçerli değildir. Ayrılma noktası ( **__try** bloğunun normal sonlandırması) ve hedefin (özel durumu işleyen **__except** bloğu) arasında etkin olan tüm **__finally** deyimleri çalıştırılmalıdır. Buna yerel geriye doğru izleme denir.

Bir **TRY** bloğu herhangi bir nedenden dolayı erken sonlandırıldıysa, bloğu geri alma işleminin bir parçası olarak sistem ilişkili **finally** bloğunu yürütür. Bu gibi durumlarda, bir, **finally** bloğu içinden çağrılırsa, [abnormalsonlandırma](/windows/win32/Debug/abnormaltermination) işlevi **true** değerini döndürür; Aksi takdirde, **false**döndürür.

Bir işlem bir **try-finally** ifadesinin ortasında sonlandırılabilmesi için sonlandırma işleyicisi çağrılmaz.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Sonlandırma İşleyicisi Yazma](../cpp/writing-a-termination-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Sonlandırma-Işleyici sözdizimi](/windows/win32/Debug/termination-handler-syntax)