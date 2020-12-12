---
description: 'Hakkında daha fazla bilgi edinin: _set_app_type'
title: _set_app_type
ms.date: 4/2/2020
api_name:
- _set_app_type
- _o__set_app_type
api_location:
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
ms.openlocfilehash: cd04f1c17f7876c08f8eafb4ef77960073fb3f33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277108"
---
# <a name="_set_app_type"></a>_set_app_type

Uygulamanın bir konsol uygulaması veya GUI uygulaması olup olmadığı CRT 'ye bildirmek için başlangıçta kullanılan bir iç işlev.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef enum _crt_app_type
{
    _crt_unknown_app,
    _crt_console_app,
    _crt_gui_app
} _crt_app_type;

void __cdecl _set_app_type(
    _crt_app_type appType
    );
```

## <a name="parameters"></a>Parametreler

*Uyg türü*<br/>
Uygulama türünü gösteren bir değer. Olası değerler şunlardır:

|Değer|Açıklama|
|----------------|-----------------|
|_crt_unknown_app|Bilinmeyen uygulama türü.|
|_crt_console_app|Konsol (komut satırı) uygulaması.|
|_crt_gui_app|GUI (Windows) uygulaması.|

## <a name="remarks"></a>Açıklamalar

Normalde, bu işlevi çağırmanız gerekmez. Uygulamanızda çağrılmadan önce yürüten C çalışma zamanı başlangıç kodunun bir parçasıdır `main` .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_set_app_type|Process. h|
