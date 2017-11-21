---
title: BEGIN_ACCESSOR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_ACCESSOR
dev_langs: C++
helpviewer_keywords:
- BEGIN_ACCESSOR macro, syntax
- BEGIN_ACCESSOR macro
ms.assetid: 59d0ff3e-7cfd-4ce8-9a1c-d664c0892a52
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 74d8d2197553f9fd2b1f5452236b343424d29148
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="beginaccessor"></a>BEGIN_ACCESSOR
Erişimci girdiyi başlangıcını işaretler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
BEGIN_ACCESSOR(  
num  
,   
bAuto  
 )  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 *NUM*  
 [in] Bu erişimcisi eşlemesindeki erişimcisi için sıfır uzaklığı numarası.  
  
 *bDil*  
 [in] Bu erişimcisi otomatik erişimci veya el ile erişimci olup olmadığını belirtir. Varsa **true**, erişimcisi otomatik; ise **yanlış**, erişimcisi el ile gerçekleştirilir. Otomatik erişimci veri taşıma işlemleri için sizin için alınmadığı anlamına gelir.  
  
## <a name="remarks"></a>Açıklamalar  
 Üzerinde bir satır kümesinde çoklu erişimci söz konusu olduğunda belirtmeniz gerekir. `BEGIN_ACCESSOR_MAP` ve `BEGIN_ACCESSOR` makrosu tek tek her erişimcisi için. `BEGIN_ACCESSOR` Makrosu ile tamamlandı `END_ACCESSOR` makrosu. `BEGIN_ACCESSOR_MAP` Makrosu ile tamamlandı `END_ACCESSOR_MAP` makrosu.  
  
## <a name="example"></a>Örnek  
 Bkz: [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)