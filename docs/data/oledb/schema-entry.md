---
title: SCHEMA_ENTRY | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SCHEMA_ENTRY
dev_langs: C++
helpviewer_keywords: SCHEMA_ENTRY macro
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 12a4026e94ea5fe5e310e0aeec7cdad10d33d2bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="schemaentry"></a>SCHEMA_ENTRY
Bir GUID sınıfı ile ilişkilendirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      SCHEMA_ENTRY(  
   guid,  
   rowsetClass   
);   
```  
  
#### <a name="parameters"></a>Parametreler  
 `guid`  
 Bir şema satır kümesi GUID'si. Bkz: [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu* şema satır kümeleri ve GUID'ler listesi.  
  
 *rowsetClass*  
 Şema satır kümesi temsil etmek için oluşturulan sınıf.  
  
## <a name="remarks"></a>Açıklamalar  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) sorgu GUID'lerin listesini harita olabilir veya bir GUID verildiyse bir satır kümesi oluşturabilirsiniz. Şema satır kümesi `IDBSchemaRowsetImpl` oluşturur standart benzer `CRowsetImpl`-sağlamanız gerekir dışında türetilmiş sınıf, bir **yürütme** aşağıdaki imzası yöntemi:  
  
```  
HRESULT Execute (
    LONG* pcRowsAffected,  
    ULONG cRestrictions,  
    const VARIANT* rgRestrictions);  
```  
  
 Bu **yürütme** işlevi satır kümesinin veri doldurur. ATL Proje Sihirbazı oluşturur açıklandığı gibi [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu*, üç ilk şema satır kümeleri projesinde her üç zorunlu OLE DB şemaları için:  
  
-   `DBSCHEMA_TABLES`  
  
-   **DBSCHEMA_COLUMNS**  
  
-   **DBSCHEMA_PROVIDER_TYPES**  
  
 Sihirbaz aynı zamanda şema eşlemesinde üç karşılık gelen girdilere ekler. Bkz: [OLE DB Şablon sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md) sağlayıcı oluşturmak için sihirbazı kullanma hakkında daha fazla bilgi için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları için makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [BEGIN_SCHEMA_MAP](../../data/oledb/begin-schema-map.md)   
 [END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)