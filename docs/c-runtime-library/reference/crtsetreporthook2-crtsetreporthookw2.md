---
title: _CrtSetReportHook2, _CrtSetReportHookW2
ms.date: 11/04/2016
apiname:
- _CrtSetReportHook2
- _CrtSetReportHookW2
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
ms.openlocfilehash: 1e850d3e83ed7b7c77873400deac073084708b78
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446780"
---
# <a name="crtsetreporthook2-crtsetreporthookw2"></a>_CrtSetReportHook2, _CrtSetReportHookW2

Yükler veya bir istemci tanımlı raporlama işlevi C çalışma zamanı hata ayıklama raporlama işlemine (yalnızca hata ayıklama sürümü) takma tarafından kaldırır.

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

*Modu*<br/>
Gerçekleştirilecek eylemi: **_CRT_RPTHOOK_INSTALL** veya **_CRT_RPTHOOK_REMOVE**.

*pfnNewHook*<br/>
Kanca yüklemek veya bu işlevi dar karakter veya geniş karakter sürümünü kaldırmak için rapor.

## <a name="return-value"></a>Dönüş Değeri

bir hatayla karşılaşıldı, -1 ile **EINVAL** veya **ENOMEM** Ayarla; Aksi takdirde başvuru sayımını döndürür *pfnNewHook* çağrısından sonra.

## <a name="remarks"></a>Açıklamalar

**_CrtSetReportHook2** ve **_CrtSetReportHookW2** kanca ya da bir işlev tutulabilir ancak izin [_CrtSetReportHook](crtsetreporthook.md) yalnızca bir işlev kanca olanak tanır.

**_CrtSetReportHook2** veya **_CrtSetReportHookW2** yerine kullanılması gereken **_CrtSetReportHook** DLL'de kanca çağrı yapılır zaman ve ne zaman birden çok DLL'leri yüklenebilir ve kendi ayarlama kanca işlevleri. Böyle bir durumda, DLL'leri farklı bir sırada bunlar yüklenmiş ve yüklenmemiş bir DLL işaret eden kanca işlevini bırakılabilir kaldırılıp. Kanca işlevlerini Raporlama ile eklendiyse, herhangi bir hata ayıklama çıktı işlem çökmesi **_CrtSetReportHook**.

Herhangi bir bağlama ile eklenen işlevler **_CrtSetReportHook** işlevleri ile eklenen hiçbir kanca varsa adlı **_CrtSetReportHook2** veya **_CrtSetReportHookW2** veya tüm bağlama ile eklenen işlevler **_CrtSetReportHook2** ve **_CrtSetReportHookW2** dönüş **FALSE**.

Bu işlev geniş karakter sürümü kullanılabilir. Kanca işlevlerini (geniş veya dar karakter) türü, bu işlev için kullanılan sürümle aynı olmalıdır, bir dize alır. Bu işlev geniş karakter sürümü ile kullanılan rapor kancaları için aşağıdaki işlev prototipi kullanın:

```C
int YourReportHook( int reportType, wchar_t *message, int *returnValue );
```

Aşağıdaki prototip, dar karakter rapor kancaları kullanın:

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

Bu işlevler kendi parametrelerini doğrular. Varsa *modu* veya **pfnNewNook** olduğundan geçersizse, bu işlevler geçersiz parametre işleyicisini açıklandığı gibi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür.

> [!NOTE]
> Uygulamanız ile derlenmişse **/CLR** ve uygulama çıkıldıktan sonra Raporlama işlevi ana çağrılır, herhangi bir CRT işlevleri Raporlama işlevini çağırırsa CLR bir özel durum oluşturur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_CrtSetReportHook2**|\<crtdbg.h >|\<errno.h >|
|**_CrtSetReportHookW2**|\<crtdbg.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

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

### <a name="output"></a>Çıkış

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

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
