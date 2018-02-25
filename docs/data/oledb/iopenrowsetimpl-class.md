---
title: "Iopenrowsetımpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOpenRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IOpenRowsetImpl class
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 67f457b4a56d57f33a18473e987fa00b6c10b0df
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="iopenrowsetimpl-class"></a>IOpenRowsetImpl Sınıfı
Uygulamasını sağlar `IOpenRowset` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
#### <a name="parameters"></a>Parametreler  
 `SessionClass`  
 Sınıfınız, türetilen `IOpenRowsetImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CreateRowset](../../data/oledb/iopenrowsetimpl-createrowset.md)|Bir satır kümesi nesnesi oluşturur. Doğrudan kullanıcı tarafından adı değil.|  
|[OpenRowset](../../data/oledb/iopenrowsetimpl-openrowset.md)|Açılır ve tek bir temel tablo veya dizini tüm satırları içeren bir satır kümesi döndürür. (ATLDB içinde değil. Y)|  
  
## <a name="remarks"></a>Açıklamalar  
 [IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx) arabirimi için bir oturum nesnesi zorunludur. Açılır ve tek bir temel tablo veya dizini tüm satırları içeren bir satır kümesi döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)