---
title: PROPERTY_INFO_ENTRY_VALUE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROPERTY_INFO_ENTRY_VALUE
dev_langs: C++
helpviewer_keywords: PROPERTY_INFO_ENTRY_VALUE macro
ms.assetid: 9690f7f3-fb20-4a7e-a75f-8a3a1cb1ce0d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 25eb1627f4024fd18dbf0d22114c2e762ab8b897
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="propertyinfoentryvalue"></a>PROPERTY_INFO_ENTRY_VALUE
Bir özellik kümesi içinde belirli bir özelliği temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
PROPERTY_INFO_ENTRY_VALUE(  
dwPropID  
, value )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Dwpropıd*  
 [in] A [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) özelliği ile birlikte kullanılan değeri bir özelliği tanımlamak için GUID ayarlayın.  
  
 *değer*  
 [in] Özellik değeri türü `DWORD`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu ile özellik değeri türü doğrudan belirtebilirsiniz `DWORD`. Varsayılan değer ATLDB içinde tanımlanan özelliğini ayarlamak için. H, kullanım [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Değer, bayrakları ve özellik seçeneklerini ayarlamak için kullanın [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları için makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md)