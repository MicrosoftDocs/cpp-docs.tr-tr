---
title: _seh_filter_dll, _seh_filter_exe
ms.date: 4/2/2020
api_name:
- _XcptFilter
- _seh_filter_dll
- _seh_filter_exe
- _o__seh_filter_dll
- _o__seh_filter_exe
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
- XcptFilter
- _XcptFilter
- _seh_filter_dll
- _seh_filter_exe
- corecrt_startup/_seh_filter_exe
- corecrt_startup/_seh_filter_dll
helpviewer_keywords:
- XcptFilter function
- _XcptFilter function
- _seh_filter_dll function
- _seh_filter_exe function
ms.assetid: 747e5963-3a12-4bf5-b5c4-d4c1b6068e15
ms.openlocfilehash: bf92ea52c2614eb133bcd1ec820a386d1f38e8f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337951"
---
# <a name="_seh_filter_dll-_seh_filter_exe"></a>_seh_filter_dll, _seh_filter_exe

İstisnayı ve alınacak ilgili eylemi tanımlar.

## <a name="syntax"></a>Sözdizimi

```C
int __cdecl _seh_filter_dll(
   unsigned long _ExceptionNum,
   struct _EXCEPTION_POINTERS* _ExceptionPtr
);
int __cdecl _seh_filter_exe(
   unsigned long _ExceptionNum,
   struct _EXCEPTION_POINTERS* _ExceptionPtr
);
```

### <a name="parameters"></a>Parametreler

*_ExceptionNum*<br/>
Özel durum tanımlayıcısı.

*_ExceptionPtr*<br/>
Özel durum bilgileri için bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Özel durum işleme sonucuna bağlı olarak yapılacak eylemi gösteren bir sonsayı.

## <a name="remarks"></a>Açıklamalar

Bu yöntemler, [try-except Deyimi'nin](../../cpp/try-except-statement.md)özel durum filtresi ifadesi ile çağrılır. Yöntem, özel durumu tanımlamak ve burada gösterildiği gibi uygun eylemi belirlemek için sabit bir iç tabloya başvurur. Özel durum numaraları winnt.h'de tanımlanır ve sinyal numaraları signal.h'de tanımlanır.

|Özel Durum Numarası (imzasız uzun)|Sinyal Numarası|
|----------------------------------------|-------------------|
|STATUS_ACCESS_VIOLATION|SIGSEGV|
|STATUS_ILLEGAL_INSTRUCTION|SIGILL|
|STATUS_PRIVILEGED_INSTRUCTION|SIGILL|
|STATUS_FLOAT_DENORMAL_OPERAND|SIGFPE|
|STATUS_FLOAT_DIVIDE_BY_ZERO|SIGFPE|
|STATUS_FLOAT_INEXACT_RESULT|SIGFPE|
|STATUS_FLOAT_INVALID_OPERATION|SIGFPE|
|STATUS_FLOAT_OVERFLOW|SIGFPE|
|STATUS_FLOAT_STACK_CHECK|SIGFPE|
|STATUS_FLOAT_UNDERFLOW|SIGFPE|

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corecrt_startup.h

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
