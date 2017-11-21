---
title: COLUMN_NAME_TYPE_SIZE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COLUMN_NAME_TYPE_SIZE
dev_langs: C++
helpviewer_keywords: COLUMN_NAME_TYPE_SIZE macro
ms.assetid: b10f8ef9-78ce-4ec9-b4cc-4278271a46dd
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9643354f4389e188d4b23ae4f47eb4bc300799bb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="columnnametypesize"></a>COLUMN_NAME_TYPE_SIZE
Satır kümesi bağlamada satır kümesindeki belirli sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makrosu ayrıca veri türü ve boyutunu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
COLUMN_NAME_TYPE_SIZE(  
pszName  
,   
wType  
,   
nLength  
,   
data  
 )  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pszName`  
 [in] Sütun adı için bir işaretçi. Adın bir UNICODE dizesi olması gerekir. Bu örneğin adı önüne bir 'L' koyarak gerçekleştirmek: `L"MyColumn"`.  
  
 `wType`  
 [in] Veri türü.  
  
 `nLength`  
 [in] Bayt cinsinden veri boyutu.  
  
 `data`  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
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
 [COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)