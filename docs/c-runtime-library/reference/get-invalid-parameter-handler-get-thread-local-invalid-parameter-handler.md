---
title: _get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler
ms.date: 4/2/2020
api_name:
- _get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
- _o__get_invalid_parameter_handler
- _o__get_thread_local_invalid_parameter_handler
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_invalid_parameter_handler
- stdlib/_get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
- stdlib/_get_thread_local_invalid_parameter_handler
helpviewer_keywords:
- _get_thread_local_invalid_parameter_handler function
- _get_invalid_parameter_handler function
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
ms.openlocfilehash: 2465852b7bcc0251f218c68df14ff33930ad2378
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345069"
---
# <a name="_get_invalid_parameter_handler-_get_thread_local_invalid_parameter_handler"></a>_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler

CRT geçersiz bir bağımsız değişken algıladığında çağrılan işlevi alır.

## <a name="syntax"></a>Sözdizimi

```C
_invalid_parameter_handler _get_invalid_parameter_handler(void);
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);
```

## <a name="return-value"></a>Dönüş Değeri

Şu anda ayarlanmış geçersiz parametre işleyicisi işleviiçin bir işaretçi veya hiçbiri ayarlanmışsa null işaretçisi.

## <a name="remarks"></a>Açıklamalar

**_get_invalid_parameter_handler** işlevi, şu anda ayarlanmış genel geçersiz parametre işleyicisini alır. Genel geçersiz parametre işleyicisi ayarlı değilse, null işaretçisi döndürür. Benzer şekilde, **_get_thread_local_invalid_parameter_handler** çağrıldığı iş parçacığının geçerli yerel geçersiz parametre işleyicisini veya işleyici ayarlı değilse null işaretçisini alır. Genel ve iş parçacığı yerel geçersiz parametre işleyicileri ayarlamak hakkında bilgi için [bkz _set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler.](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)

Döndürülen geçersiz parametre işleyicisi işlev işaretçisi aşağıdaki türe sahiptir:

```C
typedef void (__cdecl* _invalid_parameter_handler)(
    wchar_t const*,
    wchar_t const*,
    wchar_t const*,
    unsigned int,
    uintptr_t
    );
```

Geçersiz parametre işleyicisi hakkında ayrıntılı bilgi için, [_set_thread_local_invalid_parameter_handler _set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)prototip bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_invalid_parameter_handler**, **_get_thread_local_invalid_parameter_handler**|C: \<stdlib.h><br /><br /> C++: \<cstdlib \<> veya stdlib.h>|

**_get_invalid_parameter_handler** ve **_get_thread_local_invalid_parameter_handler** işlevleri Microsoft'a özgüdir. Uyumluluk bilgileri için [bkz.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[CRT Fonksiyonlarının Güvenlikle Geliştirilmiş Sürümleri](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
