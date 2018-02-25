---
title: "CNoRowset sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
dev_langs:
- C++
helpviewer_keywords:
- CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a509f93a72e1f48bc6af0e372f0353cdebb3edb8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cnorowset-class"></a>CNoRowset Sınıfı
Şablon bağımsız değişken kullanılan (`TRowset`) için [CCommand](../../data/oledb/ccommand-class.md) veya [CTable](../../data/oledb/ctable-class.md).  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TAccessor`  
 Bir erişimci sınıfı. Varsayılan, `CAccessorBase` değeridir.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `CNoRowset` komutu bir satır kümesi döndürmezse şablon bağımsız değişken olarak.  
  
 `CNoRowset` diğer erişimci sınıfı yöntemleri için her biri karşılık gelen aşağıdaki saplama yöntemlerini uygular:  
  
-   **BindFinished** -bağlama tamamlandığında gösterir (döndürür `S_OK`).  
  
-   **Kapat** -satır ve geçerli Irowset arabirimi serbest bırakır.  
  
-   `GetIID` -Bağlantı noktası arabirimi Kimliğini alır.  
  
-   **Getınterface** -bir arabirim alır.  
  
-   `GetInterfacePtr` -Kapsüllenmiş arabirim işaretçisi alır.  
  
-   **Set erişimcisi** -erişimcisi için bir işaretçi ayarlar.  
  
-   **SetupOptionalRowsetInterfaces** -isteğe bağlı arabirimler satır kümesi için ayarlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)