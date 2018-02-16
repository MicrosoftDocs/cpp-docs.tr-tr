---
title: "CSimpleRow sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
dev_langs:
- C++
helpviewer_keywords:
- CSimpleRow class
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c241118d13f7efecef9413851d3d47ff9a08b58
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="csimplerow-class"></a>CSimpleRow Sınıfı
Kullanılan satır işleyici için bir varsayılan uygulama sağlar [Irowsetımpl](../../data/oledb/irowsetimpl-class.md) sınıfı.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CSimpleRow  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[AddRefRow](../../data/oledb/csimplerow-addrefrow.md)|Bir başvuru sayısı varolan bir satır tanıtıcı ekler.|  
|[Karşılaştırma](../../data/oledb/csimplerow-compare.md)|Aynı satır örneğine bakın görmek için iki satır karşılaştırır.|  
|[CSimpleRow](../../data/oledb/csimplerow-csimplerow.md)|Oluşturucu.|  
|[ReleaseRow](../../data/oledb/csimplerow-releaserow.md)|Satır serbest bırakır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_dwRef](../../data/oledb/csimplerow-m-dwref.md)|Varolan bir satır işlemek için başvuru sayısı.|  
|[m_iRowset](../../data/oledb/csimplerow-m-irowset.md)|İmleç temsil eden satır kümesi için bir dizin.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir satır mantıksal bir sonuç satır için benzersiz bir etiket işleyicisidir. `IRowsetImpl` Yeni bir `CSimpleRow` içindeki her satır istenen için [Irowsetımpl::GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md). `CSimpleRow` Varsayılan şablon bağımsız değişken için olduğu gibi satır tanıtıcısı kendi bir uygulama ile aynı zamanda değiştirilebilir `IRowsetImpl`. Bu sınıf değiştirmek için tek gereksinim türü tek bir parametre kabul eden bir oluşturucu sağlayın değiştirme sınıfında yapmaktır **uzun**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetImpl Sınıfı](../../data/oledb/irowsetimpl-class.md)