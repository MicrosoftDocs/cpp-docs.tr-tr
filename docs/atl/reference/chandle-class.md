---
title: CHandle sınıfı
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
ms.openlocfilehash: 86d2cba6c3ee2e914d96ae2a09b642d556d46027
ms.sourcegitcommit: 07b34ca1c1fecced9fadc95de15dc5fee4f31e5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67693405"
---
# <a name="chandle-class"></a>CHandle sınıfı

Bu sınıf, oluşturma ve bir tanıtıcı nesnesi kullanılarak yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CHandle
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHandle::CHandle](#chandle)|Oluşturucu.|
|[CHandle:: ~ CHandle](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHandle::Attach](#attach)|Eklemek için bu yöntemi çağırın `CHandle` için var olan bir tanıtıcı nesnesi.|
|[CHandle::Close](#close)|Kapatmak için bu yöntemi çağıran bir `CHandle` nesne.|
|[CHandle::Detach](#detach)|Bir tanıtıcıdan ayırmak için bu yöntemi çağıran bir `CHandle` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CHandle::operator TANITICISI](#operator_handle)|Saklı tanıtıcı değerini döndürür.|
|[CHandle::operator =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CHandle::m_h](#m_h)|Tanıtıcı saklayan üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

A `CHandle` nesnesi, bir tanıtıcı gerekli olduğunda kullanılabilir: Ana fark `CHandle` nesne otomatik olarak silinecek.

> [!NOTE]
>  Başkalarının INVALID_HANDLE_VALUE kullanırken bazı API işlevleri NULL bir boş veya geçersiz tanıtıcı kullanın. `CHandle` yalnızca kullandığı edecek ve NULL INVALID_HANDLE_VALUE gerçek bir işleyici kabul eder. INVALID_HANDLE_VALUE döndürebilir bir API çağırırsanız, çağırmadan önce bu değer için denetlemelisiniz [CHandle::Attach](#attach) veya aktarması `CHandle` oluşturucusu ve bunun yerine NULL geçirin.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="attach"></a>  CHandle::Attach

Eklemek için bu yöntemi çağırın `CHandle` için var olan bir tanıtıcı nesnesi.

```
void Attach(HANDLE h) throw();
```

### <a name="parameters"></a>Parametreler

*h*<br/>
`CHandle` tanıtıcı sahipliğini *h*.

### <a name="remarks"></a>Açıklamalar

Atar `CHandle` nesnesini *h* tanıtıcısı ve çağrıları **h.Detach()** . Hatalarını düzeltir yapılarında bir ATLASSERT gerçekleştirilecektir *h* null. Tanıtıcı geçerliliğini dair herhangi bir denetim yapılmaz.

##  <a name="chandle"></a>  CHandle::CHandle

Oluşturucu.

```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Var olan bir tanıtıcı veya `CHandle`.

### <a name="remarks"></a>Açıklamalar

Yeni bir oluşturur `CHandle` nesne, isteğe bağlı olarak var olan bir tanıtıcı kullanarak veya `CHandle` nesne.

##  <a name="dtor"></a>  CHandle:: ~ CHandle

Yıkıcı.

```
~CHandle() throw();
```

### <a name="remarks"></a>Açıklamalar

Serbest bırakma `CHandle` çağırarak [CHandle::Close](#close).

##  <a name="close"></a>  CHandle::Close

Kapatmak için bu yöntemi çağıran bir `CHandle` nesne.

```
void Close() throw();
```

### <a name="remarks"></a>Açıklamalar

Bir nesne tanıtıcısı kapatır. Tanıtıcı büyük/küçük harf ise olacağı NULL olup olmadığını `Close` zaten adlı bir ATLASSERT hata ayıklama yapılarında gerçekleştirilecektir.

##  <a name="detach"></a>  CHandle::Detach

Bir tanıtıcıdan ayırmak için bu yöntemi çağıran bir `CHandle` nesne.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmakta tanıtıcısını döndürür.

### <a name="remarks"></a>Açıklamalar

Tanıtıcı sahipliğini serbest bırakır.

##  <a name="m_h"></a>  CHandle::m_h

Tanıtıcı saklayan üye değişkeni.

```
HANDLE m_h;
```

##  <a name="operator_eq"></a>  CHandle::operator =

Atama işleci.

```
CHandle& operator=(CHandle& h) throw();
```

### <a name="parameters"></a>Parametreler

*h*<br/>
`CHandle` tanıtıcı sahipliğini *h*.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir başvuru döndürür `CHandle` nesne.

### <a name="remarks"></a>Açıklamalar

Varsa `CHandle` nesnesi şu anda bir tanıtıcı içerir, kapatılacak. `CHandle` Nesne NULL olarak ayarlamak, tanıtıcı başvurusu geçirilen sahip olur. Bu, iki sağlar `CHandle` nesneleri hiçbir zaman aynı etkin tanıtıcıyı içerir.

##  <a name="operator_handle"></a>  CHandle::operator TANITICISI

Saklı tanıtıcı değerini döndürür.

```
operator HANDLE() const throw();
```

### <a name="remarks"></a>Açıklamalar

İçinde depolanan değeri döndürür [CHandle::m_h](#m_h).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
