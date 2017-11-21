---
title: CDynamicAccessor::GetColumnInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetColumnInfo
- ATL.CDynamicAccessor.GetColumnInfo
- ATL::CDynamicAccessor::GetColumnInfo
- CDynamicAccessor.GetColumnInfo
- CDynamicAccessor::GetColumnInfo
dev_langs: C++
helpviewer_keywords: GetColumnInfo method
ms.assetid: 7f2102ea-b7cc-4714-812f-3ca2857f4b9a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c3d3b24ffce579d3a74706ca9a238059ed8eb08f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicaccessorgetcolumninfo"></a>CDynamicAccessor::GetColumnInfo
Çoğu tüketiciler tarafından gerekli sütun meta verileri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT GetColumnInfo(   
   IRowset* pRowset,   
   DBORDINAL* pColumns,   
   DBCOLUMNINFO** ppColumnInfo,   
   OLECHAR** ppStringsBuffer    
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRowset`  
 [in] Bir işaretçi [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) arabirimi.  
  
 *pColumns*  
 [out] Hangi satır kümesinde sütun sayısını döndürmek bellekte bir işaretçi; varsa bu sayı yer işareti sütun içerir.  
  
 *ppColumnInfo*  
 [out] Bellek, bir dizi döndürmek bir işaretçi **DBCOLUMNINFO** yapıları. "DBCOLUMNINFO yapıları" bölümüne bakın [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 `ppStringsBuffer`  
 [out] Bellek, depolama tüm dize değerleri için bir işaretçi dönmek için bir işaretçi (içinde ya da kullanılan adları *ColumnID* veya *pwszName*) tek ayırma bloğu içinde.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) içinde *OLE DB Programcının Başvurusu* veri türleri hakkında bilgi için **DBORDINAL**, **DBCOLUMNINFO**, ve **OLECHAR**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)