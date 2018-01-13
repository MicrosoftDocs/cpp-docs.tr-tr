---
title: "CNoRowset sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
dev_langs: C++
helpviewer_keywords: CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 901d857b5095dd882a368b9a87e8a7d38d20bc42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cnorowset-class"></a>CNoRowset Sınıfı
Şablon bağımsız değişken kullanılan (`TRowset`) için [CCommand](../../data/oledb/ccommand-class.md) veya [CTable](../../data/oledb/ctable-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TAccessor`  
 Bir erişimci sınıfı. Varsayılan, `CAccessorBase` değeridir.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `CNoRowset` komutu bir satır kümesi döndürmezse şablon bağımsız değişken olarak.  
  
 `CNoRowset`diğer erişimci sınıfı yöntemleri için her biri karşılık gelen aşağıdaki saplama yöntemlerini uygular:  
  
-   **BindFinished** -bağlama tamamlandığında gösterir (döndürür `S_OK`).  
  
-   **Kapat** -satır ve geçerli Irowset arabirimi serbest bırakır.  
  
-   `GetIID`-Bağlantı noktası arabirimi Kimliğini alır.  
  
-   **Getınterface** -bir arabirim alır.  
  
-   `GetInterfacePtr`-Kapsüllenmiş arabirim işaretçisi alır.  
  
-   **Set erişimcisi** -erişimcisi için bir işaretçi ayarlar.  
  
-   **SetupOptionalRowsetInterfaces** -isteğe bağlı arabirimler satır kümesi için ayarlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)