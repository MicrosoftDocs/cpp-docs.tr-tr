---
title: "Location sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- location
- CONCRT/concurrency::location
- CONCRT/concurrency::location::location
- CONCRT/concurrency::location::current
- CONCRT/concurrency::location::from_numa_node
dev_langs: C++
helpviewer_keywords: location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aafe0500568cd9d4c9419345560272e18008df83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="location-class"></a>location Sınıfı
Bir Özet donanımda fiziksel bir konum.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class location;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Konum](#ctor)|Fazla Yüklendi. Oluşturan bir `location` nesnesi.|  
|[~ location yok Edicisi](#dtor)|Bozar bir `location` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Geçerli](#current)|Döndürür bir `location` çağıran iş parçacığı Yürütülüyor en belirli yere temsil eden nesne.|  
|[from_numa_node](#from_numa_node)|Döndürür bir `location` belirli bir NUMA düğümünde temsil eden nesne.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator! =](#operator_neq)|İki olup olmadığını belirleyen `location` nesneleri farklı bir konuma temsil eder.|  
|[işleç =](#operator_eq)|Farklı bir içeriğini atar `location` bu bir nesne.|  
|[operator ==](#operator_eq_eq)|İki olup olmadığını belirleyen `location` nesneleri aynı konumu temsil eder.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `location`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="dtor"></a>~ konumu 

 Bozar bir `location` nesnesi.  
  
```
~location();
```  
  
##  <a name="current"></a>Geçerli 

 Döndürür bir `location` çağıran iş parçacığı Yürütülüyor en belirli yere temsil eden nesne.  
  
```
static location __cdecl current();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 En belirli yere temsil eden bir konum çağıran iş parçacığı yürütüyor.  
  
##  <a name="from_numa_node"></a>from_numa_node 

 Döndürür bir `location` belirli bir NUMA düğümünde temsil eden nesne.  
  
```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```  
  
### <a name="parameters"></a>Parametreler  
 `_NumaNodeNumber`  
 İçin bir konum oluşturmak için NUMA düğüm sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirtilen NUMA düğümünü temsil eden bir konum `_NumaNodeNumber` parametresi.  
  
##  <a name="ctor"></a>Konum 

 Oluşturan bir `location` nesnesi.  
  
```
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Src`  
 `_LocationType`  
 `_Id`  
 `_BindingId`  
 `_PBinding`  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturulan varsayılan konumu, bir bütün olarak sistemini temsil eder.  
  
##  <a name="operator_neq"></a>operator! = 

 İki olup olmadığını belirleyen `location` nesneleri farklı bir konuma temsil eder.  
  
```
bool operator!= (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`iki konum farklıysa `false` Aksi takdirde.  
  
##  <a name="operator_eq"></a>işleç = 

 Farklı bir içeriğini atar `location` bu bir nesne.  
  
```
location& operator= (const location& _Rhs);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
 Kaynak `location` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq_eq"></a>operator == 

 İki olup olmadığını belirleyen `location` nesneleri aynı konumu temsil eder.  
  
```
bool operator== (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`iki konum özdeş ise ve `false` Aksi takdirde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)
