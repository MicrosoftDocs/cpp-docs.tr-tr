---
title: _set_app_type
ms.date: 11/04/2016
api_name:
- _set_app_type
api_location:
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
ms.openlocfilehash: 7e04d88d9e9981e35b7d4c80c11d27c868219f65
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957918"
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

Normalde, bu işlevi çağırmanız gerekmez. Uygulamanızda çağrılmadan önce `main` yürüten C çalışma zamanı başlangıç kodunun bir parçasıdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_set_app_type|Process. h|
