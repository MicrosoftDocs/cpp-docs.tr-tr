---
title: "scoped_d3d_access_lock sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
dev_langs: C++
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 37dadc932701354de317d253a39bd2f2ee71a495
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="scopedd3daccesslock-class"></a>scoped_d3d_access_lock Sınıfı
Accelerator_view nesnedeki D3D erişim kilit RAII sarmalayıcı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
class scoped_d3d_access_lock;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[scoped_d3d_access_lock Oluşturucusu](#ctor)|Fazla Yüklendi. Oluşturan bir `scoped_d3d_access_lock` nesnesi. Bu nesne kapsam dışına çıktığında kilidi serbest bırakılır.|  
|[~ scoped_d3d_access_lock yok Edicisi](#dtor)|İlişkili üzerindeki D3D erişim kilidi serbest `accelerator_view` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[işleç =](#operator_eq)|Başka bir kilit sahipliğini `scoped_d3d_access_lock`.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `scoped_d3d_access_lock`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amprt.h  
  
 **Namespace:** concurrency::direct3d  

##  <a name="ctor"></a>scoped_d3d_access_lock 

 Oluşturan bir `scoped_d3d_access_lock` nesnesi. Bu nesne kapsam dışına çıktığında kilidi serbest bırakılır.  
 
```  
explicit scoped_d3d_access_lock(// [1] constructor  
    accelerator_view& _Av);

 
explicit scoped_d3d_access_lock(// [2] constructor  
    accelerator_view& _Av,  
    adopt_d3d_access_lock_t _T);

 
scoped_d3d_access_lock(// [3] move constructor  
    scoped_d3d_access_lock&& _Other);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Av`  
 `accelerator_view` Benimsemek kilitleme.  
  
 `_T`  
 `adopt_d3d_access_lock_t` Nesnesi.  
  
 `_Other`  
 `scoped_d3d_access_lock` Varolan bir Kilitle taşımak nesnesi.  
  
## <a name="construction"></a>Yapı  
 [1] Oluşturucusu  
 Üzerinde D3D erişim kilit alır verilen [accelerator_view](accelerator-view-class.md) nesnesi. Kilit edinilen kadar yapım engeller.  
  
 [2] Oluşturucusu  
 Gelen D3D erişim kilit benimsemeyi verilen [accelerator_view](accelerator-view-class.md) nesnesi.  
  
 [3] taşıma Oluşturucusu  
 Varolan bir D3D erişim Kilitle başka bir alan `scoped_d3d_access_lock` nesnesi. Yapım engellemez.  

  
##  <a name="dtor"></a>~ scoped_d3d_access_lock 

 İlişkili üzerindeki D3D erişim kilidi serbest `accelerator_view` nesnesi.  
  
```  
~scoped_d3d_access_lock();
```  
## <a name="operator_eq"></a>işleç = 

Başka bir D3D erişim kilit sahipliğini `scoped_d3d_access_lock` önceki kilidin açılması nesnesi.  
 
```  
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 Accelerator_view D3D erişim kilit taşımak üzere.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `scoped_accelerator_view_lock`.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)
