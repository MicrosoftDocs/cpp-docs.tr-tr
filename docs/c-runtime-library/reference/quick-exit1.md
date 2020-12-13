---
description: 'Hakkında daha fazla bilgi edinin: quick_exit'
title: quick_exit1
ms.date: 11/04/2016
api_name:
- quick_exit
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- quick_exit
- process/quick_exit
- stdlib/quick_exit
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
ms.openlocfilehash: 85640af902092d5cc60a1c718dfd8999c41406b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137104"
---
# <a name="quick_exit"></a>quick_exit

Normal program sonlandırmasının oluşmasına neden olur.

## <a name="syntax"></a>Sözdizimi

```C
__declspec(noreturn) void quick_exit(
    int status
);
```

### <a name="parameters"></a>Parametreler

*durumlarına*<br/>
Ana bilgisayar ortamına döndürülecek durum kodu.

## <a name="return-value"></a>Dönüş Değeri

**Quick_exit** işlevi çağırana geri döndürülemiyor.

## <a name="remarks"></a>Açıklamalar

**Quick_exit** işlevi normal program sonlandırmasına neden olur. **Sinyal** işlevi tarafından kaydedilen **_onexit** veya sinyal işleyicileri tarafından kaydedilmiş hiçbir işlev **çağırılmaz**. **Quick_exit** birden çok kez çağrılırsa veya **Çıkış** işlevi de çağrılırsa davranış tanımsızdır.

**Quick_exit** işlevi, işlev kaydedildiğinde zaten çağrılan işlevler hariç, **at_quick_exit** tarafından kaydedilen işlevleri, son gelen ilk çıkar (LIFO) sırasına göre çağırır.  İşlev çağrısını sonlandıran kayıtlı bir işleve yapılan çağrı sırasında bir [longjmp](longjmp.md) çağrısı yapılırsa, davranış tanımsızdır.

Kayıtlı işlevler çağrıldıktan sonra, denetimi konak ortamına döndürmek için *durum* değerini kullanarak **_exit** **quick_exit** .

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**quick_exit**|\<process.h> veya \<stdlib.h>|

Uyumluluk hakkında daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[durdur](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec Işlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn Işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
