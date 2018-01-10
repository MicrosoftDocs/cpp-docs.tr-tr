---
title: "CNoAccessor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
dev_langs: C++
helpviewer_keywords: CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 799fe151b22748da25901139a5aefe67460b2484
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cnoaccessor-class"></a>CNoAccessor Sınıfı
Şablon bağımsız değişken kullanılan (`TAccessor`) için şablon sınıfları gibi `CCommand` ve `CTable`, erişimci sınıfı bağımsız değişken gerektirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CNoAccessor  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `CNoAccessor` parametrelerini desteklemek veya sütunların çıktısı için sınıf istemediğinizde şablon bağımsız değişken olarak.  
  
 `CNoAccessor`diğer erişimci sınıfı yöntemleri için her biri karşılık gelen aşağıdaki saplama yöntemlerini uygular:  
  
-   **BindColumns** -sütunlar için erişimciler bağlar.  
  
-   `BindParameters`-Oluşturulan parametreleri sütunları bağlar.  
  
-   **Bağlama** -bağlamaları oluşturur.  
  
-   **Kapat** -erişimcisi kapatır.  
  
-   `ReleaseAccessors`-Sınıfı tarafından oluşturulan erişimciler serbest bırakır.  
  
-   `FreeRecordMemory`-Herhangi bir sütundan boşaltılması gerek geçerli kayıttaki alan boşaltır.  
  
-   `GetColumnInfo`-Açılan satır kümesinden sütun bilgileri alır.  
  
-   `GetNumAccessors`-Sınıfı tarafından oluşturulan erişimciler sayısını alır.  
  
-   `IsAutoAccessor`-Veri taşıma işlemi sırasında otomatik olarak için erişimci alınır true değerini döndürür.  
  
-   `GetHAccessor`-Belirtilen bir erişimci erişimci tanıtıcısı alır.  
  
-   `GetBuffer`-İşaretçiyi yer işareti arabelleğe alır.  
  
-   **NoBindOnNullRowset** -boş satır kümeleri Veri bağlamada engeller.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)