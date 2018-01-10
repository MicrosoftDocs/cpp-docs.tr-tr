---
title: COLUMN_NAME_EX | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COLUMN_NAME_EX
dev_langs: C++
helpviewer_keywords: COLUMN_NAME_EX macro
ms.assetid: 4f916a85-f6ae-464a-9cbe-0a56dbb274a6
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5658a2d0fb06f6bb9e9b8f2ab062f621b189cc75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="columnnameex"></a>COLUMN_NAME_EX
Satır kümesi bağlamada satır kümesindeki belirli sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makrosu veri türü, boyutu, duyarlık, Ölçek, sütun uzunluğu ve sütun durumunu da alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
COLUMN_NAME_EX(  
pszName  
,   
wType  
,   
nLength  
,   
nPrecision  
,   
nScale  
,   
data  
,   
length  
,   
status )  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pszName`  
 [in] Sütun adı için bir işaretçi. Adın bir UNICODE dizesi olması gerekir. Bu örneğin adı önüne bir 'L' koyarak gerçekleştirmek: `L"MyColumn"`.  
  
 `wType`  
 [in] Veri türü.  
  
 `nLength`  
 [in] Bayt cinsinden veri boyutu.  
  
 `nPrecision`  
 [in] Veri alınırken kullanılacak en yüksek duyarlık ve `wType` olan `DBTYPE_NUMERIC`. Aksi takdirde, bu parametre yoksayılır.  
  
 `nScale`  
 [in] Veri alınırken kullanılacak ölçek ve `wType` olan `DBTYPE_NUMERIC` veya **DBTYPE_DECIMAL**.  
  
 `data`  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *uzunluğu*  
 [in] Sütun uzunluğu bağlanması için değişken.  
  
 *durumu*  
 [in] Sütun durumuna bağlı olmasını değişkeni.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [COLUMN_NAME](../../data/oledb/column-name.md) nerede hakkında bilgi için **COLUMN_NAME_\***  makroları kullanılır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_NAME](../../data/oledb/column-name.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)