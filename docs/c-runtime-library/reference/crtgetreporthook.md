---
description: 'Hakkında daha fazla bilgi edinin: _CrtGetReportHook'
title: _CrtGetReportHook
ms.date: 11/04/2016
api_name:
- _CrtGetReportHook
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
- CrtGetReportHook
- _CrtGetReportHook
helpviewer_keywords:
- CrtGetReportHook function
- _CrtGetReportHook function
ms.assetid: 922758ed-7edd-4359-9c92-0535192dc11a
ms.openlocfilehash: 9c950341e3f1b0231620449d983fcfe5bc0f5f12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319745"
---
# <a name="_crtgetreporthook"></a>_CrtGetReportHook

Hata ayıklama Raporlama işlemi için C çalışma zamanına dönüştürmek üzere istemci tanımlı raporlama işlevini alır (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Syntax

```C
_CRT_REPORT_HOOK _CrtGetReportHook( void );
```

## <a name="return-value"></a>Dönüş Değeri

İstemci tanımlı geçerli raporlama işlevini döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtGetReportHook** , bir uygulamanın C çalışma zamanı hata ayıklama kitaplığı Raporlama işlemi için geçerli raporlama işlevini almasına izin verir.

Diğer kanca özellikli çalışma zamanı işlevlerini kullanma ve kendi istemci tanımlı kanca işlevlerinizi yazma hakkında daha fazla bilgi için bkz. [hata ayıklama kanca Işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtGetReportHook**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

**_CrtSetReportHook** kullanmanın bir örneği için bkz. [Report](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/report).

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportHook](crtsetreporthook.md)<br/>
