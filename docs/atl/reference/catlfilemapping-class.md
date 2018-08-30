---
title: CAtlFileMapping sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 973501339d05f75414d076cbd22f5dabeb0bec7c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208729"
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping sınıfı
Bu sınıfın temsil yöntemleri için bir atama işleci ekleyerek bir bellek işlemeli dosya [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename T = char>  
class CAtlFileMapping : public CAtlFileMappingBase
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Tür dönüştürme işleci için kullanılan veri türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlFileMapping::operator T *](#operator_t_star)|Örtük dönüştürme sağlayan `CAtlFileMapping` nesneleri için `T*`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir tek atama işleci örtük dönüştürme izin vermek için bu sınıfı ekler `CAtlFileMapping` nesneleri için `T*`. Diğer üyeleri taban sınıfı tarafından sağlanan [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlfile.h  
  
##  <a name="operator_t_star"></a>  CAtlFileMapping::operator T *  
 Örtük dönüştürme sağlayan `CAtlFileMapping` nesneleri için `T*`.  
  
```  
operator T*() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `T*` bellekle eşlenen dosya işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) ve döndürülen işaretçi olarak derecenin bir `T*` burada *T* bu sınıfın şablon parametresi kullanılan bir tür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlFileMappingBase sınıfı](../../atl/reference/catlfilemappingbase-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
