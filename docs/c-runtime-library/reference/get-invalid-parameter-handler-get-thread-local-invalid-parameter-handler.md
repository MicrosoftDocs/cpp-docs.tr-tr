---
title: _get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler
ms.date: 11/04/2016
apiname:
- _get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
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
- _get_invalid_parameter_handler
- stdlib/_get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
- stdlib/_get_thread_local_invalid_parameter_handler
helpviewer_keywords:
- _get_thread_local_invalid_parameter_handler function
- _get_invalid_parameter_handler function
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
ms.openlocfilehash: 7d1a87f9ade0845994918d5a4d59dc56e190d2b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623983"
---
# <a name="getinvalidparameterhandler-getthreadlocalinvalidparameterhandler"></a>_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler

Geçersiz bağımsız değişken CRT algıladığında, çağrılan işlevi alır.

## <a name="syntax"></a>Sözdizimi

```C
_invalid_parameter_handler _get_invalid_parameter_handler(void);
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);
```

## <a name="return-value"></a>Dönüş Değeri

Şu anda ayarlanmış bir işaretçiye geçersiz parametre işleyici işlevi ya da hiçbiri alındıysa null bir işaretçi.

## <a name="remarks"></a>Açıklamalar

**_Get_invalid_parameter_handler** işlevi alır ayarlanmış genel geçersiz parametre işleyicisi. Hiçbir genel geçersiz parametre işleyicisi ayarlarsanız null bir işaretçi döndürür. Benzer şekilde, **_get_thread_local_invalid_parameter_handler** işleyici yok ayarlandıysa, geçerli iş parçacığı-yerel geçersiz parametre işleyicisi iş parçacığı üzerinde çağırıldığında ya da null bir işaretçi alır. Genel ve yerel iş parçacığı geçersiz parametre işleyicisi ayarlama hakkında daha fazla bilgi için bkz: [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).

Döndürülen geçersiz parametre işleyicisi işlev işaretçisi, şu tür vardır:

```C
typedef void (__cdecl* _invalid_parameter_handler)(
    wchar_t const*,
    wchar_t const*,
    wchar_t const*,
    unsigned int,
    uintptr_t
    );
```

Geçersiz parametre işleyicisi hakkında daha fazla bilgi için bkz: prototip [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_invalid_parameter_handler**, **_get_thread_local_invalid_parameter_handler**|C: \<stdlib.h ><br /><br /> C++: \<cstdlib > veya \<stdlib.h >|

**_Get_invalid_parameter_handler** ve **_get_thread_local_invalid_parameter_handler** Microsoft'a özgü işlevlerdir. Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[CRT İşlevlerinin Gelişmiş Güvenlik Sürümleri](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
