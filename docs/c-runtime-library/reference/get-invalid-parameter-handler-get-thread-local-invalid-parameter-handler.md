---
title: _get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler
ms.date: 11/04/2016
api_name:
- _get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
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
- _get_invalid_parameter_handler
- stdlib/_get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
- stdlib/_get_thread_local_invalid_parameter_handler
helpviewer_keywords:
- _get_thread_local_invalid_parameter_handler function
- _get_invalid_parameter_handler function
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
ms.openlocfilehash: 534590fed77fe06149db892d98ba0e555297ac7c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955826"
---
# <a name="_get_invalid_parameter_handler-_get_thread_local_invalid_parameter_handler"></a>_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler

CRT geçersiz bir bağımsız değişken algıladığında çağrılan işlevi alır.

## <a name="syntax"></a>Sözdizimi

```C
_invalid_parameter_handler _get_invalid_parameter_handler(void);
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);
```

## <a name="return-value"></a>Dönüş Değeri

Şu anda ayarlanmış geçersiz parametre işleyicisi işlevine veya hiçbiri ayarlanmamışsa boş bir işaretçiye yönelik bir işaretçi.

## <a name="remarks"></a>Açıklamalar

**_Get_ınvalid_parameter_handler** işlevi şu anda ayarlanmış olan genel geçersiz parametre işleyicisini alır. Genel geçersiz parametre işleyicisi ayarlanmamışsa null bir işaretçi döndürür. Benzer şekilde, **_get_thread_local_invalid_parameter_handler** , geçerli iş parçacığı yerel geçersiz parametre işleyicisini üzerinde çağrıldığı iş parçacığının veya hiçbir işleyici ayarlanmamışsa boş bir işaretçi alır. Genel ve iş parçacığı yerel geçersiz parametre işleyicilerini ayarlama hakkında daha fazla bilgi için bkz. [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).

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

Geçersiz parametre işleyicisiyle ilgili ayrıntılar için, [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)içindeki prototipi inceleyin.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_ınvalid_parameter_handler**, **_get_thread_local_invalid_parameter_handler**|C: \<Stdlib. h ><br /><br /> C++: \<cstdlib > veya \<Stdlib. h >|

**_Get_ınvalid_parameter_handler** ve **_get_thread_local_invalid_parameter_handler** işlevleri Microsoft 'a özgüdür. Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[CRT İşlevlerinin Gelişmiş Güvenlik Sürümleri](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
