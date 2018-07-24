---
title: Cdbpropıdset sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
- CDBPropIDSet
- CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet::CDBPropIDSet
- ATL.CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet.operator=
- ATL.CDBPropIDSet.operator=
- ATL::CDBPropIDSet::operator=
- CDBPropIDSet::operator=
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- CDBPropIDSet class
- AddPropertyID method
- CDBPropIDSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5e77b92822ac82a4fbea06fe354952c9dbd79378
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207591"
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet Sınıfı
Devralınan `DBPROPIDSET` yapısı ve anahtar alanları başlatan bir oluşturucu ekler ve [Addpropertyıd](../../data/oledb/cdbpropidset-addpropertyid.md) erişim yöntemi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CDBPropIDSet : public tagDBPROPIDSET  
```  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[AddPropertyID](#addpropertyid)|Bir özellik için özellik kimliği kümesi ekler.|  
|[CDBPropIDSet](#cdbpropidset)|Oluşturucu.|  
|[Setguıd](#setguid)|Ayarlar özellik kimliği GUID'si.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](#op_equal)|Başka bir özellik kimliği içeriğini atar ayarlayın.|  
  
## <a name="remarks"></a>Açıklamalar  
 OLE DB tüketicileri kullanım `DBPROPIDSET` yapıları için tüketici istediği özellik bilgilerini almak özellik kimlikleri dizisi geçirilecek. Tek bir tanımlanmış özellikler [DBPROPIDSET](https://msdn.microsoft.com/library/ms717981.aspx) yapısı bir özellik kümesine ait.  

## <a name="addpropertyid"></a> Cdbpropıdset::addpropertyıd
Özellik kimliği özelliği kimliği kümesine ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      bool AddPropertyID(DBPROPID propid) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *PROPID*  
 [in] Özellik kimliği için eklenecek özellik kimliği ayarlayın.  

## <a name="cdbpropidset"></a> Cdbpropıdset::cdbpropıdset
Oluşturucu. Başlatır `rgProperties`, `cProperties`ve (isteğe bağlı olarak) `guidPropertySet` alanlarının [DBPROPIDSET](https://msdn.microsoft.com/library/ms717981.aspx) yapısı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      CDBPropIDSet(const GUID& guid);  

CDBPropIDSet(const CDBPropIDSet& propidset);  

CDBPropIDSet();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *GUID*  
 [in] Bir GUID başlatmak için kullanılan `guidPropertySet` alan.  
  
 *propidset*  
 [in] Başka bir `CDBPropIDSet` kopya oluşumuna nesnesi.  

## <a name="setguid"></a> Cdbpropıdset::setguıd
GUID alanı ayarlar `DBPROPIDSET` yapısı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *GUID*  
 [in] Ayarlamak için kullanılan bir GUID `guidPropertySet` alanını [DBPROPIDSET](https://msdn.microsoft.com/library/ms717981.aspx) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu alan ayarlanabilir [Oluşturucusu](../../data/oledb/cdbpropidset-cdbpropidset.md) de. Bu sınıf için varsayılan oluşturucu kullanırsanız, bu işlevi çağırın.  

## <a name="op_equal"></a> Cdbpropıdset::operator =
Bir özellik kimliği başka bir kimlik özelliği için set içeriğini atar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      CDBPropIDSet& operator =(CDBPropIDSet& propset) throw();  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)