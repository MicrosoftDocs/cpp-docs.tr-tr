---
description: 'Daha fazla bilgi edinin: CBulkRowset Sınıfı'
title: CBulkRowset Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::CBulkRowset
- ATL.CBulkRowset
- ATL::CBulkRowset<TAccessor>
- CBulkRowset
- ATL.CBulkRowset<TAccessor>
- CBulkRowset::AddRefRows
- CBulkRowset.AddRefRows
- ATL.CBulkRowset<TAccessor>.AddRefRows
- ATL::CBulkRowset::AddRefRows
- CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset.AddRefRows
- ATL::CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset<TAccessor>.CBulkRowset
- ATL::CBulkRowset::CBulkRowset
- CBulkRowset.CBulkRowset
- CBulkRowset::CBulkRowset
- ATL.CBulkRowset.CBulkRowset
- ATL::CBulkRowset<TAccessor>::CBulkRowset
- CBulkRowset<TAccessor>::CBulkRowset
- ATL.CBulkRowset.MoveFirst
- CBulkRowset<TAccessor>.MoveFirst
- ATL.CBulkRowset<TAccessor>.MoveFirst
- ATL::CBulkRowset::MoveFirst
- ATL::CBulkRowset<TAccessor>::MoveFirst
- CBulkRowset::MoveFirst
- CBulkRowset<TAccessor>::MoveFirst
- CBulkRowset.MoveFirst
- CBulkRowset.MoveLast
- ATL.CBulkRowset.MoveLast
- ATL::CBulkRowset<TAccessor>::MoveLast
- CBulkRowset::MoveLast
- CBulkRowset<TAccessor>.MoveLast
- ATL::CBulkRowset::MoveLast
- ATL.CBulkRowset<TAccessor>.MoveLast
- CBulkRowset<TAccessor>::MoveLast
- ATL.CBulkRowset<TAccessor>.MoveNext
- ATL::CBulkRowset::MoveNext
- CBulkRowset::MoveNext
- ATL.CBulkRowset.MoveNext
- CBulkRowset.MoveNext
- ATL::CBulkRowset<TAccessor>::MoveNext
- CBulkRowset<TAccessor>.MoveNext
- CBulkRowset<TAccessor>::MoveNext
- CBulkRowset::MovePrev
- CBulkRowset<TAccessor>::MovePrev
- ATL::CBulkRowset<TAccessor>::MovePrev
- CBulkRowset<TAccessor>.MovePrev
- ATL::CBulkRowset::MovePrev
- CBulkRowset.MovePrev
- ATL.CBulkRowset.MovePrev
- ATL.CBulkRowset<TAccessor>.MovePrev
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset<TAccessor>.ReleaseRows
- ATL::CBulkRowset<TAccessor>::ReleaseRows
- ATL.CBulkRowset.ReleaseRows
- CBulkRowset<TAccessor>::ReleaseRows
- ATL::CBulkRowset::ReleaseRows
- CBulkRowset::ReleaseRows
- CBulkRowset.ReleaseRows
- ATL.CBulkRowset.SetRows
- CBulkRowset::SetRows
- CBulkRowset<TAccessor>.SetRows
- ATL.CBulkRowset<TAccessor>.SetRows
- CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset::SetRows
- CBulkRowset.SetRows
- SetRows
helpviewer_keywords:
- CBulkRowset class
- AddRefRows method
- CBulkRowset class, constructor
- MoveFirst method
- MoveLast method
- MoveNext method
- MovePrev method
- MoveToBookmark method
- MoveToRatio method
- ReleaseRows method
- SetRows method
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
ms.openlocfilehash: 106a8ffb3d70a021adbdb03b426e53ca39285b02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198381"
---
# <a name="cbulkrowset-class"></a>CBulkRowset Sınıfı

