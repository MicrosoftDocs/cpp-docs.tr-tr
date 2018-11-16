---
title: _getdrives
ms.date: 11/04/2016
apiname:
- _getdrives
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- getdrives
- _getdrives
helpviewer_keywords:
- _getdrives function
- getdrives function
- disk drives
ms.assetid: 869bb51f-4209-4328-846e-3aadebaceb9c
ms.openlocfilehash: 444a54a316b1b1e4cfd26df95d172c7e9748fb88
ms.sourcegitcommit: d441305fb19131afbd7fc259d8cda63ea26f2343
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51678320"
---
# <a name="getdrives"></a>_getdrives

Şu anda kullanılabilir disk sürücüleri temsil eden bir bit maskesi döndürür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned long _getdrives( void );
```

## <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş şu anda kullanılabilir disk sürücüleri temsil eden bir bit maskesi değeridir. Bit konumu 0 (en az önemli bit) sürücüsü, bit konumu 1 sürücüdür B, bit konumu 2 C sürücüsü ve benzeri. İşlev başarısız olursa, dönüş değeri sıfırdır. Genişletilmiş hata bilgilerini almak için arama **GetLastError**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getdrives**|\<Direct.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_getdrives.c
// This program retrieves and lists out
// all the logical drives that are
// currently mounted on the machine.

#include <windows.h>
#include <direct.h>
#include <stdio.h>
#include <tchar.h>

TCHAR g_szDrvMsg[] = _T("A:\n");

int main(int argc, char* argv[]) {
   ULONG uDriveMask = _getdrives();

   if (uDriveMask == 0)
   {
      printf( "_getdrives() failed with failure code: %d\n",
              GetLastError());
   }
   else
   {
      printf("The following logical drives are being used:\n");

      while (uDriveMask) {
         if (uDriveMask & 1)
            printf(g_szDrvMsg);

         ++g_szDrvMsg[0];
         uDriveMask >>= 1;
      }
   }
}
```

```Output
The following logical drives are being used:
A:
C:
D:
E:
```

## <a name="see-also"></a>Ayrıca bkz.

[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
