---
title: BEGIN_PROPSET_MAP | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BEGIN_PROPSET_MAP
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_PROPSET_MAP macro
ms.assetid: c3a30618-6025-4d49-8688-a171294d2e93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5b1596797672c0fff92531ff90f67b94bfd6101e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="beginpropsetmap"></a>BEGIN_PROPSET_MAP
İşaretleri özelliğin başına eşleme girdilerini ayarlayın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
BEGIN_PROPSET_MAP(Class)  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 *sınıfı*  
 [in] Bu özellik kümesinin belirtilen sınıf. Bir özellik kümesi şu OLE DB nesneleri belirtilebilir:  
  
-   [Veri kaynağı nesneleri](https://msdn.microsoft.com/en-us/library/ms721278.aspx)  
  
-   [Oturum nesneleri](https://msdn.microsoft.com/en-us/library/ms711572.aspx)  
  
-   [Komutları](https://msdn.microsoft.com/en-us/library/ms724608.aspx)  
  
## <a name="example"></a>Örnek  
 Örnek özellik kümesi eşlemesini şöyledir:  
  
 [!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/cpp/begin-propset-map_1.h)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları için makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)