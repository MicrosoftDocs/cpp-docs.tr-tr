---
title: Iıd_ppv_args_helper işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
dev_langs:
- C++
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 351e0755f786e69da1dea6a925b7afc7cb6d6bf1
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011646"
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper İşlevi
Belirtilen bağımsız değişken türü öğesinden türetilen doğrular `IUnknown` arabirimi.  
  
> [!IMPORTANT]
>  Bu şablon uzmanlığı WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir. Kullanım [IID_PPV_ARGS](http://msdn.microsoft.com/library/windows/desktop/ee330727.aspx) yerine.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename T>  
void** IID_PPV_ARGS_Helper(  
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Bağımsız değişken türünü *pp*.  
  
 *PP*  
 Karakteriyle dolaylı bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken *pp* işaretçi-için-a-işaretçisine dönüştürme **void**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir derleme zamanı hatası oluşturulur şablon parametresi *T* öğesinden türetilen değil `IUnknown`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (Windows çalışma zamanı kitaplığı)](http://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)