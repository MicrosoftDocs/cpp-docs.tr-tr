---
description: 'Daha fazla bilgi edinin: CComObjectGlobal sınıfı'
title: CComObjectGlobal sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
ms.openlocfilehash: 0f79acb0fdbb43f9456e08f26875d45eec9904c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151989"
---
# <a name="ccomobjectglobal-class"></a>CComObjectGlobal sınıfı

Bu sınıf, nesnenizin bulunduğu modüldeki başvuru sayısını yönetir `Base` .

## <a name="syntax"></a>Sözdizimi

```
template<class Base>
class CComObjectGlobal : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
Sınıfınız, [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)öğesinden türetilir ve ayrıca, nesne üzerinde desteklemek istediğiniz diğer herhangi bir arabirimden.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectGlobal:: CComObjectGlobal](#ccomobjectglobal)|Oluşturucu.|
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectGlobal:: AddRef](#addref)|Küresel bir uygular `AddRef` .|
|[CComObjectGlobal:: QueryInterface](#queryinterface)|Küresel bir uygular `QueryInterface` .|
|[CComObjectGlobal:: Release](#release)|Küresel bir uygular `Release` .|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComObjectGlobal:: m_hResFinalConstruct](#m_hresfinalconstruct)|Nesnenin oluşturulması sırasında döndürülen HRESULT 'yi içerir `CComObjectGlobal` .|

## <a name="remarks"></a>Açıklamalar

`CComObjectGlobal` nesneniz içeren modüldeki başvuru sayısını yönetir `Base` . `CComObjectGlobal` Modül serbest bırakıldığı sürece nesnenizin silinmemesini sağlar. Nesneniz yalnızca modülün tamamındaki başvuru sayısı sıfır olduğunda kaldırılacak.

Örneğin, `CComObjectGlobal` bir sınıf fabrikası kullanarak tüm istemcileri tarafından paylaşılan ortak bir genel nesne tutabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComObjectGlobal`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ccomobjectglobaladdref"></a><a name="addref"></a> CComObjectGlobal:: AddRef

Nesnenin başvuru sayısını 1 ' i arttırır.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Dönüş Değeri

Tanılama ve test için yararlı olabilecek bir değer.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `AddRef` `_Module::Lock` `_Module` bir [CComModule](../../atl/reference/ccommodule-class.md) 'un genel örneği veya ondan türetilmiş bir sınıf olan çağırır.

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="ccomobjectglobal"></a> CComObjectGlobal:: CComObjectGlobal

Oluşturucu. `FinalConstruct`Tarafından döndürülen [m_hResFinalConstruct](#m_hresfinalconstruct) çağırır ve sonra ayarlar `HRESULT` `FinalConstruct` .

```
CComObjectGlobal(void* = NULL));
```

### <a name="remarks"></a>Açıklamalar

[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)' den temel sınıfınızı türettiğiniz takdirde kendi yönteminizi sağlamanız gerekir `FinalConstruct` . Yıkıcı çağırır `FinalRelease` .

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="dtor"></a> CComObjectGlobal:: ~ CComObjectGlobal

Yok edicisi.

```
CComObjectGlobal();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır ve [Sonlandıryayım](ccomobjectrootex-class.md#finalrelease)çağırır.

## <a name="ccomobjectglobalm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a> CComObjectGlobal:: m_hResFinalConstruct

Nesnenin oluşturulması sırasında çağrı yapılacak HRESULT 'yi içerir `FinalConstruct` `CComObjectGlobal` .

```
HRESULT m_hResFinalConstruct;
```

## <a name="ccomobjectglobalqueryinterface"></a><a name="queryinterface"></a> CComObjectGlobal:: QueryInterface

İstenen arabirim işaretçisine bir işaretçi alır.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki İstenen arabirimin GUID 'SI.

*ppvObject*<br/>
dışı Arabirim bulunmazsa, IID tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi veya arabirim bulunamazsa NULL.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`QueryInterface` yalnızca COM Map tablosundaki arabirimleri işler.

## <a name="ccomobjectglobalrelease"></a><a name="release"></a> CComObjectGlobal:: Release

Nesnenin başvuru sayısını 1 ' i azaltır.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Dönüş Değeri

Hata ayıklama yapılarında, `Release` Tanılama ve test için yararlı olabilecek bir değer döndürür. Hata ayıklama olmayan derlemelerde, `Release` her zaman 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `Release` `_Module::Unlock` `_Module` bir [CComModule](../../atl/reference/ccommodule-class.md) 'un genel örneği veya ondan türetilmiş bir sınıf olan çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[CComObjectStack sınıfı](../../atl/reference/ccomobjectstack-class.md)<br/>
[CComAggObject sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
