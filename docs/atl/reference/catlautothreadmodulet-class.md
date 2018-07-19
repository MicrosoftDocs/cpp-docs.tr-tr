---
title: CAtlAutoThreadModuleT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a54818b839f13ad9114274248cfdbfc74efa033a
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883079"
---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT sınıfı
Bu sınıf, apartman modeli iş parçacığı havuza, COM sunucu uygulama için yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, 
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 COM sunucusunun uygulayan sınıf.  
  
 *ThreadAllocator*  
 İş parçacığı seçimi yönetme sınıfı. Varsayılan değer [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
 *dwWait*  
 Milisaniye cinsinden zaman aşımı aralığı belirtir. Yöntemin zaman aşımı aralığı, hiçbir zaman geçtikçe anlamına gelir ve SINIRSIZ varsayılandır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|Bu statik işlev dinamik olarak hesaplar ve en fazla işlemci sayısına göre bir EXE modülü için iş parçacıklarının sayısını döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) türetildiği `CAtlAutoThreadModuleT` apartman modeli iş parçacığı havuza, COM sunucusu uygulamak için. Geçersiz sınıf değiştirir [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
> [!NOTE]
>  Bu sınıf bir DLL içinde varsayılan olarak kullanılmamalıdır *dwWait* DLL kaldırıldığında, SONSUZ değerini karşılıklı bir kilitlenme neden olur.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="getdefaultthreads"></a>  CAtlAutoThreadModuleT::GetDefaultThreads  
 Bu statik işlev dinamik olarak hesaplar ve en fazla işlemci sayısına göre bir EXE modülü için iş parçacıklarının sayısını döndürür.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 EXE modülünde oluşturulacak iş parçacığı sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İş parçacığı sayısını hesaplamak için farklı bir yöntem kullanmak istiyorsanız bu yöntemi yok sayın. Varsayılan olarak, iş parçacığı sayısını işlemci sayısına bağlıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Iatlautothreadmodule sınıfı](../../atl/reference/iatlautothreadmodule-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)   
 [Iatlautothreadmodule sınıfı](../../atl/reference/iatlautothreadmodule-class.md)   
 [Modül sınıfları](../../atl/atl-module-classes.md)
