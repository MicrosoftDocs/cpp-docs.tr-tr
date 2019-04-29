---
title: quick_exit1
ms.date: 11/04/2016
apiname:
- quick_exit
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
- quick_exit
- process/quick_exit
- stdlib/quick_exit
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
ms.openlocfilehash: 50f1ee72cce04c2bebc8f7396a2b6fad98301dd7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358042"
---
# <a name="quickexit"></a>quick_exit

Normal program sonlandırma oluşmasına neden olur.

## <a name="syntax"></a>Sözdizimi

```C
__declspec(noreturn) void quick_exit(
    int status
);
```

### <a name="parameters"></a>Parametreler

*Durumu*<br/>
Ana bilgisayar ortamının için döndürülecek durum kodu.

## <a name="return-value"></a>Dönüş Değeri

**Quick_exit** işlevi arayanına döndüremiyor.

## <a name="remarks"></a>Açıklamalar

**Quick_exit** işlevi normal program sonlandırma neden olur. Tarafından kaydedilen hiçbir işlevleri çağırır **atexit**, **_onexit** veya sinyal işleyicileri tarafından kaydedilen **sinyal** işlevi. Davranış olup tanımsız **quick_exit** birden çok kez veya varsa çağrılır **çıkmak** işlevi ayrıca çağrılır.

**Quick_exit** işlev çağrısı, son giren ilk çıkar (LIFO) sırası, kaydeden işlevleri **at_quick_exit**zaten çağrılır, bu işlevler için işlev kaydedildiği dışında.  Davranış olup tanımsız bir [longjmp](longjmp.md) işlevi çağrısı sonlanırdı kayıtlı bir işlev çağrısı sırasında çağrı yapılır.

Kayıtlı işlevleri çağrıldıktan sonra **quick_exit** çağırır **_Exit** kullanarak *durumu* denetimi için ana bilgisayar ortamının döndürülecek değer.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**quick_exit**|\<Process.h > veya \<stdlib.h >|

Uyumluluk hakkında daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
