---
description: 'Daha fazla bilgi edinin: CBookmark sınıfı'
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
ms.openlocfilehash: 7c138776e282c287eb7e7e09b93196ac0792f7ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295074"
---
# <a name="cbookmark-class"></a>CBookmark Sınıfı

Arabellekte bir yer işareti değeri tutar.

## <a name="syntax"></a>Sözdizimi

```cpp
template < DBLENGTH nSize = 0 >
class CBookmark : public CBookmarkBase

template <>
class CBookmark< 0 > : public CBookmarkBase
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
Yer işareti arabelleğinin bayt cinsinden boyutu. *NSize* sıfır olduğunda, yer işareti arabelleği çalışma zamanında dinamik olarak oluşturulur.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[CBookmark](#cbookmark)|Oluşturucu|
|[GetBuffer](#getbuffer)|Arabelleğe işaretçiyi alır.|
|[GetSize](#getsize)|Arabelleğin boyutunu bayt cinsinden alır.|
|[SetBookmark](#setbookmark)|Yer işareti değerini ayarlar.|

### <a name="operators"></a>İşleçler

| Ad | Açıklama |
|-|-|
|[işleç =](#operator)|Bir `CBookmark` sınıfı diğerine atar.|

## <a name="remarks"></a>Açıklamalar

`CBookmark<0>` , öğesinin bir şablon özelleştirmesi olduğundan, `CBookmark` arabelleği çalışma zamanında dinamik olarak oluşturulur.

## <a name="cbookmarkcbookmark"></a><a name="cbookmark"></a> CBookmark:: CBookmark

Oluşturucu.

### <a name="syntax"></a>Sözdizimi

```cpp
CBookmark();
CBookmark(DBLENGTH nSize);
```

#### <a name="parameters"></a>Parametreler

*nSize*<br/>
'ndaki Yer işareti arabelleğinin bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

İlk işlev, arabelleği NULL ve arabellek boyutunu 0 olarak ayarlar. İkinci işlev arabellek boyutunu *nSize* ve arabelleği bir bayt dizisi olarak *nSize* bayt dizisine ayarlar.

> [!NOTE]
> Bu işlev yalnızca ' de kullanılabilir `CBookmark<0>` .

## <a name="cbookmarkgetbuffer"></a><a name="getbuffer"></a> CBookmark:: GetBuffer

Yer işareti arabelleğinin işaretçisini alır.

### <a name="syntax"></a>Syntax

```cpp
virtual BYTE* GetBuffer() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yer işareti arabelleğine yönelik bir işaretçi.

## <a name="cbookmarkgetsize"></a><a name="getsize"></a> CBookmark:: GetSize

Yer işareti arabelleğinin boyutunu alır.

### <a name="syntax"></a>Syntax

```cpp
virtual DBLENGTH GetSize() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Arabelleğin bayt cinsinden boyutu.

## <a name="cbookmarksetbookmark"></a><a name="setbookmark"></a> CBookmark:: SetBookmark

*PBuffer* tarafından başvurulan yer işareti değerini `CBookmark` arabelleğe kopyalar ve arabellek boyutunu *nSize* olarak ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT SetBookmark(DBLENGTH nSize, BYTE* pBuffer) throw();
```

#### <a name="parameters"></a>Parametreler

*nSize*<br/>
'ndaki Yer işareti arabelleğinin boyutu.

*pBuffer*<br/>
'ndaki Yer işareti değerini içeren bayt dizisine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca ' de kullanılabilir `CBookmark<0>` .

## <a name="cbookmarkoperator-"></a><a name="operator"></a> CBookmark:: operator =

Bir `CBookmark` nesneyi başka bir nesneye atar.

### <a name="syntax"></a>Syntax

```cpp
CBookmark& operator =(const CBookmark& bookmark) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç yalnızca içinde gereklidir `CBookmark<0>` .

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
