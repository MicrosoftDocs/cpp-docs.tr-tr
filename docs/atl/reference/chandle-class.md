---
title: CHandle Sınıfı
ms.date: 07/09/2019
f1_keywords:
- CHandle
- ATLBASE/ATL::CHandle
- ATLBASE/ATL::CHandle::CHandle
- ATLBASE/ATL::CHandle::Attach
- ATLBASE/ATL::CHandle::Close
- ATLBASE/ATL::CHandle::Detach
- ATLBASE/ATL::CHandle::m_h
helpviewer_keywords:
- CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
ms.openlocfilehash: 4b883bdf3159c40f8d74866f04f655ae73d82a8a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747702"
---
# <a name="chandle-class"></a>CHandle Sınıfı

Bu sınıf, bir tanıtıcı nesnesi oluşturma ve kullanma yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CHandle
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CHandle::CHandle](#chandle)|Oluşturucu.|
|[CHandle::~CHandle](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CHandle::Ekle](#attach)|Nesneyi varolan `CHandle` bir tutamaya eklemek için bu yöntemi çağırın.|
|[CHandle::Kapat](#close)|Bir `CHandle` nesneyi kapatmak için bu yöntemi çağırın.|
|[CHandle::Detach](#detach)|Bir tutamacı bir `CHandle` nesneden ayırmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CHandle::operatör HANDLE](#operator_handle)|Depolanan tanıtıcının değerini verir.|
|[CHandle::operator =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CHandle::m_h](#m_h)|Tutamacı depolayan üye değişken.|

## <a name="remarks"></a>Açıklamalar

Bir `CHandle` iş tiş için gereken her zaman bir nesne `CHandle` kullanılabilir: temel fark, nesnenin otomatik olarak silinmesidir.

> [!NOTE]
> Bazı API işlevleri BOŞ veya geçersiz tutamaç olarak NULL kullanırken, diğerleri INVALID_HANDLE_VALUE kullanır. `CHandle`yalnızca NULL kullanır ve INVALID_HANDLE_VALUE gerçek bir kulp olarak ele alacaktır. INVALID_HANDLE_VALUE döndürebilen bir API'yi ararsanız, [CHandle'ı](#attach) aramadan önce bu `CHandle` değeri kontrol etmelisiniz::Ekle veya oluşturucuya geçirin ve bunun yerine NULL'u geçmelisiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="chandleattach"></a><a name="attach"></a>CHandle::Ekle

Nesneyi varolan `CHandle` bir tutamaya eklemek için bu yöntemi çağırın.

```cpp
void Attach(HANDLE h) throw();
```

### <a name="parameters"></a>Parametreler

*H*<br/>
`CHandle`kolu *h*sahipliğini alacaktır.

### <a name="remarks"></a>Açıklamalar

Nesneyi `CHandle` *h* koluna atar ve **h.Detach()** çağırır. Debugs oluşturur, *h* NULL ise bir ATLASSERT yükseltilir. Tutamacın geçerliliği yle ilgili başka bir denetim yapılmaz.

## <a name="chandlechandle"></a><a name="chandle"></a>CHandle::CHandle

Oluşturucu.

```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```

### <a name="parameters"></a>Parametreler

*H*<br/>
Varolan bir `CHandle`tutamaç veya .

### <a name="remarks"></a>Açıklamalar

İsteğe bağlı `CHandle` olarak varolan bir tanıtıcı yı veya `CHandle` nesneyi kullanarak yeni bir nesne oluşturur.

## <a name="chandlechandle"></a><a name="dtor"></a>CHandle::~CHandle

Yıkıcı.

```
~CHandle() throw();
```

### <a name="remarks"></a>Açıklamalar

CHandle'ı arayarak nesneyi `CHandle` serbest [kapatır::Kapat.](#close)

## <a name="chandleclose"></a><a name="close"></a>CHandle::Kapat

Bir `CHandle` nesneyi kapatmak için bu yöntemi çağırın.

```cpp
void Close() throw();
```

### <a name="remarks"></a>Açıklamalar

Açık nesne tutamacını kapatır. Tutamak NULL ise, zaten çağrıldıysa `Close` durum böyle olacaksa, hata ayıklama yapılarda bir ATLASSERT yükseltilir.

## <a name="chandledetach"></a><a name="detach"></a>CHandle::Detach

Bir tutamacı bir `CHandle` nesneden ayırmak için bu yöntemi çağırın.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tutamacının ayrılmasını verir.

### <a name="remarks"></a>Açıklamalar

Tanıtıcının sahipliğini serbest bırakır.

## <a name="chandlem_h"></a><a name="m_h"></a>CHandle::m_h

Tutamacı depolayan üye değişken.

```
HANDLE m_h;
```

## <a name="chandleoperator-"></a><a name="operator_eq"></a>CHandle::operator =

Atama işleci.

```
CHandle& operator=(CHandle& h) throw();
```

### <a name="parameters"></a>Parametreler

*H*<br/>
`CHandle`kolu *h*sahipliğini alacaktır.

### <a name="return-value"></a>Dönüş Değeri

Yeni `CHandle` nesneye bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

`CHandle` Nesne şu anda bir tanıtıcı içeriyorsa, kapatılacaktır. Geçirilen `CHandle` nesnenin tutamak başvurusu NULL olarak ayarlanır. Bu, iki `CHandle` nesnenin asla aynı etkin tutamacı içermemesini sağlar.

## <a name="chandleoperator-handle"></a><a name="operator_handle"></a>CHandle::operatör HANDLE

Depolanan tanıtıcının değerini verir.

```
operator HANDLE() const throw();
```

### <a name="remarks"></a>Açıklamalar

CHandle'da depolanan değeri [verir:m_h.](#m_h)

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
