---
title: "Hata ayıklama yordamları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.debug
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- macros, debugging with
- debug routines
- debug macros
- debugging [CRT], run-time routines
ms.assetid: cb4d2664-10f3-42f7-a516-595558075471
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 158a3b782ffedc7bd206f400c066c052062ad402
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="debug-routines"></a>Hata Ayıklama Yordamları
C çalışma zamanı kitaplığı hata ayıklama sürümü hata ayıklama programları kolaylaştırmak ve geliştiricilerin izin veren çok sayıda tanı hizmetleri sağlar:  
  
-   Adımla doğrudan hata ayıklama sırasında çalışma zamanı işlevleri  
  
-   Onaylar, hataları ve özel durumları çözmek  
  
-   Yığın ayırma izleme ve bellek sızıntılarını önleme  
  
-   Kullanıcı raporu hata ayıklama iletileri  
  
 Bu yordamlar kullanılacak [_DEBUG](../c-runtime-library/debug.md) bayrağı tanımlanması gerekir. Bu yordamlar tümünün bir uygulamanın bir perakende yapı içinde hiçbir şey yapmayın. Yeni hata ayıklama yordamları kullanma hakkında daha fazla bilgi için bkz: [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).  
  
### <a name="debug-versions-of-the-c-run-time-library-routines"></a>C çalışma zamanı kitaplığı yordamları sürümleri hata ayıklama  
  
