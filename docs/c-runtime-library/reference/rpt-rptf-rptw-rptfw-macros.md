---
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
ms.openlocfilehash: 567fe0a68f5adad6f5d90ef3da9d673a75bb83a6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949079"
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
Rapor türü: **_CRT_WARN**, **_CRT_ERROR**veya **_CRT_ASSERT**.

*format*<br/>
Kullanıcı iletisini oluşturmak için kullanılan biçim denetimi dizesi.

*args*<br/>
*Biçim*tarafından kullanılan değiştirme bağımsız değişkenleri.

## <a name="remarks"></a>Açıklamalar

Tüm bu makrolar *reportType* ve *Format* parametrelerini alır. Bunlara ek olarak, makro adının sonuna eklenen sayı tarafından işaret eden dört ek bağımsız değişkeni de alabilir. Örneğin, **_Rpt0** ve **_rptf0** ek bağımsız değişkenler almaz, _RPT1 ve **_rptf1** alma *arg1*, **_rpt2** ve **_RPTF2** *arg1* ve **arg2**al ve bu şekilde devam eder.

**_Rpt** ve **_RPTF** makroları, hata ayıklama işlemi sırasında bir uygulamanın ilerlemesini izlemek için kullanılabilecekleri [printf](printf-printf-l-wprintf-wprintf-l.md) işlevine benzerdir. Ancak, bu makrolar, bir uygulamanın perakende derlemesinde çağrılmalarını engellemek için **#ifdef** deyimlerine yönlendirilmeleri gerekmeyen için **printf** 'den daha esnektir. Bu esneklik, [_Debug](../../c-runtime-library/debug.md) makrosu kullanılarak elde edilir; **_Rpt** ve **_RPTF** makroları yalnızca **_hata ayıklama** bayrağı tanımlandığında kullanılabilir. **_Hata ayıklama** tanımlanmadığında, bu makrolara yapılan çağrılar ön işleme sırasında kaldırılır.

**_Rptw** ve **_Rptfw** makroları, Bu makroların geniş karakterli sürümleridir. Bunlar **wprintf** gibidir ve geniş karakter dizelerini bağımsız değişken olarak alır.

**_Rpt** makroları, bir Kullanıcı iletisiyle hata ayıklama raporu oluşturmak Için [_Crtdbgreport](crtdbgreport-crtdbgreportw.md) işlevini çağırır. **_Rptw** makroları, geniş karakterlerle aynı raporu oluşturmak Için **_Crtdbgreportw** işlevini çağırır. **_Rptf** ve **_Rptfw** makroları, Kullanıcı iletisine ek olarak, rapor makrosunun çağrıldığı kaynak dosya ve satır numarası ile bir hata ayıklama raporu oluşturur. Kullanıcı iletisi, **arg**[*n*] bağımsız değişkenlerini, [printf](printf-printf-l-wprintf-wprintf-l.md) işlevi tarafından tanımlanan kurallara göre *Biçim* dizesi ile değiştirerek oluşturulur.

**_CrtDbgReport** veya **_Crtdbgreportw** hata ayıklama raporunu oluşturur ve geçerli rapor modlarına ve *reportType*için tanımlanan dosyaya göre hedeflerini belirler. [_Crtsetreportmode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md) işlevleri, her rapor türü için hedefleri tanımlamak üzere kullanılır.

Bir **_Rpt** makrosu çağrılırsa ve ne **_Crtsetreportmode** ne de **_Crtsetreportfile** çağrılırsa, iletiler aşağıdaki gibi görüntülenir.

|Rapor türü|Çıkış hedefi|
|-----------------|------------------------|
|**_CRT_WARN**|Uyarı metni görüntülenmiyor.|
|**_CRT_ERROR**|Açılır pencere. Belirtildiği gibi `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` aynı.|
|**_CRT_ASSERT**|**_CRT_ERROR**ile aynı.|

Hedef bir hata ayıklama iletisi penceresince ve Kullanıcı **yeniden dene** düğmesini seçtiğinde, **_Crtdbgreport** veya **_Crtdbgreportw** 1 DEĞERINI döndürür ve tam zamanında (JIT) hata ayıklamanın etkin olması şartıyla Bu makroların hata ayıklayıcıyı başlatmasını sağlar. Bu makroları hata ayıklama hatası işleme mekanizması olarak kullanma hakkında daha fazla bilgi için bkz. [makroları doğrulama ve raporlama Için kullanma](/visualstudio/debugger/macros-for-reporting).

Bir hata ayıklama raporu oluşturan diğer iki makro vardır. [_Onaylama](assert-asserte-assert-expr-macros.md) makrosu bir rapor oluşturur, ancak yalnızca kendi ifade BAĞıMSıZ değişkeni yanlış olarak değerlendirilir. [_Asserte](assert-asserte-assert-expr-macros.md) tam olarak **_onaylama**gibidir, ancak oluşturulan raporda başarısız olan ifadeyi içerir.

## <a name="requirements"></a>Gereksinimler

|Makrosu|Gerekli başlık|
|-----------|---------------------|
|**_Rpt** makroları|\<Crtdbg. h >|
|**_Rptf** makroları|\<Crtdbg. h >|
|**_Rptw** makroları|\<Crtdbg. h >|
|**_Rptfw** makroları|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

Bunlar makrolar olsalar ve Crtdbg. h dahil tarafından elde edilse de, bu makrolar diğer çalışma zamanı işlevlerini çağırdığından uygulamanın hata ayıklama kitaplıklarından birine bağlanması gerekir.

## <a name="example"></a>Örnek

[_Onaylama](assert-asserte-assert-expr-macros.md) konusundaki örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
