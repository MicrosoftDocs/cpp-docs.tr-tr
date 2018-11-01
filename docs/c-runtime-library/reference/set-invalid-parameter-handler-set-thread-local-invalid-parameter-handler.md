---
title: _set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler
ms.date: 11/04/2016
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
helpviewer_keywords:
- invalid parameter handler
- set_invalid_parameter_handler function
- _set_invalid_parameter_handler function
- _set_thread_local_invalid_parameter_handler function
ms.assetid: c0e67934-1a41-4016-ad8e-972828f3ac11
ms.openlocfilehash: 1df876d6df9327e817d5d2c401e0abe97ad7a548
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617041"
---
# <a name="setinvalidparameterhandler-setthreadlocalinvalidparameterhandler"></a>_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler

Geçersiz bağımsız değişken CRT algıladığında çağrılacak bir işlev ayarlar.

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
Yeni geçersiz parametre işleyicisi işlevi işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Geçersiz parametre işleyicisi çağırmadan önce bir işaretçi.

## <a name="remarks"></a>Açıklamalar

Çok sayıda C çalışma zamanı işlevleri bunları geçirilen bağımsız değişkenler geçerliliğini denetleyin. Geçersiz bağımsız değişken geçirilmezse, işlev ayarlayabilirsiniz **errno** hata numarasını ya da bir hata kodu döndürür. Böyle durumlarda da geçersiz parametre işleyicisi çağrılır. C çalışma zamanı program sona erer ve bir çalışma zamanı hata iletisini görüntüleyen bir varsayılan genel geçersiz parametre işleyicisi sağlar. Kullanabileceğiniz **_set_invalid_parameter_handler** kendi işlevi genel geçersiz parametre işleyicisi ayarlanacak. C çalışma zamanı, bir iş parçacığı-yerel geçersiz parametre işleyicisini de destekler. Bir iş parçacığı-yerel parametresini işleyicisi kullanarak bir iş parçacığında ayarlanıp ayarlanmadığını **_set_thread_local_invalid_parameter_handler**, iş parçacığından çağrıldığından C çalışma zamanı işlevleri yerine genel işleyici işleyicisinin kullanın. Yalnızca bir işlev, aynı anda genel geçersiz bağımsız değişken işleyici olarak belirtilebilir. Yalnızca tek bir işlevi, iş parçacığı başına iş parçacığı-yerel geçersiz bağımsız değişken işleyici olarak belirtilebilir, ancak farklı iş parçacıkları farklı iş parçacığı-yerel işleyiciler olabilir. Bu, diğer iş parçacıklarını davranışını etkilemeden, kodunuzun bir bölümünde kullanılan işleyici değiştirmenize olanak sağlar.

Çalışma zamanı geçersiz parametre işlevini çağırdığında, bu genellikle kurtarılamayan bir hata oluştuğunu anlamına gelir. Sağladığınız geçersiz parametre işleyici işlevi kullanabilirsiniz ve ardından iptal herhangi bir veri kaydetmeniz gerekir. Hata kurtarılabilir olduğundan emin olmadığınız sürece ana işlevine denetim döndürmemelidir.

Geçersiz parametre işleyici işlevi aşağıdaki prototipe sahip olmalıdır:

```C
void _invalid_parameter(
   const wchar_t * expression,
   const wchar_t * function,
   const wchar_t * file,
   unsigned int line,
   uintptr_t pReserved
);
```

*İfade* bağımsız değişkeni olan bir hata harekete geçirilen bağımsız değişken ifadesi geniş dize gösterimi. *İşlevi* bağımsız değişkeni geçersiz bağımsız değişken alan bir CRT işlevini adıdır. *Dosya* bağımsız değişken işlev içeren CRT kaynak dosyasının adıdır. *Satırı* bağımsız değişken ise bu dosyadaki satır numarası. Son bağımsız değişken ayrılmıştır. Tüm parametre değerine sahip **NULL** CRT kitaplığı hata ayıklama sürümü kullanılmıyorsa.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_invalid_parameter_handler**, **_set_thread_local_invalid_parameter_handler**|C: \<stdlib.h ><br /><br /> C++: \<cstdlib > veya \<stdlib.h >|

**_Set_invalid_parameter_handler** ve **_set_thread_local_invalid_parameter_handler** Microsoft'a özgü işlevlerdir. Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Aşağıdaki örnekte, geçersiz parametre işleyicisi, geçersiz bir parametre ve dosya ve satır CRT kaynaklarında alınan işlevi yazdırmak için kullanılır. Hata ayıklama CRT Kitaplığı kullanıldığında, geçersiz parametre hataları ayrıca bu örnek kullanılarak devre dışı bırakılmış bir onaylama yükseltmek [_CrtSetReportMode](crtsetreportmode.md).

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
