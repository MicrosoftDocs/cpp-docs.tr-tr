---
title: CComPtr sınıfı
description: Microsoft C++ etkin şablon KITAPLıĞı (ATL) CComPtr sınıfı için başvuru kılavuzu.
ms.date: 02/07/2020
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
ms.openlocfilehash: 74a12b460f55a782fa2747b02f7d00287786fae6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127413"
---
# <a name="ccomptr-class"></a>CComPtr sınıfı

COM arabirimi işaretçilerini yönetmeye yönelik akıllı bir işaretçi sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class CComPtr
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Depolanacak işaretçinin türünü belirten bir COM arabirimi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComPtr:: CComPtr](#ccomptr)|Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComPtr:: operator =](#operator_eq)|Üye işaretçisine bir işaretçi atar.|

## <a name="remarks"></a>Açıklamalar

ATL, COM arabirim işaretçilerini yönetmek için `CComPtr` ve [CComQIPtr](../../atl/reference/ccomqiptr-class.md) kullanır. Her ikisi de [CComPtrBase](../../atl/reference/ccomptrbase-class.md)öğesinden türetilir ve her ikisi de otomatik başvuru saymasıdır.

`CComPtr` ve [CComQIPtr](../../atl/reference/ccomqiptr-class.md) sınıfları, otomatik başvuru sayımı gerçekleştirerek bellek sızıntılarını ortadan kaldırmaya yardımcı olabilir.  Aşağıdaki işlevler aynı mantıksal işlemleri de işler. Ancak, ikinci sürüm `CComPtr` sınıfını kullandığından daha az hata olabilir:

[!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]

[!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]

Hata ayıklama Derlemeleriyle, kod izleme için Atlsd. lib bağlantısını yapın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

`CComPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccomptr"></a>CComPtr:: CComPtr

Oluşturucu.

```cpp
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```

### <a name="parameters"></a>Parametreler

*'nin*<br/>
Arabirim işaretçisini başlatmak için kullanılır.

*Şı*<br/>
Bir COM arabirimi.

### <a name="remarks"></a>Açıklamalar

Bir bağımsız değişken çağrısı alan oluşturucular, bir null işaretçi değilse, *LP*üzerinde `AddRef`. Null olmayan bir nesne, CComPtr nesnesinin yok edilmesiyle veya CComPtr nesnesine yeni bir nesne atanmışsa bir `Release` çağrısı alır.

## <a name="operator_eq"></a>CComPtr:: operator =

Atama işleci.

```cpp
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CComPtr` nesnesine bir işaretçi döndürür

### <a name="remarks"></a>Açıklamalar

Bu işlem, yeni nesneyi AddRefs ve varsa var olan nesneyi serbest bırakır.

## <a name="see-also"></a>Ayrıca bkz.

[CComPtr:: CComPtr](#ccomptr)<br/>
[CComQIPtr:: CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
