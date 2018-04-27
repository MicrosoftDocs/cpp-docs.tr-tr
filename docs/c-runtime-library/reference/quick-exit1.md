---
title: quick_exit1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fde06fc83b27b8bba43e3fa929cc8b97bb68dd06
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
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
Ana bilgisayar ortamına geçirmek için durum kodu.

## <a name="return-value"></a>Dönüş Değeri

**Quick_exit** işlevi çağırıcısına döndüremiyor.

## <a name="remarks"></a>Açıklamalar

**Quick_exit** işlevi normal program sonlandırma neden olur. Tarafından kaydedilen hiçbir işlevleri çağıran **atexit**, **_onexit** veya sinyal tarafından kaydedilen işleyicileri **sinyal** işlevi. Davranış ise tanımsız **quick_exit** birden çok kez veya yoksa adlı **çıkmak** işlevi olarak da adlandırılır.

**Quick_exit** işlev çağrısı, son giren ilk çıkar (LIFO) sırası, tarafından kaydedilen işlevleri **at_quick_exit**, zaten çağrılır bu işlevler için işlev kayıtlı dışında.  Davranış ise tanımlanmamış bir [longjmp](longjmp.md) işlevi çağrısında sonlandırmak kayıtlı bir işlevi çağrısı sırasında çağrı yapılır.

Kayıtlı işlevleri çağrıldıktan sonra **quick_exit** çağırır **_Exit** kullanarak *durum* denetimi konak ortamına geçirmek için değer.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**quick_exit**|\<Process.h > veya \<stdlib.h >|

Uyumluluğu hakkında daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
