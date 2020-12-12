---
description: 'Hakkında daha fazla bilgi edinin: __uncaught_exception'
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
ms.openlocfilehash: 22417e10e96e70faf2754ae2d8bb03b90bdbe020
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124819"
---
# <a name="__uncaught_exception"></a>__uncaught_exception

Bir veya daha fazla özel durumun oluşturulup oluşturulmayacağını, ancak henüz **`catch`** bir [try-catch](../../cpp/try-throw-and-catch-statements-cpp.md) ifadesinin karşılık gelen bloğu tarafından işlenmediğini belirtir.

## <a name="syntax"></a>Syntax

```cpp
bool __uncaught_exception(
   );
```

## <a name="return-value"></a>Dönüş Değeri

**`true`** bir blok içinde, **`try`** eşleşen blok başlatılana kadar bir özel durum oluşturulduğu zaman **`catch`** ; Aksi durumda, **`false`** .

## <a name="remarks"></a>Açıklamalar

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__uncaught_exception|Eh. h|

## <a name="see-also"></a>Ayrıca bkz.

[try, throw ve catch Deyimleri (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)<br/>
