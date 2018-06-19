---
title: _set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_invalid_parameter_handler
- _set_thread_local_invalid_parameter_handler
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_invalid_parameter_handler
- _set_invalid_parameter_handler
- _set_thread_local_invalid_parameter_handler
dev_langs:
- C++
helpviewer_keywords:
- invalid parameter handler
- set_invalid_parameter_handler function
- _set_invalid_parameter_handler function
- _set_thread_local_invalid_parameter_handler function
ms.assetid: c0e67934-1a41-4016-ad8e-972828f3ac11
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4808367c94ec6c869c7f3bcafd2965a317553a6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407609"
---
# <a name="setinvalidparameterhandler-setthreadlocalinvalidparameterhandler"></a>_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler

CRT geçersiz bağımsız değişken algıladığında çağrılacak işlev ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
_invalid_parameter_handler _set_invalid_parameter_handler(
   _invalid_parameter_handler pNew
);
_invalid_parameter_handler _set_thread_local_invalid_parameter_handler(
   _invalid_parameter_handler pNew
);
```

### <a name="parameters"></a>Parametreler

*pNew*<br/>
Yeni geçersiz parametre işleyicisi işlev işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Geçersiz parametre işleyicisi çağırmadan önce bir işaretçi.

## <a name="remarks"></a>Açıklamalar

Birçok C çalışma zamanı işlevleri kendisine geçirilen bağımsız değişken geçerliliğini denetleyin. Geçersiz bağımsız değişken aktarılırsa işlevi ayarlayabilirsiniz **errno** hata numarası veya return bir hata kodu. Böyle durumlarda, geçersiz parametre işleyicisi de denir. C çalışma zamanı program sonlandırır ve bir çalışma zamanı hata iletisi görüntüler varsayılan genel geçersiz parametre işleyicisi sağlar. Kullanabileceğiniz **_set_invalid_parameter_handler** kendi işlevi genel geçersiz parametre işleyicisi olarak ayarlamak için. C çalışma zamanı da bir iş parçacığı yerel geçersiz parametre işleyicisi destekler. Bir iş parçacığı yerel parametre işleyicisi kullanarak bir iş parçacığında ayarlanırsa **_set_thread_local_invalid_parameter_handler**, iş parçacığından adlı C çalışma zamanı işlevleri yerine genel işleyici işleyicisinin kullanın. Yalnızca bir işlevi genel geçersiz bağımsız değişken işleyici aynı anda belirtilebilir. İş parçacığı başına iş parçacığı yerel geçersiz bağımsız değişken işleyici olarak yalnızca bir işlevi belirtilebilir ancak farklı iş parçacıklarındaki farklı iş parçacığı yerel işleyicileri sahip olabilir. Kodunuzu bir bölümünü başka bir iş parçacığı davranışını etkilemeden kullanılan işleyicisi değiştirmenize izin verir.

Çalışma zamanı geçersiz parametre işlevi aradığında, genellikle kurtarılamayan bir hata oluştuğunu anlamına gelir. Sağladığınız geçersiz parametre işleyicisi işlevi olabilir ve daha sonra iptal herhangi bir veri kaydetmeniz gerekir. Hata kurtarılabilir olduğundan emin olmadığınız sürece main işlevi denetim vermemelidir.

Geçersiz parametre işleyicisi işlevi aşağıdaki prototipe olması gerekir:

```C
void _invalid_parameter(
   const wchar_t * expression,
   const wchar_t * function,
   const wchar_t * file,
   unsigned int line,
   uintptr_t pReserved
);
```

*İfade* bağımsız değişkeni olan bir hataya neden bağımsız değişken ifadesi geniş dize gösterimi. *İşlevi* bağımsız değişkeni geçersiz bağımsız değişken alınan CRT işlevi adıdır. *Dosya* bağımsız değişkeni işlevi içeren CRT kaynak dosya adıdır. *Satır* bağımsız değişkeni, bu dosyada satır numarasıdır. Son bağımsız değişken ayrılmıştır. Tüm parametreler değere sahip **NULL** CRT kitaplık hata ayıklama sürümü kullanılmadığı sürece.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_invalid_parameter_handler**, **_set_thread_local_invalid_parameter_handler**|C: \<stdlib.h ><br /><br /> C++: \<cstdlib > veya \<stdlib.h >|

**_Set_invalid_parameter_handler** ve **_set_thread_local_invalid_parameter_handler** Microsoft belirli işlevlerdir. Uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Aşağıdaki örnekte, bir geçersiz parametre hata işleyicisine geçersiz bir parametre ve dosya ve satır CRT kaynaklarında alınan işlevi yazdırmak için kullanılır. CRT hata ayıklama Kitaplığı kullanıldığında, geçersiz bir parametre hataları da bu örneği kullanarak devre dışı bir onaylama Yükselt [_CrtSetReportMode](crtsetreportmode.md).

```C
// crt_set_invalid_parameter_handler.c
// compile with: /Zi /MTd
#include <stdio.h>
#include <stdlib.h>
#include <crtdbg.h>  // For _CrtSetReportMode

void myInvalidParameterHandler(const wchar_t* expression,
   const wchar_t* function,
   const wchar_t* file,
   unsigned int line,
   uintptr_t pReserved)
{
   wprintf(L"Invalid parameter detected in function %s."
            L" File: %s Line: %d\n", function, file, line);
   wprintf(L"Expression: %s\n", expression);
   abort();
}

int main( )
{
   char* formatString;

   _invalid_parameter_handler oldHandler, newHandler;
   newHandler = myInvalidParameterHandler;
   oldHandler = _set_invalid_parameter_handler(newHandler);

   // Disable the message box for assertions.
   _CrtSetReportMode(_CRT_ASSERT, 0);

   // Call printf_s with invalid parameters.

   formatString = NULL;
   printf(formatString);
}
```

```Output
Invalid parameter detected in function common_vfprintf. File: minkernel\crts\ucrt\src\appcrt\stdio\output.cpp Line: 32
Expression: format != nullptr
```

## <a name="see-also"></a>Ayrıca bkz.

[_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[CRT İşlevlerinin Gelişmiş Güvenlik Sürümleri](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