|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|-------------|---------|  
|[_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Bir ifade değerlendirme ve sonucu FALSE olduğunda hata ayıklama raporunu oluşturur|  
|[_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Benzer şekilde `_ASSERT`, ancak oluşturulan rapora başarısız ifade içeriyor|  
|[_CrtCheckMemory](../c-runtime-library/reference/crtcheckmemory.md)|Hata ayıklama yığınında ayrılan bellek blokları bütünlüğünü onaylayın|  
|[_CrtDbgBreak](../c-runtime-library/reference/crtdbgbreak.md)|Bir kesme noktası ayarlar.|  
|[_CrtDbgReport, _CrtDbgReportW](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)|Bir kullanıcı iletiyle hata ayıklama rapor oluşturmak ve üç olası hedeflere raporu gönder|  
|[_CrtDoForAllClientObjects](../c-runtime-library/reference/crtdoforallclientobjects.md)|Tüm uygulama tarafından sağlanan bir işlevi çağırmak `_CLIENT_BLOCK` yığınındaki türler|  
|[_CrtDumpMemoryLeaks](../c-runtime-library/reference/crtdumpmemoryleaks.md)|Önemli bellek sızıntısı oluştuğunda hata ayıklama yığınındaki bellek blokları tümünün dökümü|  
|[_CrtIsMemoryBlock](../c-runtime-library/reference/crtismemoryblock.md)|Belirtilen bellek bloğu yerel yığın içinde bulunur ve geçerli hata ayıklama yığını blok türü tanımlayıcısı olduğundan emin olun|  
|[_CrtIsValidHeapPointer](../c-runtime-library/reference/crtisvalidheappointer.md)|Belirtilen bir işaretçi yerel yığınında olduğunu doğrular|  
|[_CrtIsValidPointer](../c-runtime-library/reference/crtisvalidpointer.md)|Belirtilen bellek aralığı okuma ve yazma için geçerli olduğunu doğrulayın|  
|[_CrtMemCheckpoint](../c-runtime-library/reference/crtmemcheckpoint.md)|Hata ayıklama yığınını geçerli durumunu almak ve bir uygulama tarafından sağlanan içinde depolamak `_CrtMemState` yapısı|  
|[_CrtMemDifference](../c-runtime-library/reference/crtmemdifference.md)|Önemli farklılıklar iki bellek durumlarını karşılaştırın ve sonuçları döndürür|  
|[_CrtMemDumpAllObjectsSince](../c-runtime-library/reference/crtmemdumpallobjectssince.md)|Belirtilen bir denetim noktası alındıktan sonra yığında veya program yürütme başından nesneler hakkındaki bilgileri dökümü|  
|[_CrtMemDumpStatistics](../c-runtime-library/reference/crtmemdumpstatistics.md)|Hata ayıklama üst bilgileri kullanıcı tarafından okunabilir bir biçimde belirtilen bellek durumu için döküm|  
|[_CrtReportBlockType](../c-runtime-library/reference/crtreportblocktype.md)|Belirli hata ayıklama yığını blok işaretçisi ile ilişkili blok türü/alt döndürür.|  
|[_CrtSetAllocHook](../c-runtime-library/reference/crtsetallochook.md)|C çalışma zamanı hata ayıklama bellek ayırma işlemine takma tarafından istemci tanımlı ayırma işlevini yükle|  
|[_CrtSetBreakAlloc](../c-runtime-library/reference/crtsetbreakalloc.md)|Belirtilen nesnenin ayırma sipariş numarası üzerinde bir kesme noktası ayarlama|  
|[_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md)|Almak veya durumunu değiştirme `_crtDbgFlag` hata ayıklama yığını Yöneticisi ayırma davranışını denetlemek için bayrağı|  
|[_CrtSetDumpClient](../c-runtime-library/reference/crtsetdumpclient.md)|Döküm için her bir hata ayıklama dökümü işlevi çağrıldığında çağrılan bir uygulama tanımlı işlevini Yükle `_CLIENT_BLOCK` bellek blokları|  
|[_CrtSetReportFile](../c-runtime-library/reference/crtsetreportfile.md)|Dosya ya da belirli bir rapor türü tarafından için hedef olarak kullanılacak akış tanımlamak`_CrtDbgReport`|  
|[_CrtSetReportHook](../c-runtime-library/reference/crtsetreporthook.md)|İşlem raporlama C çalışma zamanı hata ayıklama takma tarafından istemci tanımlı Raporlama işlevini yükle|  
|[_CrtSetReportHook2, _CrtSetReportHookW2](../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)|Yükler veya istemci tarafından tanımlanan raporlama işlevi işlem raporlama C çalışma zamanı hata ayıklama takma tarafından kaldırır.|  
|[_CrtSetReportMode](../c-runtime-library/reference/crtsetreportmode.md)|Tarafından oluşturulan belirli bir rapor türü için genel destination(s) belirtin`_CrtDbgReport`|  
|[_RPT &#91; 0,1,2,3,4 &#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Çağırarak bir hata ayıklama raporu oluşturarak uygulamanın ilerlemeyi `_CrtDbgReport` bir biçim dizesi ve değişken sayıda bağımsız değişken. Hiçbir kaynak dosya ve satır numarası bilgilerini sağlar.|  
|[_RPTF &#91; 0,1,2,3,4 &#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Benzer şekilde `_RPTn` makroları, ancak rapor isteği geldiği kaynak dosya adı ve satır numarası sağlar|  
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
  
 Hata ayıklama yordamları kullanılabilir diğer C çalışma zamanı yordamları hata ayıklama işlemi sırasında çoğu için kaynak kodunu aracılığıyla adıma. Ancak, Microsoft özel olması için bazı teknolojiler göz önünde bulundurur ve bu nedenle, kaynak kodu için bu yordamları sağlamaz. Bu yordamlar çoğu özel durum işleme veya kayan nokta işleme grupları ile ait ancak birkaç diğerleri de dahil edilir. Aşağıdaki tabloda, bu yordamları listeler.  
  
### <a name="c-run-time-routines-that-are-not-available-in-source-code-form"></a>Kaynak kodu biçiminde kullanılabilir değil C çalışma zamanı yordamları  
  
||||  
|-|-|-|  
|[acos, acosf, acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|[_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|[_nextafter](../c-runtime-library/reference/nextafter-functions.md)|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)|[POW](../c-runtime-library/reference/pow-powf-powl.md)|  
|[atan, atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[_fpreset](../c-runtime-library/reference/fpreset.md)|[Printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)*|  
|[_cabs](../c-runtime-library/reference/cabs.md)|[frexp](../c-runtime-library/reference/frexp.md)|[_scalb](../c-runtime-library/reference/scalb.md)|  
|[ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|[_hypot](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)*|  
|[_chgsign, _chgsignf, _chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|[_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|[setjmp](../c-runtime-library/reference/setjmp.md)|  
|[_clear87, _clearfp](../c-runtime-library/reference/clear87-clearfp.md)|[_j0](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[_control87, _controlfp, \__control87_2](../c-runtime-library/reference/control87-controlfp-control87-2.md)|[_j1](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[SİNH](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|[_jn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[Sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[ldexp](../c-runtime-library/reference/ldexp.md)|[_status87, _statusfp](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|  
|[COSH](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[Günlük](../c-runtime-library/reference/log-logf-log10-log10f.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[Exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[TANH](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|[_y0](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|  
|[_finite](../c-runtime-library/reference/finite-finitef.md)|[longjmp](../c-runtime-library/reference/longjmp.md)|[_y1](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|  
|[Kat](../c-runtime-library/reference/floor-floorf-floorl.md)|[_matherr](../c-runtime-library/reference/matherr.md)|[_yn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|  
|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[modf](../c-runtime-library/reference/modf-modff-modfl.md)||  
  
 \*Kaynak kodu bu yordam çoğu için kullanılabilir olsa da, başka bir yordama kaynak kodu sağlanmayan bir iç çağrı yapar.  
  
 Bazı C çalışma zamanı işlevleri ve C++ işleçleri bir uygulamanın hata ayıklama derleme çağrıldığında farklı şekilde davranır. (Bir uygulamanın hata ayıklama derlemesi ya da tanımlayarak yapılabilir Not `_DEBUG` bayrak veya C çalışma zamanı kitaplığı ile bir hata ayıklama sürümü'ile bağlanıyor.) Davranış farklılıkları genellikle ek özellikler veya hata ayıklama işlemi desteklemek için yordamı tarafından sağlanan bilgileri oluşur. Aşağıdaki tabloda, bu yordamları listeler.  
  
### <a name="routines-that-behave-differently-in-a-debug-build-of-an-application"></a>Hata ayıklama modunda farklı şekilde davranan yordamları bir uygulama oluşturma  
  
|||  
|-|-|  
|C [abort](../c-runtime-library/reference/abort.md) yordamı|C++ [silmek](../cpp/delete-operator-cpp.md) işleci|  
|C [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) yordamı|C++ [yeni](../cpp/new-operator-cpp.md) işleci|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kategorilere göre çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)   
 [Çalışma Zamanı Hata Denetimi](../c-runtime-library/run-time-error-checking.md)