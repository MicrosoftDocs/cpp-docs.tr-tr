---
title: __set_app_type
ms.date: 11/04/2016
api_name:
- __set_app_type
- _set_app_type
api_location:
- msvcr90.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __set_app_type
helpviewer_keywords:
- __set_app_type
ms.assetid: f0ac0f4d-70e6-4e96-9e43-eb9d1515490c
ms.openlocfilehash: 4d72eecd454e6c01e88c6869c96b628902690383
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940235"
---
# <a name="__set_app_type"></a>__set_app_type

Geçerli uygulama türünü ayarlar.

## <a name="syntax"></a>Sözdizimi

```cpp
void __set_app_type (
   int at
   )
```

#### <a name="parameters"></a>Parametreler

*hızı*<br/>
Uygulama türünü gösteren bir değer. Olası değerler şunlardır:

|Değer|Açıklama|
|-----------|-----------------|
|_UNKNOWN_APP|Bilinmeyen uygulama türü.|
|_CONSOLE_APP|Konsol (komut satırı) uygulaması.|
|_GU_APP|GUI (Windows) uygulaması.|

## <a name="remarks"></a>Açıklamalar

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__set_app_type|iç. h|