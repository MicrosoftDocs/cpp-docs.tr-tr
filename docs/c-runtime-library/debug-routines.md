---
title: Hata ayıklama yordamları
ms.date: 04/10/2018
f1_keywords:
- c.debug
helpviewer_keywords:
- debugging [CRT], using macros
- macros, debugging with
- debug routines
- debug macros
- debugging [CRT], runtime routines
ms.assetid: cb4d2664-10f3-42f7-a516-595558075471
ms.openlocfilehash: e1281b578435086dc7de04c7962145c2b265277a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344453"
---
# <a name="debug-routines"></a>Hata ayıklama yordamları

Hata ayıklama sürümü C çalışma zamanı kitaplığı hata ayıklama programlar kolaylaştırmak ve geliştiricilerin izin veren çok sayıda tanı hizmetleri sağlar:

- Adımla doğrudan hata ayıklama sırasında çalışma zamanı işlevleri

- Onaylar, hatalar ve özel durumları çözmek

- Yığın ayırmaları izleme ve bellek sızıntılarını önleme

- Kullanıcı raporu hata ayıklama iletileri

## <a name="debug-versions-of-the-c-runtime-library-routines"></a>Hata ayıklama sürümleri C çalışma zamanı kitaplık yordamları

Bu yordamları kullanmak için [_DEBUG](../c-runtime-library/debug.md) bayrağı tanımlanmalıdır. Bu yordamların tümünde bir uygulamanın bir perakende yapı içinde hiçbir şey yapmayın. Yeni hata ayıklama yordamları kullanma hakkında daha fazla bilgi için bkz. [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Bir ifadeyi değerlendirir ve sonucu FALSE olduğunda, hata ayıklama raporunu oluşturur|
|[_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Benzer şekilde **_ASSERT**, ancak oluşturulan raporda başarısız ifadesi içerir|
|[_CrtCheckMemory](../c-runtime-library/reference/crtcheckmemory.md)|Hata ayıklama yığın üzerinde ayrılan bellek blokları bütünlüğünü doğrulayın|
|[_CrtDbgBreak](../c-runtime-library/reference/crtdbgbreak.md)|Bir kesme noktası ayarlar.|
|[_CrtDbgReport, _CrtDbgReportW](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)|Kullanıcı iletisi ile bir hata ayıklama raporunu oluşturur ve raporu üç olası hedefe gönderin|
|[_CrtDoForAllClientObjects](../c-runtime-library/reference/crtdoforallclientobjects.md)|Tüm uygulama tarafından sağlanan bir işlev çağrısı **_clıent_block** yığındaki türler|
|[_CrtDumpMemoryLeaks](../c-runtime-library/reference/crtdumpmemoryleaks.md)|Önemli bir bellek sızıntısı oluşmadığında tüm bellek bloğu hata ayıklama yığınındaki dökümü|
|[_CrtIsMemoryBlock](../c-runtime-library/reference/crtismemoryblock.md)|Belirtilen bellek bloğu yerel yığın içinde bulunur ve geçerli hata ayıklama yığın blok türü tanımlayıcısı olduğunu doğrulayın|
|[_CrtIsValidHeapPointer](../c-runtime-library/reference/crtisvalidheappointer.md)|Belirtilen bir işaretçi yerel yığında olduğunu doğrular|
|[_CrtIsValidPointer](../c-runtime-library/reference/crtisvalidpointer.md)|Belirtilen bellek aralığının okuma ve yazma için geçerli olduğunu doğrulayın|
|[_CrtMemCheckpoint](../c-runtime-library/reference/crtmemcheckpoint.md)|Hata ayıklama yığınındaki geçerli durumunu almak ve bir uygulama tarafından sağlanan depolama **_CrtMemState** yapısı|
|[_CrtMemDifference](../c-runtime-library/reference/crtmemdifference.md)|İki bellek durumu arasında önemli farklar için karşılaştırmak ve sonuçları döndürür|
|[_CrtMemDumpAllObjectsSince](../c-runtime-library/reference/crtmemdumpallobjectssince.md)|Program yürütme başlangıcından ya da belirtilen bir denetim noktası alındıktan sonra yığındaki nesneler hakkında bilgi dökümü|
|[_CrtMemDumpStatistics](../c-runtime-library/reference/crtmemdumpstatistics.md)|Hata ayıklama üst bilgi bilgileri bir kullanıcı tarafından okunabilir bir biçimde belirtilen bellek durumu için döküm|
|[_CrtReportBlockType](../c-runtime-library/reference/crtreportblocktype.md)|Belirli hata ayıklama yığın blok işaretçisi ile ilişkili blok türü/alt döndürür.|
|[_CrtSetAllocHook](../c-runtime-library/reference/crtsetallochook.md)|Bir istemci tanımlı ayırma işlevini C çalışma zamanı hata ayıklama bellek ayırma işlemine takma tarafından yükle|
|[_CrtSetBreakAlloc](../c-runtime-library/reference/crtsetbreakalloc.md)|Belirtilen nesne ayırma sipariş numarası üzerinde bir kesme noktası ayarlayın|
|[_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md)|Almak veya durumunu değiştirme **_crtDbgFlag** hata ayıklama yığını Yöneticisi ayırma davranışını denetleyen bayrak|
|[_CrtSetDumpClient](../c-runtime-library/reference/crtsetdumpclient.md)|Uygulama tanımlı dökümünü almak için her bir hata ayıklama döküm işlevi çağrıldığında çağrılan bir işlev yükleme **_clıent_block** bellek blokları|
|[_CrtSetReportFile](../c-runtime-library/reference/crtsetreportfile.md)|Dosya ya da hedef olarak belirli bir rapor türü tarafından kullanılan akış tanımlamak **_CrtDbgReport**|
|[_CrtSetReportHook](../c-runtime-library/reference/crtsetreporthook.md)|Bir istemci tanımlı raporlama işlevi, işlem C çalışma zamanı hata ayıklama raporlama takma tarafından yükleyin|
|[_CrtSetReportHook2, _CrtSetReportHookW2](../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)|Yükler veya bir istemci tanımlı raporlama işlevi, işlem C çalışma zamanı hata ayıklama raporlama takma tarafından kaldırır.|
|[_CrtSetReportMode](../c-runtime-library/reference/crtsetreportmode.md)|Tarafından oluşturulan belirli bir rapor türü için genel destination(s) belirtin **_CrtDbgReport**|
|[_RPT&AMP;#91;0,1,2,3,4&AMP;#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Hata ayıklama raporunu çağırarak oluşturarak uygulamanın ilerlemeyi **_CrtDbgReport** bir biçim dizesi ve değişken sayıda bağımsız değişken. Hiçbir kaynak dosya ve satır numarası bilgileri sağlar.|
|[_RPTF&AMP;#91;0,1,2,3,4&AMP;#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Benzer şekilde **_RPTn** makroları, ancak rapor isteği geldiği kaynak dosya adı ve satır numarası sağlar|
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|Hata ayıklama üst bilgisi için ek alana sahip bir yığında bellek blokları belirtilen sayıda ayırmak ve arabellek üzerine|
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|Belirtilen bir yığında bellek bloğu genişletme veya blok ihtiyaçlarımıza yeniden boyutlandırma|
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|Yığında bir bellek öbeğini serbest|
|[_fullpath_dbg, _wfullpath_dbg](../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md)|Belirtilen göreli yol için bir mutlak ya da tam yol adı oluşturma kullanarak ad [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) bellek ayrılamadı.|
|[_getcwd_dbg, _wgetcwd_dbg](../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md)|Geçerli çalışma dizinini Al kullanarak [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) bellek ayrılamadı.|
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|Hata ayıklama üst bilgisi için bir ek alana sahip bir yığında bellek bloğu ayrılamadı ve arabellek üzerine yazma|
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|Yığında bellek bloğunun boyutu hesaplanamadı|
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|Belirtilen bir yığında bellek bloğu taşıma ve/veya yeniden boyutlandırma blok tarafından yeniden ayırın.|
|[_strdup_dbg, _wcsdup_dbg](../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md)|Yineleyen bir dize kullanarak [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) bellek ayrılamadı.|
|[_tempnam_dbg, _wtempnam_dbg](../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md)|Geçici dosyalar oluşturmak için kullanabileceğiniz kullanarak adları [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) bellek ayrılamadı.|

## <a name="c-runtime-routines-that-are-not-available-in-source-code-form"></a>Kullanılamayan, C çalışma zamanı yordamları kod form kaynağı

Hata ayıklayıcı kullanılabilir hata ayıklama işlemi sırasında C çalışma zamanı yordamları çoğu için kaynak kodu boyunca adım adım. Ancak, Microsoft özel olması için bazı teknolojiler göz önünde bulundurur ve bu nedenle, kaynak kodu, bu yordamların bir alt kümesi için sağlamaz. Bu yordamlar çoğu özel durum işleme veya kayan nokta işleme grupları için ait, ancak birkaç diğerleri de dahil edilir. Aşağıdaki tabloda, bu yordamların listeler.

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

Kaynak kodu için çoğu kullanılabilir olmasına rağmen **printf** ve **scanf** yordamları, yaptıkları bir iç çağrı başka bir yordama için hangi kaynak kodu sağlanmadı.

## <a name="routines-that-behave-differently-in-a-debug-build-of-an-application"></a>Hata ayıklama yapısında farklı şekilde davranan yordamları uygulama oluşturma

Bazı C çalışma zamanı işlevleri ve C++ işleçleri bir uygulamanın hata ayıklama derlemeden çağrıldığında farklı davranır. (Hata ayıklama derlemesi bir uygulamanın ya da tanımlayarak yapılabilir Not `_DEBUG` bayrak veya hata ayıklama sürümü C çalışma zamanı kitaplığı ile'ile bağlanıyor.) Ek özellik veya hata ayıklama işlemini desteklemek için yordamı tarafından sağlanan bilgiler, davranışsal farklılıklar genellikle oluşur. Aşağıdaki tabloda, bu yordamların listeler.

|||
|-|-|
|C [iptal](../c-runtime-library/reference/abort.md) yordamı|C++ [Sil](../cpp/delete-operator-cpp.md) işleci|
|C [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) yordamı|C++ [yeni](../cpp/new-operator-cpp.md) işleci|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Çalışma Zamanı Hata Denetimi](../c-runtime-library/run-time-error-checking.md)<br/>
