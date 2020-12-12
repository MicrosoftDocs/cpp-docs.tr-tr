---
description: 'Daha fazla bilgi edinin: CDBPropIDSet Class'
title: CDBPropIDSet Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
- CDBPropIDSet.AddPropertyID
- CDBPropIDSet::AddPropertyID
- AddPropertyID
- ATL.CDBPropIDSet.AddPropertyID
- ATL::CDBPropIDSet::AddPropertyID
- ATL::CDBPropIDSet::CDBPropIDSet
- CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet::CDBPropIDSet
- ATL.CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet.operator=
- ATL.CDBPropIDSet.operator=
- ATL::CDBPropIDSet::operator=
- CDBPropIDSet::operator=
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
helpviewer_keywords:
- CDBPropIDSet class
- AddPropertyID method
- CDBPropIDSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
ms.openlocfilehash: 6f0c3ea19daeef2b262f6ac1ad76599160baf266
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170834"
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet Sınıfı

`DBPROPIDSET`Yapıdan devralır ve [Addpropertyıd](#addpropertyid) erişim yöntemi ile birlikte Key alanlarını Başlatan bir Oluşturucu ekler.

## <a name="syntax"></a>Syntax

```cpp
class CDBPropIDSet : public tagDBPROPIDSET
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[Addpropertyıd](#addpropertyid)|Özellik KIMLIĞI kümesine bir özellik ekler.|
|[CDBPropIDSet](#cdbpropidset)|Oluşturucu.|
|[Setguıd](#setguid)|Özellik KIMLIĞI kümesi GUID 'INI ayarlar.|

### <a name="operators"></a>İşleçler

| Ad | Açıklama |
|-|-|
|[işleç =](#op_equal)|Bir özellik KIMLIĞI kümesinin içeriğini diğerine atar.|

## <a name="remarks"></a>Açıklamalar

OLE DB tüketicileri `DBPROPIDSET` , tüketicinin Özellik bilgilerini almak istediği Özellik kimlikleri dizisini geçirmek için yapıları kullanır. Tek bir [DBPROPIDSET](/previous-versions/windows/desktop/ms717981(v=vs.85)) yapısında tanımlanan özellikler bir özellik kümesine aittir.

## <a name="cdbpropidsetaddpropertyid"></a><a name="addpropertyid"></a> CDBPropIDSet:: Addpropertyıd

Özellik KIMLIĞI kümesine özellik KIMLIĞI ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool AddPropertyID(DBPROPID propid) throw();
```

#### <a name="parameters"></a>Parametreler

*PROPID*<br/>
'ndaki Özellik KIMLIĞI kümesine eklenecek özellik KIMLIĞI.

## <a name="cdbpropidsetcdbpropidset"></a><a name="cdbpropidset"></a> CDBPropIDSet:: CDBPropIDSet

Oluşturucu. `rgProperties` `cProperties` DBPROPIDSET yapısının, ve (isteğe bağlı) `guidPropertySet` alanlarını başlatır. [](/previous-versions/windows/desktop/ms717981(v=vs.85))

### <a name="syntax"></a>Sözdizimi

```cpp
CDBPropIDSet(const GUID& guid);

CDBPropIDSet(const CDBPropIDSet& propidset);

CDBPropIDSet();
```

#### <a name="parameters"></a>Parametreler

*guid*<br/>
'ndaki Alanı başlatmak için kullanılan bir GUID `guidPropertySet` .

*propidset*<br/>
'ndaki `CDBPropIDSet` Kopya oluşturma için başka bir nesne.

## <a name="cdbpropidsetsetguid"></a><a name="setguid"></a> CDBPropIDSet:: Setguıd

Yapıda GUID alanını ayarlar `DBPROPIDSET` .

### <a name="syntax"></a>Sözdizimi

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>Parametreler

*guid*<br/>
'ndaki `guidPropertySet` [DBPROPIDSET](/previous-versions/windows/desktop/ms717981(v=vs.85)) yapısının alanını ayarlamak için kullanılan GUID.

### <a name="remarks"></a>Açıklamalar

Bu alan, [Oluşturucu](#cdbpropidset) tarafından da ayarlanabilir. Bu sınıf için varsayılan oluşturucuyu kullanıyorsanız bu işlevi çağırın.

## <a name="cdbpropidsetoperator-"></a><a name="op_equal"></a> CDBPropIDSet:: operator =

Bir özellik KIMLIĞI kümesinin içeriğini başka bir ID özellik kümesine atar.

### <a name="syntax"></a>Syntax

```cpp
CDBPropIDSet& operator =(CDBPropIDSet& propset) throw();
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
