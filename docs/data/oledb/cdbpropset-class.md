---
title: CDBPropSet Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
- CDBPropSet::AddProperty
- CDBPropSet.AddProperty
- AddProperty
- ATL::CDBPropSet::AddProperty
- ATL.CDBPropSet.AddProperty
- CDBPropSet.CDBPropSet
- CDBPropSet::CDBPropSet
- ATL::CDBPropSet::CDBPropSet
- ATL.CDBPropSet.CDBPropSet
- CDBPropSet.operator=
- ATL::CDBPropSet::operator=
- ATL.CDBPropSet.operator=
- CDBPropSet::operator=
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- CDBPropSet::SetGUID
helpviewer_keywords:
- CDBPropSet class
- AddProperty method
- CDBPropSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
- AddProperty method
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
ms.openlocfilehash: 08cab967fbfbd4b3207e96a4fdbd2d2dbc6da793
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447454"
---
# <a name="cdbpropset-class"></a>CDBPropSet Sınıfı

`DBPROPSET` yapısından devralır ve anahtar alanlarını ve `AddProperty` erişim yöntemini Başlatan bir Oluşturucu ekler.

## <a name="syntax"></a>Sözdizimi

```cpp
class CDBPropSet : public tagDBPROPSET
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[AddProperty](#addproperty)|Özellik kümesine bir özellik ekler.|
|[CDBPropSet](#cdbpropset)|Oluşturucu.|
|[Setguıd](#setguid)|`DBPROPSET` yapısının `guidPropertySet` alanını ayarlar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#op_equal)|Bir özelliğin içeriğini başka bir özellik kümesine atar.|

## <a name="remarks"></a>Açıklamalar

OLE DB sağlayıcıları ve tüketicileri `DBPROP` yapıların dizilerini iletmek için `DBPROPSET` yapılarını kullanır. Her `DBPROP` yapısı, ayarlanabilir tek bir özelliği temsil eder.

## <a name="addproperty"></a>CDBPropSet:: AddProperty

Özellik kümesine bir özellik ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool AddProperty(DWORD dwPropertyID,
   constVARIANT& var,
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   LPCSTR szValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   LPCWSTR szValue,DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   bool bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   BYTE bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   short nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   long nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   float fltValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   double dblValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   CY cyValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();
```

#### <a name="parameters"></a>Parametreler

*dwPropertyID*<br/>
'ndaki Eklenecek özelliğin KIMLIĞI. Özellik kümesine eklenen `DBPROP` yapısının `dwPropertyID` başlatmak için kullanılır.

*var*<br/>
'ndaki Özellik kümesine eklenen `DBPROP` yapısının özellik değerini başlatmak için kullanılan bir varyant.

*szValue*<br/>
'ndaki Özellik kümesine eklenen `DBPROP` yapısının özellik değerini başlatmak için kullanılan dize.

*bDeğer*<br/>
'ndaki Özellik kümesine eklenen `DBPROP` yapısına yönelik özellik değerini başlatmak için kullanılan bir `BYTE` veya Boole değeri.

*nDeğer*<br/>
'ndaki Özellik kümesine eklenen `DBPROP` yapısının özellik değerini başlatmak için kullanılan bir tamsayı değeri.

*fltValue*<br/>
'ndaki Özellik kümesine eklenen `DBPROP` yapısının özellik değerini başlatmak için kullanılan kayan nokta değeri.

*dblValue*<br/>
'ndaki Özellik kümesine eklenen `DBPROP` yapısının özellik değerini başlatmak için kullanılan çift duyarlıklı kayan nokta değeri.

*cyValue*<br/>
'ndaki Özellik kümesine eklenen `DBPROP` yapısının özellik değerini başlatmak için kullanılan bir CY para birimi değeri.

### <a name="return-value"></a>Dönüş Değeri

Özellik başarıyla eklendiyse **true** . Aksi takdirde, **false**.

## <a name="cdbpropset"></a>CDBPropSet:: CDBPropSet

Oluşturucu. [Dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapısının `rgProperties`, `cProperties`ve `guidPropertySet` alanlarını başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
CDBPropSet(const GUID& guid);

CDBPropSet(const CDBPropSet& propset);

CDBPropSet();
```

#### <a name="parameters"></a>Parametreler

*'ini*<br/>
'ndaki `guidPropertySet` alanı başlatmak için kullanılan bir GUID.

*PropSet*<br/>
'ndaki Kopya oluşturma için başka bir `CDBPropSet` nesnesi.

## <a name="setguid"></a>CDBPropSet:: Setguıd

`DBPROPSET` yapısındaki `guidPropertySet` alanını ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>Parametreler

*'ini*<br/>
'ndaki [Dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapısının `guidPropertySet` alanını ayarlamak IÇIN kullanılan GUID.

### <a name="remarks"></a>Açıklamalar

Bu alan, [Oluşturucu](../../data/oledb/cdbpropset-cdbpropset.md) tarafından da ayarlanabilir.

## <a name="op_equal"></a>CDBPropSet:: operator =

Bir özellik kümesinin içeriğini başka bir özellik kümesine atar.

### <a name="syntax"></a>Sözdizimi

```cpp
CDBPropSet& operator =(CDBPropSet& propset) throw();
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CDBPropIDSet Sınıfı](../../data/oledb/cdbpropidset-class.md)<br/>
[Dbpropset yapısı](/previous-versions/windows/desktop/ms714367(v=vs.85))
[DBPROP yapısı](/previous-versions/windows/desktop/ms717970(v=vs.85))