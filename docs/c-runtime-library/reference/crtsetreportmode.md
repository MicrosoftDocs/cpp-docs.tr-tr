---
title: _CrtSetReportMode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd4ac54cd4bd8877e8a6ba32f585ef5d5e29e65c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="crtsetreportmode"></a>_CrtSetReportMode

Hedef veya tarafından oluşturulan belirli bir rapor türü için hedefleri belirtir **_CrtDbgReport** ve çağrı makroların [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md), gibi [_ASSERT, _ASSERTE, _ASSERT_EXPR makroları](assert-asserte-assert-expr-macros.md), [_ASSERT, _ASSERTE, _ASSERT_EXPR makroları](assert-asserte-assert-expr-macros.md), [_RPT, _RPTF, _RPTW, _RPTFW makroları](rpt-rptf-rptw-rptfw-macros.md), ve [_RPT, _RPTF, _RPTW, _RPTFW makroları](rpt-rptf-rptw-rptfw-macros.md) (yalnızca hata ayıklama sürümü).

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
Yeni rapor modu veya modlarını *reportType*.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, **_CrtSetReportMode** belirtilen rapor türü için önceki rapor modu veya modları döndürür *reportType*. Geçersiz bir değer olarak geçtiyse *reportType* veya geçersiz bir mod için belirtilen *reportMode*, **_CrtSetReportMode** geçersiz parametre işleyicisi olarak çağırır açıklanan [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve -1 döndürür. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_CrtSetReportMode** Çıkış hedefini belirtir **_CrtDbgReport**. Çünkü makrolar [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md), [_RPT](rpt-rptf-rptw-rptfw-macros.md), ve [_RPTF](rpt-rptf-rptw-rptfw-macros.md) çağrısı **_CrtDbgReport**, **_CrtSetReportMode** bu makroları ile belirtilen metin Çıkış hedefini belirtir.

Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtSetReportMode** ön işleme sırasında kaldırılır.

Değil çağırırsanız **_CrtSetReportMode** iletilerinin çıktı hedefi tanımlamak için ardından aşağıdaki varsayılanlar etkindir:

- Onaylama işlemi hataları ve hataları bir hata ayıklama iletisi penceresine yönlendirilirsiniz.

- Uyarıları Windows uygulamalardan Hata Ayıklayıcı'nın çıkış penceresine gönderilir.

- Konsol uygulamalardan uyarıları görüntülenmez.

Aşağıdaki tabloda Crtdbg.h içinde tanımlanan rapor türleri listelenmektedir.

|Rapor türü|Açıklama|
|-----------------|-----------------|
|**_CRT_WARN**|Uyarılar, iletileri ve hemen ilgilenilmesi gerekmiyor bilgiler.|
|**_CRT_ERROR**|Hataları, kurtarılamaz sorunları ve Acil dikkat gerektiren sorunları.|
|**_CRT_ASSERT**|Onaylama işlemi hataları (için değerlendirin ifadeleri uygulanan **FALSE**).|

**_CrtSetReportMode** işlevi atar belirtilen yeni rapor modu *reportMode* belirtilen rapor türü için *reportType* ve önceden tanımlanmış döndürür Rapor modu için *reportType*. İçin kullanılabilir seçenekleri aşağıdaki tabloda listelenmektedir *reportMode* ve sonuçta elde edilen davranışını **_CrtDbgReport**. Bu seçenekler Crtdbg.h bit bayrakları olarak tanımlanır.

|Rapor modu|_CrtDbgReport davranışı|
|-----------------|-----------------------------|
|**_CRTDBG_MODE_DEBUG**|Hata Ayıklayıcı'nın çıkış penceresine iletisi yazar.|
|**_CRTDBG_MODE_FILE**|Bir kullanıcı tarafından sağlanan dosya işleci iletisi yazar. [_CrtSetReportFile](crtsetreportfile.md) belirli dosya ya da hedef olarak kullanılacak akışı tanımlamak için çağrılmalıdır.|
|**_CRTDBG_MODE_WNDW**|İletiyle boyunca görüntülenecek bir ileti kutusu oluşturur [abort](abort.md), **yeniden deneme**, ve **Yoksay** düğmeler.|
|**_CRTDBG_REPORT_MODE**|Döndürür *reportMode* için belirtilen *reportType*:<br /><br /> 1 **_CRTDBG_MODE_FILE**<br /><br /> 2 **_CRTDBG_MODE_DEBUG**<br /><br /> 4 **_CRTDBG_MODE_WNDW**|

Her rapor türü bir, iki veya üç modu veya hiçbir mod hiç kullanarak bildirilebilir. Bu nedenle, tek bir rapor türü için tanımlı birden fazla hedef olması mümkündür. Örneğin, aşağıdaki kod parçası onaylama işlemi hataları bir hem hata ayıklama iletisi penceresinde ve çok gönderilmesine neden olur **stderr**:

```C
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );
```

Ayrıca, raporlama modu veya modları her rapor türü için ayrı ayrı denetlenebilir. Örneğin, belirtmek olası bir *reportType* , **_CRT_WARN** olması bir çıkış hata ayıklama dizesi gönderildi, ancak **_CRT_ASSERT** olması bir hata ayıklama iletisi penceresi kullanılarak görüntülenir ve gönderilen **stderr**, daha önce Resimli.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_CrtSetReportMode**|\<crtdbg.h >|\<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** hata ayıklama sürümleri [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
