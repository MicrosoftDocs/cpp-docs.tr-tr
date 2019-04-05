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
- SetGUID
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
ms.openlocfilehash: b58c0262d361ede37bc3db68784177ec4c29f3a4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034254"
---
# <a name="cdbpropset-class"></a>CDBPropSet Sınıfı

Devralınan `DBPROPSET` yapısı ve anahtar alanları başlatan bir oluşturucu ekler ve `AddProperty` erişim yöntemi.

## <a name="syntax"></a>Sözdizimi

```cpp
class CDBPropSet : public tagDBPROPSET
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[addProperty](#addproperty)|Bir özellik için özellik kümesi ekler.|
|[CDBPropSet](#cdbpropset)|Oluşturucu.|
|[Setguıd](#setguid)|Kümeleri `guidPropertySet` alanını `DBPROPSET` yapısı.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#op_equal)|Bir özellik kümesinden diğerine içeriğini atar.|

## <a name="remarks"></a>Açıklamalar

OLE DB sağlayıcıları ve tüketiciler kullanım `DBPROPSET` dizileri geçirilecek yapıları `DBPROP` yapıları. Her `DBPROP` yapısı ayarlanabilir tek bir özelliği temsil eder.

## <a name="addproperty"></a> CDBPropSet::AddProperty

Bir özellik için özellik kümesi ekler.

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
[in] Eklenecek özelliğin kimliği. Başlatmak için kullanılan `dwPropertyID` , `DBPROP` yapısı olarak ayarlanan özelliği eklendi.

*var*<br/>
[in] Özellik değeri başlatmak için kullanılan bir değişken `DBPROP` yapısı olarak ayarlanan özelliği eklendi.

*szValue*<br/>
[in] Özellik değeri başlatmak için kullanılan bir dize `DBPROP` yapısı olarak ayarlanan özelliği eklendi.

*bDeğer*<br/>
[in] A `BYTE` veya boolean değeri için özellik değerini başlatmak için kullanılan `DBPROP` yapısı olarak ayarlanan özelliği eklendi.

*nDeğer*<br/>
[in] Özellik değeri başlatmak için kullanılan bir tamsayı değeri `DBPROP` yapısı olarak ayarlanan özelliği eklendi.

*fltValue*<br/>
[in] Özellik değeri başlatmak için kullanılan bir kayan nokta değeri `DBPROP` yapısı olarak ayarlanan özelliği eklendi.

*dblValue*<br/>
[in] Özellik değeri başlatmak için kullanılan bir çift duyarlıklı kayan nokta değeri `DBPROP` yapısı olarak ayarlanan özelliği eklendi.

*cyValue*<br/>
[in] Özellik değeri başlatmak için kullanılan CY para birimi değeri `DBPROP` yapısı olarak ayarlanan özelliği eklendi.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa özelliği başarıyla eklendi. Aksi takdirde, **false**.

## <a name="cdbpropset"></a> CDBPropSet::CDBPropSet

Oluşturucu. Başlatır `rgProperties`, `cProperties`, ve `guidPropertySet` alanlarının [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapısı.

### <a name="syntax"></a>Sözdizimi

```cpp
CDBPropSet(const GUID& guid);

CDBPropSet(const CDBPropSet& propset);

CDBPropSet();
```

#### <a name="parameters"></a>Parametreler

*GUID*<br/>
[in] Bir GUID başlatmak için kullanılan `guidPropertySet` alan.

*propset*<br/>
[in] Başka bir `CDBPropSet` kopya oluşumuna nesnesi.

## <a name="setguid"></a> CDBPropSet::setguıd

Kümeleri `guidPropertySet` alanındaki `DBPROPSET` yapısı.

### <a name="syntax"></a>Sözdizimi

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>Parametreler

*GUID*<br/>
[in] Ayarlamak için kullanılan bir GUID `guidPropertySet` alanını [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapısı.

### <a name="remarks"></a>Açıklamalar

Bu alan ayarlanabilir [Oluşturucusu](../../data/oledb/cdbpropset-cdbpropset.md) de.

## <a name="op_equal"></a> CDBPropSet::operator =

Bir özellik için başka bir özellik set içeriğini atar.

### <a name="syntax"></a>Sözdizimi

```cpp
CDBPropSet& operator =(CDBPropSet& propset) throw();
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CDBPropIDSet Sınıfı](../../data/oledb/cdbpropidset-class.md)<br/>
[DBPROPSET yapısı](/previous-versions/windows/desktop/ms714367(v=vs.85))
[DBPROP yapısı](/previous-versions/windows/desktop/ms717970(v=vs.85))