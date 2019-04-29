---
title: __CxxFrameHandler
ms.date: 11/04/2016
apiname:
- __CxxFrameHandler
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- __CxxFrameHandler
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
ms.openlocfilehash: d059df597826c68f4f51eb85f592b7eb44ac7d1f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344622"
---
# <a name="cxxframehandler"></a>__CxxFrameHandler

İç CRT işlevi. Yapılandırılmış özel durum çerçeveler işlemek için CRT tarafından kullanılır.

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
Olası için geçirilen özel durum kaydını `catch` deyimleri.

*pRN*<br/>
Özel durumu işlemek için kullanılan yığın çerçevesi hakkında dinamik bilgi sağlar. Daha fazla bilgi için ehdata.h bakın.

*pContext*<br/>
Bağlamı. (Intel işlemci üzerinde kullanılmıyor.)

*pDC*<br/>
İşlev giriş ve yığın çerçevesi hakkında ek bilgi.

## <a name="return-value"></a>Dönüş Değeri

Aşağıdakilerden birini *filtre ifadesi* tarafından kullanılan değerleri [deneyin-except deyimi](../cpp/try-except-statement.md).

## <a name="remarks"></a>Açıklamalar

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__CxxFrameHandler|excpt.h, ehdata.h|