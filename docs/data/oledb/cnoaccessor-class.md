---
title: CNoAccessor sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
dev_langs:
- C++
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3110d20330d42fcb0816873ff3e8a25d1f8436ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cnoaccessor-class"></a>CNoAccessor Sınıfı
Şablon bağımsız değişken kullanılan (`TAccessor`) için şablon sınıfları gibi `CCommand` ve `CTable`, erişimci sınıfı bağımsız değişken gerektirir.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CNoAccessor  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `CNoAccessor` parametrelerini desteklemek veya sütunların çıktısı için sınıf istemediğinizde şablon bağımsız değişken olarak.  
  
 `CNoAccessor` diğer erişimci sınıfı yöntemleri için her biri karşılık gelen aşağıdaki saplama yöntemlerini uygular:  
  
-   **BindColumns** -sütunlar için erişimciler bağlar.  
  
-   `BindParameters` -Oluşturulan parametreleri sütunları bağlar.  
  
-   **Bağlama** -bağlamaları oluşturur.  
  
-   **Kapat** -erişimcisi kapatır.  
  
-   `ReleaseAccessors` -Sınıfı tarafından oluşturulan erişimciler serbest bırakır.  
  
-   `FreeRecordMemory` -Herhangi bir sütundan boşaltılması gerek geçerli kayıttaki alan boşaltır.  
  
-   `GetColumnInfo` -Açılan satır kümesinden sütun bilgileri alır.  
  
-   `GetNumAccessors` -Sınıfı tarafından oluşturulan erişimciler sayısını alır.  
  
-   `IsAutoAccessor` -Veri taşıma işlemi sırasında otomatik olarak için erişimci alınır true değerini döndürür.  
  
-   `GetHAccessor` -Belirtilen bir erişimci erişimci tanıtıcısı alır.  
  
-   `GetBuffer` -İşaretçiyi yer işareti arabelleğe alır.  
  
-   **NoBindOnNullRowset** -boş satır kümeleri Veri bağlamada engeller.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)