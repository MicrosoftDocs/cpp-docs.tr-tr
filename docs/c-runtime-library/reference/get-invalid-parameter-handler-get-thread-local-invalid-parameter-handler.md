---
description: 'Hakkında daha fazla bilgi edinin: _get_invalid_parameter_handler _get_thread_local_invalid_parameter_handler'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: ecb39588ea2776d661f391596d3f482628eddd7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213383"
---
# <a name="_get_invalid_parameter_handler-_get_thread_local_invalid_parameter_handler"></a>_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler

CRT geçersiz bir bağımsız değişken algıladığında çağrılan işlevi alır.

## <a name="syntax"></a>Syntax

```C
_invalid_parameter_handler _get_invalid_parameter_handler(void);
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);
```

## <a name="return-value"></a>Dönüş Değeri

Şu anda ayarlanmış geçersiz parametre işleyicisi işlevine veya hiçbiri ayarlanmamışsa boş bir işaretçiye yönelik bir işaretçi.

## <a name="remarks"></a>Açıklamalar

**_Get_invalid_parameter_handler** işlevi şu anda ayarlanmış olan genel geçersiz parametre işleyicisini alır. Genel geçersiz parametre işleyicisi ayarlanmamışsa null bir işaretçi döndürür. Benzer şekilde, **_get_thread_local_invalid_parameter_handler** , geçerli iş parçacığı yerel geçersiz parametre işleyicisini üzerinde çağrıldığı iş parçacığının veya hiçbir işleyici ayarlanmamışsa boş bir işaretçi alır. Genel ve iş parçacığı yerel geçersiz parametre işleyicilerini ayarlama hakkında daha fazla bilgi için bkz. [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).

Döndürülen geçersiz parametre işleyici işlev işaretçisi şu türe sahip:

```C
typedef void (__cdecl* _invalid_parameter_handler)(
    wchar_t const*,
    wchar_t const*,
    wchar_t const*,
    unsigned int,
    uintptr_t
    );
```

Geçersiz parametre işleyicisi hakkında daha fazla bilgi için, [_set_invalid_parameter_handler _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)prototipi konusuna bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_invalid_parameter_handler**, **_get_thread_local_invalid_parameter_handler**|, \<stdlib.h><br /><br /> C++: \<cstdlib> veya \<stdlib.h>|

**_Get_invalid_parameter_handler** ve **_get_thread_local_invalid_parameter_handler** işlevleri Microsoft 'a özgüdür. Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[CRT Işlevlerinin gelişmiş güvenlik sürümleri](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
