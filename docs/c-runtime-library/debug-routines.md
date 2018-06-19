---
title: Hata ayıklama yordamları | Microsoft Docs
ms.custom: ''
ms.date: 04/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- c.debug
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- macros, debugging with
- debug routines
- debug macros
- debugging [CRT], runtime routines
ms.assetid: cb4d2664-10f3-42f7-a516-595558075471
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4efef4c7dfb907120778390874a5e56222889350
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392308"
---
# <a name="debug-routines"></a>Hata ayıklama yordamları

C çalışma zamanı kitaplığı hata ayıklama sürümü hata ayıklama programları kolaylaştırmak ve geliştiricilerin izin veren çok sayıda tanı hizmetleri sağlar:

- Adımla doğrudan hata ayıklama sırasında çalışma zamanı işlevleri

- Onaylar, hataları ve özel durumları çözmek

- Yığın ayırma izleme ve bellek sızıntılarını önleme

- Kullanıcı raporu hata ayıklama iletileri

## <a name="debug-versions-of-the-c-runtime-library-routines"></a>C çalışma zamanı kitaplığı yordamları sürümleri hata ayıklama

Bu yordamlar kullanılacak [_DEBUG](../c-runtime-library/debug.md) bayrağı tanımlanması gerekir. Bu yordamlar tümünün bir uygulamanın bir perakende yapı içinde hiçbir şey yapmayın. Yeni hata ayıklama yordamları kullanma hakkında daha fazla bilgi için bkz: [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Bir ifade değerlendirme ve sonucu FALSE olduğunda hata ayıklama raporunu oluşturur|
|[_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Benzer şekilde **_ASSERT**, ancak oluşturulan rapora başarısız ifade içeriyor|
|[_CrtCheckMemory](../c-runtime-library/reference/crtcheckmemory.md)|Hata ayıklama yığınında ayrılan bellek blokları bütünlüğünü onaylayın|
|[_CrtDbgBreak](../c-runtime-library/reference/crtdbgbreak.md)|Bir kesme noktası ayarlar.|
|[_CrtDbgReport, _CrtDbgReportW](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)|Bir kullanıcı iletiyle hata ayıklama rapor oluşturmak ve üç olası hedeflere raporu gönder|
|[_CrtDoForAllClientObjects](../c-runtime-library/reference/crtdoforallclientobjects.md)|Tüm uygulama tarafından sağlanan bir işlevi çağırmak **_clıent_block** yığınındaki türler|
|[_CrtDumpMemoryLeaks](../c-runtime-library/reference/crtdumpmemoryleaks.md)|Önemli bellek sızıntısı oluştuğunda hata ayıklama yığınındaki bellek blokları tümünün dökümü|
|[_CrtIsMemoryBlock](../c-runtime-library/reference/crtismemoryblock.md)|Belirtilen bellek bloğu yerel yığın içinde bulunur ve geçerli hata ayıklama yığını blok türü tanımlayıcısı olduğundan emin olun|
|[_CrtIsValidHeapPointer](../c-runtime-library/reference/crtisvalidheappointer.md)|Belirtilen bir işaretçi yerel yığınında olduğunu doğrular|
|[_CrtIsValidPointer](../c-runtime-library/reference/crtisvalidpointer.md)|Belirtilen bellek aralığı okuma ve yazma için geçerli olduğunu doğrulayın|
|[_CrtMemCheckpoint](../c-runtime-library/reference/crtmemcheckpoint.md)|Hata ayıklama yığınını geçerli durumunu almak ve bir uygulama tarafından sağlanan içinde depolamak **_CrtMemState** yapısı|
|[_CrtMemDifference](../c-runtime-library/reference/crtmemdifference.md)|Önemli farklılıklar iki bellek durumlarını karşılaştırın ve sonuçları döndürür|
|[_CrtMemDumpAllObjectsSince](../c-runtime-library/reference/crtmemdumpallobjectssince.md)|Belirtilen bir denetim noktası alındıktan sonra yığında veya program yürütme başından nesneler hakkındaki bilgileri dökümü|
|[_CrtMemDumpStatistics](../c-runtime-library/reference/crtmemdumpstatistics.md)|Hata ayıklama üst bilgileri kullanıcı tarafından okunabilir bir biçimde belirtilen bellek durumu için döküm|
|[_CrtReportBlockType](../c-runtime-library/reference/crtreportblocktype.md)|Belirli hata ayıklama yığını blok işaretçisi ile ilişkili blok türü/alt döndürür.|
|[_CrtSetAllocHook](../c-runtime-library/reference/crtsetallochook.md)|C çalışma zamanı hata ayıklama bellek ayırma işlemine takma tarafından istemci tanımlı ayırma işlevini yükle|
|[_CrtSetBreakAlloc](../c-runtime-library/reference/crtsetbreakalloc.md)|Belirtilen nesnenin ayırma sipariş numarası üzerinde bir kesme noktası ayarlama|
|[_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md)|Almak veya durumunu değiştirme **_crtDbgFlag** hata ayıklama yığını Yöneticisi ayırma davranışını denetlemek için bayrağı|
|[_CrtSetDumpClient](../c-runtime-library/reference/crtsetdumpclient.md)|Döküm için her bir hata ayıklama dökümü işlevi çağrıldığında çağrılan bir uygulama tanımlı işlevini Yükle **_clıent_block** bellek blokları|
|[_CrtSetReportFile](../c-runtime-library/reference/crtsetreportfile.md)|Dosya ya da belirli bir rapor türü tarafından için hedef olarak kullanılacak akış tanımlamak **_CrtDbgReport**|
|[_CrtSetReportHook](../c-runtime-library/reference/crtsetreporthook.md)|İşlem raporlama C çalışma zamanı hata ayıklama takma tarafından istemci tanımlı Raporlama işlevini yükle|
|[_CrtSetReportHook2, _CrtSetReportHookW2](../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)|Yükler veya istemci tarafından tanımlanan raporlama işlevi işlem raporlama C çalışma zamanı hata ayıklama takma tarafından kaldırır.|
|[_CrtSetReportMode](../c-runtime-library/reference/crtsetreportmode.md)|Tarafından oluşturulan belirli bir rapor türü için genel destination(s) belirtin **_CrtDbgReport**|
|[_RPT&AMP;#91;0,1,2,3,4&AMP;#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Çağırarak bir hata ayıklama raporu oluşturarak uygulamanın ilerlemeyi **_CrtDbgReport** bir biçim dizesi ve değişken sayıda bağımsız değişken. Hiçbir kaynak dosya ve satır numarası bilgilerini sağlar.|
|[_RPTF&AMP;#91;0,1,2,3,4&AMP;#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Benzer şekilde **_RPTn** makroları, ancak rapor isteği geldiği kaynak dosya adı ve satır numarası sağlar|
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|Bellek blokları ek alana sahip yığında belirtilen sayıda için hata ayıklama üstbilgi ayırmak ve arabellekleri üzerine yaz|
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|Belirtilen bir öbek üzerinde bellek bloğu genişletme veya blok daraltılırken yeniden boyutlandırma|
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|Yığın bellek bloğu boş|
|[_fullpath_dbg, _wfullpath_dbg](../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md)|Belirtilen göreli yol için bir mutlak veya tam yol adı oluşturma kullanarak ad [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) bellek ayıramadı.|[System::IO::File:: oluşturma](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|
|[_getcwd_dbg, _wgetcwd_dbg](../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md)|Geçerli çalışma dizini get kullanarak [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) bellek ayıramadı.|
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|Bir ek alana sahip yığında bellek bloğu için hata ayıklama üstbilgi ayırın ve arabellekleri üzerine yazma|
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|Yığın bellek bloğu boyutu hesaplanamadı|
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|Belirtilen bir öbek üzerinde bellek bloğu taşıma ve/veya blok yeniden boyutlandırma yeniden ayırma|
|[_strdup_dbg, _wcsdup_dbg](../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md)|Bir dize yineleme kullanılarak [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) bellek ayıramadı.|
|[_tempnam_dbg, _wtempnam_dbg](../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md)|Geçici dosyaları oluşturmak için kullanabileceğiniz kullanarak adları [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) bellek ayıramadı.|

## <a name="c-runtime-routines-that-are-not-available-in-source-code-form"></a>Kodu biçiminde kullanılamayan C çalışma zamanı yordamları kaynağı

Hata ayıklayıcı kullanılabilir adıma hata ayıklama işlemi sırasında C çalışma zamanı yordamları çoğu için kaynak kodunu aracılığıyla. Ancak, Microsoft özel olması için bazı teknolojiler göz önünde bulundurur ve bu nedenle, bu yordamları bir kısmı için kaynak kodunu sağlamaz. Bu yordamlar çoğu özel durum işleme veya kayan nokta işleme grupları ile ait ancak birkaç diğerleri de dahil edilir. Aşağıdaki tabloda, bu yordamları listeler.

||||
|-|-|-|
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[ACOSH](../c-runtime-library/reference/acosh-acoshf-acoshl.md)|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|
|[ASİNH](../c-runtime-library/reference/asinh-asinhf-asinhl.md)|[atan, atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[ATANH](../c-runtime-library/reference/atanh-atanhf-atanhl.md)|
|[Bessel işlevleri](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[_cabs](../c-runtime-library/reference/cabs.md)|[ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|
|[_chgsign](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|[_clear87, _clearfp](../c-runtime-library/reference/clear87-clearfp.md)|[_control87, _controlfp](../c-runtime-library/reference/control87-controlfp-control87-2.md)|
|[copysign](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|[cos](../c-runtime-library/reference/cos-cosf-cosl.md)|[COSH](../c-runtime-library/reference/cosh-coshf-coshl.md)|
|[exp](../c-runtime-library/reference/exp-expf.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[_finite](../c-runtime-library/reference/finite-finitef.md)|
|[Kat](../c-runtime-library/reference/floor-floorf-floorl.md)|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|
|[_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)|[_fpreset](../c-runtime-library/reference/fpreset.md)|[frexp](../c-runtime-library/reference/frexp.md)|
|[_hypot](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|[_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|[ldexp](../c-runtime-library/reference/ldexp.md)|
|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|
|[longjmp](../c-runtime-library/reference/longjmp.md)|[_matherr](../c-runtime-library/reference/matherr.md)|[modf](../c-runtime-library/reference/modf-modff-modfl.md)|
|[_nextafter](../c-runtime-library/reference/nextafter-functions.md)|[POW](../c-runtime-library/reference/pow-powf-powl.md)|[printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|
|[Printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[_scalb](../c-runtime-library/reference/scalb.md)|[scanf_s](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|
|[scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)|[setjmp](../c-runtime-library/reference/setjmp.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl.md)|
|[SİNH](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|[_status87, _statusfp](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|
|[tan](../c-runtime-library/reference/tan-tanf-tanl.md)|[TANH](../c-runtime-library/reference/tanh-tanhf-tanhl.md)||

Kaynak kodu çoğu için kullanılabilir olmasına rağmen **printf** ve **scanf** yordamları, yaptıkları bir iç çağrısının başka bir yordama için hangi kaynak kodu sağlanmadı.

## <a name="routines-that-behave-differently-in-a-debug-build-of-an-application"></a>Hata ayıklama modunda farklı şekilde davranan yordamları bir uygulama oluşturma

Bazı C çalışma zamanı işlevleri ve C++ işleçleri bir uygulamanın hata ayıklama derleme çağrıldığında farklı şekilde davranır. (Bir uygulamanın hata ayıklama derlemesi ya da tanımlayarak yapılabilir Not `_DEBUG` bayrak veya C çalışma zamanı kitaplığı ile bir hata ayıklama sürümü'ile bağlanıyor.) Davranış farklılıkları genellikle ek özellikler veya hata ayıklama işlemi desteklemek için yordamı tarafından sağlanan bilgileri oluşur. Aşağıdaki tabloda, bu yordamları listeler.

|||
|-|-|
|C [abort](../c-runtime-library/reference/abort.md) yordamı|C++ [silmek](../cpp/delete-operator-cpp.md) işleci|
|C [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) yordamı|C++ [yeni](../cpp/new-operator-cpp.md) işleci|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Çalışma Zamanı Hata Denetimi](../c-runtime-library/run-time-error-checking.md)<br/>
