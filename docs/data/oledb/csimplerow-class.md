---
title: CSimpleRow sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
- CSimpleRow::AddRefRow
- AddRefRow
- ATL.CSimpleRow.AddRefRow
- ATL::CSimpleRow::AddRefRow
- CSimpleRow.AddRefRow
- CSimpleRow.Compare
- CSimpleRow::Compare
- CSimpleRow
- ATL::CSimpleRow::CSimpleRow
- CSimpleRow.CSimpleRow
- ATL.CSimpleRow.CSimpleRow
- CSimpleRow::CSimpleRow
- ATL::CSimpleRow::ReleaseRow
- CSimpleRow::ReleaseRow
- ReleaseRow
- CSimpleRow.ReleaseRow
- ATL.CSimpleRow.ReleaseRow
- CSimpleRow.m_dwRef
- CSimpleRow::m_dwRef
- CSimpleRow::m_iRowset
- CSimpleRow.m_iRowset
dev_langs:
- C++
helpviewer_keywords:
- CSimpleRow class
- AddRefRow method
- Compare method
- CSimpleRow class, constructor
- ReleaseRow method
- m_dwRef
- m_iRowset
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fb27c7fc401fb27b3677659f4f1b5539c19fda2c
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082702"
---
# <a name="csimplerow-class"></a>CSimpleRow Sınıfı

Satır tanıtıcısı kullanılan bir varsayılan uygulamasını sağlar [Irowsetımpl](../../data/oledb/irowsetimpl-class.md) sınıfı.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CSimpleRow  
```  

## <a name="requirements"></a>Gereksinimler  

**Başlık:** atldb.h  

## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[AddRefRow](#addrefrow)|Var olan bir satır işleyici için bir başvuru sayısı ekler.|  
|[Compare](#compare)|Aynı satır örneğine başvurmak görmek için iki satır karşılaştırır.|  
|[CSimpleRow](#csimplerow)|Oluşturucu.|  
|[ReleaseRow](#releaserow)|Satır serbest bırakır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_dwRef](#dwref)|Var olan bir satır işlemek için başvuru sayısı.|  
|[m_iRowset](#irowset)|İmleç temsil eden satır kümesi için bir dizin.|  
  
## <a name="remarks"></a>Açıklamalar  

Bir satır tanıtıcı, mantıksal bir sonuç satırı için benzersiz bir etiket değil. `IRowsetImpl` Yeni bir oluşturur `CSimpleRow` her satır içinde istenen için [Irowsetımpl::GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md). `CSimpleRow` Satır tanıtıcısı ile kendi uygulaması, varsayılan şablon bağımsız değişkeni olarak da değiştirilebilir `IRowsetImpl`. Türünde tek bir parametre kabul eden bir oluşturucu sağlayın değiştirme sınıfı için bu sınıf değiştirmek için tek gereksinim olmasıdır **uzun**.  

## <a name="addrefrow"></a> CSimpleRow::AddRefRow

Başvuru sayısı için mevcut bir satır tanıtıcısı iş parçacığı açısından güvenli bir şekilde ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
DWORD AddRefRow();  
```  

## <a name="compare"></a> CSimpleRow::Compare

Aynı satır örneğine başvurmak görmek için iki satır karşılaştırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Compare(CSimpleRow* pRow);  
```  
  
#### <a name="parameters"></a>Parametreler  

*pRow*<br/>
Bir işaretçi bir `CSimpleRow` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  

Genellikle S_OK HRESULT değerini, iki satır aynı satır örneği mı S_FALSE, iki satır belirten farklı belirten. Bkz: [IRowsetIdentity::IsSameRow](/previous-versions/windows/desktop/ms719629) içinde *OLE DB Programcının Başvurusu* diğer olası dönüş değerleri için. 

## <a name="csimplerow"></a> CSimpleRow::CSimpleRow

Oluşturucu.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
CSimpleRow(DBCOUNTITEM iRowsetCur);  
```  
  
#### <a name="parameters"></a>Parametreler  

*iRowsetCur*<br/>
[in] Geçerli satır kümesi için dizin.  
  
### <a name="remarks"></a>Açıklamalar  

Kümeleri [m_iRowset](../../data/oledb/csimplerow-m-irowset.md) için *iRowsetCur*. 

## <a name="releaserow"></a> CSimpleRow::ReleaseRow

Satır iş parçacığı açısından güvenli bir şekilde serbest bırakır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
DWORD ReleaseRow();  
```  

## <a name="dwref"></a> CSimpleRow::m_dwRef

Var olan bir satır işlemek için başvuru sayısı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
DWORD m_dwRef;  
```  

## <a name="irowset"></a> CSimpleRow::m_iRowset

İmleç temsil eden satır dizini.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
KeyType m_iRowset;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[IRowsetImpl Sınıfı](../../data/oledb/irowsetimpl-class.md)