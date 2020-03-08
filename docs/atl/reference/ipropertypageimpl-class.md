---
title: IPropertyPageImpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::Activate
- ATLCTL/ATL::IPropertyPageImpl::Apply
- ATLCTL/ATL::IPropertyPageImpl::Deactivate
- ATLCTL/ATL::IPropertyPageImpl::GetPageInfo
- ATLCTL/ATL::IPropertyPageImpl::Help
- ATLCTL/ATL::IPropertyPageImpl::IsPageDirty
- ATLCTL/ATL::IPropertyPageImpl::Move
- ATLCTL/ATL::IPropertyPageImpl::SetDirty
- ATLCTL/ATL::IPropertyPageImpl::SetObjects
- ATLCTL/ATL::IPropertyPageImpl::SetPageSite
- ATLCTL/ATL::IPropertyPageImpl::Show
- ATLCTL/ATL::IPropertyPageImpl::TranslateAccelerator
- ATLCTL/ATL::IPropertyPageImpl::m_bDirty
- ATLCTL/ATL::IPropertyPageImpl::m_dwDocString
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpContext
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpFile
- ATLCTL/ATL::IPropertyPageImpl::m_dwTitle
- ATLCTL/ATL::IPropertyPageImpl::m_nObjects
- ATLCTL/ATL::IPropertyPageImpl::m_pPageSite
- ATLCTL/ATL::IPropertyPageImpl::m_ppUnk
- ATLCTL/ATL::IPropertyPageImpl::m_size
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
ms.openlocfilehash: 69842e77aecaa94be66432e5fbba437a6fa3c5a4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864989"
---
# <a name="ipropertypageimpl-class"></a>IPropertyPageImpl sınıfı

Bu sınıf `IUnknown` uygular ve [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) arabiriminin varsayılan bir uygulamasını sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IPropertyPageImpl
```

#### <a name="parameters"></a>Parametreler

*Şı*<br/>
Sınıfınız `IPropertyPageImpl`türetilir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[IPropertyPageImpl:: IPropertyPageImpl](#ipropertypageimpl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IPropertyPageImpl:: Activate](#activate)|Özellik sayfası için iletişim kutusu penceresi oluşturur.|
|[IPropertyPageImpl:: Apply](#apply)|Geçerli özellik sayfası değerlerini `SetObjects`ile belirtilen temel nesnelere uygular. ATL uygulama S_OK döndürür.|
|[IPropertyPageImpl::D eactivate](#deactivate)|`Activate`ile oluşturulan pencereyi yok eder.|
|[IPropertyPageImpl:: GetPageInfo](#getpageinfo)|Özellik sayfası hakkındaki bilgileri alır.|
|[IPropertyPageImpl:: help](#help)|Özellik sayfası için Windows yardımını çağırır.|
|[IPropertyPageImpl:: IsPageDirty](#ispagedirty)|Özellik sayfasının etkinleştirildikten sonra değiştirilip değiştirilmediğini belirtir.|
|[IPropertyPageImpl:: Move](#move)|Özellik sayfası iletişim kutusunu konumlandırır ve yeniden boyutlandırır.|
|[IPropertyPageImpl:: SetDirty](#setdirty)|Özellik sayfasının durumunu değiştirilmiş veya değişmemiş olarak işaretler.|
|[IPropertyPageImpl:: SetObjects](#setobjects)|Özellik sayfasıyla ilişkili nesneler için `IUnknown` işaretçileri dizisi sağlar. Bu nesneler, `Apply`çağrısıyla geçerli özellik sayfası değerlerini alır.|
|[IPropertyPageImpl:: SetPageSite](#setpagesite)|Özellik sayfasının özellik çerçevesiyle iletişim kurduğu `IPropertyPageSite` işaretçiyle özellik sayfasını sağlar.|
|[IPropertyPageImpl:: show](#show)|Özellik sayfası iletişim kutusunu görünür veya görünmez hale getirir.|
|[IPropertyPageImpl:: TranslateAccelerator](#translateaccelerator)|Belirtilen tuş vuruşunu işler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[IPropertyPageImpl:: m_bDirty](#m_bdirty)|Özellik sayfası durumunun değiştirilip değiştirilmediğini belirtir.|
|[IPropertyPageImpl:: m_dwDocString](#m_dwdocstring)|Özellik sayfasını açıklayan metin dizesiyle ilişkili kaynak tanımlayıcısını depolar.|
|[IPropertyPageImpl:: m_dwHelpContext](#m_dwhelpcontext)|Özellik sayfasıyla ilişkili Yardım konusunun bağlam tanımlayıcısını depolar.|
|[IPropertyPageImpl:: m_dwHelpFile](#m_dwhelpfile)|Özellik sayfasını açıklayan Yardım dosyasının adıyla ilişkili kaynak tanımlayıcısını depolar.|
|[IPropertyPageImpl:: m_dwTitle](#m_dwtitle)|Özellik sayfasının sekmesinde görüntülenen metin dizesiyle ilişkili kaynak tanımlayıcısını depolar.|
|[IPropertyPageImpl:: m_nObjects](#m_nobjects)|Özellik sayfasıyla ilişkili nesne sayısını depolar.|
|[IPropertyPageImpl:: m_pPageSite](#m_ppagesite)|Özellik sayfasının özellik çerçevesiyle iletişim kurduğu `IPropertyPageSite` arabirimine işaret eder.|
|[IPropertyPageImpl:: m_ppUnk](#m_ppunk)|Özellik sayfasıyla ilişkili nesneler için `IUnknown` işaretçileri dizisine işaret eder.|
|[IPropertyPageImpl:: m_size](#m_size)|Özellik sayfasının iletişim kutusunun yüksekliğini ve genişliğini piksel cinsinden depolar.|

## <a name="remarks"></a>Açıklamalar

[IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) arabirimi bir nesnenin özellik sayfası içinde belirli bir özellik sayfasını yönetmesine izin verir. Sınıf `IPropertyPageImpl`, bu arabirimin varsayılan bir uygulamasını sağlar ve hata ayıklama yapılarında döküm cihazına bilgi göndererek `IUnknown` uygular.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPropertyPage`

`IPropertyPageImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

##  <a name="activate"></a>IPropertyPageImpl:: Activate

Özellik sayfası için iletişim kutusu penceresi oluşturur.

```
HRESULT Activate(
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, *bModal* parametresinin değeri ne olursa olsun iletişim kutusu her zaman modsuz olur.

Windows SDK [IPropertyPage:: Activate](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-activate) öğesine bakın.

##  <a name="apply"></a>IPropertyPageImpl:: Apply

Geçerli özellik sayfası değerlerini `SetObjects`ile belirtilen temel nesnelere uygular.

```
HRESULT Apply();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK [IPropertyPage:: Apply](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-apply) öğesine bakın.

##  <a name="deactivate"></a>IPropertyPageImpl::D eactivate

[Etkinleştir](#activate)ile oluşturulan iletişim kutusu penceresini yok eder.

```
HRESULT Deactivate();
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPropertyPage: Windows SDK eactivate:D](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-deactivate) .

##  <a name="getpageinfo"></a>IPropertyPageImpl:: GetPageInfo

*Ppageınfo* yapısını veri üyelerinde bulunan bilgilerle doldurur.

```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Açıklamalar

`GetPageInfo` [m_dwDocString](#m_dwdocstring), [m_dwHelpFile](#m_dwhelpfile)ve [m_dwTitle](#m_dwtitle)ilişkili dize kaynaklarını yükler.

Windows SDK [IPropertyPage:: GetPageInfo](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-getpageinfo) bölümüne bakın.

##  <a name="help"></a>IPropertyPageImpl:: help

Özellik sayfası için Windows yardımını çağırır.

```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IPropertyPage:: help](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-help) bölümüne bakın.

##  <a name="ipropertypageimpl"></a>IPropertyPageImpl:: IPropertyPageImpl

Oluşturucu.

```
IPropertyPageImpl();
```

### <a name="remarks"></a>Açıklamalar

Tüm veri üyelerini başlatır.

##  <a name="ispagedirty"></a>IPropertyPageImpl:: IsPageDirty

Özellik sayfasının etkinleştirildikten sonra değiştirilip değiştirilmediğini belirtir.

```
HRESULT IsPageDirty(void);
```

### <a name="remarks"></a>Açıklamalar

`IsPageDirty`, sayfa etkinleştirildikten sonra değiştirildiyse S_OK döndürür.

##  <a name="m_bdirty"></a>IPropertyPageImpl:: m_bDirty

