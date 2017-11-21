---
title: "CAtlAutoThreadModuleT sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
dev_langs: C++
helpviewer_keywords: CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 594e6bd026d214e2dd5d12e702d26a5942cfc872
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT sınıfı
Bu sınıf, bir iş parçacığı havuza, modeli COM sunucusu uygulamak için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, 
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 COM sunucusu uygulayan sınıf.  
  
 `ThreadAllocator`  
 İş parçacığı seçimi yönetme sınıfı. Varsayılan değer [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
 `dwWait`  
 Zaman aşımı aralığı, milisaniye cinsinden belirtir. Yöntemin zaman aşımı aralığı geçtikten hiçbir zaman anlamına gelir SONSUZ varsayılandır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|Bu statik işlev dinamik olarak hesaplar ve işlemci sayısına göre EXE modülü için iş parçacığı sayısını döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) türetilen `CAtlAutoThreadModuleT` apartman modeli iş parçacığı havuza, COM sunucusu uygulamak için. Artık kullanılmayan sınıfı yerini [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
> [!NOTE]
>  Bu sınıf DLL'de, varsayılan olarak kullanılmamalıdır `dwWait` DLL kaldırıldığında, SONSUZ değerini bir kilitlenmeye neden olur.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="getdefaultthreads"></a>CAtlAutoThreadModuleT::GetDefaultThreads  
 Bu statik işlev dinamik olarak hesaplar ve işlemci sayısına göre EXE modülü için iş parçacığı sayısını döndürür.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 EXE modülünde oluşturulacak iş parçacığı sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İş parçacığı sayısını hesaplamak için farklı bir yöntem kullanmak istiyorsanız bu yöntemi geçersiz kılın. Varsayılan olarak, iş parçacığı sayısını işlemci sayısına bağlıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IAtlAutoThreadModule sınıfı](../../atl/reference/iatlautothreadmodule-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [IAtlAutoThreadModule sınıfı](../../atl/reference/iatlautothreadmodule-class.md)   
 [Modül sınıfları](../../atl/atl-module-classes.md)
