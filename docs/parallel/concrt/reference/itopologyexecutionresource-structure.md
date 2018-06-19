---
title: Itopologyexecutionresource yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs:
- C++
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: adb456315b2c6d15b7a3696df9a6845a2bd2b899
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686483"
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
  
##  <a name="getid"></a>  Itopologyexecutionresource::GetID yöntemi  
 Bu yürütme kaynak için Resource Manager'ın benzersiz tanımlayıcısını döndürür.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Resource Manager'ın bu yürütme kaynak için benzersiz tanımlayıcı.  
  
##  <a name="getnext"></a>  Itopologyexecutionresource::GetNext yöntemi  
 Numaralandırma sırasında sonraki yürütme kaynak için bir arabirim döndürür.  
  
```
virtual ITopologyExecutionResource *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonraki yürütme kaynak numaralandırma sırasında bir arabirim. Bu yürütme kaynağa ait olduğu düğümü numaralandırma sırasına göre daha fazla düğüm varsa, bu yöntem değeri döndürür `NULL`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
