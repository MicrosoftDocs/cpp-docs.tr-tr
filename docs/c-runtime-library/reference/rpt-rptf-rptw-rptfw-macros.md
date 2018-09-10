---
title: _RPT, _RPTF, _RPTW, _RPTFW makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69347ab698661346b8d598dda1bb007d071a21f8
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44104153"
---
# <a name="rpt-rptf-rptw-rptfw-macros"></a>_RPT, _RPTF, _RPTW, _RPTFW Makroları

Hata ayıklama raporunu (yalnızca hata ayıklama sürümü) oluşturarak bir uygulamanın ilerlemesini izler. Unutmayın *n* bağımsız değişken sayısını belirten *args* ve 0, 1, 2, 3, 4 veya 5 olabilir.

## <a name="syntax"></a>Sözdizimi

```C
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

### <a name="parameters"></a>Parametreler

*reportType*<br/>
Rapor türü: **_CRT_WARN**, **_CRT_ERROR**, veya **_CRT_ASSERT**.

*Biçim*<br/>
Kullanıcı iletisini oluşturmak için kullanılan biçim denetimi dizesi.

*bağımsız değişken*<br/>
Tarafından kullanılan değiştirme bağımsız değişkenleri *biçimi*.

## <a name="remarks"></a>Açıklamalar

Bu makrolar ele *reportType* ve *biçimi* parametreleri. Ayrıca, bunların en fazla dört ek bağımsız değişkenler, makro adına numarası miktarlara da sürebilir. Örneğin, **_RPT0** ve **_RPTF0** hiçbir ek bağımsız değişkenler almayan **_RPT1** ve **_RPTF1** ele *arg1*, **_RPT2** ve **_RPTF2** ele *arg1* ve **arg2**ve benzeri.

**_RPT** ve **_RPTF** makroları benzer [printf](printf-printf-l-wprintf-wprintf-l.md) işlev çünkü hata ayıklama işlemi sırasında bir uygulamanın ilerleme durumunu izlemek için kullanılabilir. Ancak, bu makrolar daha esnek **printf** içinde içine alınması gerekmez çünkü **#ifdef** olmasını engellemek için ifadeleri adlı bir uygulama bir perakende yapı içinde. Bu esnekliğin kullanılarak elde edilir [_DEBUG](../../c-runtime-library/debug.md) makrosu; **_RPT** ve **_RPTF** makroları yalnızca kullanılabilir olduğunda **_DEBUG** bayrağı tanımlı. Zaman **_DEBUG** olduğu tanımlı değilse, bu makroları için çağrılar ön işleme sırasında kaldırılır.

**_RPTW** ve **_RPTFW** makrolardır Bu makroların geniş baytlık karakter sürümleridir. Gibi olduklarını **wprintf** ve geniş karakterli dize bağımsız değişkenleri olarak gerçekleştirin.

**_RPT** makro çağrısı [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) kullanıcı iletisi ile hata ayıklama rapor oluşturma için işlevi. **_RPTW** makro çağrısı **_CrtDbgReportW** geniş karakterler ile aynı raporu oluşturmak için işlev. **_RPTF** ve **_RPTFW** makroları nerede rapor makrosu çağrıldı, ayrıca kullanıcı iletisi için kaynak dosya ve satır numarası ile bir hata ayıklama raporu oluşturun. Kullanıcı iletisini getirilmesiyle oluşturulur **arg**[*n*] bağımsız değişkenleriyle *biçimi* tarafından tanımlanan aynı kuralları kullanarak, dize [printf](printf-printf-l-wprintf-wprintf-l.md)işlevi.

**_CrtDbgReport** veya **_CrtDbgReportW** hata ayıklama raporunu oluşturur ve kendi hedeflere göre geçerli rapor modlarına ve dosya için tanımlı belirler *reportType*. [_CrtSetReportMode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md) işlevler her rapor türü için hedeflerini tanımlamak için kullanılır.

Varsa bir **_RPT** makrosu çağrılır ve her iki **_CrtSetReportMode** ya da **_CrtSetReportFile** olmuştur adlı iletiler gibi görüntülenir.

|Rapor türü|Çıktı hedefi|
|-----------------|------------------------|
|**_CRT_WARN**|Uyarı metni görüntülenmez.|
|**_CRT_ERROR**|Bir açılır pencere. Aynı gibi `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` belirtilmiş.|
|**_CRT_ASSERT**|Aynı **_CRT_ERROR**.|

Olduğunda, hedef hata ayıklama ileti penceresine ve kullanıcı **yeniden** düğmesi **_CrtDbgReport** veya **_CrtDbgReportW** başlatmak Bu makrolar neden 1 döndürür Just-ın-time (JIT) hata ayıklama etkin olması koşuluyla, hata ayıklayıcı. Bu makrolar hata ayıklama bir hata işleme mekanizması olarak kullanma hakkında daha fazla bilgi için bkz. [doğrulama ve raporlama için makroları kullanma](/visualstudio/debugger/macros-for-reporting).

Diğer iki makroları hata ayıklama raporunu oluşturur yok. [_ASSERT](assert-asserte-assert-expr-macros.md) makrosu ancak ifadesi bağımsız değişkeni FALSE olarak değerlendirildiğinde yalnızca bir rapor oluşturur. [_ASSERTE](assert-asserte-assert-expr-macros.md) tam olarak benzer olan **_ASSERT**, ancak oluşturulan raporda başarısız ifadesi içerir.

## <a name="requirements"></a>Gereksinimler

|Makrosu|Gerekli başlık|
|-----------|---------------------|
|**_RPT** makroları|\<crtdbg.h >|
|**_RPTF** makroları|\<crtdbg.h >|
|**_RPTW** makroları|\<crtdbg.h >|
|**_RPTFW** makroları|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

Bu makrolar ve Crtdbg.h eklenerek elde edilir olsa da, uygulamanın bu makrolar diğer çalışma zamanı işlevleri çağırmak için hata ayıklama kitaplıklarını biriyle bağlamanız gerekir.

## <a name="example"></a>Örnek

Örnekte bakın [_ASSERT](assert-asserte-assert-expr-macros.md) konu.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
