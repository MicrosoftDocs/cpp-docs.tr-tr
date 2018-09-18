---
title: Ipropertypageımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b07609b792b7080e2c4c432ed435381007ba286
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075234"
---
# <a name="ipropertypageimpl-class"></a>Ipropertypageımpl sınıfı

Bu sınıfın uyguladığı `IUnknown` ve varsayılan bir uygulama sağlar [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) arabirimi.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IPropertyPageImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IPropertyPageImpl`.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[IPropertyPageImpl::IPropertyPageImpl](#ipropertypageimpl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IPropertyPageImpl::Activate](#activate)|Özellik sayfası iletişim kutusu penceresi oluşturur.|
|[IPropertyPageImpl::Apply](#apply)|Geçerli özellik sayfası değerleri aracılığıyla belirtilen temel nesnelere uygulanır `SetObjects`. ATL uygulamasını S_OK döndürür.|
|[IPropertyPageImpl::Deactivate](#deactivate)|Oluşturulan penceresini yok eder `Activate`.|
|[IPropertyPageImpl::GetPageInfo](#getpageinfo)|Özellik sayfasını hakkındaki bilgileri alır.|
|[IPropertyPageImpl::Help](#help)|Windows Yardım özellik sayfası için çağırır.|
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|Özellik sayfasını, etkinleştirilmesinden sonra değiştirilip değiştirilmediğini belirtir.|
|[IPropertyPageImpl::Move](#move)|Yerleştirir ve özellik sayfası iletişim kutusu yeniden boyutlandırır.|
|[IPropertyPageImpl::SetDirty](#setdirty)|Özellik sayfa durumu değiştirilmiş veya değişmemiş olarak işaretler.|
|[IPropertyPageImpl::SetObjects](#setobjects)|Bir dizi sağlar `IUnknown` özellik sayfası ile ilişkili nesnelerin işaretçileri. Bu nesneler yapılan bir çağrıyla geçerli özellik sayfası değerlerini alma `Apply`.|
|[IPropertyPageImpl::SetPageSite](#setpagesite)|Özellik sayfası ile sağlar bir `IPropertyPageSite` özellik sayfası özellik çerçevesi ile iletişim işaretçisi.|
|[IPropertyPageImpl::Show](#show)|Özellik sayfası iletişim kutusu görünür veya gizli hale getirir.|
|[IPropertyPageImpl::TranslateAccelerator](#translateaccelerator)|Belirtilen bir tuş vuruşu işler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[IPropertyPageImpl::m_bDirty](#m_bdirty)|Özellik sayfanın durumu değiştirilip değiştirilmediğini belirtir.|
|[IPropertyPageImpl::m_dwDocString](#m_dwdocstring)|Özellik sayfasını açıklayan bir metin dizesi ile ilişkili kaynak tanımlayıcısı depolar.|
|[IPropertyPageImpl::m_dwHelpContext](#m_dwhelpcontext)|Özellik sayfası ile ilişkili bir Yardım konusu bağlam tanımlayıcısı depolar.|
|[IPropertyPageImpl::m_dwHelpFile](#m_dwhelpfile)|Özellik sayfasını açıklayan Yardım dosyasının adı ile ilişkili kaynak tanımlayıcısı depolar.|
|[IPropertyPageImpl::m_dwTitle](#m_dwtitle)|Özellik sayfası için sekmesinde görüntülenen metin dizesi ile ilişkili kaynak tanımlayıcısı depolar.|
|[IPropertyPageImpl::m_nObjects](#m_nobjects)|Özellik sayfası ile ilişkili nesne sayısını depolar.|
|[IPropertyPageImpl::m_pPageSite](#m_ppagesite)|İşaret `IPropertyPageSite` özellik sayfası özellik çerçevesi ile iletişim arabirimi.|
|[IPropertyPageImpl::m_ppUnk](#m_ppunk)|İşaret dizilerine `IUnknown` özellik sayfası ile ilişkili nesne işaretçileri.|
|[IPropertyPageImpl::m_size](#m_size)|Özellik sayfasının iletişim kutusunun genişliği ve yüksekliği, piksel cinsinden depolar.|

## <a name="remarks"></a>Açıklamalar

[IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) nesnenin bir özellik sayfası içinde belirli bir özellik sayfası yönetmek arabirim sağlar. Sınıf `IPropertyPageImpl` bu arabirimin bir varsayılan uygulamasını sağlar ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

**İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPropertyPage`

`IPropertyPageImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

##  <a name="activate"></a>  IPropertyPageImpl::Activate

Özellik sayfası iletişim kutusu penceresi oluşturur.

```
HRESULT Activate(  
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, iletişim kutusunda her zaman değerine bakılmaksızın geçici *bModal* parametresi.

Bkz: [IPropertyPage::Activate](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-activate) Windows SDK içinde.

##  <a name="apply"></a>  IPropertyPageImpl::Apply

Geçerli özellik sayfası değerleri aracılığıyla belirtilen temel nesnelere uygulanır `SetObjects`.

```
HRESULT Apply();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IPropertyPage::Apply](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-apply) Windows SDK içinde.

##  <a name="deactivate"></a>  IPropertyPageImpl::Deactivate

Oluşturulan iletişim kutusu penceresini yok eder [etkinleştirme](#activate).

```
HRESULT Deactivate();
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IPropertyPage::Deactivate](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-deactivate) Windows SDK içinde.

##  <a name="getpageinfo"></a>  IPropertyPageImpl::GetPageInfo

Doldurur *pPageInfo* yapısı bilgilerle veri üyeleri.

