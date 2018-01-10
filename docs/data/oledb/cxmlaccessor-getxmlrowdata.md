---
title: CXMLAccessor::GetXMLRowData | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CXMLAccessor::GetXMLRowData
- ATL.CXMLAccessor.GetXMLRowData
- CXMLAccessor::GetXMLRowData
- CXMLAccessor.GetXMLRowData
- GetXMLRowData
dev_langs: C++
helpviewer_keywords: GetXMLRowData method
ms.assetid: 156b66e3-42fd-491c-8943-38cf5e36f687
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1cfd67065b267f01704bb0658b89d9bab2186100
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cxmlaccessorgetxmlrowdata"></a>CXMLAccessor::GetXMLRowData
Bir tablonun tüm içeriği satır XML biçimli dize verilerini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT GetXMLRowData(   
   CSimpleStringW& strOutput,   
   bool bAppend = false    
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `strOutput`  
 [out] Alınacak tablo verileri içeren bir arabellek referansı. Verileri veri deposunun sütun adlarıyla XML etiket adları ile dize veri olarak biçimlendirilir.  
  
 *bAppend*  
 [in] Bir dize çıktı verilerini sonuna olup olmayacağını belirten bir Boole değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki XML satır veri nasıl biçimlendirildiğini gösterir. `DATA`Aşağıda satır verileri temsil eder. Kullanmak istediğiniz satıra taşıma yöntemleri taşıyın.  
  
 `<row>`  
  
 `<column name>DATA</column name>`  
  
 `</row>`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CXMLAccessor Sınıfı](../../data/oledb/cxmlaccessor-class.md)