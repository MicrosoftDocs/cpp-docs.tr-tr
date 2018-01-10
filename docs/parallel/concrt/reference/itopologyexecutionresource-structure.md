---
title: "Itopologyexecutionresource yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs: C++
helpviewer_keywords: ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: caf2cc77cd31df611f71d07c5a0a49f600767f81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource Yapısı
Kaynak Yöneticisi tarafından tanımlanan bir yürütme kaynak bir arabirim.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct ITopologyExecutionResource;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Itopologyexecutionresource::GetID](#getid)|Bu yürütme kaynak için Resource Manager'ın benzersiz tanımlayıcısını döndürür.|  
|[Itopologyexecutionresource::GetNext](#getnext)|Numaralandırma sırasında sonraki yürütme kaynak için bir arabirim döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim, genellikle kaynak yöneticisi tarafından gözlemlenen sistemin topolojisi yürütmek için kullanılır.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ITopologyExecutionResource`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="getid"></a>Itopologyexecutionresource::GetID yöntemi  
 Bu yürütme kaynak için Resource Manager'ın benzersiz tanımlayıcısını döndürür.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Resource Manager'ın bu yürütme kaynak için benzersiz tanımlayıcı.  
  
##  <a name="getnext"></a>Itopologyexecutionresource::GetNext yöntemi  
 Numaralandırma sırasında sonraki yürütme kaynak için bir arabirim döndürür.  
  
```
virtual ITopologyExecutionResource *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonraki yürütme kaynak numaralandırma sırasında bir arabirim. Bu yürütme kaynağa ait olduğu düğümü numaralandırma sırasına göre daha fazla düğüm varsa, bu yöntem değeri döndürür `NULL`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
