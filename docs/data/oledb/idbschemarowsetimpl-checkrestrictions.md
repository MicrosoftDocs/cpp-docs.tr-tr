---
title: IDBSchemaRowsetImpl::CheckRestrictions | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CheckRestrictions
- IDBSchemaRowsetImpl::CheckRestrictions
- IDBSchemaRowsetImpl.CheckRestrictions
dev_langs:
- C++
helpviewer_keywords:
- CheckRestrictions method
ms.assetid: 3c9d77d2-0e4b-48fa-80db-d735da19f1cf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ab19a661e02bcfd0f5ca3730c69e22adfc3ae4db
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="idbschemarowsetimplcheckrestrictions"></a>IDBSchemaRowsetImpl::CheckRestrictions
Bir şema satır kümesi karşı kısıtlamaların geçerliliğini denetler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
HRESULT CheckRestrictions(REFGUID rguidSchema,  
   ULONG cRestrictions,  const VARIANT rgRestrictions[]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `rguidSchema`  
 [in] İstenen şema satır kümesi GUID'si başvuru (örneğin, `DBSCHEMA_TABLES`).  
  
 `cRestrictions`  
 [in] Tüketici şema satır kümesi için geçirilen kısıtlamaları sayısı.  
  
 `rgRestrictions`  
 [in] Uzunluk dizisi *cRestrictions* Kısıtlama değerlerinin ayarlanacak. Daha fazla bilgi için açıklamasına bakın `rgRestrictions` parametresinde [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `CheckRestrictions` bir şema satır kümesi karşı kısıtlamaların geçerliliğini denetlemek için. İçin kısıtlamalar denetler `DBSCHEMA_TABLES`, **DBSCHEMA_COLUMNS**, ve **DBSCHEMA_PROVIDER_TYPES** şema satır kümeleri. Bir tüketici 's belirlemek için çağrısından çağrısı **IDBSchemaRowset::GetRowset** doğrudur. Şema satır kümeleri Yukarıda listelenenler dışında desteklemek istiyorsanız, bu görevi gerçekleştirmek için kendi işlevi oluşturmanız gerekir.  
  
 `CheckRestrictions` Tüketici çağırma varsa belirler [GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) doğru kısıtlama ve doğru kısıtlama türüne (örneğin, bir `VT_BSTR` bir dize) sağlayıcının desteklediği. Kısıtlamaları doğru sayıda desteklenip desteklenmediğini belirler. Varsayılan olarak, `CheckRestrictions` sağlayıcısı aracılığıyla ister [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) çağrısı, belirli bir satır kümesinde destekliyorsa hangi kısıtlamaları. Ardından tüketici kısıtlamaları sağlayıcı tarafından desteklenenler karşı karşılaştırır ve başarılı veya başarısız olur.  
  
 Şema satır kümeleri hakkında daha fazla bilgi için bkz: [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu* Windows SDK'sındaki.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDBSchemaRowsetImpl sınıfı](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl sınıfı üyeleri](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Şema Satır Kümesi Sınıfları ve Typedef Sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)