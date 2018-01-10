---
title: "CComSimpleThreadAllocator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
dev_langs: C++
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 244443692478d0391c2079e55995c1fef1e1655e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomsimplethreadallocator-class"></a>CComSimpleThreadAllocator sınıfı
Bu sınıf sınıfı için iş parçacığı seçimi yönetir `CComAutoThreadModule`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComSimpleThreadAllocator
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComSimpleThreadAllocator::GetThread](#getthread)|Bir iş parçacığı seçer.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComSimpleThreadAllocator`iş parçacığı seçimi için yönetir [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md). `CComSimpleThreadAllocator::GetThread`yalnızca her iş parçacığı geçiş yapar ve bir sonraki sırada döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="getthread"></a>CComSimpleThreadAllocator::GetThread  
 Bir iş parçacığı sırayla sonraki iş parçacığı belirterek seçer.  
  
```
int GetThread(CComApartment* /* pApt */, int nThreads);
```  
  
### <a name="parameters"></a>Parametreler  
 `pApt`  
 ATL'ın varsayılan uygulamasında kullanılmaz.  
  
 `nThreads`  
 EXE modülündeki iş parçacığı sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır arasında bir tamsayı ve ( `nThreads` - 1). Bir iş parçacığı EXE modülünde tanımlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçersiz kılabilirsiniz `GetThread` seçimin farklı bir yöntem sağlamak ya da yapmak için kullanımı `pApt` parametresi.  
  
 `GetThread`tarafından çağrılır [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComApartment sınıfı](../../atl/reference/ccomapartment-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
