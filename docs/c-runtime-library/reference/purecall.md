---
title: _purecall
ms.date: 11/04/2016
apiname:
- _purecall
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
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- purecall
- _purecall
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
ms.openlocfilehash: a7a6db42dc4b8d9b2962a66c7866aae9db55eb3b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541197"
---
# <a name="purecall"></a>_purecall

Varsayılan saf sanal işlev çağrısı hata işleyicisi. Derleyici bir saf sanal üye işlevi çağrıldığında bu işlevi çağırmak için kod oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>Açıklamalar

**_Purecall** işlev, Microsoft Visual C++ derleyicisi, Microsoft'a özgü bir uygulama ayrıntısı. Bu işlev kodunuz tarafından doğrudan çağrılması amaçlanmamıştır ve hiçbir ortak üstbilgi bildirimi sahiptir. C çalışma zamanı kitaplığı, ortak bir dışarı aktarma olduğundan burada belgelenmektedir.

Uygulaması olduğundan saf sanal işlev çağrısı bir hata var. Derleyici çağırmak için kod oluşturur **_purecall** saf sanal işlevi çağrıldığında hata işleyicisi işlevi. Varsayılan olarak, **_purecall** programını sonlandırır. Sonlandırma önce **_purecall** işlevi çağıran bir **_purecall_handler** bir işlem için ayarlanmışsa işlev. Hata ayıklama veya raporlama amacıyla bunları yakalamak için saf sanal işlev çağrıları, kendi hata işleyici işlevi yükleyebilirsiniz. Kendi hata işleyicisi kullanacak şekilde sahip bir işlev oluşturma **_purecall_handler** imzası, ardından [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) geçerli işleyici yapma.

## <a name="requirements"></a>Gereksinimler

**_Purecall** işlevi bir üst bilgi bildirimi yok. **_Purecall_handler** typedef tanımlanmış \<stdlib.h >.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler, _set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