```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Açıklamalar

`GetPageInfo` ilişkili dize kaynakları yükler [m_dwDocString](#m_dwdocstring), [m_dwHelpFile](#m_dwhelpfile), ve [m_dwTitle](#m_dwtitle).

Bkz: [IPropertyPage::GetPageInfo](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-getpageinfo) Windows SDK içinde.

##  <a name="help"></a>  IPropertyPageImpl::Help

Windows Yardım özellik sayfası için çağırır.

```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IPropertyPage::Help](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-help) Windows SDK içinde.

##  <a name="ipropertypageimpl"></a>  IPropertyPageImpl::IPropertyPageImpl

Oluşturucu.

```
IPropertyPageImpl();
```

### <a name="remarks"></a>Açıklamalar

Tüm veri üyeleri başlatır.

##  <a name="ispagedirty"></a>  IPropertyPageImpl::IsPageDirty

Özellik sayfasını, etkinleştirilmesinden sonra değiştirilip değiştirilmediğini belirtir.

```
HRESULT IsPageDirty(void);
```

### <a name="remarks"></a>Açıklamalar

`IsPageDirty` etkinleştirildi ancak sayfa değişmişse S_OK döndürür.

##  <a name="m_bdirty"></a>  IPropertyPageImpl::m_bDirty

Özellik sayfanın durumu değiştirilip değiştirilmediğini belirtir.

```
BOOL m_bDirty;
```

##  <a name="m_nobjects"></a>  IPropertyPageImpl::m_nObjects

Özellik sayfası ile ilişkili nesne sayısını depolar.

```
ULONG m_nObjects;
```

##  <a name="m_dwhelpcontext"></a>  IPropertyPageImpl::m_dwHelpContext

Özellik sayfası ile ilişkili bir Yardım konusu bağlam tanımlayıcısı depolar.

```
DWORD m_dwHelpContext;
```

##  <a name="m_dwdocstring"></a>  IPropertyPageImpl::m_dwDocString

Özellik sayfasını açıklayan bir metin dizesi ile ilişkili kaynak tanımlayıcısı depolar.

```
UINT m_dwDocString;
```

##  <a name="m_dwhelpfile"></a>  IPropertyPageImpl::m_dwHelpFile

Özellik sayfasını açıklayan Yardım dosyasının adı ile ilişkili kaynak tanımlayıcısı depolar.

```
UINT m_dwHelpFile;
```

##  <a name="m_dwtitle"></a>  IPropertyPageImpl::m_dwTitle

Özellik sayfası için sekmesinde görüntülenen metin dizesi ile ilişkili kaynak tanımlayıcısı depolar.

```
UINT m_dwTitle;
```

##  <a name="m_ppagesite"></a>  IPropertyPageImpl::m_pPageSite

İşaret [IPropertyPageSite](/windows/desktop/api/ocidl/nn-ocidl-ipropertypagesite) özellik sayfası özellik çerçevesi ile iletişim arabirimi.

```
IPropertyPageSite* m_pPageSite;
```

##  <a name="m_ppunk"></a>  IPropertyPageImpl::m_ppUnk

İşaret dizilerine `IUnknown` özellik sayfası ile ilişkili nesne işaretçileri.

```
IUnknown** m_ppUnk;
```

##  <a name="m_size"></a>  IPropertyPageImpl::m_size

Özellik sayfasının iletişim kutusunun genişliği ve yüksekliği, piksel cinsinden depolar.

```
SIZE m_size;
```

##  <a name="move"></a>  IPropertyPageImpl::Move

Yerleştirir ve özellik sayfası iletişim kutusu yeniden boyutlandırır.

```
HRESULT Move(LPCRECT pRect);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IPropertyPage::Move](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-move) Windows SDK içinde.

##  <a name="setdirty"></a>  IPropertyPageImpl::SetDirty

Özellik sayfa durumu olarak değiştirilmiş veya değerine bağlı olarak, değiştirilmeden bayrakları *bDirty*.

```
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Parametreler

*bDirty*<br/>
[in] TRUE ise özellik sayfanın durumu değişmiş olarak işaretlenir. Aksi takdirde, işaretli olarak değişmez.

### <a name="remarks"></a>Açıklamalar

Gerekirse, `SetDirty` özellik sayfasını değişti çerçeve bildirir.

##  <a name="setobjects"></a>  IPropertyPageImpl::SetObjects

Bir dizi sağlar `IUnknown` özellik sayfası ile ilişkili nesnelerin işaretçileri.

```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IPropertyPage::SetObjects](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-setobjects) Windows SDK içinde.

##  <a name="setpagesite"></a>  IPropertyPageImpl::SetPageSite

Özellik sayfası ile sağlar bir [IPropertyPageSite](/windows/desktop/api/ocidl/nn-ocidl-ipropertypagesite) özellik sayfası özellik çerçevesi ile iletişim işaretçisi.

```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IPropertyPage::SetPageSite](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-setpagesite) Windows SDK içinde.

##  <a name="show"></a>  IPropertyPageImpl::Show

Özellik sayfası iletişim kutusu görünür veya gizli hale getirir.

```
HRESULT Show(UINT nCmdShow);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IPropertyPage::Show](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-show) Windows SDK içinde.

##  <a name="translateaccelerator"></a>  IPropertyPageImpl::TranslateAccelerator

Belirtilen tuş vuruşu işler `pMsg`.

```
HRESULT TranslateAccelerator(MSG* pMsg);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IPropertyPage::TranslateAccelerator](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-translateaccelerator) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca Bkz.

[IPropertyPage2Impl Sınıfı](../../atl/reference/ipropertypage2impl-class.md)<br/>
[IPerPropertyBrowsingImpl Sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl Sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
