---
title: "_RPT, _RPTF, _RPTW, _RPTFW makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- RPT3
- RPTF4
- _RPT4
- RPT1
- _RPTF0
- RPTF3
- _RPTF4
- RPTF1
- RPT4
- _RPT1
- _RPT0
- RPT0
- _RPTF2
- RPTF0
- _RPT3
- _RPT2
- _RPTF3
- RPT2
- _RPTF1
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- _RPTW3 macro
- _RPT0 macro
- RPTW4 macro
- _RPTF3 macro
- _RPTW4 macro
- RPTF4 macro
- RPTFW2 macro
- RPTW macros
- RPT1 macro
- _RPTF macros
- RPTFW3 macro
- _RPTW0 macro
- _RPTF0 macro
- macros, debugging with
- _RPTW2 macro
- RPTF3 macro
- RPT3 macro
- RPT0 macro
- _RPT macros
- RPTW3 macro
- _RPTFW macros
- debug reporting macros
- RPTF macros
- RPT macros
- _RPTW macros
- RPTF2 macro
- _RPTF1 macro
- _RPT1 macro
- _RPT4 macro
- _RPTFW2 macro
- _RPTFW1 macro
- RPTF0 macro
- _RPT2 macro
- RPTFW macros
- _RPTW1 macro
- _RPTFW0 macro
- RPT4 macro
- _RPT3 macro
- _RPTFW3 macro
- _RPTF4 macro
- _RPTFW4 macro
- _RPTF2 macro
- RPTW0 macro
- RPTFW4 macro
- RPTFW0 macro
- RPTW2 macro
- RPTF1 macro
- RPT2 macro
- RPTFW1 macro
- RPTW1 macro
ms.assetid: a5bf8b30-57f7-4971-8030-e773b7a1ae13
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 51668f9b286a6b438d7f7b686114b2fcf70c25ed
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="rpt-rptf-rptw-rptfw-macros"></a>_RPT, _RPTF, _RPTW, _RPTFW Makroları
Hata ayıklama rapor (yalnızca hata ayıklama sürümü) oluşturarak uygulamanın ilerleme durumunu izler. Unutmayın  *n*  değişkenlerinde sayısını belirtir `args` ve 0, 1, 2, 3, 4 veya 5 olabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      _RPT  
      n  
      (  
   reportType,  
   format,  
...[args]  
);  
_RPTFn(  
   reportType,  
   format,  
   [args]  
);  
_RPTWn(  
   reportType,  
   format   
   [args]  
);  
_RPTFWn(  
   reportType,  
   format   
   [args]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `reportType`  
 Rapor türü: `_CRT_WARN`, `_CRT_ERROR`, veya `_CRT_ASSERT`.  
  
 `format`  
 Kullanıcı iletisi oluşturmak için kullanılan biçim denetimi dizesi.  
  
 `args`  
 Tarafından kullanılan değiştirme bağımsız `format`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makroları ele `reportType` ve `format` parametreleri. Ayrıca, bunlar en çok dört ek bağımsız değişkenler, makrosu adına eklenen numarasına göre miktarlara de alabilir. Örneğin, `_RPT0` ve `_RPTF0` hiçbir ek bağımsız değişkenler almayan `_RPT1` ve `_RPTF1` ele `arg1`, `_RPT2` ve `_RPTF2` ele `arg1` ve `arg2`ve benzeri.  
  
 `_RPT` Ve `_RPTF` makroları benzer [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) işlev çünkü hata ayıklama işlemi sırasında bir uygulamanın ilerleme durumunu izlemek için kullanılabilir. Ancak, bu makroları daha esnektir `printf` içinde alınmalıdır gerekmediği için `#ifdef` olmasını engellemek için deyimleri adlı bir uygulama bir perakende yapı içinde. Bu esneklik kullanılarak elde edilir [_DEBUG](../../c-runtime-library/debug.md) makrosu; `_RPT` ve `_RPTF` makroları yalnızca kullanılabilir olduğunda `_DEBUG` bayrağı tanımlanır. Zaman `_DEBUG` olan tanımlı değilse, bu makroları çağrıları ön işleme sırasında kaldırılır.  
  
 `_RPTW` Ve `_RPTFW` makroları bu makroları geniş karakter sürümü bulunmaktadır. Gibi oldukları `wprintf` ve joker karakter dizeleri bağımsız olarak gerçekleştirin.  
  
 `_RPT` Makroları çağrısı [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) kullanıcı iletisi içeren bir hata ayıklama rapor oluşturmak için işlev. `_RPTW` Makroları çağrısı `_CrtDbgReportW` geniş karakterler ile aynı rapor oluşturmak için işlev. `_RPTF` Ve `_RPTFW` makroları nerede rapor makrosu çağrıldı, ayrıca kullanıcı iletisi kaynak dosyasının ve satır numarası ile hata ayıklama rapor oluşturun. Kullanıcı ileti getirilmesiyle oluşturulur `arg`[*n*] bağımsız değişkenleriyle `format` tarafından tanımlanan aynı kurallarını kullanarak, dize [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) işlevi.  
  
 `_CrtDbgReport` veya `_CrtDbgReportW` hata ayıklama rapor oluşturur ve onun geçerli rapor modlarını dayalı hedefleri ve dosyası için tanımlı belirler `reportType`. [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) ve [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) işlevleri, her rapor türü için hedefleri tanımlamak için kullanılır.  
  
 Varsa bir `_RPT` makrosu çağrılır ve hiçbiri `_CrtSetReportMode` ya da `_CrtSetReportFile` bırakıldı olarak adlandırılan, iletileri gibi görüntülenir.  
  
|Rapor türü|Çıktı hedefi|  
|-----------------|------------------------|  
|`_CRT_WARN`|Uyarı metni görüntülenmez.|  
|`_CRT_ERROR`|Açılır pencere. Aynı gibi `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` belirtilmiş.|  
|`_CRT_ASSERT`|Aynı `_CRT_ERROR`.|  
  
 Ne zaman hedef bir hata ayıklama iletisi penceredir ve kullanıcının seçtiği **yeniden deneme** düğmesi, `_CrtDbgReport` veya `_CrtDbgReportW` koşuluyla tam zamanında (JIT) hata ayıklama etkin hata ayıklayıcı başlatmak bu makroları neden 1 döndürür. Hata ayıklama bir hata işleme mekanizması olarak bu makroları kullanma hakkında daha fazla bilgi için bkz: [doğrulama ve raporlama makroları kullanarak](/visualstudio/debugger/macros-for-reporting).  
  
 Diğer iki makroları hata ayıklama raporu oluşturan mevcut. [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makrosu ancak ifade bağımsız değişkeni FALSE olarak değerlendirildiğinde yalnızca bir rapor oluşturur. [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) tam olarak benzer olduğunu `_ASSERT`, ancak oluşturulan rapora başarısız ifade içeriyor.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Makrosu|Gerekli başlık|  
|-----------|---------------------|  
|`_RPT` Makroları|\<crtdbg.h>|  
|`_RPTF` Makroları|\<crtdbg.h>|  
|`_RPTW` Makroları|\<crtdbg.h>|  
|`_RPTFW` Makroları|\<crtdbg.h>|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
 Bunlar makrolar ve Crtdbg.h dahil ederek elde edilir, ancak uygulama bu makroları diğer çalışma zamanı işlevleri çağırmak için hata ayıklama kitaplıklarından birini bağlamanız gerekir.  
  
## <a name="example"></a>Örnek  
 Örnekte bkz [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) konu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)