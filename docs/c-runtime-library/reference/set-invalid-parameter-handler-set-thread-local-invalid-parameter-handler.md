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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 404a865cceb5e4014969b15e9877761187af777b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914002"
---
# <a name="_set_invalid_parameter_handler-_set_thread_local_invalid_parameter_handler"></a>_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler

CRT geçersiz bir bağımsız değişken algıladığında çağrılacak işlevi ayarlar.

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
Yeni geçersiz parametre işleyicisine işlev işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Çağrıdan önce geçersiz parametre işleyicisine yönelik bir işaretçi.

## <a name="remarks"></a>Açıklamalar

Birçok C çalışma zamanı işlevi, kendisine geçirilen bağımsız değişkenlerin geçerliliğini denetler. Geçersiz bir bağımsız değişken geçirilmemişse, işlev **errno** hata numarasını ayarlayabilir veya bir hata kodu döndürebilir. Böyle durumlarda, geçersiz parametre işleyicisi de çağırılır. C çalışma zamanı, programı sonlandıran varsayılan bir genel geçersiz parametre işleyicisi sağlar ve bir çalışma zamanı hata iletisi görüntüler. Kendi işlevinizi genel geçersiz parametre işleyicisi olarak ayarlamak için **_set_invalid_parameter_handler** kullanabilirsiniz. C çalışma zamanı, iş parçacığı yerel geçersiz parametre işleyicisini de destekler. İş parçacığı yerel parametre işleyicisi **_set_thread_local_invalid_parameter_handler**kullanarak bir iş parçacığında ayarlandıysa, iş parçacığından çağrılan C çalışma zamanı işlevleri genel işleyici yerine bu işleyiciyi kullanır. Tek seferde genel geçersiz bağımsız değişken işleyicisi olarak yalnızca bir işlev belirtilebilir. İş parçacığı başına geçersiz iş parçacığı-yerel bağımsız değişken işleyicisi olarak yalnızca bir işlev belirtilebilir, ancak farklı iş parçacıkları farklı iş parçacığı yerel işleyicilerine sahip olabilir. Bu, diğer iş parçacıklarının davranışını etkilemeden kodunuzun bir bölümünde kullanılan işleyiciyi değiştirmenize olanak sağlar.

Çalışma zamanı geçersiz parametre işlevini çağırdığında, genellikle kurtarılabilir olmayan bir hata meydana gelir. Sağladığınız geçersiz parametre işleyici işlevi, bir bütün verileri kaydetmeli ve sonra iptal etmelidir. Hatanın kurtarılabilir olduğundan emin olmadığınız takdirde, denetimi Main işlevine döndürmemelidir.

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

*İfade* bağımsız değişkeni, hatayı oluşturan bağımsız değişken ifadesinin geniş bir dize gösterimidir. *İşlev* bağımsız değişkeni, geçersiz bağımsız DEĞIŞKENI alan CRT işlevinin adıdır. *Dosya* bağımsız değişkeni, IŞLEVINI içeren CRT kaynak dosyasının adıdır. *Satır* bağımsız değişkeni bu dosyadaki satır numarasıdır. Son bağımsız değişken ayrılmıştır. CRT kitaplığı hata ayıklama sürümü kullanılmadığı takdirde parametrelerin hepsi **null** değeri vardır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_invalid_parameter_handler**, **_set_thread_local_invalid_parameter_handler**|C: \<Stdlib. h><br /><br /> C++: \<cstdlib> veya \<stdlib. h>|

**_Set_invalid_parameter_handler** ve **_set_thread_local_invalid_parameter_handler** işlevleri Microsoft 'a özgüdür. Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Aşağıdaki örnekte, geçersiz parametreyi ve CRT kaynaklardaki dosyayı ve satırı alan işlevi yazdırmak için geçersiz bir parametre hata işleyicisi kullanılır. Hata ayıklama CRT kitaplığı kullanıldığında, geçersiz parametre hataları [_CrtSetReportMode](crtsetreportmode.md)kullanarak bu örnekte devre dışı bırakılmış bir onaylama işlemi de yükseltir.

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
[CRT Işlevlerinin gelişmiş güvenlik sürümleri](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
