---
title: __set_app_type
ms.date: 11/04/2016
apiname:
- __set_app_type
- _set_app_type
apilocation:
- msvcr90.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __set_app_type
helpviewer_keywords:
- __set_app_type
ms.assetid: f0ac0f4d-70e6-4e96-9e43-eb9d1515490c
ms.openlocfilehash: f42ac1c173637cf85d727adf25ebf9079f4cb37c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62343159"
---
# <a name="setapptype"></a>__set_app_type

Geçerli uygulama türünü ayarlar.

## <a name="syntax"></a>Sözdizimi

```cpp
void __set_app_type (
   int at
   )
```

#### <a name="parameters"></a>Parametreler

*konumunda*<br/>
Uygulama türünü belirten bir değer. Olası değerler şunlardır:

|Değer|Açıklama|
|-----------|-----------------|
|_UNKNOWN_APP|Bilinmeyen uygulama türü.|
|_CONSOLE_APP|(Komut satırı) konsol uygulaması.|
|_GUI_APP|GUI (Windows) uygulama.|

## <a name="remarks"></a>Açıklamalar

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__set_app_type|internal.h|