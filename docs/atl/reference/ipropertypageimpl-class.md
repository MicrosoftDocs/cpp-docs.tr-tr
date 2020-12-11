---
description: ': IPropertyPageImpl sınıfı hakkında daha fazla bilgi edinin'
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
ms.openlocfilehash: c3b8a52d3aff0beeb175a18af56a207284ff538d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158146"
---
# <a name="ipropertypageimpl-class"></a>IPropertyPageImpl sınıfı

Bu sınıf `IUnknown` , [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) arabiriminin varsayılan bir uygulamasını uygular ve sunar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IPropertyPageImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IPropertyPageImpl` .

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[IPropertyPageImpl:: IPropertyPageImpl](#ipropertypageimpl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IPropertyPageImpl:: Activate](#activate)|Özellik sayfası için iletişim kutusu penceresi oluşturur.|
|[IPropertyPageImpl:: Apply](#apply)|Geçerli özellik sayfası değerlerini ile belirtilen temel nesnelere uygular `SetObjects` . ATL uygulama S_OK döndürür.|
|[IPropertyPageImpl::D eactivate](#deactivate)|İle oluşturulan pencereyi yok eder `Activate` .|
|[IPropertyPageImpl:: GetPageInfo](#getpageinfo)|Özellik sayfası hakkındaki bilgileri alır.|
|[IPropertyPageImpl:: help](#help)|Özellik sayfası için Windows yardımını çağırır.|
|[IPropertyPageImpl:: IsPageDirty](#ispagedirty)|Özellik sayfasının etkinleştirildikten sonra değiştirilip değiştirilmediğini belirtir.|
|[IPropertyPageImpl:: Move](#move)|Özellik sayfası iletişim kutusunu konumlandırır ve yeniden boyutlandırır.|
|[IPropertyPageImpl:: SetDirty](#setdirty)|Özellik sayfasının durumunu değiştirilmiş veya değişmemiş olarak işaretler.|
|[IPropertyPageImpl:: SetObjects](#setobjects)|`IUnknown`Özellik sayfasıyla ilişkili nesneler için bir işaretçiler dizisi sağlar. Bu nesneler, öğesine yapılan çağrısıyla geçerli özellik sayfası değerlerini alır `Apply` .|
|[IPropertyPageImpl:: SetPageSite](#setpagesite)|Özellik sayfasının `IPropertyPageSite` özellik çerçevesiyle iletişim kurduğu bir işaretçi ile özellik sayfasını sağlar.|
|[IPropertyPageImpl:: show](#show)|Özellik sayfası iletişim kutusunu görünür veya görünmez hale getirir.|
|[IPropertyPageImpl:: TranslateAccelerator](#translateaccelerator)|Belirtilen tuş vuruşunu işler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[IPropertyPageImpl:: m_bDirty](#m_bdirty)|Özellik sayfası durumunun değiştirilip değiştirilmediğini belirtir.|
|[IPropertyPageImpl:: m_dwDocString](#m_dwdocstring)|Özellik sayfasını açıklayan metin dizesiyle ilişkili kaynak tanımlayıcısını depolar.|
|[IPropertyPageImpl:: m_dwHelpContext](#m_dwhelpcontext)|Özellik sayfasıyla ilişkili Yardım konusunun bağlam tanımlayıcısını depolar.|
|[IPropertyPageImpl:: m_dwHelpFile](#m_dwhelpfile)|Özellik sayfasını açıklayan Yardım dosyasının adıyla ilişkili kaynak tanımlayıcısını depolar.|
|[IPropertyPageImpl:: m_dwTitle](#m_dwtitle)|Özellik sayfasının sekmesinde görüntülenen metin dizesiyle ilişkili kaynak tanımlayıcısını depolar.|
|[IPropertyPageImpl:: m_nObjects](#m_nobjects)|Özellik sayfasıyla ilişkili nesne sayısını depolar.|
|[IPropertyPageImpl:: m_pPageSite](#m_ppagesite)|Özellik `IPropertyPageSite` sayfasının özellik çerçevesiyle iletişim kurduğu arabirime işaret eder.|
|[IPropertyPageImpl:: m_ppUnk](#m_ppunk)|`IUnknown`Özellik sayfasıyla ilişkili nesnelere işaretçiler dizisine işaret eder.|
|[IPropertyPageImpl:: m_size](#m_size)|Özellik sayfasının iletişim kutusunun yüksekliğini ve genişliğini piksel cinsinden depolar.|

## <a name="remarks"></a>Açıklamalar

[IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) arabirimi bir nesnenin özellik sayfası içinde belirli bir özellik sayfasını yönetmesine izin verir. Sınıfı, `IPropertyPageImpl` Bu arabirimin varsayılan bir uygulamasını sağlar ve `IUnknown` hata ayıklama yapılarında döküm cihazına bilgi göndererek uygular.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPropertyPage`

`IPropertyPageImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="ipropertypageimplactivate"></a><a name="activate"></a> IPropertyPageImpl:: Activate

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

## <a name="ipropertypageimplapply"></a><a name="apply"></a> IPropertyPageImpl:: Apply

Geçerli özellik sayfası değerlerini ile belirtilen temel nesnelere uygular `SetObjects` .

```
HRESULT Apply();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK [IPropertyPage:: Apply](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-apply) öğesine bakın.

## <a name="ipropertypageimpldeactivate"></a><a name="deactivate"></a> IPropertyPageImpl::D eactivate

[Etkinleştir](#activate)ile oluşturulan iletişim kutusu penceresini yok eder.

```
HRESULT Deactivate();
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPropertyPage: Windows SDK eactivate:D](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-deactivate) .

## <a name="ipropertypageimplgetpageinfo"></a><a name="getpageinfo"></a> IPropertyPageImpl:: GetPageInfo

*Ppageınfo* yapısını veri üyelerinde bulunan bilgilerle doldurur.

```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Açıklamalar

`GetPageInfo`[m_dwDocString](#m_dwdocstring), [m_dwHelpFile](#m_dwhelpfile)ve [m_dwTitle](#m_dwtitle)ile ilişkili dize kaynaklarını yükler.

Windows SDK [IPropertyPage:: GetPageInfo](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-getpageinfo) bölümüne bakın.

## <a name="ipropertypageimplhelp"></a><a name="help"></a> IPropertyPageImpl:: help

Özellik sayfası için Windows yardımını çağırır.

```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IPropertyPage:: help](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-help) bölümüne bakın.

## <a name="ipropertypageimplipropertypageimpl"></a><a name="ipropertypageimpl"></a> IPropertyPageImpl:: IPropertyPageImpl

Oluşturucu.

```
IPropertyPageImpl();
```

### <a name="remarks"></a>Açıklamalar

Tüm veri üyelerini başlatır.

## <a name="ipropertypageimplispagedirty"></a><a name="ispagedirty"></a> IPropertyPageImpl:: IsPageDirty

Özellik sayfasının etkinleştirildikten sonra değiştirilip değiştirilmediğini belirtir.

```
HRESULT IsPageDirty(void);
```

### <a name="remarks"></a>Açıklamalar

`IsPageDirty` sayfa etkinleştirildikten sonra değiştiyse S_OK döndürür.

## <a name="ipropertypageimplm_bdirty"></a><a name="m_bdirty"></a> IPropertyPageImpl:: m_bDirty

Özellik sayfası durumunun değiştirilip değiştirilmediğini belirtir.

```
BOOL m_bDirty;
```

## <a name="ipropertypageimplm_nobjects"></a><a name="m_nobjects"></a> IPropertyPageImpl:: m_nObjects

Özellik sayfasıyla ilişkili nesne sayısını depolar.

```
ULONG m_nObjects;
```

## <a name="ipropertypageimplm_dwhelpcontext"></a><a name="m_dwhelpcontext"></a> IPropertyPageImpl:: m_dwHelpContext

Özellik sayfasıyla ilişkili Yardım konusunun bağlam tanımlayıcısını depolar.

```
DWORD m_dwHelpContext;
```

## <a name="ipropertypageimplm_dwdocstring"></a><a name="m_dwdocstring"></a> IPropertyPageImpl:: m_dwDocString

Özellik sayfasını açıklayan metin dizesiyle ilişkili kaynak tanımlayıcısını depolar.

```
UINT m_dwDocString;
```

## <a name="ipropertypageimplm_dwhelpfile"></a><a name="m_dwhelpfile"></a> IPropertyPageImpl:: m_dwHelpFile

Özellik sayfasını açıklayan Yardım dosyasının adıyla ilişkili kaynak tanımlayıcısını depolar.

```
UINT m_dwHelpFile;
```

## <a name="ipropertypageimplm_dwtitle"></a><a name="m_dwtitle"></a> IPropertyPageImpl:: m_dwTitle

Özellik sayfasının sekmesinde görüntülenen metin dizesiyle ilişkili kaynak tanımlayıcısını depolar.

```
UINT m_dwTitle;
```

## <a name="ipropertypageimplm_ppagesite"></a><a name="m_ppagesite"></a> IPropertyPageImpl:: m_pPageSite

Özellik sayfasının özellik çerçevesiyle iletişim kurduğu [IPropertyPageSite](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) arabirimine işaret eder.

```
IPropertyPageSite* m_pPageSite;
```

## <a name="ipropertypageimplm_ppunk"></a><a name="m_ppunk"></a> IPropertyPageImpl:: m_ppUnk

`IUnknown`Özellik sayfasıyla ilişkili nesnelere işaretçiler dizisine işaret eder.

```
IUnknown** m_ppUnk;
```

## <a name="ipropertypageimplm_size"></a><a name="m_size"></a> IPropertyPageImpl:: m_size

Özellik sayfasının iletişim kutusunun yüksekliğini ve genişliğini piksel cinsinden depolar.

```
SIZE m_size;
```

## <a name="ipropertypageimplmove"></a><a name="move"></a> IPropertyPageImpl:: Move

Özellik sayfası iletişim kutusunu konumlandırır ve yeniden boyutlandırır.

```
HRESULT Move(LPCRECT pRect);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IPropertyPage:: Move](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-move) öğesine bakın.

## <a name="ipropertypageimplsetdirty"></a><a name="setdirty"></a> IPropertyPageImpl:: SetDirty

*BDirty* değerine bağlı olarak, özellik sayfasının durumunu değiştirilmiş veya değiştirilmemiş olarak işaretler.

```cpp
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Parametreler

*bDirty*<br/>
'ndaki TRUE ise Özellik sayfasının durumu değiştirildi olarak işaretlenir. Aksi takdirde, değiştirilmez olarak işaretlenir.

### <a name="remarks"></a>Açıklamalar

Gerekirse, `SetDirty` Özellik sayfasının değiştiğini çerçeveye bildirir.

## <a name="ipropertypageimplsetobjects"></a><a name="setobjects"></a> IPropertyPageImpl:: SetObjects

`IUnknown`Özellik sayfasıyla ilişkili nesneler için bir işaretçiler dizisi sağlar.

```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IPropertyPage:: SetObjects](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setobjects) öğesine bakın.

## <a name="ipropertypageimplsetpagesite"></a><a name="setpagesite"></a> IPropertyPageImpl:: SetPageSite

Özellik sayfasının özellik çerçevesiyle iletişim kurduğu bir [IPropertyPageSite](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) işaretçisi ile özellik sayfasını sağlar.

```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IPropertyPage:: SetPageSite](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setpagesite) bölümüne bakın.

## <a name="ipropertypageimplshow"></a><a name="show"></a> IPropertyPageImpl:: show

Özellik sayfası iletişim kutusunu görünür veya görünmez hale getirir.

```
HRESULT Show(UINT nCmdShow);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPropertyPage:: Windows SDK gösterme](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-show) .

## <a name="ipropertypageimpltranslateaccelerator"></a><a name="translateaccelerator"></a> IPropertyPageImpl:: TranslateAccelerator

İçinde belirtilen tuş vuruşunu işler `pMsg` .

```
HRESULT TranslateAccelerator(MSG* pMsg);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IPropertyPage:: TranslateAccelerator](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-translateaccelerator) öğesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[IPropertyPage2Impl sınıfı](../../atl/reference/ipropertypage2impl-class.md)<br/>
[Iperpropertybrowsingimpl sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Idiifyıpropertypagesimpl sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
