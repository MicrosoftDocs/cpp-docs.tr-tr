---
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
ms.openlocfilehash: bf88bae40031f6e92d6f936ac8a50f85d6c4e36c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942287"
---
# <a name="_crtsetreportfile"></a>_CrtSetReportFile

**_CRTDBG_MODE_FILE**belirtmek Için [_Crtsetreportmode](crtsetreportmode.md) komutunu kullandıktan sonra, ileti metnini alacak dosya tanıtıcısını belirtebilirsiniz. **_Crtsetreportfile** Ayrıca, metin hedefini belirtmek Için [_Crtdbgreport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) tarafından da kullanılır (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
_HFILE _CrtSetReportFile(
   int reportType,
   _HFILE reportFile
);
```

### <a name="parameters"></a>Parametreler

*reportType*<br/>
Rapor türü: **_CRT_WARN**, **_CRT_ERROR**ve **_CRT_ASSERT**.

*reportFile*<br/>
*ReportType*için yeni rapor dosyası.

## <a name="return-value"></a>Dönüş Değeri

Başarılı tamamlandığında, **_Crtsetreportfile** , *reportType*içinde belirtilen rapor türü için tanımlanan önceki rapor dosyasını döndürür. *ReportType*için geçersiz bir değer geçirilirse, bu Işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **_CRTDBG_HFILE_ERROR**döndürür. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Crtsetreportfile** , **_Crtdbgreport**tarafından oluşturulan belirli bir rapor türü için hedefi veya hedefleri tanımlamak üzere [_Crtsetreportmode](crtsetreportmode.md) işleviyle birlikte kullanılır. **_Crtsetreportmode** , belirli bir rapor türü için **_CRTDBG_MODE_FILE** Raporlama modunu atamak üzere çağrıldığında, hedef olarak kullanılacak belirli dosya veya akışı tanımlamak Için **_Crtsetreportfile** çağrılmalıdır. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_Crtsetreportfile** çağrıları ön işleme sırasında kaldırılır.

Aşağıdaki listede *ReportFile* için kullanılabilen seçenekler ve **_Crtdbgreport**'un elde edilen davranışı gösterilmektedir. Bu seçenekler, Crtdbg. h içinde bit bayrakları olarak tanımlanmıştır.

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

- **_CRTDBG_REPORT_**

   Geçerli rapor modunu döndürür.

Her rapor türü tarafından kullanılan rapor dosyası ayrı olarak denetlenebilir. Örneğin, bir **_CRT_ERROR** *reportType* **'ın,** Kullanıcı tanımlı bir dosya tanıtıcısına veya akışına bildirildiği bir rapor *türü* olan **stderr**'e raporlanabilmesi olasıdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<Crtdbg. h >|\<errno. h >|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout**ve **stderr**Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kütüphaneler** Yalnızca [CRT kitaplığı özelliklerinin](../../c-runtime-library/crt-library-features.md) hatalarını ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
