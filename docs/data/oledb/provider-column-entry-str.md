---
title: PROVIDER_COLUMN_ENTRY_STR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- PROVIDER_COLUMN_ENTRY_STR
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_STR macro
ms.assetid: f1c27dd6-9ab8-4821-8685-d4dd15e76e88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9ede31951c916c8b70b4942c3077442b5e2e3313
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104626"
---
# <a name="providercolumnentrystr"></a>PROVIDER_COLUMN_ENTRY_STR
Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
PROVIDER_COLUMN_ENTRY_STR(name  
, ordinal, member )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Adı*  
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