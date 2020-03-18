---
title: CArrayRowset Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL.CArrayRowset<TAccessor>
- ATL.CArrayRowset
- CArrayRowset
- ATL::CArrayRowset
- ATL::CArrayRowset<TAccessor>
- ATL::CArrayRowset::CArrayRowset
- CArrayRowset.CArrayRowset
- ATL.CArrayRowset.CArrayRowset
- ATL.CArrayRowset<TAccessor>.CArrayRowset
- CArrayRowset::CArrayRowset
- CArrayRowset<TAccessor>::CArrayRowset
- ATL::CArrayRowset<TAccessor>::CArrayRowset
- CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset::Snapshot
- Snapshot
- CArrayRowset<TAccessor>::Snapshot
- ATL.CArrayRowset.Snapshot
- ATL.CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset<TAccessor>::Snapshot
- CArrayRowset::Snapshot
- CArrayRowset.Snapshot
- CArrayRowset::operator[]
- CArrayRowset.operator[]
- ATL::CArrayRowset::m_nRowsRead
- ATL::CArrayRowset<TAccessor>::m_nRowsRead
- CArrayRowset<TAccessor>::m_nRowsRead
- ATL.CArrayRowset<TAccessor>.m_nRowsRead
- CArrayRowset.m_nRowsRead
- m_nRowsRead
- ATL.CArrayRowset.m_nRowsRead
- CArrayRowset::m_nRowsRead
helpviewer_keywords:
- CArrayRowset class
- CArrayRowset class, constructor
- Snapshot method
- operator [], arrays
- '[] operator'
- operator[], arrays
- m_nRowsRead
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
ms.openlocfilehash: 66b7607eb28392196f6b7d3790aee976a861f2b6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441718"
---
# <a name="carrayrowset-class"></a>CArrayRowset Sınıfı

Dizi sözdizimini kullanarak bir satır kümesinin öğelerine erişir.

## <a name="syntax"></a>Sözdizimi

```cpp
template < class TAccessor >
class CArrayRowset :
   public CVirtualBuffer <TAccessor>,
   protected CBulkRowset <TAccessor>
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Satır kümesinin kullanmasını istediğiniz erişimci sınıfının türü.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CArrayRowset](#carrayrowset)|Oluşturucu.|
|[Anlık Görüntü](#snapshot)|Tüm satır kümesini belleğe okur.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[İşlecinde&#91;&#93;](#operator)|Satır kümesinin bir öğesine erişir.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[CArrayRowset::m_nRowsRead](#nrowsread)|Zaten okunan satır sayısı.|

## <a name="carrayrowset"></a>CArrayRowset:: CArrayRowset

Yeni bir `CArrayRowset` nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
CArrayRowset(int nMax = 100000);
```

#### <a name="parameters"></a>Parametreler

*Ngünde en çok*<br/>
'ndaki Satır kümesindeki en fazla satır sayısı.

## <a name="snapshot"></a>CArrayRowset:: Snapshot

Tüm satır kümesini belleğe okur, görüntünün görüntüsünü veya anlık görüntüsünü oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Snapshot() throw();
```

## <a name="operator"></a>CArrayRowset:: işleci

Satır kümesindeki bir satıra erişmek için dizi benzeri sözdizimi sağlar.

### <a name="syntax"></a>Sözdizimi

```cpp
TAccessor & operator[](int nrow);
```

#### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Satır kümesinde depolanan erişimci türünü belirten şablonlu bir parametre.

*Nsatır*<br/>
'ndaki Erişmek istediğiniz satır (dizi öğesi) sayısı.

### <a name="return-value"></a>Dönüş Değeri

İstenen satırın içeriği.

### <a name="remarks"></a>Açıklamalar

*NRow* , satır kümesindeki satır sayısını aşarsa, bir özel durum oluşturulur.

## <a name="nrowsread"></a>CArrayRowset:: m_nRowsRead

Satır kümesindeki, zaten okunmuş olan satır sayısını içerir.

### <a name="syntax"></a>Sözdizimi

```cpp
ULONG m_nRowsRead;
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CRowset Sınıfı](../../data/oledb/crowset-class.md)