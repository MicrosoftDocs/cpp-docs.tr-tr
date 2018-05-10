---
title: Itopologynode yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
dev_langs:
- C++
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c4168fbfbd2bf17ad8b8b752d2843c8f57b0f3f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="itopologynode-structure"></a>ITopologyNode Yapısı
Kaynak Yöneticisi tarafından tanımlanan bir topoloji düğüme bir arabirim. Bir düğüm bir veya daha fazla yürütme kaynakları içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct ITopologyNode;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Itopologynode::getexecutionresourcecount](#getexecutionresourcecount)|Bu düğüm altında gruplanmış yürütme kaynakların sayısını döndürür.|  
|[Itopologynode::getfirstexecutionresource](#getfirstexecutionresource)|Numaralandırma sırasında bu düğüm altında gruplanmış ilk yürütme kaynak döndürür.|  
|[Itopologynode::GetID](#getid)|Bu düğüm için Resource Manager'ın benzersiz tanımlayıcısını döndürür.|  
|[Itopologynode::GetNext](#getnext)|Sonraki topoloji düğümü numaralandırma sırasında bir arabirim döndürür.|  
|[Itopologynode::getnumanode](#getnumanode)|Bu kaynak Maanger düğüm ait olduğu NUMA düğüm numarasını döndürür Windows atanır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim, genellikle kaynak yöneticisi tarafından gözlemlenen sistemin topolojisi yürütmek için kullanılır.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ITopologyNode`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="getexecutionresourcecount"></a>  Itopologynode::getexecutionresourcecount yöntemi  
 Bu düğüm altında gruplanmış yürütme kaynakların sayısını döndürür.  
  
```
virtual unsigned int GetExecutionResourceCount() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yürütme kaynak sayısı bu düğüm altında gruplanmış.  
  
##  <a name="getfirstexecutionresource"></a>  Itopologynode::getfirstexecutionresource yöntemi  
 Numaralandırma sırasında bu düğüm altında gruplanmış ilk yürütme kaynak döndürür.  
  
```
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk yürütme kaynak numaralandırma sırasında bu düğüm altında gruplanmış olarak.  
  
##  <a name="getid"></a>  Itopologynode::GetID yöntemi  
 Bu düğüm için Resource Manager'ın benzersiz tanımlayıcısını döndürür.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Resource Manager'ın bu düğüm için benzersiz tanımlayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Eşzamanlılık Çalışma zamanı işlemci düğümlerinin gruplarındaki sistem üzerinde donanım iş parçacığı temsil eder. Düğümleri genellikle sistem donanım topolojisine türetilir. Örneğin, belirli bir yuva veya belirli bir NUMA düğümünde tüm işlemcilerin aynı işlemci düğüme ait olabilir. Resource Manager başlayarak bu düğümler benzersiz tanımlayıcı atar `0` dahil `nodeCount - 1`, burada `nodeCount` işlemci düğümleri sistemdeki toplam sayısını temsil eder.  
  
 Düğüm sayısı işlevinden elde edilebilir [GetProcessorNodeCount](concurrency-namespace-functions.md).  
  
##  <a name="getnext"></a>  Itopologynode::GetNext yöntemi  
 Sonraki topoloji düğümü numaralandırma sırasında bir arabirim döndürür.  
  
```
virtual ITopologyNode *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Numaralandırma sırasında bir sonraki düğüme bir arabirim. Sistem topoloji numaralandırması sırasına göre daha fazla düğüm varsa, bu yöntem değeri döndürür `NULL`.  
  
##  <a name="getnumanode"></a>  Itopologynode::getnumanode yöntemi  
 Bu kaynak Maanger düğüm ait olduğu NUMA düğüm numarasını döndürür Windows atanır.  
  
```
virtual unsigned long GetNumaNode() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Windows bu Resource Manager düğüm ait olduğu NUMA düğüm numarası atanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu düğüme ait bir sanal işlemcinin kök üzerinde çalışan bir iş parçacığı proxy en az benzeşimi gerekir bu yöntem tarafından döndürülen NUMA düğümü için NUMA düğümü düzeyi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
