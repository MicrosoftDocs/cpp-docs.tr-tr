---
title: _CrtSetReportMode
ms.date: 11/04/2016
api_name:
- _CrtSetReportMode
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
- _CrtSetReportMode
- CrtSetReportMode
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
ms.openlocfilehash: ae7e83ac009d572f8a9f6484519b0cdfb7499ce3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938458"
---
# <a name="_crtsetreportmode"></a>_CrtSetReportMode

**_CrtDbgReport** tarafından oluşturulan belirli bir rapor türü için hedef veya hedefleri belirtir ve __ASSERT_EXPR [, _asserte, Macros](assert-asserte-assert-expr-macros.md), _ONAY, _asserte, _ gibi _Crtdbgreport [, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)gibi tüm makrolar [ ASSERT_EXPR makroları](assert-asserte-assert-expr-macros.md), [_rpt, _RPTF, _RPTW, _RPTFW makroları](rpt-rptf-rptw-rptfw-macros.md)ve [_rpt, _rptf, _rptw, _rptfw makroları](rpt-rptf-rptw-rptfw-macros.md) (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
int _CrtSetReportMode(
   int reportType,
   int reportMode
);
```

### <a name="parameters"></a>Parametreler

*reportType*<br/>
Rapor türü: **_CRT_WARN**, **_CRT_ERROR**ve **_CRT_ASSERT**.

*reportMode*<br/>
*ReportType*için yeni rapor modu veya modlar.

## <a name="return-value"></a>Dönüş Değeri

Başarılı tamamlandığında, **_Crtsetreportmode** , *reportType*içinde belirtilen rapor türü için önceki rapor modunu veya modlarını döndürür. ReportType olarak geçersiz bir değer geçirilmemişse veya *reportMode*için geçersiz bir mod belirtilmişse, **_CrtSetReportMode** [parametresi, parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve-1 döndürür. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Crtsetreportmode** , **_Crtdbgreport**için çıkış hedefini belirtir. Makrolar [_Onayı](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md), [_Rpt](rpt-rptf-rptw-rptfw-macros.md)ve [_Rptf](rpt-rptf-rptw-rptfw-macros.md) Call **_CrtDbgReport**, **_CrtSetReportMode** , bu makrolarla belirtilen metnin çıkış hedefini belirtir.

[_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_Crtsetreportmode** 'a yapılan çağrılar ön işleme sırasında kaldırılır.

İletilerin çıkış hedefini tanımlamak için **_Crtsetreportmode** öğesini çağırmayın, aşağıdaki varsayılanlar geçerli olur:

- Onaylama hataları ve hataları bir hata ayıklama iletisi penceresine yönlendirilir.

- Windows uygulamalarından gelen uyarılar, hata ayıklayıcının çıkış penceresine gönderilir.

- Konsol uygulamalarından gelen uyarılar gösterilmez.

Aşağıdaki tabloda, Crtdbg. h içinde tanımlanan rapor türleri listelenmektedir.

|Rapor türü|Açıklama|
|-----------------|-----------------|
|**_CRT_WARN**|Uyarılar, iletiler ve anında ilgilenilmesi gerekmeyen bilgiler.|
|**_CRT_ERROR**|Hatalar, kurtarılamaz sorunlar ve anında ilgilenilmesi gereken sorunlar.|
|**_CRT_ASSERT**|Onaylama hatalarıyla ( **yanlış**sonucunu veren ifadeler).|

**_Crtsetreportmode** işlevi, *reportMode* 'da belirtilen yeni rapor modunu *reportType* Içinde belirtilen rapor türüne atar ve *reportType*için önceden tanımlanmış rapor modunu döndürür. Aşağıdaki tabloda, *reportMode* için kullanılabilen seçimler ve **_Crtdbgreport**'un elde edilen davranışı listelenmektedir. Bu seçenekler, Crtdbg. h içinde bit bayrakları olarak tanımlanmıştır.

|Rapor modu|_CrtDbgReport davranışı|
|-----------------|-----------------------------|
|**_CRTDBG_MODE_DEBUG**|İletiyi hata ayıklayıcının çıkış penceresine yazar.|
|**_CRTDBG_MODE_FILE**|İletiyi Kullanıcı tarafından sağlanan bir dosya tanıtıcısına yazar. Hedef olarak kullanılacak belirli dosya veya akışı tanımlamak için [_Crtsetreportfile](crtsetreportfile.md) çağrılmalıdır.|
|**_CRTDBG_MODE_WNDW**|İletiyi [Durdur](abort.md), **yeniden dene**ve **Yoksay** düğmeleriyle birlikte göstermek için bir ileti kutusu oluşturur.|
|**_CRTDBG_REPORT_MODE**|Belirtilen *reportType*Için *reportMode* döndürür:<br /><br /> 1 **_CRTDBG_MODE_FILE**<br /><br /> 2   **_CRTDBG_MODE_DEBUG**<br /><br /> 4   **_CRTDBG_MODE_WNDW**|

Her rapor türü bir, iki veya üç mod kullanılarak bildirilebilir veya hiçbir mod yoktur. Bu nedenle, tek bir rapor türü için birden çok hedefin tanımlanması mümkündür. Örneğin, aşağıdaki kod parçası onaylama hatalarının hem hata ayıklama iletisi penceresine hem de **stderr**'e gönderilmesine neden olur:

```C
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );
```

Ayrıca, her rapor türü için raporlama modu veya modları ayrı olarak denetlenebilir. Örneğin, bir **_CRT_WARN** *reportType* 'ın bir çıkış hata ayıklama dizesine gönderilmesini, **_CRT_ASSERT** bir hata ayıklama iletisi penceresi kullanılarak görüntülenmeyeceğini ve daha önce gösterildiği gibi **stderr**'e gönderileceğini belirtmek mümkündür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_CrtSetReportMode**|\<Crtdbg. h >|\<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kütüphaneler** Yalnızca [CRT kitaplığı özelliklerinin](../../c-runtime-library/crt-library-features.md) hatalarını ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
