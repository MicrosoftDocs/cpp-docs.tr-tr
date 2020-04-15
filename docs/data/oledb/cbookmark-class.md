---
title: CBookmark Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL.CBookmark
- ATL::CBookmark<nSize>
- CBookmark
- ATL.CBookmark<nSize>
- ATL::CBookmark
- CBookmark<0>.CBookmark<0>
- CBookmark::CBookmark
- ATL.CBookmark.CBookmark
- CBookmark.CBookmark
- ATL::CBookmark<0>::CBookmark<0>
- ATL.CBookmark<0>.CBookmark<0>
- CBookmark<0>::CBookmark<0>
- ATL::CBookmark::CBookmark
- ATL.CBookmark<0>.GetBuffer
- ATL.CBookmark.GetBuffer
- ATL::CBookmark<0>::GetBuffer
- ATL::CBookmark::GetBuffer
- CBookmark.GetBuffer
- ATL::CBookmark<nSize>::GetBuffer
- ATL.CBookmark<nSize>.GetBuffer
- CBookmark<0>.GetBuffer
- CBookmark<nSize>::GetBuffer
- CBookmark<0>::GetBuffer
- CBookmark<nSize>.GetBuffer
- CBookmark::GetBuffer
- CBookmark::GetSize
- ATL.CBookmark<nSize>.GetSize
- CBookmark<nSize>.GetSize
- CBookmark.GetSize
- ATL::CBookmark::GetSize
- CBookmark<0>::GetSize
- ATL::CBookmark<nSize>::GetSize
- ATL.CBookmark<0>.GetSize
- ATL::CBookmark<0>::GetSize
- ATL.CBookmark.GetSize
- CBookmark<0>.GetSize
- CBookmark<nSize>::GetSize
- CBookmark<0>::SetBookmark
- ATL.CBookmark<0>.SetBookmark
- CBookmark<0>.SetBookmark
- SetBookmark
- ATL::CBookmark::SetBookmark
- ATL::CBookmark<0>::SetBookmark
- CBookmark.SetBookmark
- ATL.CBookmark.SetBookmark
- CBookmark::SetBookmark
- CBookmark<0>::operator=
- CBookmark<0>.operator=
- ATL.CBookmark.operator=
- CBookmark::operator=
- ATL.CBookmark<0>.operator=
- ATL::CBookmark<0>::operator=
- CBookmark.operator=
- ATL::CBookmark::operator=
helpviewer_keywords:
- CBookmark class
- CBookmark class, constructor
- GetBuffer method
- GetSize method
- SetBookmark method
- = operator, with OLE DB templates
- operator =, bookmarks
- operator=, bookmarks
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
ms.openlocfilehash: d3d82ea09b7ed2c1cbaf325906b4f9b480e1eb4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359329"
---
# <a name="cbookmark-class"></a>CBookmark Sınıfı

Arabelleğinde yer imi değeri tutar.

## <a name="syntax"></a>Sözdizimi

```cpp
template < DBLENGTH nSize = 0 >
class CBookmark : public CBookmarkBase

template <>
class CBookmark< 0 > : public CBookmarkBase
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
Baytlarda yer imi arabelleği boyutu. *nSize* sıfır olduğunda, yer imi arabelleği çalışma zamanında dinamik olarak oluşturulur.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Cbookmark](#cbookmark)|Yapıcı|
|[Getbuffer](#getbuffer)|Arabellek işaretçisini alır.|
|[GetSize](#getsize)|Arabellek boyutunu baytalır.|
|[Setbookmark](#setbookmark)|Yer imi değerini ayarlar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#operator)|Bir `CBookmark` sınıfı diğerine atar.|

## <a name="remarks"></a>Açıklamalar

`CBookmark<0>`bir şablon uzmanlık `CBookmark`olduğunu; arabelleği çalışma zamanında dinamik olarak oluşturulur.

## <a name="cbookmarkcbookmark"></a><a name="cbookmark"></a>CBookmark::CBookmark

Oluşturucu.

### <a name="syntax"></a>Sözdizimi

```cpp
CBookmark();
CBookmark(DBLENGTH nSize);
```

#### <a name="parameters"></a>Parametreler

*nSize*<br/>
[içinde] Baytlarda yer imi arabelleği boyutu.

### <a name="remarks"></a>Açıklamalar

İlk işlev arabelleği NULL'a, arabellek boyutunu 0'a ayarlar. İkinci işlev arabellek boyutunu *nSize'a,* arabelleği de *nSize* bayt dizisine ayarlar.

> [!NOTE]
> Bu işlev yalnızca `CBookmark<0>`.

## <a name="cbookmarkgetbuffer"></a><a name="getbuffer"></a>CBookmark::GetBuffer

Yer imi arabelleği işaretçisini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual BYTE* GetBuffer() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yer imi arabelleği için bir işaretçi.

## <a name="cbookmarkgetsize"></a><a name="getsize"></a>CBookmark::GetSize

Yer imi arabelleği boyutunu alır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual DBLENGTH GetSize() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Baytlarda arabelleğen boyutu.

## <a name="cbookmarksetbookmark"></a><a name="setbookmark"></a>CBookmark::SetBookmark

*Arabellek için pBuffer* `CBookmark` tarafından başvurulan yer imi değeri kopyalar ve *nSize*için arabellek boyutunu ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT SetBookmark(DBLENGTH nSize, BYTE* pBuffer) throw();
```

#### <a name="parameters"></a>Parametreler

*nSize*<br/>
[içinde] Yer imi arabelleği boyutu.

*Pbuffer*<br/>
[içinde] Yer işareti değerini içeren bayt dizisine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca `CBookmark<0>`.

## <a name="cbookmarkoperator-"></a><a name="operator"></a>CBookmark::operatör =

Bir nesneyi başka bir `CBookmark` nesneye atar.

### <a name="syntax"></a>Sözdizimi

```cpp
CBookmark& operator =(const CBookmark& bookmark) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç yalnızca `CBookmark<0>`.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
