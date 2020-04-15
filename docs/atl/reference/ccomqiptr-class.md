---
title: CComQIPtr Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
ms.openlocfilehash: 2b1d8b92fbc5e95a5061956bafc4922d249a6f18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327427"
---
# <a name="ccomqiptr-class"></a>CComQIPtr Sınıfı

COM arabirim işaretçilerini yönetmek için akıllı işaretçi sınıfı.

## <a name="syntax"></a>Sözdizimi

```
template<class T, const IID* piid= &__uuidof(T)>
class CComQIPtr: public CComPtr<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Depolanacak işaretçi türünü belirten bir COM arabirimi.

*piid*<br/>
*T*IID için bir işaretçi .

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComQIPtr::CComQIPtr](#ccomqiptr)|Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CComQIPtr::operatör =](#operator_eq)|Üye işaretçiye bir işaretçi atar.|

## <a name="remarks"></a>Açıklamalar

ATL, `CComQIPtr` her ikisi de [CComPtrBase'den](../../atl/reference/ccomptrbase-class.md)türetilen COM arabirim işaretçilerini yönetmek için Kullanır ve [CComPtr'ı](../../atl/reference/ccomptr-class.md) kullanır. Her iki sınıf `AddRef` da aramalar `Release`yoluyla otomatik başvuru sayma yapar ve. Aşırı yüklü işleçler işaretçi işlemlerini işler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

[Ccomptr](../../atl/reference/ccomptr-class.md)

`CComQIPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomcli.h

## <a name="ccomqiptrccomqiptr"></a><a name="ccomqiptr"></a>CComQIPtr::CComQIPtr

Oluşturucu.

```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```

### <a name="parameters"></a>Parametreler

*Lp*<br/>
Arabirim işaretçisini başlatmak için kullanılır.

*T*<br/>
Com arabirimi.

*piid*<br/>
*T*IID için bir işaretçi .

## <a name="ccomqiptroperator-"></a><a name="operator_eq"></a>CComQIPtr::operatör =

Atama işleci.

```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```

### <a name="parameters"></a>Parametreler

*Lp*<br/>
Arabirim işaretçisini başlatmak için kullanılır.

*T*<br/>
Com arabirimi.

*piid*<br/>
*T*IID için bir işaretçi .

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneye `CComQIPtr` bir işaretçi döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComPtr::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)<br/>
[CComQIPtr::CComQIPtr](#ccomqiptr)<br/>
[CComPtrBase Sınıfı](../../atl/reference/ccomptrbase-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[CComQIPtrElementTraits Sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)
