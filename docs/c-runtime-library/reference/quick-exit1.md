---
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
ms.openlocfilehash: 86246ed7a32dcd2f12b38aa4148570fc5fb3b7a6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949683"
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

*status*<br/>
Ana bilgisayar ortamına döndürülecek durum kodu.

## <a name="return-value"></a>Dönüş Değeri

**Quick_exit** işlevi, çağırana geri dönemeyebilir.

## <a name="remarks"></a>Açıklamalar

**Quick_exit** işlevi normal program sonlandırmasına neden olur. Bu, **sinyal** işlevi tarafından kaydedilen **atexit**, **_onexit** veya Signal işleyicileri tarafından kaydedilen hiçbir işlev çağırmayın. **Quick_exit** birden çok kez çağrılırsa veya **Çıkış** işlevi de çağrılırsa, davranış tanımsızdır.

**Quick_exit** işlevi, işlev kaydedildiğinde zaten çağrılan işlevler hariç, **at_quick_exit**tarafından kaydedilen işlevleri, son gelen ilk çıkar (LIFO) sırasına göre çağırır.  İşlev çağrısını sonlandıran kayıtlı bir işleve yapılan çağrı sırasında bir [longjmp](longjmp.md) çağrısı yapılırsa, davranış tanımsızdır.

Kayıtlı işlevler çağrıldıktan sonra, **quick_exit** , ana bilgisayar ortamına denetim döndürmek için *durum* değerini kullanarak **_exit** 'i çağırır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**quick_exit**|\<Process. h > veya \<Stdlib. h >|

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
