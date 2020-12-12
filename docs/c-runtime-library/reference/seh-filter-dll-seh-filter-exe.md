---
description: 'Hakkında daha fazla bilgi edinin: _seh_filter_dll _seh_filter_exe'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: f1f297e0ace4a342dcc7370472c1ff1e9f409ce5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288938"
---
# <a name="_seh_filter_dll-_seh_filter_exe"></a>_seh_filter_dll, _seh_filter_exe

Özel durumu ve gerçekleştirilecek ilgili eylemi tanımlar.

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
Özel durum için tanımlayıcı.

*_ExceptionPtr*<br/>
Özel durum bilgisine yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Özel durum işlemenin sonucuna bağlı olarak gerçekleştirilecek eylemi belirten bir tamsayı.

## <a name="remarks"></a>Açıklamalar

Bu yöntemler, [try-except deyiminin](../../cpp/try-except-statement.md)özel durum filtresi ifadesi tarafından çağırılır. Yöntemi, özel durumu tanımlamak ve burada gösterildiği gibi uygun eylemi belirlemek için sabit bir iç tablo sağlar. Özel durum numaraları, Winnt. h içinde tanımlanır ve sinyal numaraları, Signal. h içinde tanımlanır.

|Özel durum numarası (imzasız Long)|Sinyal numarası|
|----------------------------------------|-------------------|
|STATUS_ACCESS_VIOLATION|SıGSEGV|
|STATUS_ILLEGAL_INSTRUCTION|SıGıLL|
|STATUS_PRIVILEGED_INSTRUCTION|SıGıLL|
|STATUS_FLOAT_DENORMAL_OPERAND|SıGFPE|
|STATUS_FLOAT_DIVIDE_BY_ZERO|SıGFPE|
|STATUS_FLOAT_INEXACT_RESULT|SıGFPE|
|STATUS_FLOAT_INVALID_OPERATION|SıGFPE|
|STATUS_FLOAT_OVERFLOW|SıGFPE|
|STATUS_FLOAT_STACK_CHECK|SıGFPE|
|STATUS_FLOAT_UNDERFLOW|SıGFPE|

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** corecrt_startup. h

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
