---
title: _set_app_type | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- _set_app_type
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
dev_langs:
- C++
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b2ad7e22bf6ba366a33dd44ce49c1a384f88b87
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041265"
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

