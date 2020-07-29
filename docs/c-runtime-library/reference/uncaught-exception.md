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
ms.openlocfilehash: 1eb06abbda7978acf578555f966f0857dff02053
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211638"
---
# <a name="__uncaught_exception"></a>__uncaught_exception

Bir veya daha fazla özel durumun oluşturulup oluşturulmayacağını, ancak henüz **`catch`** bir [try-catch](../../cpp/try-throw-and-catch-statements-cpp.md) ifadesinin karşılık gelen bloğu tarafından işlenmediğini belirtir.

## <a name="syntax"></a>Sözdizimi

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
