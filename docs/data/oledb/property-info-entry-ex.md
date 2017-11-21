---
title: PROPERTY_INFO_ENTRY_EX | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROPERTY_INFO_ENTRY_EX
dev_langs: C++
helpviewer_keywords: PROPERTY_INFO_ENTRY_EX macro
ms.assetid: af32dfcd-4c50-449d-af3b-48d21bd67a04
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 61842dc963ae442d23f802c1fd64c037f4a882e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="propertyinfoentryex"></a>PROPERTY_INFO_ENTRY_EX
Bir özellik kümesi içinde belirli bir özelliği temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
PROPERTY_INFO_ENTRY_EX(  
dwPropID  
, vt, dwFlags, value, options )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Dwpropıd*  
 [in] A [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) özelliği ile birlikte kullanılan değeri bir özelliği tanımlamak için GUID ayarlayın.  
  
 *VT*  
 [in] [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) bu özellik girişinin.  
  
 `dwFlags`  
 [in] A [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) bu özellik giriş açıklayan değeri.  
  
 *değer*  
 [in] Özellik değeri türü `DWORD`.  
  
 `options`  
 Her iki **DBPROPOPTIONS_REQUIRED** veya **DBPROPOPTIONS_SETIFCHEAP**. Normalde, bir sağlayıcı ayarlamak gerekmez `options` çünkü tüketici tarafından ayarlanır.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu ile özellik değeri türü doğrudan belirtebilirsiniz `DWORD` seçenekleri ve bayrakları yanı sıra. Yalnızca bir özellik ATLDB içinde tanımlanan varsayılan bir değer ayarlamak için. H, kullanım [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Bir özellik seçeneklerini ayarlama ya da bayrakları olmadan tercih ettiğiniz bir değere ayarlamak için kullanın [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları için makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md)