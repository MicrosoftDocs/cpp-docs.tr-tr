---
description: 'Daha fazla bilgi edinin: hata ayıklama yordamları'
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
ms.openlocfilehash: 60857549cbbb0871da208708e9acd812444b3274
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321290"
---
# <a name="debug-routines"></a>Hata ayıklama yordamları

C çalışma zamanı kitaplığının hata ayıklama sürümü, hata ayıklama programlarını daha kolay hale getirir ve geliştiricilerin şunları yapmasına olanak tanıyan birçok tanılama hizmeti sağlar:

- Hata ayıklama sırasında doğrudan çalışma zamanı işlevlerine adımla

- Onayları, hataları ve özel durumları çözümleyin

- Yığın ayırmalarını izleme ve bellek sızıntılarını önleme

- Hata ayıklama iletilerini kullanıcıya bildir

## <a name="debug-versions-of-the-c-runtime-library-routines"></a>C çalışma zamanı kitaplığı yordamlarının hata ayıklama sürümleri

Bu yordamları kullanmak için [_DEBUG](../c-runtime-library/debug.md) bayrağının tanımlanması gerekir. Bu yordamların hepsi, bir uygulamanın perakende derlemesinde hiçbir şey yapmaz. Yeni hata ayıklama yordamlarını kullanma hakkında daha fazla bilgi için bkz. [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

| Yordam | Kullanın |
|--|--|
| [`_ASSERT`](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) | Bir ifadeyi değerlendirin ve sonuç yanlış olduğunda bir hata ayıklama raporu oluşturur |
| [`_ASSERTE`](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) | İle benzerdir **`_ASSERT`** , ancak oluşturulan raporda başarısız olan ifadeyi içerir |
| [`_CrtCheckMemory`](../c-runtime-library/reference/crtcheckmemory.md) | Hata ayıklama yığınında ayrılan bellek bloklarının bütünlüğünü onaylayın |
| [`_CrtDbgBreak`](../c-runtime-library/reference/crtdbgbreak.md) | Bir kesme noktası ayarlar. |
| [`_CrtDbgReport`, `_CrtDbgReportW`](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) | Kullanıcı iletisiyle bir hata ayıklama raporu oluşturun ve raporu üç olası hedefe gönderin |
| [`_CrtDoForAllClientObjects`](../c-runtime-library/reference/crtdoforallclientobjects.md) | Yığındaki tüm türler için uygulama tarafından sağlanan bir işlev çağırma `_CLIENT_BLOCK` |
| [`_CrtDumpMemoryLeaks`](../c-runtime-library/reference/crtdumpmemoryleaks.md) | Önemli bir bellek sızıntısı oluştuğunda hata ayıklama yığınındaki tüm bellek bloklarının dökümünü alın |
| [`_CrtIsMemoryBlock`](../c-runtime-library/reference/crtismemoryblock.md) | Belirtilen bir bellek bloğunun yerel yığında bulunduğunu ve geçerli bir hata ayıklama yığını blok türü tanımlayıcısına sahip olduğunu doğrulayın |
| [`_CrtIsValidHeapPointer`](../c-runtime-library/reference/crtisvalidheappointer.md) | Belirtilen işaretçinin yerel yığında olduğunu doğrular |
| [`_CrtIsValidPointer`](../c-runtime-library/reference/crtisvalidpointer.md) | Belirtilen bir bellek aralığının okuma ve yazma için geçerli olduğunu doğrulayın |
| [`_CrtMemCheckpoint`](../c-runtime-library/reference/crtmemcheckpoint.md) | Hata ayıklama yığınının geçerli durumunu alın ve uygulama tarafından sağlanan bir `_CrtMemState` yapıda depolayın |
| [`_CrtMemDifference`](../c-runtime-library/reference/crtmemdifference.md) | Önemli farklılıklar için iki bellek durumunu karşılaştırın ve sonuçları döndürün |
| [`_CrtMemDumpAllObjectsSince`](../c-runtime-library/reference/crtmemdumpallobjectssince.md) | Belirtilen bir denetim noktası alındığından veya program yürütme başlangıcından itibaren yığındaki nesneler hakkında bilgi döküm |
| [`_CrtMemDumpStatistics`](../c-runtime-library/reference/crtmemdumpstatistics.md) | Kullanıcı tarafından okunabilen bir formda belirtilen bellek durumu için hata ayıklama üst bilgisi bilgilerini dökümünü al |
| [`_CrtReportBlockType`](../c-runtime-library/reference/crtreportblocktype.md) | Verilen bir hata ayıklama yığını blok işaretçisi ile ilişkili blok türünü/alt türü döndürür. |
| [`_CrtSetAllocHook`](../c-runtime-library/reference/crtsetallochook.md) | C çalışma zamanı hata ayıklama belleği ayırma işlemine bağlanarak istemci tanımlı bir ayırma işlevi yükleme |
| [`_CrtSetBreakAlloc`](../c-runtime-library/reference/crtsetbreakalloc.md) | Belirtilen nesne ayırma sıra numarası üzerinde bir kesme noktası ayarlayın |
| [`_CrtSetDbgFlag`](../c-runtime-library/reference/crtsetdbgflag.md) | `_crtDbgFlag`Hata ayıklama yığın yöneticisinin ayırma davranışını denetlemek için bayrağın durumunu alın veya değiştirin |
| [`_CrtSetDumpClient`](../c-runtime-library/reference/crtsetdumpclient.md) | Tür belleği bloklarının dökümünü almak için bir hata ayıklama dökümü işlevi çağrıldığında çağrılan uygulama tanımlı bir işlev yükler `_CLIENT_BLOCK` |
| [`_CrtSetReportFile`](../c-runtime-library/reference/crtsetreportfile.md) | Belirli bir rapor türü için hedef olarak kullanılacak dosyayı veya akışı tanımla `_CrtDbgReport` |
| [`_CrtSetReportHook`](../c-runtime-library/reference/crtsetreporthook.md) | C çalışma zamanı hata ayıklama raporlama işlemine bağlanarak istemci tanımlı bir raporlama işlevi yükler |
| [`_CrtSetReportHook2`, `_CrtSetReportHookW2`](../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) | , C çalışma zamanı hata ayıklama raporlama işlemine bağlanarak istemci tanımlı bir raporlama işlevini kurar veya kaldırır. |
| [`_CrtSetReportMode`](../c-runtime-library/reference/crtsetreportmode.md) | Tarafından oluşturulan belirli bir rapor türü için genel hedefi belirtin `_CrtDbgReport` |
| [_RPT&#91;0, 1, 2, 3, 4&#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) | `_CrtDbgReport`Bir biçim dizesiyle ve değişken sayıda bağımsız değişkenle çağırarak bir hata ayıklama raporu oluşturarak uygulamanın ilerlemesini izleyin. Kaynak dosya ve satır numarası bilgisi sağlamaz. |
| [_RPTF&#91;0, 1, 2, 3, 4&#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) | `_RPTn`Makrolara benzer ancak rapor isteğinin kaynaklandığı kaynak dosya adı ve satır numarası sağlar |
| [`_calloc_dbg`](../c-runtime-library/reference/calloc-dbg.md) | Bir hata ayıklama üst bilgisi ve üzerine yazma arabellekleri için ek alana sahip yığında belirtilen sayıda bellek bloğunu ayırın |
| [`_expand_dbg`](../c-runtime-library/reference/expand-dbg.md) | Bloğu genişleterek veya değiştirerek yığında belirtilen bellek bloğunu yeniden boyutlandırın |
| [`_free_dbg`](../c-runtime-library/reference/free-dbg.md) | Yığında bellek bloğunu boşaltma |
| [`_fullpath_dbg`, `_wfullpath_dbg`](../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md) | Belirtilen göreli yol adı için, bellek ayırmak için kullanarak mutlak veya tam yol adı oluşturun [`_malloc_dbg`](../c-runtime-library/reference/malloc-dbg.md) . |
| [`_getcwd_dbg`, `_wgetcwd_dbg`](../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md) | Bellek ayırmak için kullanarak geçerli çalışma dizinini alın [`_malloc_dbg`](../c-runtime-library/reference/malloc-dbg.md) . |
| [`_malloc_dbg`](../c-runtime-library/reference/malloc-dbg.md) | Hata ayıklama üst bilgisi ve üzerine yazma arabellekleri için ek alana sahip yığında bir bellek bloğu ayırın |
| [`_msize_dbg`](../c-runtime-library/reference/msize-dbg.md) | Yığında bellek bloğunun boyutunu hesaplama |
| [`_realloc_dbg`](../c-runtime-library/reference/realloc-dbg.md) | Bloğu taşıyarak ve/veya yeniden boyutlandırarak yığında belirtilen bellek bloğunu yeniden tahsis edin |
| [`_strdup_dbg`, `_wcsdup_dbg`](../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md) | Bellek ayırmak için kullanarak bir dizeyi çoğaltır [`_malloc_dbg`](../c-runtime-library/reference/malloc-dbg.md) . |
| [`_tempnam_dbg`, `_wtempnam_dbg`](../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md) | Bellek ayırmak için kullanarak geçici dosyalar oluşturmak için kullanabileceğiniz adlar oluşturun [`_malloc_dbg`](../c-runtime-library/reference/malloc-dbg.md) . |

## <a name="c-runtime-routines-that-are-not-available-in-source-code-form"></a>Kaynak kodu formunda kullanılamayan C çalışma zamanı yordamları

Hata ayıklayıcı, hata ayıklama işlemi sırasında C çalışma zamanı yordamlarının büyük bir kısmının kaynak kodunu adım adım yapmak için kullanılabilir. Ancak Microsoft, bazı teknolojileri mülkiyet açısından düşünür ve bu nedenle, bu yordamların bir alt kümesi için kaynak kodu sağlamıyor. Bu yordamların çoğu özel durum işleme veya kayan nokta işleme gruplarına aittir, ancak bazıları da daha fazla yer alır. Aşağıdaki tabloda bu yordamlar listelenmektedir.

:::row:::
   :::column span="":::
      [`acos`](../c-runtime-library/reference/acos-acosf-acosl.md)\
      [`acosh`](../c-runtime-library/reference/acosh-acoshf-acoshl.md)\
      [`asin`](../c-runtime-library/reference/asin-asinf-asinl.md)\
      [`asinh`](../c-runtime-library/reference/asinh-asinhf-asinhl.md)\
      [`atan`, `atan2`](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)\
      [`atanh`](../c-runtime-library/reference/atanh-atanhf-atanhl.md)\
      [`Bessel functions`](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)\
      [`_cabs`](../c-runtime-library/reference/cabs.md)\
      [`ceil`](../c-runtime-library/reference/ceil-ceilf-ceill.md)\
      [`_chgsign`](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)\
      [`_clear87`, `_clearfp`](../c-runtime-library/reference/clear87-clearfp.md)\
      [`_control87`, `_controlfp`](../c-runtime-library/reference/control87-controlfp-control87-2.md)
   :::column-end:::
   :::column span="":::
      [`copysign`](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)\
      [`cos`](../c-runtime-library/reference/cos-cosf-cosl.md)\
      [`cosh`](../c-runtime-library/reference/cosh-coshf-coshl.md)\
      [`Exp`](../c-runtime-library/reference/exp-expf.md)\
      [`fabs`](../c-runtime-library/reference/fabs-fabsf-fabsl.md)\
      [`_finite`](../c-runtime-library/reference/finite-finitef.md)\
      [`floor`](../c-runtime-library/reference/floor-floorf-floorl.md)\
      [`fmod`](../c-runtime-library/reference/fmod-fmodf.md)\
      [`_fpclass`](../c-runtime-library/reference/fpclass-fpclassf.md)\
      [`_fpieee_flt`](../c-runtime-library/reference/fpieee-flt.md)\
      [`_fpreset`](../c-runtime-library/reference/fpreset.md)\
      [`frexp`](../c-runtime-library/reference/frexp.md)
   :::column-end:::
   :::column span="":::
      [`_hypot`](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)\
      [`_isnan`](../c-runtime-library/reference/isnan-isnan-isnanf.md)\
      [`ldexp`](../c-runtime-library/reference/ldexp.md)\
      [`log`](../c-runtime-library/reference/log-logf-log10-log10f.md)\
      [`_logb`](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)\
      [`log10`](../c-runtime-library/reference/log-logf-log10-log10f.md)\
      [`longjmp`](../c-runtime-library/reference/longjmp.md)\
      [`_matherr`](../c-runtime-library/reference/matherr.md)\
      [`modf`](../c-runtime-library/reference/modf-modff-modfl.md)\
      [`_nextafter`](../c-runtime-library/reference/nextafter-functions.md)\
      [`pow`](../c-runtime-library/reference/pow-powf-powl.md)\
      [`printf_s`](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)
   :::column-end:::
   :::column span="":::
      [`printf`](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\
      [`_scalb`](../c-runtime-library/reference/scalb.md)\
      [`scanf_s`](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)\
      [`scanf`](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)\
      [`setjmp`](../c-runtime-library/reference/setjmp.md)\
      [`sin`](../c-runtime-library/reference/sin-sinf-sinl.md)\
      [`sinh`](../c-runtime-library/reference/sinh-sinhf-sinhl.md)\
      [`sqrt`](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)\
      [`_status87`, `_statusfp`](../c-runtime-library/reference/status87-statusfp-statusfp2.md)\
      [`tan`](../c-runtime-library/reference/tan-tanf-tanl.md)\
      [`tanh`](../c-runtime-library/reference/tanh-tanhf-tanhl.md)
   :::column-end:::
:::row-end:::

Kaynak kodu, **printf** ve **scanf** yordamlarının çoğu için kullanılabilir olsa da, kaynak kodu sağlanmayan diğer bir yordama iç çağrı yapar.

## <a name="routines-that-behave-differently-in-a-debug-build-of-an-application"></a>Bir uygulamanın hata ayıklama derlemesinde farklı davranan yordamlar

Bazı C çalışma zamanı işlevleri ve C++ işleçleri, bir uygulamanın hata ayıklama derlemeden çağrıldığında farklı şekilde davranır. (Bir uygulamanın hata ayıklama derlemesinin, `_DEBUG` bayrağı tanımlayarak veya C çalışma zamanı kitaplığının hata ayıklama sürümüyle bağlantı kurarak yapılabileceğini unutmayın.) Davranış farkları genellikle hata ayıklama sürecini desteklemek için yordam tarafından belirtilen ek özelliklerden veya bilgilerden oluşur. Aşağıdaki tabloda bu yordamlar listelenmektedir.

:::row:::
   :::column span="":::
      C [`abort`](../c-runtime-library/reference/abort.md) yordamı
   :::column-end:::
   :::column span="":::
      C [`assert`](../c-runtime-library/reference/assert-macro-assert-wassert.md) yordamı
   :::column-end:::
   :::column span="":::
      C++ [`delete`](../cpp/delete-operator-cpp.md) işleci
   :::column-end:::
   :::column span="":::
      C++ [`new`](../cpp/new-operator-cpp.md) işleci
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Çalışma zamanı hata denetimi](../c-runtime-library/run-time-error-checking.md)<br/>
