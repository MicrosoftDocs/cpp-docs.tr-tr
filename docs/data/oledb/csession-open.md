---
title: CSession::Open | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: c2050c2c-9817-4857-be49-189f346968f6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b3aa0f6b694bc594ec00511ce39b7887bf26ecae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csessionopen"></a>CSession::Open
Veri kaynağı nesnesi için yeni bir oturum açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT Open(  
   const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ds`  
 [in] Oturum açılacak olduğu veri kaynağı.  
  
 *pPropSet*  
 [in] Bir dizi için bir işaretçi [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) özellikleri ve ayarlanacak değerleri içeren yapıları. Bkz: [özellik kümeleri ve özellik grupları](https://msdn.microsoft.com/en-us/library/ms713696.aspx) içinde *OLE DB Programcının Başvurusu* Windows SDK.  
  
 `ulPropSets`  
 [in] Sayısı [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) yapıları geçirilen *pPropSet* bağımsız değişkeni.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Veri kaynağı nesnesi kullanılarak açmalısınız [CDataSource::Open](../../data/oledb/cdatasource-open.md) kendisine geçirmeden önce `CSession::Open`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSession Sınıfı](../../data/oledb/csession-class.md)