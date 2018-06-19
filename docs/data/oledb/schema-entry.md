---
title: SCHEMA_ENTRY | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SCHEMA_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- SCHEMA_ENTRY macro
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 665b337861959b28670a0b2e57649814853a7384
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109527"
---
# <a name="schemaentry"></a>SCHEMA_ENTRY
Bir GUID sınıfı ile ilişkilendirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      SCHEMA_ENTRY(guid,  
   rowsetClass);   
```  
  
#### <a name="parameters"></a>Parametreler  
 `guid`  
 Bir şema satır kümesi GUID'si. Bkz: [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu* şema satır kümeleri ve GUID'ler listesi.  
  
 *rowsetClass*  
 Şema satır kümesi temsil etmek için oluşturulan sınıf.  
  
## <a name="remarks"></a>Açıklamalar  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) sorgu GUID'lerin listesini harita olabilir veya bir GUID verildiyse bir satır kümesi oluşturabilirsiniz. Şema satır kümesi `IDBSchemaRowsetImpl` oluşturur standart benzer `CRowsetImpl`-sağlamanız gerekir dışında türetilmiş sınıf, bir **yürütme** aşağıdaki imzası yöntemi:  
  
```  
HRESULT Execute (LONG* pcRowsAffected,  
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