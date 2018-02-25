---
title: BEGIN_PROPSET_MAP | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- BEGIN_PROPSET_MAP
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_PROPSET_MAP macro
ms.assetid: c3a30618-6025-4d49-8688-a171294d2e93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ec9dc0b1481a3443c769c81d051d370747f3813d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
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