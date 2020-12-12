---
description: 'Hakkında daha fazla bilgi edinin: _CrtSetReportFile'
title: _CrtSetReportFile
ms.date: 11/04/2016
api_name:
- _CrtSetReportFile
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
- CrtSetReportFile
- _CrtSetReportFile
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
ms.openlocfilehash: 6b22a76a1a168239210a9f2b93d5cf17d073ec51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206961"
---
# <a name="_crtsetreportfile"></a>_CrtSetReportFile

**_CRTDBG_MODE_FILE** belirtmek için [_CrtSetReportMode](crtsetreportmode.md) kullandıktan sonra, ileti metnini almak için dosya tanıtıcısını belirtebilirsiniz. **_CrtSetReportFile** Ayrıca, metin hedefini belirtmek için [_CrtDbgReportW _CrtDbgReport](crtdbgreport-crtdbgreportw.md) da kullanılır (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
_HFILE _CrtSetReportFile(
   int reportType,
   _HFILE reportFile
);
```

### <a name="parameters"></a>Parametreler

*reportType*<br/>
Rapor türü: **_CRT_WARN**, **_CRT_ERROR** ve **_CRT_ASSERT**.

*reportFile*<br/>
*ReportType* için yeni rapor dosyası.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, **_CrtSetReportFile** *reportType* içinde belirtilen rapor türü için tanımlanan önceki rapor dosyasını döndürür. *ReportType* için geçersiz bir değer geçirilirse, bu Işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **_CRTDBG_HFILE_ERROR** döndürür. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_CrtSetReportFile** , **_CrtDbgReport** tarafından oluşturulan belirli bir rapor türü için hedefi veya hedefleri tanımlamak üzere [_CrtSetReportMode](crtsetreportmode.md) işleviyle birlikte kullanılır. Belirli bir rapor türü için **_CRTDBG_MODE_FILE** Raporlama modunu atamak üzere **_CrtSetReportMode** çağrıldığında **_CrtSetReportFile** , hedef olarak kullanılacak belirli dosya veya akışı tanımlamak için çağrılmalıdır. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, **_CrtSetReportFile** çağrıları ön işleme sırasında kaldırılır.

Aşağıdaki listede *ReportFile* için kullanılabilir seçenekler ve **_CrtDbgReport** elde edilen davranış gösterilmektedir. Bu seçenekler, Crtdbg. h içinde bit bayrakları olarak tanımlanmıştır.

- **dosya tanıtıcısı**

   İleti hedefi olacak dosyanın bir tutamacı. Tanıtıcının geçerliliğini doğrulamak için girişimde bulunuldu. Dosya tanıtıcısını açmanız ve kapatmanız gerekir. Örneğin:

   ```C
   HANDLE hLogFile;
   hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,
      FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,
      FILE_ATTRIBUTE_NORMAL, NULL);
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, hLogFile);

   _RPT0(_CRT_WARN,"file message\n");
   CloseHandle(hLogFile);
   ```

- **_CRTDBG_FILE_STDERR**

   **Stderr**'e ileti yazar ve şu şekilde yeniden yönlendirilebilir:

   ```C
   freopen( "c:\\log2.txt", "w", stderr);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);

   _RPT0(_CRT_ERROR,"1st message\n");
   ```

- **_CRTDBG_FILE_STDOUT**

   Yeniden yönlendirebilmeniz için **stdout**'a ileti yazar.

- **_CRTDBG_REPORT_FILE**

   Geçerli rapor modunu döndürür.

Her rapor türü tarafından kullanılan rapor dosyası ayrı olarak denetlenebilir. Örneğin, bir *reporttype* **_CRT_ERROR** **stderr**'e raporlanırken, bir **_CRT_ASSERT** *reportType* Kullanıcı tanımlı dosya tanıtıcısına veya akışa bildirilirken belirtilebilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<crtdbg.h>|\<errno.h>|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout** ve **stderr** Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** Yalnızca [CRT kitaplığı özelliklerinin](../../c-runtime-library/crt-library-features.md) hatalarını ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
