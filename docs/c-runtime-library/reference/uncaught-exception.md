---
title: __uncaught_exception
ms.date: 11/04/2016
apiname:
- __uncaught_exception
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
apitype: DLLExport
f1_keywords:
- __uncaught_exception
helpviewer_keywords:
- __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
ms.openlocfilehash: 19d1e18af27722d6f9da39ebaaf6c9415c281849
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62268903"
---
# <a name="uncaughtexception"></a>__uncaught_exception

Bir veya daha fazla özel durum atılmış olup, ancak henüz karşılık gelen tarafından işlenmemiş olup olmadığını gösterir **catch** bloğu bir [try-catch](../../cpp/try-throw-and-catch-statements-cpp.md) deyimi.

## <a name="syntax"></a>Sözdizimi

```cpp
bool __uncaught_exception(
   );
```

## <a name="return-value"></a>Dönüş Değeri

**doğru** zamanından bir özel durum oluşturulur bir **deneyin** eşleşen kadar blok **catch** bloğudur başlatıldı; Aksi takdirde **false**.

## <a name="remarks"></a>Açıklamalar

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__uncaught_exception|EH.h|

## <a name="see-also"></a>Ayrıca bkz.

[try, throw ve catch Deyimleri (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)<br/>
