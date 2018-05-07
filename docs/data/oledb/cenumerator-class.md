---
title: CEnumerator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CEnumerator
dev_langs:
- C++
helpviewer_keywords:
- CEnumerator class
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b7e390212da53f85cb50dd5bb151ea6740784b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DBVIEWER](../../visual-cpp-samples.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)