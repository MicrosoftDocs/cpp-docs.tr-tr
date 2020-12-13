---
description: 'Daha fazla bilgi edinin: CHandle Class'
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
ms.openlocfilehash: 01c3b281daf829bc6488df35114c6cb853640ed1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141680"
---
# <a name="chandle-class"></a>CHandle sınıfı

Bu sınıf bir tanıtıcı nesnesi oluşturmak ve kullanmak için yöntemler sağlar.

## <a name="syntax"></a>Syntax

```
class CHandle
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHandle::CHandle](#chandle)|Oluşturucu.|
|[CHandle:: ~ CHandle](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHandle:: Attach](#attach)|`CHandle`Nesneyi var olan bir tanıtıcıya iliştirmek için bu yöntemi çağırın.|
|[CHandle:: Close](#close)|Bir nesneyi kapatmak için bu yöntemi çağırın `CHandle` .|
|[CHandle::D etach](#detach)|Bir tanıtıcıyı bir nesneden ayırmak için bu yöntemi çağırın `CHandle` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CHandle:: operator işleci](#operator_handle)|Saklı tanıtıcının değerini döndürür.|
|[CHandle:: operator =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CHandle:: m_h](#m_h)|Tanıtıcıyı depolayan üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bir `CHandle` tanıtıcı her gerektiğinde bir nesne kullanılabilir: temel fark, `CHandle` nesnenin otomatik olarak silineceği bir değer olacaktır.

> [!NOTE]
> Bazı API işlevleri boş veya geçersiz bir tanıtıcı olarak NULL kullanır, diğerleri INVALID_HANDLE_VALUE kullanır. `CHandle` yalnızca NULL kullanır ve INVALID_HANDLE_VALUE gerçek bir tanıtıcı olarak değerlendirir. INVALID_HANDLE_VALUE döndürebilen bir API çağırırsanız, [CHandle:: Attach](#attach) ' i çağırmadan veya oluşturucuya geçirmeden önce bu değeri denetlemeniz gerekir `CHandle` ve bunun yerine NULL geçirin.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="chandleattach"></a><a name="attach"></a> CHandle:: Attach

`CHandle`Nesneyi var olan bir tanıtıcıya iliştirmek için bu yöntemi çağırın.

```cpp
void Attach(HANDLE h) throw();
```

### <a name="parameters"></a>Parametreler

*h*<br/>
`CHandle` , tanıtıcı *h*'nin sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

`CHandle`Nesnesini *h* tanıtıcısına atar ve ardından **h. detach ()** çağırır. Hata ayıklama GS yapılarında, *h* null olduğunda ATLASSERT tetiklenir. Tanıtıcının geçerliliği için başka bir denetim yapılmaz.

## <a name="chandlechandle"></a><a name="chandle"></a> CHandle::CHandle

Oluşturucu.

```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Var olan bir tanıtıcı veya `CHandle` .

### <a name="remarks"></a>Açıklamalar

`CHandle`İsteğe bağlı olarak var olan bir tanıtıcı veya nesne kullanarak yeni bir nesne oluşturur `CHandle` .

## <a name="chandlechandle"></a><a name="dtor"></a> CHandle:: ~ CHandle

Yok edicisi.

```
~CHandle() throw();
```

### <a name="remarks"></a>Açıklamalar

`CHandle` [CHandle:: Close](#close)çağırarak nesneyi serbest bırakır.

## <a name="chandleclose"></a><a name="close"></a> CHandle:: Close

Bir nesneyi kapatmak için bu yöntemi çağırın `CHandle` .

```cpp
void Close() throw();
```

### <a name="remarks"></a>Açıklamalar

Açık nesne tanıtıcısını kapatır. Tanıtıcı NULL ise, bu durum, `Close` zaten çağrılırsa, hata ayıklama yapılarında BIR ATLASSERT tetiklenir.

## <a name="chandledetach"></a><a name="detach"></a> CHandle::D etach

Bir tanıtıcıyı bir nesneden ayırmak için bu yöntemi çağırın `CHandle` .

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmakta olan tutamacı döndürür.

### <a name="remarks"></a>Açıklamalar

Tanıtıcının sahipliğini yayınlar.

## <a name="chandlem_h"></a><a name="m_h"></a> CHandle:: m_h

Tanıtıcıyı depolayan üye değişkeni.

```
HANDLE m_h;
```

## <a name="chandleoperator-"></a><a name="operator_eq"></a> CHandle:: operator =

Atama işleci.

```
CHandle& operator=(CHandle& h) throw();
```

### <a name="parameters"></a>Parametreler

*h*<br/>
`CHandle` , tanıtıcı *h*'nin sahipliğini alır.

### <a name="return-value"></a>Dönüş Değeri

Yeni nesneye bir başvuru döndürür `CHandle` .

### <a name="remarks"></a>Açıklamalar

`CHandle`Nesne şu anda bir tanıtıcı içeriyorsa kapalı olur. `CHandle`Geçirilen nesnenin tanıtıcı başvurusu null olarak ayarlanmalıdır. Bu `CHandle` , iki nesnenin aynı etkin tanıtıcıyı hiçbir şekilde bulundurmamasını sağlar.

## <a name="chandleoperator-handle"></a><a name="operator_handle"></a> CHandle:: operator işleci

Saklı tanıtıcının değerini döndürür.

```
operator HANDLE() const throw();
```

### <a name="remarks"></a>Açıklamalar

[CHandle:: m_h](#m_h)içinde depolanan değeri döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
