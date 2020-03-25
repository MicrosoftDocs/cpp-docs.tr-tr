---
title: __CxxFrameHandler
ms.date: 11/04/2016
api_name:
- __CxxFrameHandler
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __CxxFrameHandler
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
ms.openlocfilehash: db856850688e378cde9eaa1fb510cb325ce0644b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170988"
---
# <a name="__cxxframehandler"></a>__CxxFrameHandler

İç CRT işlevi. Yapılandırılmış özel durum çerçevelerini işlemek için CRT tarafından kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
EXCEPTION_DISPOSITION __CxxFrameHandler(
      EHExceptionRecord  *pExcept,
      EHRegistrationNode *pRN,
      void               *pContext,
      DispatcherContext  *pDC
   )
```

#### <a name="parameters"></a>Parametreler

*pExcept*<br/>
Olası `catch` deyimlerine geçirilen özel durum kaydı.

*pRN*<br/>
Özel durumu işlemek için kullanılan yığın çerçevesiyle ilgili dinamik bilgiler. Daha fazla bilgi için bkz. ehdata. h.

*pContext*<br/>
Bağlam. (Intel işlemcilerde kullanılmaz.)

*Kökündeki*<br/>
İşlev girişi ve yığın çerçevesi hakkında ek bilgiler.

## <a name="return-value"></a>Dönüş Değeri

[Try-except deyimi](../cpp/try-except-statement.md)tarafından kullanılan *filtre ifadesi* değerlerinden biri.

## <a name="remarks"></a>Açıklamalar

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__CxxFrameHandler|excpt. h, ehdata. h|
