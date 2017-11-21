---
title: "Iıd_ppv_args_helper işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/IID_PPV_ARGS_Helper
dev_langs: C++
helpviewer_keywords: IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 705f1ee7f1b471491b6df5953cf92b12f6edc13c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper İşlevi
Belirtilen bağımsız değişken türü öğesinden türetilen doğrular `IUnknown` arabirimi.  
  
> [!IMPORTANT]
>  Bu şablon uzmanlık WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir. Kullanım [IID_PPV_ARGS](http://msdn.microsoft.com/library/windows/desktop/ee330727.aspx) yerine.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename T  
>  
void** IID_PPV_ARGS_Helper(  
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bağımsız değişken türü `pp`.  
  
 `pp`  
 Karakteriyle dolaylı bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken `pp` gösteren bir işaretçi-için-a-işaretçi cast `void`.  
  
## <a name="remarks"></a>Açıklamalar  
 Derleme zamanı hatası ise oluşturulur şablon parametresi `T` öğesinden türetilen değil `IUnknown`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (Windows çalışma zamanı kitaplığı)](http://msdn.microsoft.com/en-us/00000000-0000-0000-0000-000000000000)