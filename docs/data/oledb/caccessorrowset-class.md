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
- ATL.CAccessorRowset.CAccessorRowset
- ATL::CAccessorRowset::CAccessorRowset
- CAccessorRowset.Close
- CAccessorRowset::Close
- CAccessorRowset::FreeRecordMemory
- CAccessorRowset.FreeRecordMemory
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
ms.openlocfilehash: efb5618c03b1f70a809bb2bafe9611474799e00b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212257"
---
# <a name="caccessorrowset-class"></a>CAccessorRowset Sınıfı

Bir satır kümesini ve onunla ilişkili erişimcileri tek bir sınıfta kapsüller.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CNoAccessor,
   template <typename T> class TRowset = CRowset>
class CAccessorRowset : public TAccessor, public TRowset<TAccessor>
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Erişimci sınıfı.

*TRowset*<br/>
Satır kümesi sınıfı.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Bind](#bind)|Bağlamalar oluşturur (`bBind`, [CCommand:: Open](../../data/oledb/ccommand-open.md)içinde **false** olarak belirtildiğinde kullanılır).|
|[CAccessorRowset](#caccessorrowset)|Oluşturucu.|
|[~Eksik](#close)|Satır kümesini ve tüm erişimcileri kapatır.|
|[FreeRecordMemory](#freerecordmemory)|Geçerli kayıttaki, serbest olması gereken tüm sütunları serbest bırakır.|
|[GetColumnInfo](#getcolumninfo)|[IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\))uygular.|

## <a name="remarks"></a>Açıklamalar

Sınıf `TAccessor` erişimciyi yönetir. *TRowset* sınıfı satır kümesini yönetir.

## <a name="caccessorrowsetbind"></a><a name="bind"></a>CAccessorRowset:: bind

[CCommand:: Open](../../data/oledb/ccommand-open.md)içinde `bBind` **false** olarak belirttiyseniz bağlamaları oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Bind();
```

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="caccessorrowsetcaccessorrowset"></a><a name="caccessorrowset"></a>CAccessorRowset:: CAccessorRowset

`CAccessorRowset` nesnesini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
CAccessorRowset();
```

## <a name="caccessorrowsetclose"></a><a name="close"></a>CAccessorRowset:: Close

Tüm etkin erişimcileri ve satır kümesini yayınlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

İlişkili tüm belleği serbest bırakır.

## <a name="caccessorrowsetfreerecordmemory"></a><a name="freerecordmemory"></a>CAccessorRowset:: FreeRecordMemory

Geçerli kayıttaki, serbest olması gereken tüm sütunları serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
void FreeRecordMemory();
```

## <a name="caccessorrowsetgetcolumninfo"></a><a name="getcolumninfo"></a>CAccessorRowset:: GetColumnInfo

Açılan satır kümesinden sütun bilgilerini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetColumnInfo(DBORDINAL* pulColumns,
   DBCOLUMNINFO** ppColumnInfo,
   LPOLESTR* ppStrings) const;

HRESULT GetColumnInfo(DBORDINAL* pColumns,
   DBCOLUMNINFO** ppColumnInfo);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Kullanıcı döndürülen sütun bilgisini ve dize arabelleğini boşaltmalıdır. [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) kullandığınızda bu yöntemin ikinci sürümünü kullanın ve bağlamaları geçersiz kılmanız gerekir.

Daha fazla bilgi için *OLE DB Programcı başvurusunda* [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
