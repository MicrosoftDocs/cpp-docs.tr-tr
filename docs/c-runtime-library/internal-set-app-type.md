---
description: 'Hakkında daha fazla bilgi edinin: __set_app_type'
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
ms.openlocfilehash: 19aafebc4f7fd848804e21193332fb693af56010
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246779"
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
|_GUI_APP|GUI (Windows) uygulaması.|

## <a name="remarks"></a>Açıklamalar

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__set_app_type|iç. h|
