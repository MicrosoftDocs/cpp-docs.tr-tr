---
description: 'Daha fazla bilgi edinin: CComQIPtr sınıfı'
title: CComQIPtr sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
ms.openlocfilehash: e5af938cd7b2bbae3b091eac5323d3455ce1cf02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142330"
---
# <a name="ccomqiptr-class"></a>CComQIPtr sınıfı

COM arabirimi işaretçilerini yönetmeye yönelik akıllı bir işaretçi sınıfı.

## <a name="syntax"></a>Sözdizimi

```
template<class T, const IID* piid= &__uuidof(T)>
class CComQIPtr: public CComPtr<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Depolanacak işaretçinin türünü belirten bir COM arabirimi.

*piıd*<br/>
*T* IID 'sine yönelik bir işaretçi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComQIPtr:: CComQIPtr](#ccomqiptr)|Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComQIPtr:: operator =](#operator_eq)|Üye işaretçisine bir işaretçi atar.|

## <a name="remarks"></a>Açıklamalar

ATL `CComQIPtr` , her ikisi de [CComPtrBase](../../atl/reference/ccomptrbase-class.md)'den türeten com arabirim işaretçilerini yönetmek Için ve [CComPtr](../../atl/reference/ccomptr-class.md) kullanır. Her iki sınıf de ve çağrıları aracılığıyla otomatik başvuru sayımı gerçekleştirir `AddRef` `Release` . Aşırı yüklenmiş işleçler, işaretçi işlemlerini işler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

[CComPtr](../../atl/reference/ccomptr-class.md)

`CComQIPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomclı. h

## <a name="ccomqiptrccomqiptr"></a><a name="ccomqiptr"></a> CComQIPtr:: CComQIPtr

Oluşturucu.

```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```

### <a name="parameters"></a>Parametreler

*'nin*<br/>
Arabirim işaretçisini başlatmak için kullanılır.

*T*<br/>
Bir COM arabirimi.

*piıd*<br/>
*T* IID 'sine yönelik bir işaretçi.

## <a name="ccomqiptroperator-"></a><a name="operator_eq"></a> CComQIPtr:: operator =

Atama işleci.

```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```

### <a name="parameters"></a>Parametreler

*'nin*<br/>
Arabirim işaretçisini başlatmak için kullanılır.

*T*<br/>
Bir COM arabirimi.

*piıd*<br/>
*T* IID 'sine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneye bir işaretçi döndürür `CComQIPtr` .

## <a name="see-also"></a>Ayrıca bkz.

[CComPtr:: CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)<br/>
[CComQIPtr:: CComQIPtr](#ccomqiptr)<br/>
[CComPtrBase sınıfı](../../atl/reference/ccomptrbase-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Ccomqıptrelementnitelikler sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)
