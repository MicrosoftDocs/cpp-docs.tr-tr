---
title: _purecall
ms.date: 4/2/2020
api_name:
- _purecall
- _o__purecall
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- purecall
- _purecall
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
ms.openlocfilehash: f841bc70a4a5365bb9cc6086dd752bd2a1b583ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338482"
---
# <a name="_purecall"></a>_purecall

Varsayılan saf sanal işlev çağrı hata işleyicisi. Derleyici, saf bir sanal üye işlev çağrıldığında bu işlevi çağırmak için kod oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>Açıklamalar

**_purecall** işlevi, Microsoft C++ derleyicisinin Microsoft'a özgü bir uygulama ayrıntısıdır. Bu işlev, doğrudan kodunuz tarafından çağrılması amaçlanmamıştır ve ortak üstbilgi bildirimi yoktur. C Runtime Kitaplığı'nın genel dışa aktarDığı için burada belgelenmiştir.

Hiçbir uygulama olduğundan saf sanal işleviçin bir çağrı bir hatadır. Derleyici, saf bir sanal işlev çağrıldığında **_purecall** hata işleyicisi işlevini çağırmak için kod oluşturur. Varsayılan olarak, **_purecall** programı sonlandırır. Sonlandırmadan önce, **_purecall** işlevi işlem için ayarlanmışsa **_purecall_handler** bir işlev çağırır. Hata ayıklama veya raporlama amacıyla bunları yakalamak için saf sanal işlev çağrıları için kendi hata işleyicisi işlevi yükleyebilirsiniz. Kendi hata işleyicinizi kullanmak **için, _purecall_handler** imzasına sahip bir işlev oluşturun ve ardından geçerli işleyici yapmak için [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

**_purecall** işlevinin üstbilgi bildirimi yoktur. **_purecall_handler** typedef \<stdlib.h> tanımlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler, _set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