Özellik sayfası durumunun değiştirilip değiştirilmediğini belirtir.

```
BOOL m_bDirty;
```

##  <a name="m_nobjects"></a>IPropertyPageImpl:: m_nObjects

Özellik sayfasıyla ilişkili nesne sayısını depolar.

```
ULONG m_nObjects;
```

##  <a name="m_dwhelpcontext"></a>IPropertyPageImpl:: m_dwHelpContext

Özellik sayfasıyla ilişkili Yardım konusunun bağlam tanımlayıcısını depolar.

```
DWORD m_dwHelpContext;
```

##  <a name="m_dwdocstring"></a>IPropertyPageImpl:: m_dwDocString

Özellik sayfasını açıklayan metin dizesiyle ilişkili kaynak tanımlayıcısını depolar.

```
UINT m_dwDocString;
```

##  <a name="m_dwhelpfile"></a>IPropertyPageImpl:: m_dwHelpFile

Özellik sayfasını açıklayan Yardım dosyasının adıyla ilişkili kaynak tanımlayıcısını depolar.

```
UINT m_dwHelpFile;
```

##  <a name="m_dwtitle"></a>IPropertyPageImpl:: m_dwTitle

Özellik sayfasının sekmesinde görüntülenen metin dizesiyle ilişkili kaynak tanımlayıcısını depolar.

```
UINT m_dwTitle;
```

##  <a name="m_ppagesite"></a>IPropertyPageImpl:: m_pPageSite

Özellik sayfasının özellik çerçevesiyle iletişim kurduğu [IPropertyPageSite](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) arabirimine işaret eder.

```
IPropertyPageSite* m_pPageSite;
```

##  <a name="m_ppunk"></a>IPropertyPageImpl:: m_ppUnk

Özellik sayfasıyla ilişkili nesneler için `IUnknown` işaretçileri dizisine işaret eder.

```
IUnknown** m_ppUnk;
```

##  <a name="m_size"></a>IPropertyPageImpl:: m_size

Özellik sayfasının iletişim kutusunun yüksekliğini ve genişliğini piksel cinsinden depolar.

```
SIZE m_size;
```

##  <a name="move"></a>IPropertyPageImpl:: Move

Özellik sayfası iletişim kutusunu konumlandırır ve yeniden boyutlandırır.

```
HRESULT Move(LPCRECT pRect);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IPropertyPage:: Move](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-move) öğesine bakın.

##  <a name="setdirty"></a>IPropertyPageImpl:: SetDirty

*BDirty*değerine bağlı olarak, özellik sayfasının durumunu değiştirilmiş veya değiştirilmemiş olarak işaretler.

```
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Parametreler

*bDirty*<br/>
'ndaki TRUE ise Özellik sayfasının durumu değiştirildi olarak işaretlenir. Aksi takdirde, değiştirilmez olarak işaretlenir.

### <a name="remarks"></a>Açıklamalar

Gerekirse, `SetDirty` Özellik sayfasının değiştiğini çerçeveye bildirir.

##  <a name="setobjects"></a>IPropertyPageImpl:: SetObjects

Özellik sayfasıyla ilişkili nesneler için `IUnknown` işaretçileri dizisi sağlar.

```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IPropertyPage:: SetObjects](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setobjects) öğesine bakın.

##  <a name="setpagesite"></a>IPropertyPageImpl:: SetPageSite

Özellik sayfasının özellik çerçevesiyle iletişim kurduğu bir [IPropertyPageSite](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) işaretçisi ile özellik sayfasını sağlar.

```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IPropertyPage:: SetPageSite](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setpagesite) bölümüne bakın.

##  <a name="show"></a>IPropertyPageImpl:: show

Özellik sayfası iletişim kutusunu görünür veya görünmez hale getirir.

```
HRESULT Show(UINT nCmdShow);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPropertyPage:: Windows SDK gösterme](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-show) .

##  <a name="translateaccelerator"></a>IPropertyPageImpl:: TranslateAccelerator

`pMsg`belirtilen tuş vuruşunu işler.

```
HRESULT TranslateAccelerator(MSG* pMsg);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IPropertyPage:: TranslateAccelerator](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-translateaccelerator) öğesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[IPropertyPage2Impl Sınıfı](../../atl/reference/ipropertypage2impl-class.md)<br/>
[IPerPropertyBrowsingImpl Sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl Sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
