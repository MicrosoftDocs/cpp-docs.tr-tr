---
title: __uncaught_exception
ms.date: 11/04/2016
api_name:
- __uncaught_exception
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __uncaught_exception
helpviewer_keywords:
- __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
ms.openlocfilehash: 0130776ec2511aefd42d1700f950d97738e9fb14
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70945944"
---
# <a name="__uncaught_exception"></a>__uncaught_exception

Bir veya daha fazla özel durumun oluşturulup oluşturulmayacağını, ancak henüz bir [try-catch](../../cpp/try-throw-and-catch-statements-cpp.md) ifadesinin karşılık gelen **catch** bloğu tarafından işlenmediğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
bool __uncaught_exception(
   );
```

## <a name="return-value"></a>Dönüş Değeri

bir **TRY** bloğunda, eşleşen **catch** bloğu başlatılana kadar bir özel durum oluşturulduğu zamandan **doğru** . Aksi takdirde, **false**.

## <a name="remarks"></a>Açıklamalar

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__uncaught_exception|Eh. h|

## <a name="see-also"></a>Ayrıca bkz.

[try, throw ve catch Deyimleri (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)<br/>
