---
description: 'Hakkında daha fazla bilgi edinin: _RPT, _RPTF, _RPTW, _RPTFW Makrolar'
title: _RPT, _RPTF, _RPTW, _RPTFW Makroları
ms.date: 11/04/2016
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 6cc20032454002b33b4f3d297db582af09c90805
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341444"
---
# <a name="_rpt-_rptf-_rptw-_rptfw-macros"></a>_RPT, _RPTF, _RPTW, _RPTFW Makroları

Bir hata ayıklama raporu oluşturarak uygulamanın ilerlemesini izler (yalnızca hata ayıklama sürümü). *N* , Bağımsız değişkenlerdeki bağımsız değişkenlerin sayısını belirtir *ve 0* , 1, 2, 3, 4 veya 5 olabilir.

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
Rapor türü: **_CRT_WARN**, **_CRT_ERROR** veya **_CRT_ASSERT**.

*formatını*<br/>
Kullanıcı iletisini oluşturmak için kullanılan biçim denetimi dizesi.

*args*<br/>
*Biçim* tarafından kullanılan değiştirme bağımsız değişkenleri.

## <a name="remarks"></a>Açıklamalar

Tüm bu makrolar *reportType* ve *Format* parametrelerini alır. Bunlara ek olarak, makro adının sonuna eklenen sayı tarafından işaret eden dört ek bağımsız değişkeni de alabilir. Örneğin, **_RPT0** ve **_RPTF0** hiçbir ek bağımsız değişken almaz, **_RPT1** ve **_RPTF1** alma *,* **_RPT2** ve **_RPTF2** Al *arg1* ve **arg2**.

**_RPT** ve **_RPTF** makroları, hata ayıklama işlemi sırasında uygulamanın ilerlemesini izlemek için kullanılabilecekleri [printf](printf-printf-l-wprintf-wprintf-l.md) işlevine benzerdir. Ancak, bu makrolar, bir uygulamanın perakende derlemesinde çağrılmalarını engellemek için **#ifdef** deyimlerine yönlendirilmeleri gerekmeyen için **printf** 'den daha esnektir. Bu esneklik [_DEBUG](../../c-runtime-library/debug.md) makro kullanılarak elde edilir; **_RPT** ve **_RPTF** makroları yalnızca **_DEBUG** bayrağı tanımlandığında kullanılabilir. **_DEBUG** tanımlanmadığında, bu makrolara yapılan çağrılar ön işleme sırasında kaldırılır.

**_Rptw** ve **_rptfw** makroları, Bu makroların geniş karakterli sürümleridir. Bunlar **wprintf** gibidir ve geniş karakter dizelerini bağımsız değişken olarak alır.

**_RPT** makroları, bir Kullanıcı iletisiyle hata ayıklama raporu oluşturmak için [_CrtDbgReport](crtdbgreport-crtdbgreportw.md) işlevini çağırır. **_Rptw** makroları, geniş karakterlerle aynı raporu oluşturmak için **_CrtDbgReportW** işlevini çağırır. **_RPTF** ve **_rptfw** makroları, Kullanıcı iletisine ek olarak, rapor makrosunun çağrıldığı kaynak dosya ve satır numarası ile bir hata ayıklama raporu oluşturur. Kullanıcı iletisi, **arg**[*n*] bağımsız değişkenlerini, [printf](printf-printf-l-wprintf-wprintf-l.md) işlevi tarafından tanımlanan kurallara göre *Biçim* dizesi ile değiştirerek oluşturulur.

**_CrtDbgReport** veya **_CrtDbgReportW** , hata ayıklama raporunu oluşturur ve geçerli rapor modlarına ve *reportType* için tanımlanan dosyaya göre hedeflerini belirler. [_CrtSetReportMode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md) işlevleri, her rapor türü için hedefleri tanımlamak üzere kullanılır.

**_RPT** bir makro çağrılırsa ve **_CrtSetReportMode** veya **_CrtSetReportFile** çağrılmadıysa, iletiler aşağıdaki gibi görüntülenir.

|Rapor türü|Çıkış hedefi|
|-----------------|------------------------|
|**_CRT_WARN**|Uyarı metni görüntülenmiyor.|
|**_CRT_ERROR**|Açılır pencere. Belirtildiği gibi aynı `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` .|
|**_CRT_ASSERT**|**_CRT_ERROR** ile aynı.|

Hedef bir hata ayıklama iletisi penceresidir ve Kullanıcı **yeniden dene** düğmesini seçtiğinde, **_CrtDbgReport** veya **_CrtDbgReportW** 1 DEĞERINI döndürür ve tam zamanında (JIT) hata ayıklamanın etkin olması şartıyla Bu makroların hata ayıklayıcıyı başlatmasını sağlar. Bu makroları hata ayıklama hatası işleme mekanizması olarak kullanma hakkında daha fazla bilgi için bkz. [makroları doğrulama ve raporlama Için kullanma](/visualstudio/debugger/macros-for-reporting).

Bir hata ayıklama raporu oluşturan diğer iki makro vardır. [_Assert](assert-asserte-assert-expr-macros.md) makro bir rapor oluşturur, ancak yalnızca kendi ifade BAĞıMSıZ değişkeni yanlış olarak değerlendirilir. [_ASSERTE](assert-asserte-assert-expr-macros.md) tam olarak **_assert** gibidir, ancak oluşturulan raporda başarısız olan ifadeyi içerir.

## <a name="requirements"></a>Gereksinimler

|Makroya|Gerekli başlık|
|-----------|---------------------|
|**_RPT** makrolar|\<crtdbg.h>|
|**_RPTF** makrolar|\<crtdbg.h>|
|**_Rptw** makrolar|\<crtdbg.h>|
|**_Rptfw** makrolar|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

Bunlar makrolar olsalar ve Crtdbg. h dahil tarafından elde edilse de, bu makrolar diğer çalışma zamanı işlevlerini çağırdığından uygulamanın hata ayıklama kitaplıklarından birine bağlanması gerekir.

## <a name="example"></a>Örnek

[_Assert](assert-asserte-assert-expr-macros.md) konusundaki örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
