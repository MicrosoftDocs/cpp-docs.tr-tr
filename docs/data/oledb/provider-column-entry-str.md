---
title: PROVIDER_COLUMN_ENTRY_STR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROVIDER_COLUMN_ENTRY_STR
dev_langs: C++
helpviewer_keywords: PROVIDER_COLUMN_ENTRY_STR macro
ms.assetid: f1c27dd6-9ab8-4821-8685-d4dd15e76e88
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fc45826fed148b2d3d7990ce512bc9a1861fdff0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="providercolumnentrystr"></a>PROVIDER_COLUMN_ENTRY_STR
Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
PROVIDER_COLUMN_ENTRY_STR(  
name  
, ordinal, member )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *adı*  
 [in] Sütun adı.  
  
 `ordinal`  
 [in] Sütun numarası. Bir yer işareti sütun sütun olmadığı sürece sütun numarası 0 olmalıdır.  
  
 `member`  
 [in] Üye değişkeni veri sınıfında verileri depolar.  
  
## <a name="remarks"></a>Açıklamalar  
 Sütun veri olduğu varsayılarak bu makrosu kullanın [DBTYPE_STR](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
## <a name="example"></a>Örnek  
 Bkz: [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları için makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)