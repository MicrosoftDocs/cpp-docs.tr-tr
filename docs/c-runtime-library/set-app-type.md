---
title: _set_app_type
ms.date: 4/2/2020
api_name:
- _set_app_type
- _o__set_app_type
api_location:
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
ms.openlocfilehash: 9791cff55ccd55c32d124ab89cc43ab54c0f9c69
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360967"
---
# <a name="_set_app_type"></a>_set_app_type

Başlangıçta CRT'ye uygulamanın bir konsol uygulaması mı yoksa GUI uygulaması mı olduğunu söylemek için kullanılan dahili bir işlev.

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

*appType*<br/>
Uygulama türünü gösteren bir değer. Olası değerler şunlardır:

|Değer|Açıklama|
|----------------|-----------------|
|_crt_unknown_app|Bilinmeyen uygulama türü.|
|_crt_console_app|Konsol (komut satırı) uygulaması.|
|_crt_gui_app|GUI (Windows) uygulaması.|

## <a name="remarks"></a>Açıklamalar

Normalde, bu işlevi aramanız gerekmez. Uygulamanızda çağrılmadan önce `main` yürüten C çalışma zamanı başlangıç kodunun bir parçasıdır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_set_app_type|process.h|
