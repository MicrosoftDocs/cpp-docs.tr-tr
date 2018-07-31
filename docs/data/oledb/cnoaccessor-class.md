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
ms.openlocfilehash: 0527f4b154b4b5d0dc07b2b152a3975f49746abf
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336745"
---
# <a name="cnoaccessor-class"></a>CNoAccessor Sınıfı
Bir şablon bağımsız değişkeni kullanılabilir (`TAccessor`) için şablon sınıfları gibi `CCommand` ve `CTable`, bir erişimci sınıfında bağımsız değişken gerektirir.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CNoAccessor  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `CNoAccessor` parametrelerini veya sütunlarını çıkış desteklemeye sınıfı istemediğinizde bir şablon bağımsız değişkeni olarak.  
  
 `CNoAccessor` karşılık gelen her biri için diğer erişimcisi sınıf yöntemleri aşağıdaki saptama yöntemleri uygular:  
  
-   `BindColumns` -Sütunları için erişimciler bağlar.  
  
-   `BindParameters` -Sütun oluşturulan parametreleri bağlar.  
  
-   `Bind` -Bağlamaları oluşturur.  
  
-   `Close` -Erişimci kapatır.  
  
-   `ReleaseAccessors` -Sınıfı tarafından oluşturulan erişimcileri serbest bırakır.  
  
-   `FreeRecordMemory` -Boşaltılması için gereken geçerli kayıt tüm sütunları bırakır.  
  
-   `GetColumnInfo` -Açık satır kümesinden sütun bilgileri alır.  
  
-   `GetNumAccessors` -Sınıfı tarafından oluşturulan erişimcileri sayısını alır.  
  
-   `IsAutoAccessor` -Veri taşıma işlemi sırasında otomatik olarak için erişimci alınır true değerini döndürür.  
  
-   `GetHAccessor` -Belirtilen bir erişimci erişimci tanıtıcısı alır.  
  
-   `GetBuffer` -Yer işareti arabellek için işaretçi alır.  
  
-   `NoBindOnNullRowset` -Boş satır kümeleri üzerinde veri bağlamasını engeller.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)