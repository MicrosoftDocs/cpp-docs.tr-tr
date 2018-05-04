---
title: _CrtSetReportFile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3df4f54ad8e191dac7110a914bdde1cec888ff9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile

Kullandıktan sonra [_CrtSetReportMode](crtsetreportmode.md) belirtmek için **_CRTDBG_MODE_FILE**, ileti metnini almak için dosya tanıtıcısı belirtebilirsiniz. **_CrtSetReportFile** tarafından da kullanılan [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) metin (yalnızca hata ayıklama sürümü) hedef belirtmek için.

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

Başarıyla tamamlandığında, **_CrtSetReportFile** önceki rapor dosyası içinde belirtilen rapor türü için tanımlı döndürür *reportType*. Geçersiz bir değer geçtiyse *reportType*, bu işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlevi döndürür **_CRTDBG_HFILE_ERROR**. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_CrtSetReportFile** ile kullanılan [_CrtSetReportMode](crtsetreportmode.md) hedef veya tarafından oluşturulan belirli bir rapor türü için hedefleri tanımlamak için işlevi **_CrtDbgReport**. Zaman **_CrtSetReportMode** atamak için adlı **_CRTDBG_MODE_FILE** belirli bir rapor türü için modu raporlama **_CrtSetReportFile** için çağrılmalıdır belirli dosya ya da hedef olarak kullanmak için akış tanımlayın. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtSetReportFile** ön işleme sırasında kaldırılır.

Aşağıdaki liste için kullanılabilir seçenekleri gösterir *reportFile* ve sonuçta elde edilen davranışını **_CrtDbgReport**. Bu seçenekler Crtdbg.h bit bayrakları olarak tanımlanır.

- **dosya tanıtıcısı**

   İletileri için hedef olacaktır dosyası için bir tanıtıcı. Tanıtıcı geçerliliğini doğrulamak için girişimde bulunulmaz. Açın ve dosyanın tanıtıcısını kapatın. Örneğin:

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

   Yazma iletiye **stderr**, hangi yeniden yönlendirilen gibi:

   ```C
   freopen( "c:\\log2.txt", "w", stderr);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);

   _RPT0(_CRT_ERROR,"1st message\n");
   ```

- **_CRTDBG_FILE_STDOUT**

   Yazma iletiye **stdout**, hangi yeniden yönlendirebilirsiniz.

- **_CRTDBG_REPORT_FILE**

   Geçerli rapor modu döndürür.

Her rapor türü tarafından kullanılan rapor dosyası ayrı olarak denetlenebilir. Örneğin, belirtmek olası bir *reportType* , **_CRT_ERROR** bildirilen **stderr**, sırada bir *reportType* ,**_CRT_ASSERT** için bir kullanıcı tanımlı dosya tanıtıcısı veya akış bildirdi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<crtdbg.h >|\<errno.h >|

Konsol Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsol ile ilişkili standart akış tanıtıcıları **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri UWP uygulamalarında kullanabilmek için önce yeniden yönlendirilmesi gerekiyor . Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** hata ayıklama sürümleri [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
