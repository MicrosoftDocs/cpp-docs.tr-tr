---
title: _CrtSetReportFile
ms.date: 11/04/2016
apiname:
- _CrtSetReportFile
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
- CrtSetReportFile
- _CrtSetReportFile
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
ms.openlocfilehash: 32a560e09c47468daf48c185e23d6e289c6d1d9b
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64343014"
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile

Kullandıktan sonra [_CrtSetReportMode](crtsetreportmode.md) belirtmek için **_CRTDBG_MODE_FILE**, ileti metnini almak için dosya tanıtıcısını belirleyebilirsiniz. **_CrtSetReportFile** tarafından da kullanılan [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) metni (yalnızca hata ayıklama sürümü) hedefini belirtmek için.

## <a name="syntax"></a>Sözdizimi

```C
_HFILE _CrtSetReportFile(
   int reportType,
   _HFILE reportFile
);
```

### <a name="parameters"></a>Parametreler

*reportType*<br/>
Rapor türü: **_CRT_WARN**, **_CRT_ERROR**, ve **_CRT_ASSERT**.

*reportFile*<br/>
Yeni rapor dosyası için *reportType*.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, **_CrtSetReportFile** içinde belirtilen rapor türü için tanımlanmış olan önceki rapor dosyasını döndürür *reportType*. Geçersiz bir değer geçtiyse *reportType*, bu işlev içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **_CRTDBG_HFILE_ERROR**. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_CrtSetReportFile** ile kullanılan [_CrtSetReportMode](crtsetreportmode.md) hedefi veya hedefleri tarafından oluşturulan belirli bir rapor türü için tanımlamak üzere işlevi **_CrtDbgReport**. Zaman **_CrtSetReportMode** atamak adlı **_CRTDBG_MODE_FILE** modu, belirli bir rapor türü için raporlama **_CrtSetReportFile** için çağrılmalıdır belirli dosya ya da hedef olarak kullanılmak üzere stream tanımlayın. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtSetReportFile** ön işleme sırasında kaldırılır.

Aşağıdaki liste için kullanılabilen seçenekleri gösterir *reportFile* ve sonuçta elde edilen davranışını **_CrtDbgReport**. Bu seçenekler, Crtdbg.h'de bit bayrakları olarak tanımlanır.

- **dosya tanıtıcısı**

   İletilerin hedefi olacak dosyaya tanıtıcı. Tanıtıcı geçerliliğini doğrulamak için girişimde bulunulmaz. Açın ve dosya tanıtıcısını kapatmanız gerekir. Örneğin:

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

   İleti yazar **stderr**, hangi yönlendirilebilir gibi:

   ```C
   freopen( "c:\\log2.txt", "w", stderr);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);

   _RPT0(_CRT_ERROR,"1st message\n");
   ```

- **_CRTDBG_FILE_STDOUT**

   İleti yazar **stdout**, hangi bunu yeniden yönlendirebilirsiniz.

- **_CRTDBG_REPORT_FILE**

   Geçerli rapor modunu döndürür.

Her rapor türü tarafından kullanılan rapor dosyası ayrı olarak denetlenebilir. Örneğin belirtmek olası bir *reportType* , **_CRT_ERROR** rapor **stderr**, ancak bir *reportType* ,**_CRT_ASSERT** bir kullanıcı tanımlı tanıtıcıya veya akışa rapor.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<crtdbg.h >|\<errno.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** Hata ayıklama sürümleri [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
