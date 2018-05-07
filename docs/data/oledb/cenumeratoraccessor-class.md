---
title: CEnumeratorAccessor sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
dev_langs:
- C++
helpviewer_keywords:
- CEnumeratorAccessor class
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bb071f47eb7079c8de63da47ee0d837f44442c1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cenumeratoraccessor-class"></a>CEnumeratorAccessor Sınıfı
Tarafından kullanılan [CEnumerator](../../data/oledb/cenumerator-class.md) Numaralandırıcı satır kümesinden verilere erişmek için.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CEnumeratorAccessor  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_bIsParent](../../data/oledb/cenumeratoraccessor-m-bisparent.md)|Satır bir numaralandırıcı ise Numaralandırıcı üst Numaralandırıcı olup olmadığını belirten bir değişken.|  
|[m_nType](../../data/oledb/cenumeratoraccessor-m-ntype.md)|Satır bir veri kaynağı veya bir numaralandırıcı tanımlayıp tanımlamadığını belirten bir değişken.|  
|[m_szDescription](../../data/oledb/cenumeratoraccessor-m-szdescription.md)|Veri kaynağı veya numaralandırıcı açıklaması.|  
|[m_szName](../../data/oledb/cenumeratoraccessor-m-szname.md)|Veri kaynağı veya numaralandırıcı adı.|  
|[m_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)|Geçirilecek dize [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) Numaralandırıcı ve veri kaynağı için bir ad elde edilir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu satır kümesi veri kaynakları ve numaralandırmalar geçerli Numaralandırıcının görünür oluşur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)