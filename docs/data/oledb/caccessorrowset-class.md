---
title: CAccessorRowset Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAccessorRowset
- ATL.CAccessorRowset
- ATL::CAccessorRowset
- CAccessorRowset.Bind
- CAccessorRowset::Bind
- CAccessorRowset::CAccessorRowset
- CAccessorRowset.CAccessorRowset
- CAccessorRowset
- ATL.CAccessorRowset.CAccessorRowset
- ATL::CAccessorRowset::CAccessorRowset
- CAccessorRowset.Close
- CAccessorRowset::Close
- CAccessorRowset::FreeRecordMemory
- CAccessorRowset.FreeRecordMemory
- FreeRecordMemory
- GetColumnInfo
- CAccessorRowset.GetColumnInfo
- CAccessorRowset::GetColumnInfo
helpviewer_keywords:
- CAccessorRowset class
- CAccessorRowset class, methods
- CAccessorRowset class, members
- Bind method
- CAccessorRowset class, constructor
- Close method
- FreeRecordMemory method
- GetColumnInfo method
ms.assetid: bd4f58ed-cebf-4d43-8985-1e5fcbf06953
ms.openlocfilehash: af38695ccee79e539782dc3f695a567f72fa41c7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033910"
---
# <a name="caccessorrowset-class"></a>CAccessorRowset Sınıfı

Bir satır kümesi ve tek bir sınıftaki ilişkili erişimcilerini kapsüller.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CNoAccessor,
   template <typename T> class TRowset = CRowset>
class CAccessorRowset : public TAccessor, public TRowset<TAccessor>
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Bir erişimci sınıfı.

*CRowset*<br/>
Bir satır kümesi sınıfı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[bağlama](#bind)|Bağlamaları oluşturur (kullanılabilir `bBind` olarak belirtilen **false** içinde [CCommand::Open](../../data/oledb/ccommand-open.md)).|
|[CAccessorRowset](#caccessorrowset)|Oluşturucu.|
|[Close](#close)|Satır kümesi ve tüm erişimcileri kapatır.|
|[FreeRecordMemory](#freerecordmemory)|Hiçbir sütun boşaltılması için gereken geçerli kayıtta serbest bırakır.|
|[GetColumnInfo](#getcolumninfo)|Implements [IColumnsInfo::GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)).|

## <a name="remarks"></a>Açıklamalar

Sınıf `TAccessor` erişimci yönetir. Sınıf *CRowset* satır kümesi yönetir.

## <a name="bind"></a> CAccessorRowset::Bind

Belirttiyseniz bağlamaları oluşturur `bBind` olarak **false** içinde [CCommand::Open](../../data/oledb/ccommand-open.md).

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Bind();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="caccessorrowset"></a> CAccessorRowset::CAccessorRowset

Başlatır `CAccessorRowset` nesne.

### <a name="syntax"></a>Sözdizimi

```cpp
CAccessorRowset();
```

## <a name="close"></a> CAccessorRowset::Close

Tüm etkin erişimciler ve satır kümesi serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

Herhangi bir ilişkili belleği serbest bırakır.

## <a name="freerecordmemory"></a> CAccessorRowset::FreeRecordMemory

Hiçbir sütun boşaltılması için gereken geçerli kayıtta serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
void FreeRecordMemory();
```

## <a name="getcolumninfo"></a> CAccessorRowset::GetColumnInfo

Açık satır kümesinden sütun bilgileri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetColumnInfo(DBORDINAL* pulColumns,
   DBCOLUMNINFO** ppColumnInfo,
   LPOLESTR* ppStrings) const;

HRESULT GetColumnInfo(DBORDINAL* pColumns,
   DBCOLUMNINFO** ppColumnInfo);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IColumnsInfo::GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Kullanıcı, döndürülen sütun bilgileri ve dize arabellek boşaltmanız gerekir. Dosyanın ikinci sürümü, bu yöntemi kullandığınızda kullanın [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) ve bağlamaları geçersiz kılmanız gerekir.

Daha fazla bilgi için [IColumnsInfo::GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)