---
title: _CrtSetReportMode
ms.date: 11/04/2016
apiname:
- _CrtSetReportMode
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
- _CrtSetReportMode
- CrtSetReportMode
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
ms.openlocfilehash: 2096d39a8ba316fc76c97517a16e34231940e7f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335301"
---
# <a name="crtsetreportmode"></a>_CrtSetReportMode

Hedef veya hedefleri tarafından oluşturulan belirli bir rapor türü için belirtir **_CrtDbgReport** ve çağıran makroların [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md), gibi [_ASSERT, _ASSERTE, _ASSERT_EXPR makroları](assert-asserte-assert-expr-macros.md), [_ASSERT, _ASSERTE, _ASSERT_EXPR makroları](assert-asserte-assert-expr-macros.md), [_RPT, _RPTF, _RPTW, _RPTFW makroları](rpt-rptf-rptw-rptfw-macros.md), ve [_RPT, _RPTF, _RPTW, _RPTFW makroları](rpt-rptf-rptw-rptfw-macros.md) (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
int _CrtSetReportMode(
   int reportType,
   int reportMode
);
```

### <a name="parameters"></a>Parametreler

*reportType*<br/>
Rapor türü: **_CRT_WARN**, **_CRT_ERROR**, ve **_CRT_ASSERT**.

*reportMode*<br/>
Yeni rapor modu veya modları için *reportType*.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, **_CrtSetReportMode** içinde belirtilen rapor türü için önceki rapor modu veya modları döndürür *reportType*. Geçersiz bir değer olarak geçtiyse *reportType* ya da geçersiz bir mod için belirtilen *reportMode*, **_CrtSetReportMode** olarak geçersiz parametre işleyicisini çağırır açıklanan [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve -1 döndürür. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_CrtSetReportMode** Çıkış hedefini belirtir **_CrtDbgReport**. Çünkü makroları [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md), [_RPT](rpt-rptf-rptw-rptfw-macros.md), ve [_RPTF](rpt-rptf-rptw-rptfw-macros.md) çağrı **_CrtDbgReport**, **_CrtSetReportMode** makroları ile belirtilen metin Çıkış hedefini belirtir.

Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtSetReportMode** ön işleme sırasında kaldırılır.

Değil çağırırsanız **_CrtSetReportMode** iletileri çıkış hedefinin tanımlamak için ardından aşağıdaki varsayılan değerler geçerli olur:

- Onaylama hatalarını ve hata ayıklama ileti penceresine yönlendirilirsiniz.

- Uyarıları Windows uygulamalarından hata ayıklayıcının çıkış penceresinde gönderilir.

- Konsol uygulamaları gelen uyarılar görüntülenmez.

Aşağıdaki tabloda, Crtdbg.h tanımlanan rapor türlerini listeler.

|Rapor türü|Açıklama|
|-----------------|-----------------|
|**_CRT_WARN**|Uyarılar, iletileri ve hemen ilgilenilmesi gerekmiyor bilgileri.|
|**_CRT_ERROR**|Hatalar, kurtarılamayan sorunlar ve dikkat gerektiren sorunlar.|
|**_CRT_ASSERT**|Onaylama işlemi hataları (vermesi ifadeleri onaylanan **FALSE**).|

**_CrtSetReportMode** işlevi atar belirtilen yeni rapor modu *reportMode* belirtilen rapor türü için *reportType* ve önceden tanımlanmış döndürür Rapor modu için *reportType*. Aşağıdaki tablo için kullanılabilen seçenekleri listeler *reportMode* ve sonuçta elde edilen davranışını **_CrtDbgReport**. Bu seçenekler, Crtdbg.h'de bit bayrakları olarak tanımlanır.

|Rapor modu|_CrtDbgReport davranışı|
|-----------------|-----------------------------|
|**_CRTDBG_MODE_DEBUG**|Hata Ayıklayıcı'nın çıkış penceresine ileti yazar.|
|**_CRTDBG_MODE_FILE**|Bir kullanıcı tarafından sağlanan dosya işleci ileti yazar. [_CrtSetReportFile](crtsetreportfile.md) belirli dosya ya da hedef olarak kullanılmak üzere akış tanımlamak için çağrılmalıdır.|
|**_CRTDBG_MODE_WNDW**|Beraber iletiyi görüntülemek için bir ileti kutusu oluşturur [iptal](abort.md), **yeniden**, ve **Yoksay** düğmeleri.|
|**_CRTDBG_REPORT_MODE**|Döndürür *reportMode* için belirtilen *reportType*:<br /><br /> 1   **_CRTDBG_MODE_FILE**<br /><br /> 2   **_CRTDBG_MODE_DEBUG**<br /><br /> 4   **_CRTDBG_MODE_WNDW**|

Her rapor türü, hiç bir, iki veya üç modları veya yok modu kullanılarak bildirilebilir. Bu nedenle, bir tek bir rapor türü için tanımlanan birden fazla hedef olması mümkündür. Örneğin, aşağıdaki kod parçası ve için hem bir hata ayıklama ileti penceresine gönderilecek onaylama işlemi hataları neden **stderr**:

```C
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );
```

Ayrıca, raporlama modu veya modları her rapor türü için ayrı olarak denetlenebilir. Örneğin belirtmek olası bir *reportType* , **_CRT_WARN** olması bir çıkış hata ayıklama dizeye gönderilirken, **_CRT_ASSERT** olması bir hata ayıklama ileti penceresine kullanılarak görüntülenir ve gönderilen **stderr**, daha önce Resimli.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_CrtSetReportMode**|\<crtdbg.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** Hata ayıklama sürümleri [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
