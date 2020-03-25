---
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
ms.openlocfilehash: a52d7443ab335e8546a4bcce03cf68c3b1d60e3d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212047"
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet Sınıfı

`DBPROPIDSET` yapısından devralır ve [Addpropertyıd](../../data/oledb/cdbpropidset-addpropertyid.md) erişim yöntemi ile birlikte anahtar alanlarını Başlatan bir Oluşturucu ekler.

## <a name="syntax"></a>Sözdizimi

```cpp
class CDBPropIDSet : public tagDBPROPIDSET
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Addpropertyıd](#addpropertyid)|Özellik KIMLIĞI kümesine bir özellik ekler.|
|[CDBPropIDSet](#cdbpropidset)|Oluşturucu.|
|[Setguıd](#setguid)|Özellik KIMLIĞI kümesi GUID 'INI ayarlar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#op_equal)|Bir özellik KIMLIĞI kümesinin içeriğini diğerine atar.|

## <a name="remarks"></a>Açıklamalar

OLE DB tüketicileri, tüketicinin Özellik bilgilerini almak istediği özellik kimliklerinin bir dizisini iletmek için `DBPROPIDSET` yapılarını kullanır. Tek bir [DBPROPIDSET](/previous-versions/windows/desktop/ms717981(v=vs.85)) yapısında tanımlanan özellikler bir özellik kümesine aittir.

## <a name="cdbpropidsetaddpropertyid"></a><a name="addpropertyid"></a>CDBPropIDSet:: Addpropertyıd

Özellik KIMLIĞI kümesine özellik KIMLIĞI ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool AddPropertyID(DBPROPID propid) throw();
```

#### <a name="parameters"></a>Parametreler

*PROPID*<br/>
'ndaki Özellik KIMLIĞI kümesine eklenecek özellik KIMLIĞI.

## <a name="cdbpropidsetcdbpropidset"></a><a name="cdbpropidset"></a>CDBPropIDSet:: CDBPropIDSet

Oluşturucu. [DBPROPIDSET](/previous-versions/windows/desktop/ms717981(v=vs.85)) yapısının `rgProperties`, `cProperties`ve (isteğe bağlı) `guidPropertySet` alanlarını başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
CDBPropIDSet(const GUID& guid);

CDBPropIDSet(const CDBPropIDSet& propidset);

CDBPropIDSet();
```

#### <a name="parameters"></a>Parametreler

*'ini*<br/>
'ndaki `guidPropertySet` alanı başlatmak için kullanılan bir GUID.

*propidset*<br/>
'ndaki Kopya oluşturma için başka bir `CDBPropIDSet` nesnesi.

## <a name="cdbpropidsetsetguid"></a><a name="setguid"></a>CDBPropIDSet:: Setguıd

`DBPROPIDSET` yapısındaki GUID alanını ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>Parametreler

*'ini*<br/>
'ndaki [DBPROPIDSET](/previous-versions/windows/desktop/ms717981(v=vs.85)) yapısının `guidPropertySet` alanını ayarlamak IÇIN kullanılan GUID.

### <a name="remarks"></a>Açıklamalar

Bu alan, [Oluşturucu](../../data/oledb/cdbpropidset-cdbpropidset.md) tarafından da ayarlanabilir. Bu sınıf için varsayılan oluşturucuyu kullanıyorsanız bu işlevi çağırın.

## <a name="cdbpropidsetoperator-"></a><a name="op_equal"></a>CDBPropIDSet:: operator =

Bir özellik KIMLIĞI kümesinin içeriğini başka bir ID özellik kümesine atar.

### <a name="syntax"></a>Sözdizimi

```cpp
CDBPropIDSet& operator =(CDBPropIDSet& propset) throw();
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
