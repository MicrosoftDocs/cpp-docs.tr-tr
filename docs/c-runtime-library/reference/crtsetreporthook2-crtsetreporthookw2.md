---
description: 'Hakkında daha fazla bilgi edinin: _CrtSetReportHook2 _CrtSetReportHookW2'
title: _CrtSetReportHook2, _CrtSetReportHookW2
ms.date: 11/04/2016
api_name:
- _CrtSetReportHook2
- _CrtSetReportHookW2
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
- CrtSetReportHookW2
- CrtSetReportHook2
- _CrtSetReportHookW2
- _CrtSetReportHook2
helpviewer_keywords:
- CrtSetReportHook2 function
- _CrtSetReportHook2 function
- _CrtSetReportHookW2 function
- CrtSetReportHookW2 function
ms.assetid: 12e5f68d-c8a7-4b1a-9a75-72ba4a8592d0
ms.openlocfilehash: eab1ad4da90d5a86b821c374aae0aeceb97d7518
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135726"
---
# <a name="_crtsetreporthook2-_crtsetreporthookw2"></a>_CrtSetReportHook2, _CrtSetReportHookW2

, C çalışma zamanı hata ayıklama raporlama işlemine (yalnızca hata ayıklama sürümü) bağlanarak, istemci tanımlı bir raporlama işlevini kurar veya kaldırır.

## <a name="syntax"></a>Sözdizimi

```C
int _CrtSetReportHook2(
   int mode,
   _CRT_REPORT_HOOK pfnNewHook
);
int _CrtSetReportHookW2(
   int mode,
   _CRT_REPORT_HOOKW pfnNewHook
);
```

### <a name="parameters"></a>Parametreler

*modundaysa*<br/>
Gerçekleştirilecek eylem: **_CRT_RPTHOOK_INSTALL** veya **_CRT_RPTHOOK_REMOVE**.

*pfnNewHook*<br/>
Bu işlevin dar karakter veya geniş karakter sürümünde yüklenmek veya kaldırmak için rapor kancası.

## <a name="return-value"></a>Dönüş Değeri

-1 **EINVAL** veya **ENOMEM** kümesi ile bir hata ile karşılaşılırsa; Aksi takdirde, çağrıdan sonra *pnewhook* başvuru sayısını döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtSetReportHook2** ve **_CrtSetReportHookW2** bir işlevi dönüştürmenizi veya geri almanızı sağlar, ancak [_CrtSetReportHook](crtsetreporthook.md) yalnızca bir işlevi barındırmanıza olanak tanır.

**_CrtSetReportHook2** veya **_CRTSETREPORTHOOKW2** , bir dll 'de kanca çağrısı yapıldığında ve birden çok dll yüklenip kendi kanca işlevlerini ayarlarken **_CrtSetReportHook** yerine kullanılmalıdır. Böyle bir durumda, dll 'Ler yüklenenden farklı bir sırayla kaldırılabilir ve kanca işlevi, yüklenmeyen bir DLL 'ye işaret ediyor olabilir. Kanca işlevleri **_CrtSetReportHook** ile eklendiyse, herhangi bir hata ayıklama çıkışı işlemi çöker.

**_CrtSetReportHook** ile eklenen tüm kanca işlevleri, **_CrtSetReportHook2** veya **_CrtSetReportHookW2** ile eklenen hiçbir kanca işlevi yoksa veya tüm kanca Işlevleri **_CrtSetReportHook2** ile eklenirse ve **_CrtSetReportHookW2** **false** döndürmesi durumunda çağrılır.

Bu işlevin geniş karakterli sürümü kullanılabilir. Rapor kancası işlevleri, türü (geniş veya dar karakterler) kullanılan bu işlevin sürümüyle eşleşmesi gereken bir dize alır. Bu işlevin geniş karakterli sürümüyle kullanılan rapor kancaları için aşağıdaki işlev prototipini kullanın:

```C
int YourReportHook( int reportType, wchar_t *message, int *returnValue );
```

Dar karakterli rapor kancaları için aşağıdaki prototipi kullanın:

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

Bu işlevler, parametrelerini doğrular. *Mode* veya **pfnNewNook** geçersiz Ise, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve-1 döndürür.

> [!NOTE]
> Uygulamanız **/clr** ile derlenirse ve raporlama işlevi uygulama Main 'den çıktıktan sonra çağrılırsa, raporlama işlevi HERHANGI bir CRT IŞLEVINI çağırırsa clr bir özel durum oluşturur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_CrtSetReportHook2**|\<crtdbg.h>|\<errno.h>|
|**_CrtSetReportHookW2**|\<crtdbg.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

```C
// crt_setreporthook2.c
#include <windows.h>
#include <stdio.h>
#include <crtdbg.h>
#include <assert.h>

int __cdecl TestHook1(int nReportType, char* szMsg, int* pnRet)
{
   int nRet = FALSE;

   printf("CRT report hook 1.\n");
   printf("CRT report type is \"");
   switch (nReportType)
   {
      case _CRT_ASSERT:
      {
         printf("_CRT_ASSERT");
         // nRet = TRUE;   // Always stop for this type of report
         break;
      }

      case _CRT_WARN:
      {
         printf("_CRT_WARN");
         break;
      }

      case _CRT_ERROR:
      {
         printf("_CRT_ERROR");
         break;
      }

      default:
      {
         printf("???Unknown???");
         break;
      }
   }

   printf("\".\nCRT report message is:\n\t");
   printf(szMsg);

   if   (pnRet)
      *pnRet = 0;

   return   nRet;
}

int __cdecl   TestHook2(int nReportType, char* szMsg, int* pnRet)
{
   int   nRet = FALSE;

   printf("CRT report hook 2.\n");
   printf("CRT report type is \"");
   switch   (nReportType)
   {
      case _CRT_WARN:
      {
         printf("_CRT_WARN");
         break;
      }

      case _CRT_ERROR:
      {
         printf("_CRT_ERROR");
         break;
      }

      case _CRT_ASSERT:
      {
         printf("_CRT_ASSERT");
         nRet = TRUE;   // Always stop for this type of report
         break;
      }

      default:
      {
         printf("???Unknown???");
         break;
      }
   }

   printf("\".\nCRT report message is: \t");
   printf(szMsg);

   if   (pnRet)
      *pnRet = 0;
   // printf("CRT report code is %d.\n", *pnRet);
   return   nRet;
}

int   main(int argc, char* argv[])
{
   int   nRet = 0;

   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1);
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1)"
          " returned %d\n", nRet);
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2);
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2)"
          " returned %d\n", nRet);
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2);
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2)"
          " returned %d\n", nRet);
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1);
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1)"
          " returned %d\n", nRet);
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1);
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1)"
          " returned %d\n", nRet);

   _ASSERT(0);

   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2);
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2)"
          " returned %d\n", nRet);
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2);
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2)"
          " returned %d\n", nRet);
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2);
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2)"
          " returned %d\n", nRet);
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1);
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1)"
          " returned %d\n", nRet);

   return   nRet;
}
```

### <a name="output"></a>Çıktı

```Output
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1) returned 0
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2) returned 0
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2) returned 0
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1) returned 0
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1) returned 0
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2) returned 0
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2) returned 0
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2) returned 0
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1) returned 0
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
