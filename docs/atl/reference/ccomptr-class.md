---
title: CComPtr sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
ms.openlocfilehash: 5e3e510291daa50ddcf5d63451edef0428d66ed1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280478"
---
# <a name="ccomptr-class"></a>CComPtr sınıfı

COM arabirim işaretçilerini yönetmek için bir akıllı işaretçi sınıfının.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class CComPtr
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Depolanacak işaretçi türü belirten bir COM arabirimi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComPtr::CComPtr](#ccomptr)|Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComPtr::operator =](#operator_eq)|Bir işaretçi, üye işaretçisi atar.|

## <a name="remarks"></a>Açıklamalar

ATL kullanan `CComPtr` ve [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM arabirim işaretçilerini yönetmek için. Her ikisi de türetilmiş [CComPtrBase](../../atl/reference/ccomptrbase-class.md), ve her ikisi de otomatik başvuru sayımı gerçekleştirin.

`CComPtr` Ve [CComQIPtr](../../atl/reference/ccomqiptr-class.md) sınıfları otomatik başvuru sayımı gerçekleştirerek bellek sızıntılarını ortadan yardımcı olabilir.  Aşağıdaki işlevler hem de aynı mantıksal işlemleri; Ancak, nasıl ikinci sürüm kullanarak hataya daha az olabileceğine dikkat edin `CComPtr` sınıfı:

[!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]

[!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]

Hata ayıklama yapılarında, kod izleme atlsd.lib bağlayın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

`CComPtr`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="ccomptr"></a>  CComPtr::CComPtr

Oluşturucu.

```
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```

### <a name="parameters"></a>Parametreler

*LP*<br/>
Arabirim işaretçisi başlatmak için kullanılır.

*T*<br/>
Bir COM arabirimi.

##  <a name="operator_eq"></a>  CComPtr::operator =

Atama işleci.

```
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş bir işaretçi döndürür `CComPtr` nesnesi

### <a name="remarks"></a>Açıklamalar

Bu işlem AddRefs yeni bir nesne ve sürümler var olan nesne yok.

## <a name="see-also"></a>Ayrıca bkz.

[CComPtr::CComPtr](#ccomptr)<br/>
[CComQIPtr::CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
