---
title: "Irowsetınfoımpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetInfoImpl
- IRowsetInfoImpl
- ATL::IRowsetInfoImpl
dev_langs: C++
helpviewer_keywords: IRowsetInfoImpl class
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cba03cfdda0b7a55c8f4719d5340566ee5dc6050
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetinfoimpl-class"></a>IRowsetInfoImpl Sınıfı
Bir uygulamasını sağlar [IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE IRowsetInfoImpl :   
   public IRowsetInfo,    
   public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IRowsetInfoImpl`.  
  
 `PropClass`  
 Varsayılan olarak bir kullanıcı tarafından tanımlanabilen özellik sınıfı `T`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)|Satır kümesi tarafından desteklenen tüm özelliklerinin geçerli ayarları döndürür.|  
|[GetReferencedRowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)|Arabirim işaretçisi yer işareti uygulandığı satır kümesi döndürür.|  
|[GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)|Arabirim işaretçisi bu satır kümesini oluşturan nesnede (komut veya oturum) döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Satır kümeleri üzerinde zorunlu bir arabirim. Bu sınıf satır kümesi özelliklerini kullanarak uygulayan [özellik kümesi eşlemesini](../../data/oledb/begin-propset-map.md) komutu sınıfında tanımlanır. Satır kümesi sınıfı komutu sınıf özelliği kullanılmasını ayarlar görüntülenir, ancak bir komut veya oturum nesnesi tarafından oluşturulduğunda satır kümesi çalışma zamanı özellikleri, kendine ait kopyasını sağlanır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** altdb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)