---
title: CXMLAccessor sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CXMLAccessor
- CXMLAccessor
- ATL.CXMLAccessor
- ATL.CXMLAccessor.GetXMLColumnData
- CXMLAccessor::GetXMLColumnData
- CXMLAccessor.GetXMLColumnData
- ATL::CXMLAccessor::GetXMLColumnData
- GetXMLColumnData
- ATL::CXMLAccessor::GetXMLRowData
- ATL.CXMLAccessor.GetXMLRowData
- CXMLAccessor::GetXMLRowData
- CXMLAccessor.GetXMLRowData
- GetXMLRowData
dev_langs:
- C++
helpviewer_keywords:
- CXMLAccessor class
- GetXMLColumnData method
- GetXMLRowData method
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f25d02b5b8b86a70f63dc2b0ca8d2ba9cb60066b
ms.sourcegitcommit: b217daee32d3413cf33753d9b4dc35a0022b1bfa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233424"
---
# <a name="cxmlaccessor-class"></a>CXMLAccessor Sınıfı
Veri deposunun şeması (temelindeki) olanağıyla olduğunda dize verileri veri kaynaklarına erişim sağlar.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CXMLAccessor : public CDynamicStringAccessorW  
```  

## <a name="requirements"></a>Gereksinimler  
 **Üst bilgi**: atldbcli.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[GetXMLColumnData](#getxmlcolumndata)|Sütun bilgileri alır.|  
|[GetXMLRowData](#getxmlrowdata)|Bir tablonun tüm içeriğini satırlara göre alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ancak, `CXMLAccessor` farklıdır `CDynamicStringAccessorW` içeren XML biçimli (etiketli) veri veri deposundan erişilen tüm verileri dönüştürür. Bu çıkış XML kullanan Web sayfaları için özellikle kullanışlıdır. XML etiket adları veri deposunun sütun adları mümkün olduğunca yakın eşleşir.  
  
 Kullanım `CDynamicAccessor` sütun bilgisi edinmek için. Erişimci çalışma zamanında dinamik olarak oluşturmak için bu sütun bilgileri kullanın.  
  
 Sütun bilgisi oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Sütun bilgileri kullanarak elde [GetXMLColumnData](#getxmlcolumndata) veya sütun verileri kullanarak satır elde [GetXMLRowData](#getxmlrowdata).  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]  

## <a name="getxmlcolumndata"></a> CXMLAccessor::GetXMLColumnData
Sütunu örneğe göre olarak XML biçimli dize verileri, bir tablonun sütun türü bilgisini alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT GetXMLColumnData(CSimpleStringW& strOutput) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *strOutput*  
 [out] Alınacak sütun türü bilgilerini içeren bir dize arabelleğine başvuru. Dize veri deposunun sütun adları eşleşen XML etiket adları ile biçimlendirilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki XML sütun türü bilgisini nasıl biçimlendirildiğini gösterir. `type` sütunun veri türünü belirtir. OLE DB veri türlerini, erişilen veritabanı, veri türleri temel unutmayın.  
  
 `<columninfo>`  
  
 `<column type = I2/> ColumnName`  
  
 `</columninfo>` 

## <a name="getxmlrowdata"></a> CXMLAccessor::GetXMLRowData
Tüm içeriğini tablo XML biçimli dize verileri, satır alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT GetXMLRowData(CSimpleStringW& strOutput,   
   bool bAppend = false) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *strOutput*  
 [out] Alınacak tablo verilerini içeren bir arabelleği başvuru. Veriler, dize verileri veri deposunun sütun adlarının eşleşmesi XML etiket adlarına sahip olarak biçimlendirilir.  
  
 *bAppend*  
 [in] Bir dize çıktı verilerini sonuna belirten bir Boole değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki XML'de biçimlendirilmiş satır verileri nasıl gösterir. `DATA` Aşağıdaki satır verisini temsil eder. Kullanmak istediğiniz satıra taşımak için yöntemleri taşıyın.  
  
 `<row>`  
  
 `<column name>DATA</column name>`  
  
 `</row>`   
  
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