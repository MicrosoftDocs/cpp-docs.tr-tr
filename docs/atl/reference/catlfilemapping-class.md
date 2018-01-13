---
title: "CAtlFileMapping sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
dev_langs: C++
helpviewer_keywords: CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2dce8e219c2a64ecc6e9b307533ecc0ea11d2792
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping sınıfı
Bu sınıf yöntemleri için bir atama işleci ekleyerek bir bellek eşlemeli dosyasını temsil eder [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename T = char>  
class CAtlFileMapping : public CAtlFileMappingBase
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Atama işleci için kullanılan veri türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlFileMapping::operator T *](#operator_t_star)|Örtük dönüştürme verir `CAtlFileMapping` nesneleri `T`  **\*** .|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, örtük dönüştürmeye izin vermek için tek atama işleci ekler `CAtlFileMapping` nesneleri `T`  **\*** . Diğer üyeleri temel sınıfı tarafından sağlanan [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlfile.h  
  
##  <a name="operator_t_star"></a>CAtlFileMapping::operator T *  
 Örtük dönüştürme verir `CAtlFileMapping` nesneleri `T`  **\*** .  
  
```  
operator T*() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `T`  **\***  bellekle eşlenen dosya başlangıç işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) ve döndürülen işaretçi olarak reinterprets bir `T`  **\***  nerede *T* şablon olarak kullanılan türü Bu sınıf parametresi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlFileMappingBase sınıfı](../../atl/reference/catlfilemappingbase-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
