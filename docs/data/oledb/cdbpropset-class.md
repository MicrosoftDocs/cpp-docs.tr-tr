---
title: CDBPropSet sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6e8415fdac405f0a639b03cc90a710214d2c8d0c
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207844"
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
|[AddProperty](#addproperty)|Bir özellik için özellik kümesi ekler.|  
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
 *dwPropertyID*  
 [in] Eklenecek özelliğin kimliği. Başlatmak için kullanılan `dwPropertyID` , `DBPROP` yapısı olarak ayarlanan özelliği eklendi.  
  
 *var*  
 [in] Özellik değeri başlatmak için kullanılan bir değişken `DBPROP` yapısı olarak ayarlanan özelliği eklendi.  
  
 *szValue*  
 [in] Özellik değeri başlatmak için kullanılan bir dize `DBPROP` yapısı olarak ayarlanan özelliği eklendi.  
  
 *bDeğer*  
 [in] A `BYTE` veya boolean değeri için özellik değerini başlatmak için kullanılan `DBPROP` yapısı olarak ayarlanan özelliği eklendi.  
  
 *nDeğer*  
 [in] Özellik değeri başlatmak için kullanılan bir tamsayı değeri `DBPROP` yapısı olarak ayarlanan özelliği eklendi.  
  
 *fltValue*  
 [in] Özellik değeri başlatmak için kullanılan bir kayan nokta değeri `DBPROP` yapısı olarak ayarlanan özelliği eklendi.  
  
 *dblValue*  
 [in] Özellik değeri başlatmak için kullanılan bir çift duyarlıklı kayan nokta değeri `DBPROP` yapısı olarak ayarlanan özelliği eklendi.  
  
 *cyValue*  
 [in] Özellik değeri başlatmak için kullanılan CY para birimi değeri `DBPROP` yapısı olarak ayarlanan özelliği eklendi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa özelliği başarıyla eklendi. Aksi takdirde, **false**. 

## <a name="cdbpropset"></a> CDBPropSet::CDBPropSet
Oluşturucu. Başlatır `rgProperties`, `cProperties`, ve `guidPropertySet` alanlarının [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) yapısı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      CDBPropSet(const GUID& guid);  

CDBPropSet(const CDBPropSet& propset);  

CDBPropSet();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *GUID*  
 [in] Bir GUID başlatmak için kullanılan `guidPropertySet` alan.  
  
 *propset*  
 [in] Başka bir `CDBPropSet` kopya oluşumuna nesnesi.  

## <a name="setguid"></a> CDBPropSet::setguıd
Kümeleri `guidPropertySet` alanındaki `DBPROPSET` yapısı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *GUID*  
 [in] Ayarlamak için kullanılan bir GUID `guidPropertySet` alanını [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu alan ayarlanabilir [Oluşturucusu](../../data/oledb/cdbpropset-cdbpropset.md) de.  

## <a name="op_equal"></a> CDBPropSet::operator =
Bir özellik için başka bir özellik set içeriğini atar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      CDBPropSet& operator =(CDBPropSet& propset) throw();  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Cdbpropıdset sınıfı](../../data/oledb/cdbpropidset-class.md)   
 [DBPROPSET yapısı](https://msdn.microsoft.com/library/ms714367.aspx)   
 [DBPROP yapısı](https://msdn.microsoft.com/library/ms717970.aspx)