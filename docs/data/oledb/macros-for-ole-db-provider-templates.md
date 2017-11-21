---
title: "OLE DB sağlayıcı şablonları için makrolar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.templates.ole
dev_langs: C++
helpviewer_keywords:
- OLE DB provider templates, macros
- macros, OLE DB Provider Templates
- Provider Template macros (OLE DB)
- OLE DB Provider Template macros
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 11a5ae3d0ba5c3da517a380adf795e579d0dce51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="macros-for-ole-db-provider-templates"></a>OLE DB Sağlayıcı Şablonları için Makrolar
OLE DB Şablonları sağlayıcısı makroları Aşağıdaki kategorilerde işlevleri sunar:  
  
### <a name="property-set-map-macros"></a>Özellik kümesi eşleme makroları  
  
|||  
|-|-|  
|[BEGIN_PROPERTY_SET](../../data/oledb/begin-property-set.md)|Bir özellik kümesi başlangıcını işaretler.|  
|[BEGIN_PROPERTY_SET_EX](../../data/oledb/begin-property-set-ex.md)|Bir özellik kümesi başlangıcını işaretler.|  
|[BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)|Bir özelliğin başına kümesi işaretleri gizli veya sağlayıcı kapsamı dışında tanımlanmış.|  
|[CHAIN_PROPERTY_SET](../../data/oledb/chain-property-set.md)|Özellik grupları zincir oluşturur.|  
|[END_PROPERTY_SET](../../data/oledb/end-property-set.md)|Bir özellik kümesi sonunu işaretler.|  
|[END_PROPSET_MAP](../../data/oledb/end-propset-map.md)|Bir özellik kümesi eşlemesini sonunu işaretler.|  
|[PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)|Bir özellik için varsayılan bir değer kümesi içinde belirli bir özellik ayarlar.|  
|[PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)|Belirli bir özellik tarafından sağlanan bir değer olarak ayarlanan bir özelliği ayarlar. Ayrıca, bayrakları ve seçenekleri ayarlamanıza olanak sağlar.|  
|[PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)|Belirli bir özellik tarafından sağlanan bir değer olarak ayarlanan bir özelliği ayarlar.|  
  
### <a name="column-map-macros"></a>Sütun eşleme makroları  
  
|||  
|-|-|  
|[BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md)|Sağlayıcı sütun eşlemesi girdileri başlangıcını işaretler.|  
|[END_PROVIDER_COLUMN_MAP](../../data/oledb/end-provider-column-map.md)|Sağlayıcı sütun eşlemesi girdileri sonunu işaretler.|  
|[PROVIDER_COLUMN_ENTRY](../../data/oledb/provider-column-entry.md)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.|  
|[PROVIDER_COLUMN_ENTRY_GN](../../data/oledb/provider-column-entry-gn.md)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütunun boyutu, veri türü, duyarlık, ölçek ve şema satır kümesi GUID'si belirtebilirsiniz.|  
|[PROVIDER_COLUMN_ENTRY_FIXED](../../data/oledb/provider-column-entry-fixed.md)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütunun veri türünü belirtebilirsiniz.|  
|[PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Sütun boyutu belirtebilirsiniz.|  
|[PROVIDER_COLUMN_ENTRY_STR](../../data/oledb/provider-column-entry-str.md)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Bu sütun türü bir dize olduğunu varsayar.|  
|[PROVIDER_COLUMN_ENTRY_TYPE_LENGTH](../../data/oledb/provider-column-entry-type-length.md)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Provıder_column_entry_length benzer, ama boyutu yanı sıra sütunun veri türünü belirtmenizi sağlar.|  
|[PROVIDER_COLUMN_ENTRY_WSTR](../../data/oledb/provider-column-entry-wstr.md)|Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder. Bu, Unicode karakter dizesi sütun türü olduğunu varsayar.|  
  
### <a name="schema-rowset-macros"></a>Şema satır kümesi makroları  
  
|||  
|-|-|  
|[BEGIN_SCHEMA_MAP](../../data/oledb/begin-schema-map.md)|Şema eşleme başlangıcını işaretler.|  
|[SCHEMA_ENTRY](../../data/oledb/schema-entry.md)|Bir GUID sınıfı ile ilişkilendirir.|  
|[END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)|Şema eşleme sonunu işaretler.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md)   
 [OLE DB sağlayıcı şablonları başvurusu](../../data/oledb/ole-db-provider-templates-reference.md)