---
description: 'Daha fazla bilgi edinin: CXMLAccessor sınıfı'
title: CXMLAccessor Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- CXMLAccessor class
- GetXMLColumnData method
- GetXMLRowData method
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
ms.openlocfilehash: 30725f47add9f9b965fe36226a366342988275e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287703"
---
# <a name="cxmlaccessor-class"></a>CXMLAccessor Sınıfı

Veri deposunun şeması (temel yapı) hakkında bilginiz olmadığında veri kaynaklarına dize verileri olarak erişmenizi sağlar.

## <a name="syntax"></a>Syntax

```cpp
class CXMLAccessor : public CDynamicStringAccessorW
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[GetXMLColumnData](#getxmlcolumndata)|Sütun bilgisini alır.|
|[GetXMLRowData](#getxmlrowdata)|Tablonun tüm içeriğini satırlara göre alır.|

## <a name="remarks"></a>Açıklamalar

Ancak, `CXMLAccessor` `CDynamicStringAccessorW` veri deposundan erişilen tüm verileri XML biçimli (etiketli) veriler olarak dönüştürdüğünden öğesinden farklıdır. Bu, özellikle XML kullanan Web sayfalarına çıkış için yararlıdır. XML etiketi adları, veri deposunun sütun adlarıyla mümkün olduğunca yakından eşleştirecektir.

`CDynamicAccessor`Sütun bilgilerini almak için yöntemleri kullanın. Bu sütun bilgilerini, çalışma zamanında dinamik olarak bir erişimci oluşturmak için kullanırsınız.

Sütun bilgileri bu sınıf tarafından oluşturulan ve yönetilen bir arabellekte saklanır. [GetXMLColumnData](#getxmlcolumndata) kullanarak sütun bilgilerini alın veya [GetXMLRowData](#getxmlrowdata)kullanarak sütun verilerini satırlara göre alın.

## <a name="example"></a>Örnek

[!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]

## <a name="cxmlaccessorgetxmlcolumndata"></a><a name="getxmlcolumndata"></a> CXMLAccessor:: GetXMLColumnData

Bir tablonun sütun türü bilgilerini XML biçimli dize verileri olarak sütuna göre alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetXMLColumnData(CSimpleStringW& strOutput) throw();
```

#### <a name="parameters"></a>Parametreler

*strOutput*<br/>
dışı Alınacak sütun türü bilgilerini içeren bir dize arabelleğine başvuru. Dize, veri deposunun sütun adlarıyla eşleşen XML etiketi adlarıyla biçimlendirilir.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Aşağıda sütun türü bilgisinin XML biçiminde nasıl biçimlendirildiği gösterilmektedir. `type` sütunun veri türünü belirtir. Veri türlerinin erişilmekte olan veritabanına değil OLE DB veri türlerini temel alan olduğunu unutmayın.

`<columninfo>`

`<column type = I2/> ColumnName`

`</columninfo>`

## <a name="cxmlaccessorgetxmlrowdata"></a><a name="getxmlrowdata"></a> CXMLAccessor:: GetXMLRowData

Bir tablonun tüm içeriğini XML biçimli dize verileri olarak satıra göre alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetXMLRowData(CSimpleStringW& strOutput,
   bool bAppend = false) throw();
```

#### <a name="parameters"></a>Parametreler

*strOutput*<br/>
dışı Alınacak tablo verilerini içeren bir arabelleğe başvuru. Veriler, veri deposunun sütun adlarıyla eşleşen XML etiketi adlarıyla dize verileri olarak biçimlendirilir.

*bAppend*<br/>
'ndaki Çıktı verilerinin sonuna bir dize eklenip eklenmeyeceğini belirten bir Boole değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Aşağıda satır verilerinin XML biçiminde nasıl biçimlendirildiği gösterilmektedir. `DATA` Aşağıda satır verileri temsil eder. İstenen satıra gitmek için Move yöntemlerini kullanın.

`<row>`

`<column name>DATA</column name>`

`</row>`

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor sınıfı](../../data/oledb/caccessor-class.md)<br/>
[CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicParameterAccessor sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CDynamicStringAccessor sınıfı](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
[CDynamicStringAccessorA sınıfı](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
[CDynamicStringAccessorW sınıfı](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
[CManualAccessor sınıfı](../../data/oledb/cmanualaccessor-class.md)
