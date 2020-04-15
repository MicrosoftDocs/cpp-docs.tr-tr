---
title: IDataObjectImpl Sınıfı
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
ms.openlocfilehash: 618f8248a03297120ae2504bcb30ba8f080b184d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329835"
---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl Sınıfı

Bu sınıf, Tek düzen Veri Aktarımı'nı desteklemek ve bağlantıları yönetmek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IDataObjectImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IDataObjectImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IDataObjectImpl::DAdvise](#dadvise)|Veri nesnesi ile bir tavsiye lavabosu arasında bir bağlantı kurar. Bu, tavsiye lavabosu nesnedeğişiklikleri bildirimleri almak için sağlar.|
|[IDataObjectImpl::DTavsiye yok](#dunadvise)|Daha önce kurulan bir bağlantıyı `DAdvise`sonlandırır.|
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|Geçerli danışma bağlantıları aracılığıyla yinelemek için bir sayısallaştırıcı oluşturur.|
|[iDataObjectImpl::EnumFormatEtc](#enumformatetc)|Veri nesnesi tarafından desteklenen `FORMATETC` yapılar aracılığıyla yinelemek için bir sayısallaştırıcı oluşturur. ATL uygulaması E_NOTIMPL döndürür.|
|[IDataObjectImpl::FireDataChange](#firedatachange)|Her tavsiye lavabogeri bir değişiklik bildirimi gönderir.|
|[iDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|Mantıksal olarak eşdeğer `FORMATETC` bir yapıyı daha karmaşık bir yapıya alır. ATL uygulaması E_NOTIMPL döndürür.|
|[IDataObjectImpl::Veri Alın](#getdata)|Veri nesnesinden verileri istemciye aktarın. Veriler bir `FORMATETC` yapıda tanımlanır ve bir `STGMEDIUM` yapı üzerinden aktarılır.|
|[IDataObjectImpl::GetDataHere](#getdatahere)|Benzer `GetData`, istemci dışında `STGMEDIUM` yapı yı ayırması gerekir. ATL uygulaması E_NOTIMPL döndürür.|
|[IDataObjectImpl::QueryGetData](#querygetdata)|Veri nesnesinin veri aktarımı `FORMATETC` için belirli bir yapıyı destekleyip desteklemediğini belirler. ATL uygulaması E_NOTIMPL döndürür.|
|[IDataObjectImpl::SetData](#setdata)|Verileri istemciden veri nesnesine aktarın. ATL uygulaması E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

[IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) arabirimi, Tek düzen Veri Aktarımını destekleyen yöntemler sağlar. `IDataObject`verileri almak ve depolamak için format yapılarını [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) ve [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) kullanır.

`IDataObject`ayrıca, veri değişikliği bildirimlerini işlemek için lavabolara tavsiyelerde bulunmak için bağlantıları yönetir. İstemcinin veri nesnesinden veri değişikliği bildirimleri alabilmesi için, istemcinin [iAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) arabirimini tavsiye lavabosu adı verilen bir nesneye uygulaması gerekir. İstemci daha `IDataObject::DAdvise`sonra aradığında, veri nesnesi ile tavsiye lavabosu arasında bir bağlantı kurulur.

Sınıf `IDataObjectImpl` varsayılan bir `IDataObject` uygulama sağlar `IUnknown` ve hata ayıklama oluştururda dökümü aygıtına bilgi göndererek uygular.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IDataObject`

`IDataObjectImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="idataobjectimpldadvise"></a><a name="dadvise"></a>IDataObjectImpl::DAdvise

Veri nesnesi ile bir tavsiye lavabosu arasında bir bağlantı kurar.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Açıklamalar

Bu, tavsiye lavabosu nesnedeğişiklikleri bildirimleri almak için sağlar.

Bağlantıyı sonlandırmak için [DUnadvise'ı](#dunadvise)arayın.

Bkz. [IDataObject::DWindows](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) SDK'da tavsiye verin.

## <a name="idataobjectimpldunadvise"></a><a name="dunadvise"></a>IDataObjectImpl::DTavsiye yok

[DAdvise](#dadvise)aracılığıyla daha önce kurulmuş olan bağlantıyı sonlandırır.

```
HRESULT DUnadvise(DWORD dwConnection);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IDataObject::DWindows](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) SDK'da tavsiye edilmemiş.

## <a name="idataobjectimplenumdadvise"></a><a name="enumdadvise"></a>IDataObjectImpl::EnumDAdvise

Geçerli danışma bağlantıları aracılığıyla yinelemek için bir sayısallaştırıcı oluşturur.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IDataObject::Windows](/windows/win32/api/objidl/nf-objidl-idataobject-enumdadvise) SDK'da EnumDAdvise.

## <a name="idataobjectimplenumformatetc"></a><a name="enumformatetc"></a>iDataObjectImpl::EnumFormatEtc

Veri nesnesi tarafından desteklenen `FORMATETC` yapılar aracılığıyla yinelemek için bir sayısallaştırıcı oluşturur.

```
HRESULT EnumFormatEtc(
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IDataObject::Windows](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) SDK'da EnumFormatEtc.

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

## <a name="idataobjectimplfiredatachange"></a><a name="firedatachange"></a>IDataObjectImpl::FireDataChange

Şu anda yönetilen her bir tavsiye lavabosu için bir değişiklik bildirimi gönderir.

```
HRESULT FireDataChange();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="idataobjectimplgetcanonicalformatetc"></a><a name="getcanonicalformatetc"></a>iDataObjectImpl::GetCanonicalFormatEtc

Mantıksal olarak eşdeğer `FORMATETC` bir yapıyı daha karmaşık bir yapıya alır.

```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IDataObject::Windows SDK'da GetCanonicalFormatEtc.](/windows/win32/api/objidl/nf-objidl-idataobject-getcanonicalformatetc)

## <a name="idataobjectimplgetdata"></a><a name="getdata"></a>IDataObjectImpl::Veri Alın

Veri nesnesinden verileri istemciye aktarın.

```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```

### <a name="remarks"></a>Açıklamalar

*PformatetcIn* parametresi bir depolama orta tipi TYMED_MFPICT belirtmelidir.

Bkz. [IDataObject::Windows](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) SDK'da Veri Alma.

## <a name="idataobjectimplgetdatahere"></a><a name="getdatahere"></a>IDataObjectImpl::GetDataHere

Benzer `GetData`, istemci dışında `STGMEDIUM` yapı yı ayırması gerekir.

```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IDataObject::GetDataHere](/windows/win32/api/objidl/nf-objidl-idataobject-getdatahere) in The Windows SDK.

## <a name="idataobjectimplquerygetdata"></a><a name="querygetdata"></a>IDataObjectImpl::QueryGetData

Veri nesnesinin veri aktarımı `FORMATETC` için belirli bir yapıyı destekleyip desteklemediğini belirler.

```
HRESULT QueryGetData(FORMATETC* pformatetc);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IDataObject::QueryGetData](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) in Windows SDK.

## <a name="idataobjectimplsetdata"></a><a name="setdata"></a>IDataObjectImpl::SetData

Verileri istemciden veri nesnesine aktarın.

```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IDataObject::Windows](/windows/win32/api/objidl/nf-objidl-idataobject-setdata) SDK'daki SetData.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
