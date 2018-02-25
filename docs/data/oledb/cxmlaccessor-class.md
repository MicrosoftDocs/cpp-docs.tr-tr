---
title: "CXMLAccessor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CXMLAccessor
- CXMLAccessor
- ATL.CXMLAccessor
dev_langs:
- C++
helpviewer_keywords:
- CXMLAccessor class
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1d8d42599e9fe87355dc5392e1a473aa0a9c1e1d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cxmlaccessor-class"></a>CXMLAccessor Sınıfı
Veri deposunun şeması (temel yapısı) olanağıyla olduğunda veri kaynakları dize verilerini erişmenize olanak tanır.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CXMLAccessor : public CDynamicStringAccessorW  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)|Sütun bilgileri alır.|  
|[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)|Bir tablonun tüm içeriği satırlara göre alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ancak, `CXMLAccessor` farklıdır `CDynamicStringAccessorW` içeren XML biçimli (etiketli) veri olarak veri deposundan erişilen tüm verileri dönüştürür. Bu çıktı XML kullanan Web sayfaları için özellikle yararlıdır. XML etiket adları veri deposunun sütun adları mümkün olduğunca yakın eşleşir.  
  
 Kullanım `CDynamicAccessor` sütun bilgileri almak için yöntemleri. Erişimci çalışma zamanında dinamik olarak oluşturmak için bu sütun bilgileri kullanın.  
  
 Sütun bilgileri oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Sütun bilgileri kullanarak elde [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) veya sütun veri kullanarak satırlara göre elde [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md).  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor sınıfı](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CDynamicStringAccessor sınıfı](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicStringAccessorA sınıfı](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW sınıfı](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CManualAccessor Sınıfı](../../data/oledb/cmanualaccessor-class.md)