---
title: "CEnumeratorAccessor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
dev_langs:
- C++
helpviewer_keywords:
- CEnumeratorAccessor class
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 57595cb2440aa8ad83c7cc0ad6916b3f22d6fb37
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
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