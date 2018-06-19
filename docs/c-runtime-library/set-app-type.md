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
ms.openlocfilehash: fc9b3901cb031a1cc08d911889dc97818cfb5a44
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410187"
---
# <a name="setapptype"></a>_set_app_type
Başlangıçta uygulama bir konsol uygulaması veya bir GUI uygulaması olup CRT bildirmek için kullanılan bir iç işlev.  
  
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
 `appType`  
 Uygulama türünü belirten bir değer. Olası değerler şunlardır:  
  
|Değer|Açıklama|  
|----------------|-----------------|  
|_crt_unknown_app|Bilinmeyen uygulama türü.|  
|_crt_console_app|(Komut satırı) konsol uygulaması.|  
|_crt_gui_app|GUI (Windows) uygulama.|  
  
## <a name="remarks"></a>Açıklamalar  
 Normalde, bu işlevi çağırmak gerekmez. Önce yürütür C çalışma zamanı başlatma kodunu parçası olan `main` uygulamanızda olarak adlandırılır.
 
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|_set_app_type|Process.h|

