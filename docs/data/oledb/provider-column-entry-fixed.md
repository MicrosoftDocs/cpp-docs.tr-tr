---
title: PROVIDER_COLUMN_ENTRY_FIXED | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROVIDER_COLUMN_ENTRY_FIXED
dev_langs: C++
helpviewer_keywords: PROVIDER_COLUMN_ENTRY_FIXED macro
ms.assetid: 71f9c9aa-56a0-488b-96ba-5c72da9c71d0
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e404e18a072650d89f3987d8e8f0e286240d022a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="providercolumnentryfixed"></a>PROVIDER_COLUMN_ENTRY_FIXED
Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
PROVIDER_COLUMN_ENTRY_FIXED(  
name  
, ordinal, dbtype, member )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *adı*  
 [in] Sütun adı.  
  
 `ordinal`  
 [in] Sütun numarası. Bir yer işareti sütun sütun olmadığı sürece sütun numarası 0 olmalıdır.  
  
 `dbtype`  
 [in] Veri türü [DBTYPE](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
 `member`  
 [in] Üye değişkeni `dataClass` verileri depolar.  
  
## <a name="remarks"></a>Açıklamalar  
 Sütun veri türü belirtmenize olanak tanır.  
  
## <a name="example"></a>Örnek  
 Bkz: [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları için makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md)