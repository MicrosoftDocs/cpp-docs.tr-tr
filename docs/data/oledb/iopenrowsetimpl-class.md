---
title: Iopenrowsetımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IOpenRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IOpenRowsetImpl class
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dd34987fcff3bee663a06276e3ded3c44d7ae77c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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