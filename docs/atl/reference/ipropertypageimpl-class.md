---
title: IPropertyPageImpl Sınıfı
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
ms.openlocfilehash: ac8fcb3b8b2bd0f876cf28d58e195000112373f4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329584"
---
# <a name="ipropertypageimpl-class"></a>IPropertyPageImpl Sınıfı

Bu `IUnknown` [sınıf, IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) arabiriminin varsayılan uygulamasını uygular ve sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IPropertyPageImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IPropertyPageImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[IPropertyPageImpl::IPropertyPageImpl](#ipropertypageimpl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IPropertyPageImpl::Etkinleştir](#activate)|Özellik sayfası için iletişim kutusu penceresini oluşturur.|
|[IPropertyPageImpl::Uygula](#apply)|`SetObjects`'den belirtilen temel nesnelere geçerli özellik sayfası değerlerini uygular. ATL uygulaması S_OK döndürür.|
|[IPropertyPageImpl::Deactivate](#deactivate)|`Activate`' ile oluşturulan pencereyi yok eder.|
|[IPropertyPageImpl::GetPageInfo](#getpageinfo)|Özellik sayfası yla ilgili bilgileri alır.|
|[IPropertyPageImpl::Yardım](#help)|Özellik sayfası için Windows yardımı çağırır.|
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|Özellik sayfasının etkinleştirildiğinden beri değişip değişmediğini gösterir.|
|[IPropertyPageImpl::Taşı](#move)|Özellik sayfası iletişim kutusunu konumlandırıp yeniden boyutlandırın.|
|[IPropertyPageImpl::SetDirty](#setdirty)|Özellik sayfasının durumunu değiştirilmiş veya değişmemiş olarak işaretler.|
|[IPropertyPageImpl::SetObjects](#setobjects)|Özellik sayfasıyla `IUnknown` ilişkili nesneler için bir dizi işaretçi sağlar. Bu nesneler, geçerli özellik sayfası değerlerini `Apply`bir çağrı yoluyla alır.|
|[IPropertyPageImpl::SetPageSite](#setpagesite)|Özellik sayfası, özellik `IPropertyPageSite` sayfasının özellik çerçevesiyle iletişim kurduğu bir işaretçi sağlar.|
|[IPropertyPageImpl::Göster](#show)|Özellik sayfası iletişim kutusunu görünür veya görünmez yapar.|
|[IPropertyPageImpl::TranslateAccelerator](#translateaccelerator)|Belirli bir tuş vuruşunu işler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[IPropertyPageImpl::m_bDirty](#m_bdirty)|Özellik sayfasının durumunun değişip değişmediğini belirtir.|
|[IPropertyPageImpl::m_dwDocString](#m_dwdocstring)|Özellik sayfasını açıklayan metin dizesiyle ilişkili kaynak tanımlayıcısını depolar.|
|[IPropertyPageImpl::m_dwHelpContext](#m_dwhelpcontext)|Özellik sayfasıyla ilişkili yardım konusu için bağlam tanımlayıcısını depolar.|
|[IPropertyPageImpl::m_dwHelpFile](#m_dwhelpfile)|Özellik sayfasını açıklayan yardım dosyasının adı ile ilişkili kaynak tanımlayıcısını depolar.|
|[IPropertyPageImpl::m_dwTitle](#m_dwtitle)|Özellik sayfasının sekmesinde görünen metin dizesiyle ilişkili kaynak tanımlayıcısını depolar.|
|[IPropertyPageImpl::m_nObjects](#m_nobjects)|Özellik sayfasıyla ilişkili nesnelerin sayısını depolar.|
|[IPropertyPageImpl::m_pPageSite](#m_ppagesite)|Özellik sayfasının `IPropertyPageSite` özellik çerçevesiyle iletişim kurduğu arabirime işaret eder.|
|[IPropertyPageImpl::m_ppUnk](#m_ppunk)|Özellik sayfasıyla `IUnknown` ilişkili nesnelere işaretçiler dizisine işaret eder.|
|[IPropertyPageImpl::m_size](#m_size)|Özellik sayfasının iletişim kutusunun yüksekliğini ve genişliğini piksellerde depolar.|

## <a name="remarks"></a>Açıklamalar

[IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) arabirimi, bir nesnenin bir özellik sayfası içindeki belirli bir özellik sayfasını yönetmesine olanak tanır. Sınıf `IPropertyPageImpl` bu arabirimin varsayılan bir `IUnknown` uygulamasını sağlar ve hata ayıklama oluştururda dökümü aygıtına bilgi göndererek uygular.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPropertyPage`

`IPropertyPageImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="ipropertypageimplactivate"></a><a name="activate"></a>IPropertyPageImpl::Etkinleştir

Özellik sayfası için iletişim kutusu penceresini oluşturur.

```
HRESULT Activate(
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, iletişim kutusu her zaman modeless, ne olursa olsun *bModal* parametre değeri.

Bkz. [IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-activate) SDK'da etkinleştirin.

## <a name="ipropertypageimplapply"></a><a name="apply"></a>IPropertyPageImpl::Uygula

`SetObjects`'den belirtilen temel nesnelere geçerli özellik sayfası değerlerini uygular.

```
HRESULT Apply();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-apply) SDK'da uygulayın.

## <a name="ipropertypageimpldeactivate"></a><a name="deactivate"></a>IPropertyPageImpl::Deactivate

[Etkinleştir](#activate)ile oluşturulan iletişim kutusu penceresini yok eder.

```
HRESULT Deactivate();
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPropertyPage::DWindows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-deactivate) SDK'da etkinleştirin.

## <a name="ipropertypageimplgetpageinfo"></a><a name="getpageinfo"></a>IPropertyPageImpl::GetPageInfo

*pPageInfo* yapısını veri üyelerinde bulunan bilgilerle doldurur.

```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Açıklamalar

`GetPageInfo`[m_dwDocString,](#m_dwdocstring) [m_dwHelpFile](#m_dwhelpfile)ve [m_dwTitle](#m_dwtitle)ile ilişkili dize kaynaklarını yükler.

Bkz. [IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-getpageinfo) SDK'daki GetPageInfo.

## <a name="ipropertypageimplhelp"></a><a name="help"></a>IPropertyPageImpl::Yardım

Özellik sayfası için Windows yardımı çağırır.

```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-help) SDK'da yardım.

## <a name="ipropertypageimplipropertypageimpl"></a><a name="ipropertypageimpl"></a>IPropertyPageImpl::IPropertyPageImpl

Oluşturucu.

```
IPropertyPageImpl();
```

### <a name="remarks"></a>Açıklamalar

Tüm veri üyelerini ilk olarak karşılar.

## <a name="ipropertypageimplispagedirty"></a><a name="ispagedirty"></a>IPropertyPageImpl::IsPageDirty

Özellik sayfasının etkinleştirildiğinden beri değişip değişmediğini gösterir.

```
HRESULT IsPageDirty(void);
```

### <a name="remarks"></a>Açıklamalar

`IsPageDirty`sayfa etkinleştirildiğinden beri değişmişse S_OK döndürür.

## <a name="ipropertypageimplm_bdirty"></a><a name="m_bdirty"></a>IPropertyPageImpl::m_bDirty

Özellik sayfasının durumunun değişip değişmediğini belirtir.

```
BOOL m_bDirty;
```

## <a name="ipropertypageimplm_nobjects"></a><a name="m_nobjects"></a>IPropertyPageImpl::m_nObjects

Özellik sayfasıyla ilişkili nesnelerin sayısını depolar.

```
ULONG m_nObjects;
```

## <a name="ipropertypageimplm_dwhelpcontext"></a><a name="m_dwhelpcontext"></a>IPropertyPageImpl::m_dwHelpContext

Özellik sayfasıyla ilişkili yardım konusu için bağlam tanımlayıcısını depolar.

```
DWORD m_dwHelpContext;
```

## <a name="ipropertypageimplm_dwdocstring"></a><a name="m_dwdocstring"></a>IPropertyPageImpl::m_dwDocString

Özellik sayfasını açıklayan metin dizesiyle ilişkili kaynak tanımlayıcısını depolar.

```
UINT m_dwDocString;
```

## <a name="ipropertypageimplm_dwhelpfile"></a><a name="m_dwhelpfile"></a>IPropertyPageImpl::m_dwHelpFile

Özellik sayfasını açıklayan yardım dosyasının adı ile ilişkili kaynak tanımlayıcısını depolar.

```
UINT m_dwHelpFile;
```

## <a name="ipropertypageimplm_dwtitle"></a><a name="m_dwtitle"></a>IPropertyPageImpl::m_dwTitle

Özellik sayfasının sekmesinde görünen metin dizesiyle ilişkili kaynak tanımlayıcısını depolar.

```
UINT m_dwTitle;
```

## <a name="ipropertypageimplm_ppagesite"></a><a name="m_ppagesite"></a>IPropertyPageImpl::m_pPageSite

Özellik sayfasının özellik çerçevesiyle iletişim kurduğu [IPropertyPageSite](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) arabirimine işaret eder.

```
IPropertyPageSite* m_pPageSite;
```

## <a name="ipropertypageimplm_ppunk"></a><a name="m_ppunk"></a>IPropertyPageImpl::m_ppUnk

Özellik sayfasıyla `IUnknown` ilişkili nesnelere işaretçiler dizisine işaret eder.

```
IUnknown** m_ppUnk;
```

## <a name="ipropertypageimplm_size"></a><a name="m_size"></a>IPropertyPageImpl::m_size

Özellik sayfasının iletişim kutusunun yüksekliğini ve genişliğini piksellerde depolar.

```
SIZE m_size;
```

## <a name="ipropertypageimplmove"></a><a name="move"></a>IPropertyPageImpl::Taşı

Özellik sayfası iletişim kutusunu konumlandırıp yeniden boyutlandırın.

```
HRESULT Move(LPCRECT pRect);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-move) SDK'da taşıyın.

## <a name="ipropertypageimplsetdirty"></a><a name="setdirty"></a>IPropertyPageImpl::SetDirty

*BDirty*değerine bağlı olarak özellik sayfasının durumunu değiştirilmiş veya değişmemiş olarak işaretleyin.

```
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Parametreler

*bKirli*<br/>
[içinde] TRUE ise, özellik sayfasının durumu değiştirilmiş olarak işaretlenir. Aksi takdirde, değişmeden olarak işaretlenir.

### <a name="remarks"></a>Açıklamalar

Gerekirse, `SetDirty` özellik sayfasının değiştiği çerçeveyi bildirir.

## <a name="ipropertypageimplsetobjects"></a><a name="setobjects"></a>IPropertyPageImpl::SetObjects

Özellik sayfasıyla `IUnknown` ilişkili nesneler için bir dizi işaretçi sağlar.

```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setobjects) SDK'daki Nesneleri Ayarla.

## <a name="ipropertypageimplsetpagesite"></a><a name="setpagesite"></a>IPropertyPageImpl::SetPageSite

Özellik sayfası, özellik sayfasının özellik çerçevesiyle iletişim kurduğu bir [IPropertyPageSite](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) işaretçisi sağlar.

```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setpagesite) SDK'da SetPageSite.

## <a name="ipropertypageimplshow"></a><a name="show"></a>IPropertyPageImpl::Göster

Özellik sayfası iletişim kutusunu görünür veya görünmez yapar.

```
HRESULT Show(UINT nCmdShow);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-show) SDK'da gösterin.

## <a name="ipropertypageimpltranslateaccelerator"></a><a name="translateaccelerator"></a>IPropertyPageImpl::TranslateAccelerator

'de `pMsg`belirtilen tuş vuruşunu işler

```
HRESULT TranslateAccelerator(MSG* pMsg);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPropertyPage::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-translateaccelerator) SDK'da TranslateAccelerator.

## <a name="see-also"></a>Ayrıca bkz.

[IPropertyPage2Impl Sınıfı](../../atl/reference/ipropertypage2impl-class.md)<br/>
[IPerPropertyBrowsingImpl Sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl Sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
