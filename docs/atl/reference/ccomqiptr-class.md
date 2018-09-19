---
title: CComQIPtr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
dev_langs:
- C++
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4c35ab13d5cf2448135b1e07405a1e31a5eec86
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116678"
---
# <a name="ccomqiptr-class"></a>CComQIPtr sınıfı

COM arabirim işaretçilerini yönetmek için bir akıllı işaretçi sınıfının.

## <a name="syntax"></a>Sözdizimi

```
template<class T, const IID* piid= &__uuidof(T)>
class CComQIPtr: public CComPtr<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Depolanacak işaretçi türü belirten bir COM arabirimi.

*piid*<br/>
Laboratuvardaki işaretçisi *T*.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComQIPtr::CComQIPtr](#ccomqiptr)|Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComQIPtr::operator =](#operator_eq)|Bir işaretçi, üye işaretçisi atar.|

## <a name="remarks"></a>Açıklamalar

ATL kullanan `CComQIPtr` ve [CComPtr](../../atl/reference/ccomptr-class.md) COM arabirim işaretçilerini yönetmek için ikisi için de öğesinden türetilen [CComPtrBase](../../atl/reference/ccomptrbase-class.md). Her iki sınıfları otomatik başvuru yapılan çağrılar aracılığıyla sayımı gerçekleştirmek `AddRef` ve `Release`. Aşırı yüklenmiş işleçler, işaretçi işlemleri işleyin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

[CComPtr](../../atl/reference/ccomptr-class.md)

`CComQIPtr`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcomcli.h

##  <a name="ccomqiptr"></a>  CComQIPtr::CComQIPtr

Oluşturucu.

```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```

### <a name="parameters"></a>Parametreler

*LP*<br/>
Arabirim işaretçisi başlatmak için kullanılır.

*T*<br/>
Bir COM arabirimi.

*piid*<br/>
Laboratuvardaki işaretçisi *T*.

##  <a name="operator_eq"></a>  CComQIPtr::operator =

Atama işleci.

```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```

### <a name="parameters"></a>Parametreler

*LP*<br/>
Arabirim işaretçisi başlatmak için kullanılır.

*T*<br/>
Bir COM arabirimi.

*piid*<br/>
Laboratuvardaki işaretçisi *T*.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş bir işaretçi döndürür `CComQIPtr` nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[CComPtr::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)<br/>
[CComQIPtr::CComQIPtr](#ccomqiptr)<br/>
[CComPtrBase Sınıfı](../../atl/reference/ccomptrbase-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[CComQIPtrElementTraits Sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)
