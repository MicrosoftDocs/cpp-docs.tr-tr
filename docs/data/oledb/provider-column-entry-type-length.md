---
title: PROVIDER_COLUMN_ENTRY_TYPE_LENGTH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
dev_langs: C++
helpviewer_keywords: PROVIDER_COLUMN_ENTRY_TYPE_LENGTH macro
ms.assetid: a60b1a8b-0903-4ff4-91ec-ed62126449fb
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8b7f072c2a83bb476c4e088d36643e21bd075473
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="providercolumnentrytypelength"></a>PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
PROVIDER_COLUMN_ENTRY_TYPE_LENGTH(  
name  
, ordinal, dbtype, size, member )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *adı*  
  
 [in] Sütun adı.  
  
 `ordinal`  
 [in] Sütun numarası. Bir yer işareti sütun sütun olmadığı sürece sütun numarası 0 olmalıdır.  
  
 `dbtype`  
 [in] Veri türü [DBTYPE](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
 `size`  
 [in] Sütun boyutunu bayt cinsinden.  
  
 `member`  
 [in] Üye değişkeni veri sınıfında verileri depolar.  
  
## <a name="remarks"></a>Açıklamalar  
 Benzer şekilde [provıder_column_entry_length](../../data/oledb/provider-column-entry-length.md) ancak boyutu yanı sıra sütunun veri türünü belirtmenizi sağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları için makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md)