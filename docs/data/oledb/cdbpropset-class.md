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
ms.openlocfilehash: 45772896cac520eba35ec475f8b6ae7bd2993045
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502469"
---
# <a name="cdbpropset-class"></a>CDBPropSet Sınıfı

`DBPROPSET`Yapıdan devralır ve ayrıca, anahtar alanlarını ve erişim yöntemini Başlatan bir Oluşturucu ekler `AddProperty` .

## <a name="syntax"></a>Sözdizimi

```cpp
class CDBPropSet : public tagDBPROPSET
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[AddProperty](#addproperty)|Özellik kümesine bir özellik ekler.|
|[CDBPropSet](#cdbpropset)|Oluşturucu.|
|[Setguıd](#setguid)|`guidPropertySet`Yapının alanını ayarlar `DBPROPSET` .|

### <a name="operators"></a>İşleçler

| Ad | Açıklama |
|-|-|
|[işleç =](#op_equal)|Bir özelliğin içeriğini başka bir özellik kümesine atar.|

## <a name="remarks"></a>Açıklamalar

OLE DB sağlayıcıları ve tüketiciler yapıların `DBPROPSET` dizilerini geçirmek için yapıları kullanır `DBPROP` . Her `DBPROP` Yapı, ayarlanabilir tek bir özelliği temsil eder.

## <a name="cdbpropsetaddproperty"></a><a name="addproperty"></a> CDBPropSet:: AddProperty

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
'ndaki Eklenecek özelliğin KIMLIĞI. `dwPropertyID` `DBPROP` Özellik kümesine eklenen yapının kümesini başlatmak için kullanılır.

*l*<br/>
'ndaki Özellik kümesine eklenen yapının özellik değerini başlatmak için kullanılan bir varyant `DBPROP` .

*szValue*<br/>
'ndaki Özellik kümesine eklenen yapının özellik değerini başlatmak için kullanılan dize `DBPROP` .

*bDeğer*<br/>
'ndaki `BYTE` Özellik kümesine eklenen yapının özellik değerini başlatmak için kullanılan veya Boole değeri `DBPROP` .

*nDeğer*<br/>
'ndaki Özellik kümesine eklenen yapının özellik değerini başlatmak için kullanılan bir tamsayı değeri `DBPROP` .

*fltValue*<br/>
'ndaki Özellik kümesine eklenen yapının özellik değerini başlatmak için kullanılan kayan nokta değeri `DBPROP` .

*dblValue*<br/>
'ndaki Özellik kümesine eklenen yapının özellik değerini başlatmak için kullanılan çift duyarlıklı kayan nokta değeri `DBPROP` .

*cyValue*<br/>
'ndaki Özellik kümesine eklenen yapının özellik değerini başlatmak için kullanılan bir CY para birimi değeri `DBPROP` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** Özellik başarıyla eklendiyse. Aksi takdirde, **`false`** .

## <a name="cdbpropsetcdbpropset"></a><a name="cdbpropset"></a> CDBPropSet:: CDBPropSet

Oluşturucu. `rgProperties` `cProperties` `guidPropertySet` [Dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapısının, ve alanlarını başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
CDBPropSet(const GUID& guid);

CDBPropSet(const CDBPropSet& propset);

CDBPropSet();
```

#### <a name="parameters"></a>Parametreler

*guid*<br/>
'ndaki Alanı başlatmak için kullanılan bir GUID `guidPropertySet` .

*PropSet*<br/>
'ndaki `CDBPropSet` Kopya oluşturma için başka bir nesne.

## <a name="cdbpropsetsetguid"></a><a name="setguid"></a> CDBPropSet:: Setguıd

`guidPropertySet`Yapıdaki alanı ayarlar `DBPROPSET` .

### <a name="syntax"></a>Sözdizimi

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>Parametreler

*guid*<br/>
'ndaki `guidPropertySet` [Dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapısının alanını ayarlamak için kullanılan GUID.

### <a name="remarks"></a>Açıklamalar

Bu alan, [Oluşturucu](#cdbpropset) tarafından da ayarlanabilir.

## <a name="cdbpropsetoperator-"></a><a name="op_equal"></a> CDBPropSet:: operator =

Bir özellik kümesinin içeriğini başka bir özellik kümesine atar.

### <a name="syntax"></a>Sözdizimi

```cpp
CDBPropSet& operator =(CDBPropSet& propset) throw();
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CDBPropIDSet sınıfı](../../data/oledb/cdbpropidset-class.md)<br/>
[Dbpropset yapısı](/previous-versions/windows/desktop/ms714367(v=vs.85)) 
 [DBPROP yapısı](/previous-versions/windows/desktop/ms717970(v=vs.85))
