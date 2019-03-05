---
title: Idataobjectımpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl::DAdvise
- ATLCTL/ATL::IDataObjectImpl::DUnadvise
- ATLCTL/ATL::IDataObjectImpl::EnumDAdvise
- ATLCTL/ATL::IDataObjectImpl::EnumFormatEtc
- ATLCTL/ATL::IDataObjectImpl::FireDataChange
- ATLCTL/ATL::IDataObjectImpl::GetCanonicalFormatEtc
- ATLCTL/ATL::IDataObjectImpl::GetData
- ATLCTL/ATL::IDataObjectImpl::GetDataHere
- ATLCTL/ATL::IDataObjectImpl::QueryGetData
- ATLCTL/ATL::IDataObjectImpl::SetData
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
ms.openlocfilehash: b73cfe83075b9595bc98ca05ab2ec2e1771a038d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271976"
---
# <a name="idataobjectimpl-class"></a>Idataobjectımpl sınıfı

Bu sınıf, Tekdüzen veri aktarımı destekleyen ve bağlantıları yönetmek için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IDataObjectImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IDataObjectImpl`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IDataObjectImpl::DAdvise](#dadvise)|Veri nesnesi ve bir öneri havuz arasında bir bağlantı kurar. Bu nesnede değişiklik bildirimleri almak öneri havuz sağlar.|
|[IDataObjectImpl::DUnadvise](#dunadvise)|Daha önce aracılığıyla kurulan bir bağlantıyı sonlandırır `DAdvise`.|
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|Geçerli danışmanlık bağlantıları yineleme yapmak için bir numaralandırıcı oluşturur.|
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|Yinelemek için bir numaralandırıcı oluşturur `FORMATETC` veri nesnesi tarafından desteklenen yapılar. ATL uygulamasını E_NOTIMPL döndürür.|
|[IDataObjectImpl::FireDataChange](#firedatachange)|Bir değişiklik bildirimi her öneri havuza geri gönderir.|
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|Mantıksal eşdeğer alır `FORMATETC` daha karmaşık bir yapısı. ATL uygulamasını E_NOTIMPL döndürür.|
|[IDataObjectImpl::GetData](#getdata)|Verileri veri nesnesinden istemciye aktarır. Veri bölümünde açıklanan bir `FORMATETC` yapısı ve üzerinden aktarılan bir `STGMEDIUM` yapısı.|
|[IDataObjectImpl::GetDataHere](#getdatahere)|Benzer şekilde `GetData`istemci ayırmalısınız dışında `STGMEDIUM` yapısı. ATL uygulamasını E_NOTIMPL döndürür.|
|[IDataObjectImpl::QueryGetData](#querygetdata)|Belirli bir veri nesnesi destekleyip desteklemediğini belirler `FORMATETC` aktarılması veri yapısı. ATL uygulamasını E_NOTIMPL döndürür.|
|[IDataObjectImpl::SetData](#setdata)|İstemciden, verileri veri nesnesine aktarır. ATL uygulamasını E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

[IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) arabirimi Tekdüzen veri aktarımı desteklemek için yöntemler sağlar. `IDataObject` standart biçim yapıları kullanan [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) ve [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) veri depolamak ve almak için.

`IDataObject` Ayrıca veri değişikliği bildirimleri işlemek için havuzlarını bildirmek için bağlantıları yönetir. İstemci istemcinin veri nesnesinden veri değişikliği bildirimleri almak sırada uygulamalıdır [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink) arabirimdeki bir öneri havuz adlı bir nesne. İstemci ardından çağırdığında `IDataObject::DAdvise`, öneri havuz veri nesnesi arasında bir bağlantı kurulur.

Sınıf `IDataObjectImpl` bir varsayılan uygulamayı sağlar `IDataObject` ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

**İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IDataObject`

`IDataObjectImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

##  <a name="dadvise"></a>  IDataObjectImpl::DAdvise

Veri nesnesi ve bir öneri havuz arasında bir bağlantı kurar.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Açıklamalar

Bu nesnede değişiklik bildirimleri almak öneri havuz sağlar.

Bağlantıyı sonlandırmak için çağrı [DUnadvise](#dunadvise).

Bkz: [IDataObject::DAdvise](/windows/desktop/api/objidl/nf-objidl-idataobject-dadvise) Windows SDK içinde.

##  <a name="dunadvise"></a>  IDataObjectImpl::DUnadvise

Daha önce aracılığıyla kurulan bir bağlantıyı sonlandırır [DAdvise](#dadvise).

```
HRESULT DUnadvise(DWORD dwConnection);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IDataObject::DUnadvise](/windows/desktop/api/objidl/nf-objidl-idataobject-dunadvise) Windows SDK içinde.

##  <a name="enumdadvise"></a>  IDataObjectImpl::EnumDAdvise

Geçerli danışmanlık bağlantıları yineleme yapmak için bir numaralandırıcı oluşturur.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IDataObject::EnumDAdvise](/windows/desktop/api/objidl/nf-objidl-idataobject-enumdadvise) Windows SDK içinde.

##  <a name="enumformatetc"></a>  IDataObjectImpl::EnumFormatEtc

Yinelemek için bir numaralandırıcı oluşturur `FORMATETC` veri nesnesi tarafından desteklenen yapılar.

```
HRESULT EnumFormatEtc(
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IDataObject::EnumFormatEtc](/windows/desktop/api/objidl/nf-objidl-idataobject-enumformatetc) Windows SDK içinde.

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

##  <a name="firedatachange"></a>  IDataObjectImpl::FireDataChange

Şu anda yönetilen geri her öneri havuz için bir değişiklik bildirimi gönderir.

```
HRESULT FireDataChange();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="getcanonicalformatetc"></a>  IDataObjectImpl::GetCanonicalFormatEtc

Mantıksal eşdeğer alır `FORMATETC` daha karmaşık bir yapısı.

```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

### <a name="remarks"></a>Açıklamalar

Bkz: [IDataObject::GetCanonicalFormatEtc](/windows/desktop/api/objidl/nf-objidl-idataobject-getcanonicalformatetc) Windows SDK içinde.

##  <a name="getdata"></a>  IDataObjectImpl::GetData

Verileri veri nesnesinden istemciye aktarır.

```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```

### <a name="remarks"></a>Açıklamalar

*PformatetcIn* parametresini TYMED_MFPICT depolama Orta türünü belirtmeniz gerekir.

Bkz: [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) Windows SDK içinde.

##  <a name="getdatahere"></a>  IDataObjectImpl::GetDataHere

Benzer şekilde `GetData`istemci ayırmalısınız dışında `STGMEDIUM` yapısı.

```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

### <a name="remarks"></a>Açıklamalar

Bkz: [TYMED](/windows/desktop/api/objidl/nf-objidl-idataobject-getdatahere) Windows SDK içinde.

##  <a name="querygetdata"></a>  IDataObjectImpl::QueryGetData

Belirli bir veri nesnesi destekleyip desteklemediğini belirler `FORMATETC` aktarılması veri yapısı.

```
HRESULT QueryGetData(FORMATETC* pformatetc);
```

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

### <a name="remarks"></a>Açıklamalar

Bkz: [IDataObject::QueryGetData](/windows/desktop/api/objidl/nf-objidl-idataobject-querygetdata) Windows SDK içinde.

##  <a name="setdata"></a>  IDataObjectImpl::SetData

İstemciden, verileri veri nesnesine aktarır.

```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

### <a name="remarks"></a>Açıklamalar

Bkz: [IDataObject::SetData](/windows/desktop/api/objidl/nf-objidl-idataobject-setdata) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
