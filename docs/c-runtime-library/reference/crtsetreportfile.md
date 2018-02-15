---
title: _CrtSetReportFile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a97e3f856dae60eeae9b96f3d5b422f8a262c68a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile
Kullandıktan sonra [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) belirtmek için `_CRTDBG_MODE_FILE`, ileti metnini almak için dosya tanıtıcısı belirtebilirsiniz. `_CrtSetReportFile` tarafından da kullanılan [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) metin (yalnızca hata ayıklama sürümü) hedef belirtmek için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_HFILE _CrtSetReportFile(   
   int reportType,  
   _HFILE reportFile   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `reportType`  
 Rapor türü: `_CRT_WARN`, `_CRT_ERROR`, ve `_CRT_ASSERT`.  
  
 `reportFile`  
 Yeni rapor dosyası için `reportType`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarıyla tamamlandığında, `_CrtSetReportFile` önceki rapor dosyası içinde belirtilen rapor türü için tanımlı döndürür `reportType`. Geçersiz bir değer geçtiyse `reportType`, bu işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevi döndürür `_CRTDBG_HFILE_ERROR`. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_CrtSetReportFile` ile birlikte kullanılan [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) hedef veya tarafından oluşturulan belirli bir rapor türü için hedefleri tanımlamak için işlevi `_CrtDbgReport`. Zaman `_CrtSetReportMode` atamak için adlı `_CRTDBG_MODE_FILE` belirli bir rapor türü için modu raporlama `_CrtSetReportFile` belirli dosya ya da hedef olarak kullanılacak akışı tanımlamak için çağrılmalıdır. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar `_CrtSetReportFile` ön işleme sırasında kaldırılır.  
  
 Aşağıdaki tabloda kullanılabilir seçenekler için bir listesini gösterir `reportFile` ve sonuçta elde edilen davranışını `_CrtDbgReport`. Bu seçenekler Crtdbg.h bit bayrakları olarak tanımlanır.  
  
 `file handle`  
 İletileri için hedef olacaktır dosyası için bir tanıtıcı. Tanıtıcı geçerliliğini doğrulamak için girişimde bulunulmaz. Açın ve dosyanın tanıtıcısını kapatın. Örneğin:  
  
```  
HANDLE hLogFile;  
hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,   
   FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,   
   FILE_ATTRIBUTE_NORMAL, NULL);  
_CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_WARN, hLogFile);  
  
_RPT0(_CRT_WARN,"file message\n");  
CloseHandle(hLogFile);  
```  
  
 `_CRTDBG_FILE_STDERR`  
 Yazma iletiye `stderr`, hangi yeniden yönlendirilen gibi:  
  
```  
freopen( "c:\\log2.txt", "w", stderr);  
_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);  
  
_RPT0(_CRT_ERROR,"1st message\n");  
```  
  
 `_CRTDBG_FILE_STDOUT`  
 Yazma iletiye `stdout`, hangi yeniden yönlendirebilirsiniz.  
  
 `_CRTDBG_REPORT_FILE`  
 Geçerli rapor modu döndürür.  
  
 Her rapor türü tarafından kullanılan rapor dosyası ayrı olarak denetlenebilir. Örneğin, belirtmek olası bir `reportType` , `_CRT_ERROR` bildirilen `stderr`, sırada bir `reportType` , `_CRT_ASSERT` bildirilen bir kullanıcı tanımlı dosya tanıtıcısı veya akış.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_CrtSetReportFile`|\<crtdbg.h>|\<errno.h >|  
  
 Konsol Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsol ile ilişkili standart akış tanıtıcıları —`stdin`, `stdout`, ve `stderr`— C çalışma zamanı işlevleri UWP uygulamalarında kullanabilmek için önce yeniden yönlendirilmesi gerekiyor. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
 **Kitaplıklar:** hata ayıklama sürümleri [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)