---
title: BEGIN_COLUMN_MAP | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_COLUMN_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_COLUMN_MAP macro
ms.assetid: d6ffe633-e0da-4e33-8faa-f7f259d05420
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 29e62e08ef03d863b17ea0d269cf049b23602774
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="begincolumnmap"></a>BEGIN_COLUMN_MAP
Sütun eşleme girişi başlangıcını işaretler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
BEGIN_COLUMN_MAP(  
x  
 )  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Kullanıcı kayıt sınıfı adını türetilmiş `CAccessor`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu bir satır kümesi üzerinde tek bir erişimcisi söz konusu olduğunda kullanılır. Satır kümesinde çoklu erişimci varsa, [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
 `BEGIN_COLUMN_MAP` Makrosu ile tamamlandı `END_COLUMN_MAP` makrosu. Yalnızca bir erişimci kullanıcı kaydına gerekli olduğunda bu makrosu kullanılır.  
  
 Sütunları bağlamak istediğiniz satır kümesi alanlarına karşılık gelir.  
  
## <a name="example"></a>Örnek  
 Bir örnek sütun ve parametre eşlemesi şöyledir:  
  
 <!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)