Tek bir çağrıda birden çok satır tanıtıcısı alarak verileri toplu olarak çalışmak için satırları getirir ve yönetir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor>
class CBulkRowset : public CRowset<TAccessor>
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Erişimci sınıfı.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[AddRefRows](#addrefrows)|Başvuru sayısını artırır.|
|[CBulkRowset](#cbulkrowset)|Oluşturucu.|
|[MoveFirst](#movefirst)|İlk veri satırını alır ve gerekirse yeni bir toplu getirme işlemi gerçekleştirerek.|
|[MoveLast](#movelast)|Son satıra gider.|
|[Iken](#movenext)|Sonraki veri satırını alır.|
|[MovePrev](#moveprev)|Önceki satıra gider.|
|[MoveToBookmark](#movetobookmark)|Bir yer işareti tarafından işaretlenen satırı veya bu yer işaretinin belirtilen uzaklığında satırı getirir.|
|[MoveToRatio](#movetoratio)|Satır kümesindeki kesirli konumdan başlayarak satırları getirir.|
|[ReleaseRows](#releaserows)|Geçerli satırı ( `m_nCurrentRow` ) sıfıra ayarlar ve tüm satırları serbest bırakır.|
|[SetRows](#setrows)|Tek bir çağrı tarafından alınacak satır tanıtıcılarının sayısını ayarlar.|

## <a name="example"></a>Örnek

Aşağıdaki örnek sınıfının kullanımını gösterir `CBulkRowset` .

[!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/cpp/cbulkrowset-class_1.cpp)]

## <a name="cbulkrowsetaddrefrows"></a><a name="addrefrows"></a> CBulkRowset:: AddRefRows

Toplu satır kümesinden alınmış olan tüm satırların başvuru sayısını artırmak için [IRowset:: AddRefRows](/previous-versions/windows/desktop/ms719619(v=vs.85)) çağırır.

### <a name="syntax"></a>Syntax

```cpp
HRESULT AddRefRows() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="cbulkrowsetcbulkrowset"></a><a name="cbulkrowset"></a> CBulkRowset:: CBulkRowset

Yeni bir `CBulkRowset` nesne oluşturur ve varsayılan satır sayısını 10 olarak ayarlar.

### <a name="syntax"></a>Syntax

```cpp
CBulkRowset();
```

## <a name="cbulkrowsetmovefirst"></a><a name="movefirst"></a> CBulkRowset:: MoveFirst

İlk veri satırını alır.

### <a name="syntax"></a>Syntax

```cpp
HRESULT MoveFirst() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="cbulkrowsetmovelast"></a><a name="movelast"></a> CBulkRowset:: MoveLast

Son satıra gider.

### <a name="syntax"></a>Syntax

```cpp
HRESULT MoveLast() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="cbulkrowsetmovenext"></a><a name="movenext"></a> CBulkRowset:: MoveNext

Sonraki veri satırını alır.

### <a name="syntax"></a>Syntax

```cpp
HRESULT MoveNext() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT. Satır kümesinin sonuna ulaşıldığında DB_S_ENDOFROWSET döndürür.

## <a name="cbulkrowsetmoveprev"></a><a name="moveprev"></a> CBulkRowset:: Moveöncekini

Önceki satıra gider.

### <a name="syntax"></a>Syntax

```cpp
HRESULT MovePrev() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="cbulkrowsetmovetobookmark"></a><a name="movetobookmark"></a> CBulkRowset:: MoveToBookmark

Yer işaretiyle işaretlenmiş satırı veya belirtilen bir uzaklığında (*lSkip*) satırı bu yer işaretinden getirir.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark,
   DBCOUNTITEM lSkip = 0) throw();
```

#### <a name="parameters"></a>Parametreler

*bookmark*<br/>
'ndaki Veri getirmek istediğiniz konuma işaret eden bir yer işareti.

*lSkip*<br/>
'ndaki Yer işaretinden hedef satıra ait satır sayısı. *LSkip* sıfır ise, ilk alınan satır yer işareti yer işaretiyle kaydedilir. *LSkip* 1 ise, getirilen ilk satır, yer işareti alınan satırdan sonraki satırdır. *LSkip* -1 ise, getirilen ilk satır, yer işareti alınan satırdan önceki satırdır.

### <a name="return-value"></a>Dönüş Değeri

*OLE DB Programcı başvurusunda* [IRowset:: GetData](/previous-versions/windows/desktop/ms716988(v=vs.85)) ' na bakın.

## <a name="cbulkrowsetmovetoratio"></a><a name="movetoratio"></a> CBulkRowset:: MoveToRatio

Satır kümesindeki kesirli konumdan başlayarak satırları getirir.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,
   DBCOUNTITEM nDenominator)throw();
```

#### <a name="parameters"></a>Parametreler

*Npay*<br/>
'ndaki Verilerin alınacağı kesirli konumunu belirlemede kullanılan pay.

*Npayda*<br/>
'ndaki Verilerin alınacağı kesirli konumunu belirlemede kullanılan payda.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

`MoveToRatio` satırları aşağıdaki formüle göre kabaca getirir:

`(nNumerator *  RowsetSize ) / nDenominator`

Burada satır `RowsetSize` kümesinin, satırlarda ölçülen boyutudur. Bu formülün doğruluğu, belirli sağlayıcıya bağlıdır. Ayrıntılar için *OLE DB Programcı başvurusunda* [IRowsetScroll:: GetRowsAtRatio](/previous-versions/windows/desktop/ms709602(v=vs.85)) bölümüne bakın.

## <a name="cbulkrowsetreleaserows"></a><a name="releaserows"></a> CBulkRowset:: ReleaseRows

Toplu satır kümesinden alınmış olan tüm satırların başvuru sayısını azaltmak için [IRowset:: ReleaseRows](/previous-versions/windows/desktop/ms719771(v=vs.85)) çağırır.

### <a name="syntax"></a>Syntax

```cpp
HRESULT ReleaseRows() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="cbulkrowsetsetrows"></a><a name="setrows"></a> CBulkRowset:: SetRows

Her çağrının aldığı satır tanıtıcılarının sayısını ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void SetRows(DBROWCOUNT nRows) throw();
```

#### <a name="parameters"></a>Parametreler

*nsatırlar*<br/>
'ndaki Satır kümesinin yeni boyutu (satır sayısı).

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırırsanız, satır kümesi açılmadan önce gelmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
