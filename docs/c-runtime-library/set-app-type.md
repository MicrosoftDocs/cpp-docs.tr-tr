---
title: _set_app_type
ms.date: 11/04/2016
apiname:
- _set_app_type
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
ms.openlocfilehash: 5a29fd94cca7fdbf6bbb24699b7f510bf1465f15
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749197"
---
# <a name="setapptype"></a>_set_app_type

Başlangıçta, uygulamayı bir konsol uygulaması veya bir GUI uygulaması olup CRT bildirmek için kullanılan bir iç işlev.

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

*uygulama türü*<br/>
Uygulama türünü belirten bir değer. Olası değerler şunlardır:

|Değer|Açıklama|
|----------------|-----------------|
|_crt_unknown_app|Bilinmeyen uygulama türü.|
|_crt_console_app|(Komut satırı) konsol uygulaması.|
|_crt_gui_app|GUI (Windows) uygulama.|

## <a name="remarks"></a>Açıklamalar

Normalde, bu işlevi çağırın gerekmez. Önce yürütülen C çalışma zamanı başlatma kod parçası `main` uygulamanızda çağrılır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_set_app_type|Process.h|
