---
title: "CEnumerator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEnumerator
dev_langs:
- C++
helpviewer_keywords:
- CEnumerator class
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d0ac9fe73b2d8b37e345ddcf602dd98316eedf46
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cenumerator-class"></a>CEnumerator Sınıfı
Kullanıma sunan bir OLE DB Numaralandırıcı nesne kullanan [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) arabirimi tüm veri kaynakları ve numaralandırmalar açıklayan bir satır kümesi döndürür.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Bul](../../data/oledb/cenumerator-find.md)|Kullanılabilir sağlayıcılar (veri kaynakları) belirtilen ada sahip bir arayan arar.|  
|[GetMoniker](../../data/oledb/cenumerator-getmoniker.md)|Alır `IMoniker` geçerli kayıt için arabirim.|  
|[Açık](../../data/oledb/cenumerator-open.md)|Numaralayıcı açar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Alabilirsiniz **ISourcesRowset** dolaylı olarak bu sınıfın verileri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:**atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)