---
title: _CrtSetReportHook2, _CrtSetReportHookW2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportHook2 function
- _CrtSetReportHook2 function
- _CrtSetReportHookW2 function
- CrtSetReportHookW2 function
ms.assetid: 12e5f68d-c8a7-4b1a-9a75-72ba4a8592d0
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e730df790da9584d7367564cbe7e07e3912b0b8c
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="crtsetreporthook2-crtsetreporthookw2"></a>_CrtSetReportHook2, _CrtSetReportHookW2

Yükler veya istemci tarafından tanımlanan raporlama işlevi C çalışma zamanı hata ayıklama raporlama işlemine (yalnızca hata ayıklama sürümü) takma tarafından kaldırır.

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
Yapılacak eylem: **_CRT_RPTHOOK_INSTALL** veya **_CRT_RPTHOOK_REMOVE**.

*pfnNewHook*<br/>
Kanca yüklemek veya bu işlevi dar karakter veya joker karakter sürümünde kaldırmak için rapor.

## <a name="return-value"></a>Dönüş Değeri

bir hatayla karşılaşıldı, -1 ile **EINVAL** veya **ENOMEM** başvuru sayısını döndürür; kümesi *pfnNewHook* çağrısından sonra.

## <a name="remarks"></a>Açıklamalar

**_CrtSetReportHook2** ve **_CrtSetReportHookW2** bağlayın veya bir işlev unhook ancak sağlar [_CrtSetReportHook](crtsetreporthook.md) yalnızca bir işlev bağlanmanıza olanak sağlar.

**_CrtSetReportHook2** veya **_CrtSetReportHookW2** yerine kullanılmalıdır **_CrtSetReportHook** kanca çağrı DLL'de yapılır ne zaman ve ne zaman birden çok DLL'ler yüklü olmayabilir ve kendi ayarlama kanca işlevleri. Böyle bir durumda DLL'leri farklı bir sırada yüklenen ve kaldırılmış bir DLL işaret eden kanca işlevini bırakılabilir çok bellekten. Kanca işlevlerini ile eklendiyse herhangi bir hata ayıklama çıktı işlem çökmesi **_CrtSetReportHook**.

Herhangi bir kanca ile eklenen işlevler **_CrtSetReportHook** eklenen işlevleri hiçbir kanca varsa adlı **_CrtSetReportHook2** veya **_CrtSetReportHookW2** veya tüm bağlayın ile eklenen işlevler **_CrtSetReportHook2** ve **_CrtSetReportHookW2** dönmek **FALSE**.

Bu işlev geniş karakter sürümü kullanılabilir. Kanca işlevlerini raporlama bir dize türü (geniş veya dar karakter) kullanılan bu işlev sürümü eşleşmelidir alın. Bu işlev geniş karakter sürümü ile kullanılan rapor kancaları için aşağıdaki işlev prototipi kullanın:

```C
int YourReportHook( int reportType, wchar_t *message, int *returnValue );
```

Aşağıdaki prototipe dar karakterlik rapor kancaları kullanın:

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

Bu işlevler kendi parametreleri doğrulayın. Varsa *modu* veya **pfnNewNook** olan geçersiz, bu işlevler geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür.

> [!NOTE]
> Uygulamanız ile derlenmiş ise **/CLR** ve uygulama çıkıldıktan sonra Raporlama işlevi ana çağrılır, Raporlama işlevini herhangi CRT işlevleri çağırırsa CLR bir özel durum oluşturur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_CrtSetReportHook2**|\<crtdbg.h >|\<errno.h >|
|**_CrtSetReportHookW2**|\<crtdbg.h >|\<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
