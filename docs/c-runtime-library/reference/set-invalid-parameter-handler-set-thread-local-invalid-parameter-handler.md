---
title: _set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler
ms.date: 4/2/2020
api_name:
- _set_invalid_parameter_handler
- _set_thread_local_invalid_parameter_handler
- _o__set_invalid_parameter_handler
- _o__set_thread_local_invalid_parameter_handler
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 0637937d4596d28875c40efec62f79a32f533dcf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337675"
---
# <a name="_set_invalid_parameter_handler-_set_thread_local_invalid_parameter_handler"></a>_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler

CRT geçersiz bir bağımsız değişken algıladığında çağrılacak bir işlev ayarlar.

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

*pYeni*<br/>
Yeni geçersiz parametre işleyicisi için işlev işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Aramadan önce geçersiz parametre işleyicisi için bir işaretçi.

## <a name="remarks"></a>Açıklamalar

Birçok C çalışma zamanı işlevi, kendilerine geçen bağımsız değişkenlerin geçerliliğini denetler. Geçersiz bir bağımsız değişken geçirilirse, işlev **hatalı** hata numarasını ayarlayabilir veya bir hata kodu döndürebilir. Bu gibi durumlarda, geçersiz parametre işleyicisi de çağrılır. C çalışma zamanı, programı sonlandıran ve çalışma zamanı hata iletisi görüntüleyen varsayılan genel geçersiz parametre işleyicisi sağlar. **_set_invalid_parameter_handler,** kendi işlevinizi geçersiz parametre işleyicisi olarak ayarlamak için kullanabilirsiniz. C çalışma zamanı, iş parçacığı yerel geçersiz parametre işleyicisini de destekler. İş parçacığı yerel parametre **işleyicisi _set_thread_local_invalid_parameter_handler**kullanılarak bir iş parçacığı ayarlanırsa, iş parçacığı çağrılan C çalışma zamanı işlevleri, genel işleyici yerine bu işleyiciyi kullanır. Aynı anda yalnızca bir işlev geçersiz bağımsız değişken işleyicisi olarak belirtilebilir. İş parçacığı başına iş parçacığı yerel geçersiz bağımsız değişken işleyicisi olarak yalnızca bir işlev belirtilebilir, ancak farklı iş parçacıkları farklı iş parçacığı yerel işleyicileri olabilir. Bu, diğer iş parçacıklarının davranışını etkilemeden kodunuzu bir bölümünde kullanılan işleyiciyi değiştirmenize olanak tanır.

Çalışma zamanı geçersiz parametre işlevini aradığında, genellikle kurtarılamayan bir hata oluştuğu anlamına gelir. Sağladığınız geçersiz parametre işleyicisi işlevi, kaydedebileceği verileri kaydetmeli ve sonra iptal etmelidir. Hatanın kurtarılabilir olduğundan emin değilseniz, denetimi ana işleve döndürmemelidir.

Geçersiz parametre işleyicisi işlevi aşağıdaki prototipe sahip olmalıdır:

```C
void _invalid_parameter(
   const wchar_t * expression,
   const wchar_t * function,
   const wchar_t * file,
   unsigned int line,
   uintptr_t pReserved
);
```

*İfade* bağımsız değişkeni, hatayı yükselten bağımsız değişken ifadesinin geniş bir dize gösterimidir. *İşlev* bağımsız değişkeni, geçersiz bağımsız değişkeni alan CRT işlevinin adıdır. *Dosya* bağımsız değişkeni, işlevi içeren CRT kaynak dosyasının adıdır. *Satır* bağımsız değişkeni, o dosyadaki satır numarasıdır. Son bağımsız değişken ayrılmıştır. CRT kitaplığın hata ayıklama sürümü kullanılmadığı sürece parametrelerin tümü **NULL** değerine sahiptir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_invalid_parameter_handler**, **_set_thread_local_invalid_parameter_handler**|C: \<stdlib.h><br /><br /> C++: \<cstdlib \<> veya stdlib.h>|

**_set_invalid_parameter_handler** ve **_set_thread_local_invalid_parameter_handler** işlevleri Microsoft'a özgüdir. Uyumluluk bilgileri için [bkz.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Aşağıdaki örnekte, geçersiz parametre hata işleyicisi, geçersiz parametreyi ve dosyayı ve satırı CRT kaynaklarında alan işlevi yazdırmak için kullanılır. Hata ayıklama CRT kitaplığı kullanıldığında, geçersiz parametre hataları da [_CrtSetReportMode](crtsetreportmode.md)kullanarak bu örnekte devre dışı bırakılan bir iddia yı gündeme getiriyor.

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
[CRT Fonksiyonlarının Güvenlikle Geliştirilmiş Sürümleri](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
