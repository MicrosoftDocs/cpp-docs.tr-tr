---
title: "CAccessor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
dev_langs: C++
helpviewer_keywords: CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 759ea7436124c1806ae26fb6a91a59d56c86d04a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="caccessor-class"></a>CAccessor Sınıfı
Erişimci türleri birini temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      template < class   
      T  
       >  
class CAccessor : public CAccessorBase, public T  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Kullanıcı kayıt sınıfı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir kayıt statik olarak bir veri kaynağına bağlı olduğunda kullanılır. Kayıt arabellek içeriyor. Bu sınıf, bir satır kümesinde çoklu erişimci destekler.  
  
 Yapı ve veritabanı türü bildiğiniz durumlarda bu erişimcisi türünü kullanın.  
  
 Erişimcisi bellek noktası alanları içeriyorsa (gibi bir `BSTR` veya arabirim) olması gerekir serbest, üye işlevini çağırın [CAccessorRowset::FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md) önce sonraki kaydı okur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)