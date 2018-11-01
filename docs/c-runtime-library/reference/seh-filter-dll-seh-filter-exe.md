---
title: _seh_filter_dll, _seh_filter_exe
ms.date: 11/04/2016
apiname:
- _XcptFilter
- _seh_filter_dll
- _seh_filter_exe
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
ms.openlocfilehash: 51d6a21b3867eb830a7d9f9b4b9b0ac844cd5aa1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573043"
---
# <a name="sehfilterdll-sehfilterexe"></a>_seh_filter_dll, _seh_filter_exe

Özel durum ve gerçekleştirilecek ilgili eylemi tanımlar.

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
Özel durum bilgilerini bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Özel durum işleme sonucuna göre alınacak, eylemin gösteren bir tamsayı.

## <a name="remarks"></a>Açıklamalar

Bu yöntemler tarafından özel durum filtresi ifadesi olarak adlandırılan [deneyin-except deyimi](../../cpp/try-except-statement.md). Yöntemi, burada gösterildiği gibi özel durumu tanımlamak ve uygun eylemi belirlemek için sabit bir iç tablo danışır. Özel durum sayıları winnt.h içinde tanımlanmıştır ve sinyal sayıları sıgnal.h'de tanımlanır.

|Özel durum numarasını (işaretsiz uzun)|Sinyal sayısı|
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

## <a name="requirements"></a>Gereksinimler

**Başlık:** corecrt_startup.h

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
