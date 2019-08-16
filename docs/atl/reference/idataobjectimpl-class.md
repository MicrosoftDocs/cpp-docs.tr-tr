---
title: IDataObjectImpl sınıfı
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
ms.openlocfilehash: 8e3369edd0731ede0892a405ef3de4e7b4cfdef1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495938"
---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl sınıfı

Bu sınıf Tekdüzen Veri Aktarımı desteklemek ve bağlantıları yönetmek için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IDataObjectImpl
```

#### <a name="parameters"></a>Parametreler

*ŞI*<br/>
Sınıfınız, öğesinden `IDataObjectImpl`türetilir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IDataObjectImpl::D Advise](#dadvise)|Veri nesnesi ve öneri havuzu arasında bir bağlantı kurar. Bu, öneri havuzunun nesnedeki değişikliklere ilişkin bildirimler almasını sağlar.|
|[IDataObjectImpl::D Unadvise](#dunadvise)|Daha önce tarafından `DAdvise`kurulan bir bağlantıyı sonlandırır.|
|[IDataObjectImpl:: enumdadmen](#enumdadvise)|Geçerli danışmanlık bağlantılarında yinelemek için bir Numaralandırıcı oluşturur.|
|[IDataObjectImpl:: EnumFormatEtc](#enumformatetc)|Veri nesnesi tarafından desteklenen `FORMATETC` yapılar arasında yinelemek için bir Numaralandırıcı oluşturur. ATL uygulama E_NOTIMPL döndürür.|
|[IDataObjectImpl:: FireDataChange](#firedatachange)|Her öneri havuzuna bir değişiklik bildirimi gönderir.|
|[IDataObjectImpl:: GetCanonicalFormatEtc](#getcanonicalformatetc)|Mantıksal olarak eşdeğer `FORMATETC` bir yapıyı daha karmaşık bir yapıya alır. ATL uygulama E_NOTIMPL döndürür.|
|[IDataObjectImpl:: GetData](#getdata)|Veri nesnesinden istemciye veri aktarır. Veriler bir `FORMATETC` yapıda tanımlanır ve bir `STGMEDIUM` yapı aracılığıyla aktarılır.|
|[IDataObjectImpl:: GetDataHere](#getdatahere)|Benzer şekilde `GetData`, istemci `STGMEDIUM` yapıyı ayırmalıdır. ATL uygulama E_NOTIMPL döndürür.|
|[IDataObjectImpl:: QueryGetData](#querygetdata)|Veri nesnesinin veri aktarmaya yönelik belirli `FORMATETC` bir yapıyı destekleyip desteklemediğini belirler. ATL uygulama E_NOTIMPL döndürür.|
|[IDataObjectImpl:: SetData](#setdata)|İstemciden veri nesnesine veri aktarır. ATL uygulama E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

[IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) arabirimi Tekdüzen veri aktarımı desteklemek için yöntemler sağlar. `IDataObject`verileri almak ve depolamak için [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) ve [stgmedium](/windows/win32/api/objidl/ns-objidl-stgmedium) standart biçim yapılarını kullanır.

`IDataObject`Ayrıca, veri değişikliği bildirimlerini işlemek üzere öneri havuzları bağlantılarını yönetir. İstemcinin veri nesnesinden veri değişikliği bildirimleri alabilmesi için, istemci, bir öneri havuzu adlı bir nesneye [ıvısesink](/windows/win32/api/objidl/nn-objidl-iadvisesink) arabirimini gerçekleştirmelidir. İstemci daha sonra çağırdığında `IDataObject::DAdvise`, veri nesnesi ve öneri havuzu arasında bir bağlantı oluşturulur.

Sınıfı `IDataObjectImpl` , hata ayıklama yapılarında döküm `IDataObject` cihazına bilgi `IUnknown` göndererek varsayılan bir uygulamasını sağlar ve uygular.

**Ilgili makaleler** ATL [öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IDataObject`

`IDataObjectImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

##  <a name="dadvise"></a>IDataObjectImpl::D Advise

Veri nesnesi ve öneri havuzu arasında bir bağlantı kurar.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Açıklamalar

Bu, öneri havuzunun nesnedeki değişikliklere ilişkin bildirimler almasını sağlar.

Bağlantıyı sonlandırmak için [DUnadvise](#dunadvise)çağırın.

Windows SDK için bkz. IDataObject [::D Advise](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) .

##  <a name="dunadvise"></a>IDataObjectImpl::D Unadvise

Daha önce Dadtıon aracılığıyla kurulan [](#dadvise)bir bağlantıyı sonlandırır.

```
HRESULT DUnadvise(DWORD dwConnection);
```

### <a name="remarks"></a>Açıklamalar

Bkz. IDataObject [: Windows SDK:D Unadvise](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) .

##  <a name="enumdadvise"></a>IDataObjectImpl:: enumdadmen

Geçerli danışmanlık bağlantılarında yinelemek için bir Numaralandırıcı oluşturur.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. IDataObject [:: Enumdadmenlik](/windows/win32/api/objidl/nf-objidl-idataobject-enumdadvise) .

##  <a name="enumformatetc"></a>IDataObjectImpl:: EnumFormatEtc

Veri nesnesi tarafından desteklenen `FORMATETC` yapılar arasında yinelemek için bir Numaralandırıcı oluşturur.

```
HRESULT EnumFormatEtc(
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IDataObject:: EnumFormatEtc](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) .

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

##  <a name="firedatachange"></a>IDataObjectImpl:: FireDataChange

Şu anda yönetilmekte olan her bir öneri havuzuna bir değişiklik bildirimi gönderir.

```
HRESULT FireDataChange();
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="getcanonicalformatetc"></a>IDataObjectImpl:: GetCanonicalFormatEtc

Mantıksal olarak eşdeğer `FORMATETC` bir yapıyı daha karmaşık bir yapıya alır.

```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IDataObject:: GetCanonicalFormatEtc](/windows/win32/api/objidl/nf-objidl-idataobject-getcanonicalformatetc) .

##  <a name="getdata"></a>IDataObjectImpl:: GetData

Veri nesnesinden istemciye veri aktarır.

```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```

### <a name="remarks"></a>Açıklamalar

*Pformatetcin* PARAMETRESI, TYMED_MFPICT türünde bir depolama ortamı türü belirtmelidir.

Windows SDK için bkz. [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) .

##  <a name="getdatahere"></a>IDataObjectImpl:: GetDataHere

Benzer şekilde `GetData`, istemci `STGMEDIUM` yapıyı ayırmalıdır.

```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK [buraya IDataObject:: GetDataHere](/windows/win32/api/objidl/nf-objidl-idataobject-getdatahere) yazın.

##  <a name="querygetdata"></a>IDataObjectImpl:: QueryGetData

Veri nesnesinin veri aktarmaya yönelik belirli `FORMATETC` bir yapıyı destekleyip desteklemediğini belirler.

```
HRESULT QueryGetData(FORMATETC* pformatetc);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IDataObject:: QueryGetData](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) .

##  <a name="setdata"></a>IDataObjectImpl:: SetData

İstemciden veri nesnesine veri aktarır.

```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. IDataObject [:: SetData](/windows/win32/api/objidl/nf-objidl-idataobject-setdata) .

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
