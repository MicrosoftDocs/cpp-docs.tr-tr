---
title: _CrtSetReportMode
description: 'Hakkında daha fazla bilgi edinin: _CrtSetReportMode'
ms.date: 3/8/2021
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
ms.openlocfilehash: 770ef955894563dc11dee9f13946067d5d024c11
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514388"
---
# `_CrtSetReportMode`

**_CrtDbgReport** tarafından oluşturulan belirli bir rapor türü için hedef veya hedefleri ve [`_CrtDbgReport, _CrtDbgReportW`](crtdbgreport-crtdbgreportw.md) [ `_ASSERT, _ASSERTE, _ASSERT_EXPR` makrolar](assert-asserte-assert-expr-macros.md), [ `_ASSERT, _ASSERTE, _ASSERT_EXPR` makrolar](assert-asserte-assert-expr-macros.md), [ `_RPT, _RPTF, _RPTW, _RPTFW` makrolar](rpt-rptf-rptw-rptfw-macros.md)ve [ `_RPT, _RPTF, _RPTW, _RPTFW` makrolar](rpt-rptf-rptw-rptfw-macros.md) gibi çağıran tüm makroları belirtir (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
int _CrtSetReportMode(
   int reportType,
   int reportMode
);
```

### <a name="parameters"></a>Parametreler

*`reportType`*\
Rapor türü: **`_CRT_WARN`** , **`_CRT_ERROR`** , ve **`_CRT_ASSERT`** .

*`reportMode`*\
İçin yeni rapor modu veya modları *`reportType`* .

## <a name="return-value"></a>Dönüş Değeri

Başarılı bir şekilde tamamlandığında, **`_CrtSetReportMode`** içinde belirtilen rapor türü için önceki rapor modunu veya modlarını döndürür *`reportType`* . İçin geçersiz bir değer geçirilir *`reportType`* veya için geçersiz bir mod belirtilmişse *`reportMode`* , **`_CrtSetReportMode`** [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev öğesini **`errno`** olarak ayarlar **`EINVAL`** ve-1 döndürür. Daha fazla bilgi için bkz. [`errno, _doserrno, _sys_errlist, and _sys_nerr`](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**`_CrtSetReportMode`** için çıkış hedefini belirtir **`_CrtDbgReport`** . Makrolar [`_ASSERT`](assert-asserte-assert-expr-macros.md) , [`_ASSERTE`](assert-asserte-assert-expr-macros.md) , [`_RPT`](rpt-rptf-rptw-rptfw-macros.md) ve [`_RPTF`](rpt-rptf-rptw-rptfw-macros.md) çağrısı **`_CrtDbgReport`** , **`_CrtSetReportMode`** Bu makrolarla belirtilen metnin çıkış hedefini belirtiyor.

[`_DEBUG`](../../c-runtime-library/debug.md)Tanımlı olmadığında, çağrısı, **`_CrtSetReportMode`** ön işleme sırasında kaldırılır.

**`_CrtSetReportMode`** İletilerin çıkış hedefini tanımlamak için öğesini çağırmayın, aşağıdaki varsayılanlar geçerli olur:

- Onaylama hataları ve hataları bir hata ayıklama iletisi penceresine yönlendirilir.

- Windows uygulamalarından gelen uyarılar, hata ayıklayıcının çıkış penceresine gönderilir.

- Konsol uygulamalarından gelen uyarılar gösterilmez.

Aşağıdaki tablo, içinde tanımlanan rapor türlerini listeler `Crtdbg.h` .

|Rapor türü|Description|
|-----------------|-----------------|
|**`_CRT_WARN`**|Uyarılar, iletiler ve anında ilgilenilmesi gerekmeyen bilgiler.|
|**`_CRT_ERROR`**|Hatalar, kurtarılamaz sorunlar ve anında ilgilenilmesi gereken sorunlar.|
|**`_CRT_ASSERT`**|Onaylama işlemi sayısı (sonucunu veren ifadeler **`FALSE`** ).|

İşlevi ' de belirtilen **`_CrtSetReportMode`** Yeni rapor modunu *`reportMode`* ' de belirtilen rapor türüne atar *`reportType`* ve için önceden tanımlanmış rapor modunu döndürür *`reportType`* . Aşağıdaki tabloda, için kullanılabilen seçimler *`reportMode`* ve sonuç davranışı listelenmektedir **`_CrtDbgReport`** . Bu seçenekler, Crtdbg. h içinde bit bayrakları olarak tanımlanmıştır.

|Rapor modu|_CrtDbgReport davranışı|
|-----------------|-----------------------------|
|**`_CRTDBG_MODE_DEBUG`**|İletiyi hata ayıklayıcının çıkış penceresine yazar.|
|**`_CRTDBG_MODE_FILE`**|İletiyi Kullanıcı tarafından sağlanan bir dosya tanıtıcısına yazar. [`_CrtSetReportFile`](crtsetreportfile.md) hedef olarak kullanılacak belirli dosya veya akışı tanımlamak için çağrılmalıdır.|
|**`_CRTDBG_MODE_WNDW`**|İletiyi [`abort`](abort.md) ,, **`Retry`** ve **Ignore** düğmeleriyle birlikte görüntüleyen bir ileti kutusu oluşturur.|
|**`_CRTDBG_REPORT_MODE`**|*`reportMode`* Belirtilen için döndürür *`reportType`* :<br /><br /> 1   **`_CRTDBG_MODE_FILE`**<br /><br /> iki   **`_CRTDBG_MODE_DEBUG`**<br /><br /> 4   **`_CRTDBG_MODE_WNDW`**|

Her rapor türü bir, iki veya üç mod kullanılarak bildirilebilir veya hiçbir mod yoktur. Bu nedenle, tek bir rapor türü için birden çok hedefin tanımlanması mümkündür. Örneğin, aşağıdaki kod parçası onaylama hatalarının hem hata ayıklama iletisi penceresine hem de şunları yapmasına neden olur **`stderr`** :

```C
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );
```

Ayrıca, her rapor türü için raporlama modu veya modları ayrı olarak denetlenebilir. Örneğin, bir *`reportType`* **`_CRT_WARN`** çıkış hata ayıklama dizesine gönderilmesini, **`_CRT_ASSERT`** **`stderr`** daha önce gösterildiği gibi bir hata ayıklama iletisi penceresi kullanılarak görüntülen, ve öğesine gönderilmesini belirtmek mümkündür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**`_CrtSetReportMode`**|`<crtdbg.h>`|`<errno.h>`|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) hata ayıklama sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)
