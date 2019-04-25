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
- CBookmark
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
ms.openlocfilehash: fb2e3ec99471405f9c6521e0b70672c1da1b755c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209396"
---
# <a name="cbookmark-class"></a>CBookmark Sınıfı

Bir yer işareti değeri kendi arabellekte tutar.

## <a name="syntax"></a>Sözdizimi

```cpp
template < DBLENGTH nSize = 0 >
class CBookmark : public CBookmarkBase

template <>
class CBookmark< 0 > : public CBookmarkBase
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
Yer işareti arabelleğin bayt cinsinden boyutu. Zaman *nSize* sıfırsa, yer işareti arabellek çalışma zamanında dinamik olarak oluşturulur.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CBookmark](#cbookmark)|Oluşturucu|
|[GetBuffer](#getbuffer)|Arabellek için işaretçi alır.|
|[GetSize](#getsize)|Arabelleğin bayt cinsinden boyutunu alır.|
|[SetBookmark](#setbookmark)|Yer işareti değeri ayarlar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#operator)|Atar `CBookmark` başka bir sınıf.|

## <a name="remarks"></a>Açıklamalar

`CBookmark<0>` bir şablon uzmanlığı olan `CBookmark`; kendi arabelleğini çalışma zamanında dinamik olarak oluşturulur.

## <a name="cbookmark"></a> CBookmark::CBookmark

Oluşturucu.

### <a name="syntax"></a>Sözdizimi

```cpp
CBookmark();
CBookmark(DBLENGTH nSize);
```

#### <a name="parameters"></a>Parametreler

*nSize*<br/>
[in] Yer işareti arabelleğin bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

İlk işlev arabellek NULL ve arabellek boyutu 0 olarak ayarlar. Arabellek boyutu ikinci işlevi ayarlar *nSize*ve bir bayt dizisi olarak arabelleğe *nSize* bayt.

> [!NOTE]
>  Bu işlev yalnızca kullanılabilir `CBookmark<0>`.

## <a name="getbuffer"></a> CBookmark::GetBuffer

Yer işareti arabellek için işaretçi alır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual BYTE* GetBuffer() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yer işareti arabellek için işaretçi.

## <a name="getsize"></a> CBookmark::GetSize

Yer işareti arabellek boyutunu alır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual DBLENGTH GetSize() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Arabelleğin bayt cinsinden boyutu.

## <a name="setbookmark"></a> CBookmark::SetBookmark

Yer işareti değeri tarafından başvurulan kopyalar *pBuffer* için `CBookmark` arabellek ve arabellek boyutu ayarlar *nSize*.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT SetBookmark(DBLENGTH nSize, BYTE* pBuffer) throw();
```

#### <a name="parameters"></a>Parametreler

*nSize*<br/>
[in] Yer işareti arabellek boyutu.

*pBuffer*<br/>
[in] Yer işareti değeri içeren bir bayt dizisine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca kullanılabilir `CBookmark<0>`.

## <a name="operator"></a> CBookmark::operator =

Atayan bir `CBookmark` başka bir nesne.

### <a name="syntax"></a>Sözdizimi

```cpp
CBookmark& operator =(const CBookmark& bookmark) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç yalnızca gerekli `CBookmark<0>`.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)