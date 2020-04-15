---
title: CComPtr Sınıfı
description: Microsoft C++ Etkin Şablon Kitaplığı (ATL) sınıfı CComPtr için başvuru kılavuzu.
ms.date: 02/07/2020
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
ms.openlocfilehash: 855466225db2672755658dcbbc9a266d09e0e7be
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327522"
---
# <a name="ccomptr-class"></a>CComPtr Sınıfı

COM arabirim işaretçilerini yönetmek için akıllı işaretçi sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class CComPtr
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Depolanacak işaretçi türünü belirten bir COM arabirimi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComPtr::CComPtr](#ccomptr)|Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CComPtr::operatör =](#operator_eq)|Üye işaretçiye bir işaretçi atar.|

## <a name="remarks"></a>Açıklamalar

Com arabirim işaretçileri yönetmek için ATL kullanır `CComPtr` ve [CComQIPtr.](../../atl/reference/ccomqiptr-class.md) Her ikisi de [CComPtrBase](../../atl/reference/ccomptrbase-class.md)türetilmiştir , ve her ikisi de otomatik referans sayma yapmak.

Ve `CComPtr` [CComQIPtr](../../atl/reference/ccomqiptr-class.md) sınıfları otomatik başvuru sayımı gerçekleştirerek bellek sızıntılarını ortadan kaldırmaya yardımcı olabilir.  Aşağıdaki işlevlerin her ikisi de aynı mantıksal işlemleri yapar. Ancak, `CComPtr` sınıfı kullandığından ikinci sürüm daha az hataya yatkın olabilir:

[!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]

[!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]

Hata Ayıklama oluşturur, kod izleme için bağlantı atlsd.lib.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

`CComPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccomptrccomptr"></a><a name="ccomptr"></a>CComPtr::CComPtr

Oluşturucu.

```cpp
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```

### <a name="parameters"></a>Parametreler

*Lp*<br/>
Arabirim işaretçisini başlatmak için kullanılır.

*T*<br/>
Com arabirimi.

### <a name="remarks"></a>Açıklamalar

Bir argüman çağrısı `AddRef` almak yapıcılar *lp*, null işaretçi değilse. Null olmayan bir nesne `Release` CComPtr nesnenin imha sı üzerine bir çağrı alır veya CComPtr nesnesine yeni bir nesne atanırsa.

## <a name="ccomptroperator-"></a><a name="operator_eq"></a>CComPtr::operatör =

Atama işleci.

```cpp
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçiyi `CComPtr` güncelleştirilmiş nesneye döndürür

### <a name="remarks"></a>Açıklamalar

Bu işlem AddRefs yeni nesne ve varsa varolan nesneyi salgılar.

## <a name="see-also"></a>Ayrıca bkz.

[CComPtr::CComPtr](#ccomptr)<br/>
[CComQIPtr::CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
