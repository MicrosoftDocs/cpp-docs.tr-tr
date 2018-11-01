---
title: CBulkRowset Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::CBulkRowset
- ATL.CBulkRowset
- ATL::CBulkRowset<TAccessor>
- CBulkRowset
- ATL.CBulkRowset<TAccessor>
- CBulkRowset::AddRefRows
- AddRefRows
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
- CBulkRowset
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
- MoveLast
- ATL.CBulkRowset<TAccessor>.MoveNext
- ATL::CBulkRowset::MoveNext
- CBulkRowset::MoveNext
- ATL.CBulkRowset.MoveNext
- CBulkRowset.MoveNext
- ATL::CBulkRowset<TAccessor>::MoveNext
- CBulkRowset<TAccessor>.MoveNext
- CBulkRowset<TAccessor>::MoveNext
- CBulkRowset::MovePrev
- MovePrev
- CBulkRowset<TAccessor>::MovePrev
- ATL::CBulkRowset<TAccessor>::MovePrev
- CBulkRowset<TAccessor>.MovePrev
- ATL::CBulkRowset::MovePrev
- CBulkRowset.MovePrev
- ATL.CBulkRowset.MovePrev
- ATL.CBulkRowset<TAccessor>.MovePrev
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
- ReleaseRows
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
ms.openlocfilehash: c62dd4ba7f4f91371378b7c1a6b0295edb3625e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431076"
---
# <a name="cbulkrowset-class"></a>CBulkRowset Sınıfı

Getirir ve tek bir çağrı ile birden çok satır işleyicilerini alarak, toplu veriler üzerinde çalışmaya satırları yönetir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor>
class CBulkRowset : public CRowset<TAccessor>
```

### <a name="parameters"></a>Parametreler

*TAccessor*<br/>
Bir erişimci sınıfı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[AddRefRows](#addrefrows)|Başvuru sayısını artırır.|
|[CBulkRowset](#cbulkrowset)|Oluşturucu.|
|[MoveFirst](#movefirst)|Gerekirse, yeni bir toplu getirme gerçekleştirme verilerin ilk satırı alır.|
|[MoveLast](#movelast)|Son satıra taşır.|
|[MoveNext](#movenext)|Sonraki satırda veri alır.|
|[MovePrev](#moveprev)|Önceki satıra taşır.|
|[MoveToBookmark](#movetobookmark)|Bu yer işaretinden yer işareti tarafından işaretlenen satırı veya belirtilen bir uzaklık satırı getirir.|
|[MoveToRatio](#movetoratio)|Satır kümesindeki kesirli bir konumdan başlayan satırları getirir.|
|[ReleaseRows](#releaserows)|Geçerli satırın ayarlar (`m_nCurrentRow`) sıfır ve sürümlere tüm satırlar.|
|[SetRows](#setrows)|Bir çağrı tarafından alınacak olan satır işleyicilerini sayısını ayarlar.|

## <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir. `CBulkRowset` sınıfı.

[!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/cpp/cbulkrowset-class_1.cpp)]

## <a name="addrefrows"></a> CBulkRowset::AddRefRows

Çağrıları [IRowset::AddRefRows](/previous-versions/windows/desktop/ms719619) şu anda toplu satır kümesinden alınan tüm satırlar için başvuru sayısını artırmak için.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT AddRefRows() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="cbulkrowset"></a> CBulkRowset::CBulkRowset

Yeni bir oluşturur `CBulkRowset` nesnesini ve varsayılan satır sayısı 10'a ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
CBulkRowset();
```

## <a name="movefirst"></a> CBulkRowset::MoveFirst

İlk veri satırı alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT MoveFirst() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="movelast"></a> CBulkRowset::MoveLast

Son satıra taşır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT MoveLast() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="movenext"></a> CBulkRowset::MoveNext

Sonraki satırda veri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT MoveNext() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT. Satır sonuna ulaşıldığında DB_S_ENDOFROWSET döndürür.

## <a name="moveprev"></a> CBulkRowset::MovePrev

Önceki satıra taşır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT MovePrev() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="movetobookmark"></a> CBulkRowset::MoveToBookmark

Bir yer işareti veya belirtilen bir uzaklık satırında tarafından işaretlenen satırı getirir (*lSkip*), yer işareti öğesinden.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark,
   DBCOUNTITEM lSkip = 0) throw();
```

#### <a name="parameters"></a>Parametreler

*Yer işareti*<br/>
[in] Veri getirmek istediğiniz yeri işaretlemek bir yer işareti.

*lSkip*<br/>
[in] Yer işareti hedef satır satır numarası sayısı. Varsa *lSkip* sıfırsa, getirilen ilk satır işaretli bir satırdır. Varsa *lSkip* 1, getirilen ilk satırın sonuna işaretli satır satırdır. Varsa *lSkip* -1, ilk satırın getirilen işaretli satır önce satırdır.

### <a name="return-value"></a>Dönüş Değeri

Bkz: ['yı](/previous-versions/windows/desktop/ms716988) içinde *OLE DB Programcının Başvurusu*.

## <a name="movetoratio"></a> CBulkRowset::MoveToRatio

Satır kümesindeki kesirli bir konumdan başlayan satırları getirir.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,
   DBCOUNTITEM nDenominator)throw();
```

#### <a name="parameters"></a>Parametreler

*nNumerator*<br/>
[in] Veri getirme kesirli konumu belirlemek için kullanılan pay.

*nDenominator*<br/>
[in] Payda verileri getirmek kesirli konumu belirlemek için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

`MoveToRatio` aşağıdaki formülü göre kabaca satırları getirir:

`(nNumerator *  RowsetSize ) / nDenominator`

Burada `RowsetSize` satırlarda ölçülen satır boyutu. Bu formül doğruluğunu belirli sağlayıcısına bağlıdır. Ayrıntılar için bkz [IRowsetScroll::GetRowsAtRatio](/previous-versions/windows/desktop/ms709602) içinde *OLE DB Programcının Başvurusu*.

## <a name="releaserows"></a> CBulkRowset::ReleaseRows

Çağrıları [IRowset::ReleaseRows](/previous-versions/windows/desktop/ms719771) şu anda toplu satır kümesinden alınan tüm satırlar için başvuru sayısını azaltmak için.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT ReleaseRows() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="setrows"></a> CBulkRowset::SetRows

Her bir çağrı tarafından alınan satır işleyicilerin sayısını ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void SetRows(DBROWCOUNT nRows) throw();
```

#### <a name="parameters"></a>Parametreler

*nRows*<br/>
[in] Satır kümesi (satır sayısı) yeni boyutu.

### <a name="remarks"></a>Açıklamalar

Bu işlev çağırırsanız, satır kümesi açılmadan önce olmalıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)