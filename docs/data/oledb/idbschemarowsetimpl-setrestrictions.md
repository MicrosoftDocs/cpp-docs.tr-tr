---
title: IDBSchemaRowsetImpl::SetRestrictions | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDBSchemaRowsetImpl::SetRestrictions
- SetRestrictions
- IDBSchemaRowsetImpl.SetRestrictions
dev_langs:
- C++
helpviewer_keywords:
- SetRestrictions method
ms.assetid: 707d5065-b853-4d38-9b67-3066b4d3b279
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f3ac45e93e0a2561bd8ab24dc7c0c6b19b245b60
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="idbschemarowsetimplsetrestrictions"></a>IDBSchemaRowsetImpl::SetRestrictions
Belirli şema satır kümesinde destek hangi kısıtlamaları belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
void SetRestrictions(ULONG cRestrictions,  
  GUID* /* rguidSchema */,  
   ULONG* rgRestrictions);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cRestrictions`  
 [in] Bazı kısıtlamalar `rgRestrictions` dizi ve içinde GUID'ler sayısı `rguidSchema` dizi.  
  
 `rguidSchema`  
 [in] Şema satır kümeleri, kısıtlamalar getirmek için GUID'lerini dizisi. Bir şema satır kümesi GUID'si her dizi öğesi içerir (örneğin, `DBSCHEMA_TABLES`).  
  
 `rgRestrictions`  
 [in] Uzunluk dizisi `cRestrictions` Kısıtlama değerlerinin ayarlanacak. Her öğe GUID ile tanımlanan şeması satır kümesi üzerindeki kısıtlamaları karşılık gelir. Bir şema satır kümesi sağlayıcı tarafından desteklenmiyorsa, öğenin sıfır olarak ayarlanır. Aksi takdirde, **ULONG** değeri bu şeması satır kümesi üzerinde desteklenen kısıtlamaları temsil eden bir bit maskesi içerir. Şema satır kümesi GUID'ler tablo üzerinde kısıtlamaları karşılık gelen bir belirli şema satır kümesi için daha fazla bilgi için başvurun içinde [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu* Windows SDK.  
  
## <a name="remarks"></a>Açıklamalar  
 **IDBSchemaRowset** nesne çağrıları `SetRestrictions` hangi kısıtlamaları belirlemek için belirli şema satır kümesinde desteği (çağrılır [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) upcasted işaretçi aracılığıyla). Kısıtlamalar yalnızca eşleşen satırları getirmeye tüketicileri izin ver (örneğin, tüm sütunlara "MyTable" tablosunda Bul). Kısıtlamaları isteğe bağlıdır ve durumda hiçbirinin desteklenir (varsayılan), tüm veriler her zaman döndürülür.  
  
 Bu yöntem varsayılan uygulaması ayarlar `rgRestrictions` 0 öğeleri dizisi. Varsayılan oturum sınıfınızda varsayılan dışındaki kısıtlamaları ayarlamak için geçersiz kılar.  
  
 Şema satır kümesi desteği uygulama hakkında daha fazla bilgi için bkz: [şema satır kümelerini destekleme](../../data/oledb/supporting-schema-rowsets.md).  
  
 Şema satır kümeleri destekleyen bir sağlayıcı örneği için bkz: [UpdatePV](../../visual-cpp-samples.md) örnek.  
  
 Şema satır kümeleri hakkında daha fazla bilgi için bkz: [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu* Windows SDK'sındaki.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDBSchemaRowsetImpl sınıfı](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl sınıfı üyeleri](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [Şema satır kümelerini destekleme](../../data/oledb/supporting-schema-rowsets.md)   
 [UpdatePV](../../visual-cpp-samples.md)