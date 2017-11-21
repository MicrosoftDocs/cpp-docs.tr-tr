---
title: "CAccessorRowset sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CAccessorRowset
- ATL.CAccessorRowset
- ATL::CAccessorRowset
dev_langs: C++
helpviewer_keywords: CAccessorRowset class
ms.assetid: bd4f58ed-cebf-4d43-8985-1e5fcbf06953
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4b7340baabb24ef18806442504a4bd5dadf73a41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="caccessorrowset-class"></a>CAccessorRowset Sınıfı
Bir satır kümesi ve onun ilişkili erişimciler tek bir sınıftaki yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <   
   class TAccessor = CNoAccessor,    
   template <typename T> class TRowset = CRowset    
>  
class CAccessorRowset :   
   public TAccessor,    
   public TRowset<TAccessor>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TAccessor`  
 Bir erişimci sınıfı.  
  
 `TRowset`  
 Bir satır kümesi sınıfı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Bağlama](../../data/oledb/caccessorrowset-bind.md)|Bağlamaları oluşturur (kullanılır **bBind** false olarak belirtilen [CCommand::Open](../../data/oledb/ccommand-open.md)).|  
|[CAccessorRowset](../../data/oledb/caccessorrowset-caccessorrowset.md)|Oluşturucu.|  
|[Kapat](../../data/oledb/caccessorrowset-close.md)|Satır kümesi ve tüm erişimciler kapatır.|  
|[FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md)|Herhangi bir sütundan boşaltılması gerek geçerli kayıttaki alan boşaltır.|  
|[GetColumnInfo](../../data/oledb/caccessorrowset-getcolumninfo.md)|Implements [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx).|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf `TAccessor` erişimci yönetir. Sınıf *CRowset* satır yönetir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)