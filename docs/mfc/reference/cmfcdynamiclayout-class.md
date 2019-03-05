---
title: CMFCDynamicLayout sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout::AddItem
- AFXLAYOUT/CMFCDynamicLayout::Adjust
- AFXLAYOUT/CMFCDynamicLayout::Create
- AFXLAYOUT/CMFCDynamicLayout::GetHostWnd
- AFXLAYOUT/CMFCDynamicLayout::GetMinSize
- AFXLAYOUT/CMFCDynamicLayout::GetWindowRect
- AFXLAYOUT/CMFCDynamicLayout::HasItem
- AFXLAYOUT/CMFCDynamicLayout::IsEmpty
- AFXLAYOUT/CMFCDynamicLayout::LoadResource
- AFXLAYOUT/CMFCDynamicLayout::SetMinSize
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
ms.openlocfilehash: 40dedbe2737a79b7531b8acd47870ce7cb788604
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288408"
---
# <a name="cmfcdynamiclayout-class"></a>CMFCDynamicLayout sınıfı

Kullanıcı yeniden boyutlandırır gibi yeniden boyutlandırılan bir pencerede denetimlerinin nasıl taşınmış ve belirtir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDynamicLayout : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCDynamicLayout::CMFCDynamicLayout`|Oluşturur bir `CMFCDynamicLayout` nesne.|
|`CMFCDynamicLayout::~CMFCDynamicLayout`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDynamicLayout::AddItem](#additem)|Dinamik düzen yönetici tarafından denetlenen windows listesi için genellikle bir denetimi alt pencere ekler.|
|[CMFCDynamicLayout::Adjust](#adjust)|Dinamik düzen yönetici tarafından denetlenen windows listesi için genellikle bir denetimi alt pencere ekler.|
|[CMFCDynamicLayout::Create](#create)|Depolar ve konak penceresinin doğrular.|
|[CMFCDynamicLayout::GetHostWnd](#gethostwnd)|Bir konak penceresine bir işaretçi döndürür.|
|[CMFCDynamicLayout::GetMinSize](#getminsize)|Hangi düzenin aşağıda pencere boyutu ayarlanamadı döndürür.|
|[CMFCDynamicLayout::GetWindowRect](#getwindowrect)|Geçerli istemci bölge penceresinin için dikdörtgen alır.|
|[CMFCDynamicLayout::HasItem](#hasitem)|Dinamik düzen için bir alt denetimin eklendiyse denetler.|
|[CMFCDynamicLayout::IsEmpty](#isempty)|Dinamik düzen eklenen herhangi bir alt öğe pencerelerini sahip olup olmadığını denetler.|
|[CMFCDynamicLayout::LoadResource](#loadresource)|Dinamik düzen AFX_DIALOG_LAYOUT kaynağından okur ve ana pencereyi düzeni uygular.|
|statik [CMFCDynamicLayout::MoveHorizontal](#movehorizontal)|Alır bir [MoveSettings](#movesettings_structure) değer kullanıcının kendi barındırma penceresi yeniden boyutlandırdığında ne kadar bir alt denetimin yatay olarak tanımlar.|
|statik [CMFCDynamicLayout::MoveHorizontalAndVertical](#movehorizontalandvertical)|Alır bir [MoveSettings](#movesettings_structure) değer kullanıcının kendi barındırma penceresi yeniden boyutlandırdığında ne kadar bir alt denetimin yatay olarak tanımlar.|
|statik [CMFCDynamicLayout::MoveNone](#movenone)|Alır bir [MoveSettings](#movesettings_structure) dikey veya yatay bir alt denetimin için hiçbir hareket gösteren bir değer.|
|statik [CMFCDynamicLayout::MoveVertical](#movevertical)|Alır bir [MoveSettings](#movesettings_structure) değer kullanıcının kendi barındırma penceresi yeniden boyutlandırdığında ne kadar bir alt denetimin dikey olarak tanımlar.|
|[CMFCDynamicLayout::SetMinSize](#setminsize)|Hangi düzenin aşağıda pencere boyutu ayarlanamadı ayarlar.|
|statik [CMFCDynamicLayout::SizeHorizontal](#sizehorizontal)|Alır bir [SizeSettings](#sizesettings_structure) kullanıcı kendi barındırma penceresi yeniden boyutlandırdığında ne kadar bir alt denetimin yatay olarak yeniden boyutlandırıldığını tanımlar değeri.|
|statik [CMFCDynamicLayout::SizeHorizontalAndVertical](#sizehorizontalandvertical)|Alır bir [SizeSettings](#sizesettings_structure) kullanıcı kendi barındırma penceresi yeniden boyutlandırdığında ne kadar bir alt denetimin yatay olarak yeniden boyutlandırıldığını tanımlar değeri.|
|statik [CMFCDynamicLayout::SizeNone](#sizenone)|Alır bir [SizeSettings](#sizesettings_structure) bir alt denetimin boyutunu değişiklik gösteren bir değer.|
|statik [CMFCDynamicLayout::SizeVertical](#sizevertical)|Alır bir [SizeSettings](#sizesettings_structure) kullanıcı kendi barındırma penceresi yeniden boyutlandırdığında ne kadar bir alt denetimin dikey olarak yeniden boyutlandırıldığını tanımlar değeri.|

## <a name="nested-types"></a>İç içe Geçmiş Türler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDynamicLayout::MoveSettings yapısı](#movesettings_structure)|Dinamik düzen denetimleri için veri taşıma kapsüller.|
|[CMFCDynamicLayout::SizeSettings yapısı](#sizesettings_structure)|Dinamik düzen denetimleri boyutu değişiklik verilerini kapsüller.|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxlayout.h

##  <a name="additem"></a>  CMFCDynamicLayout::AddItem

Dinamik düzen yönetici tarafından denetlenen windows listesi için genellikle bir denetimi alt pencere ekler.

```
BOOL AddItem(
    HWND hwnd,
    MoveSettings moveSettings SizeSettings sizeSettings);

BOOL AddItem(
    int nID,
    MoveSettings moveSettings SizeSettings sizeSettings);
```

### <a name="parameters"></a>Parametreler

*HWND*<br/>
Eklenecek penceresine tanıtıcısı.

*nID*<br/>
Eklemek için alt denetimin kimliği.

*moveSettings*<br/>
Pencere boyutu değiştikçe denetimi nasıl taşınacağını açıklar yapısı.

*sizeSettings*<br/>
Denetimi pencere boyutu değiştikçe nasıl boyutlandırılıp açıklayan yapısı.

### <a name="return-value"></a>Dönüş Değeri

Öğesi başarıyla eklenmişse TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bir alt denetimin boyutunu ve konumunu değiştiğinde dinamik barındırma penceresi yeniden boyutlandırılırken.

##  <a name="adjust"></a>  CMFCDynamicLayout::Adjust

Dinamik düzen yönetici tarafından denetlenen windows listesi için genellikle bir denetimi alt pencere ekler.

```
void Adjust();
```

### <a name="remarks"></a>Açıklamalar

Bir alt denetimin boyutunu ve konumunu değiştiğinde dinamik barındırma penceresi yeniden boyutlandırılırken.

##  <a name="create"></a>  CMFCDynamicLayout::Create

Depolar ve konak penceresinin doğrular.

```
BOOL Create(CWnd* pHostWnd);
```

### <a name="parameters"></a>Parametreler

*pHostWnd*<br/>
Ana pencere işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Oluşturma başarılı olursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="gethostwnd"></a>  CMFCDynamicLayout::GetHostWnd

Bir konak penceresine bir işaretçi döndürür.

```
CWnd* GetHostWnd();
```

### <a name="return-value"></a>Dönüş Değeri

Ana pencere işaretçisi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu penceresiyle ilişkili tüm alt denetim konumları yeniden hesaplanır.

##  <a name="getminsize"></a>  CMFCDynamicLayout::GetMinSize

Hangi düzenin aşağıda pencere boyutu ayarlanamadı döndürür.

```
CSize GetMinSize();
```

### <a name="return-value"></a>Dönüş Değeri

Pencere boyutu altında Düzen değil ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bir alt denetimin boyutunu ve konumunu değiştiğinde dinamik barındırma penceresi yeniden boyutlandırılıyor, ancak en az boyutu altında Düzen değil ayarlanır. Kullanıcı pencereyi daha küçük bir boyuta yeniden boyutlandırabilirsiniz, ancak pencere bölümlerini ardından görünümünden gizlenen.

##  <a name="getwindowrect"></a>  CMFCDynamicLayout::GetWindowRect

Geçerli istemci bölge penceresinin için dikdörtgen alır.

```
void GetHostWndRect(CRect& rect,);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Bu parametre, işlev döndürdükten sonra Düzen alanına sınırlayıcı dikdörtgenini içerir. Out parametresi budur; giriş değeri üzerine yazılır.

### <a name="remarks"></a>Açıklamalar

##  <a name="hasitem"></a>  CMFCDynamicLayout::HasItem

Dinamik düzen için bir alt denetimin eklendiyse denetler.

```
BOOL HasItem(HWND hwnd);
```

### <a name="parameters"></a>Parametreler

*HWND*<br/>
Denetimi için Pencere işleyicisi.

### <a name="return-value"></a>Dönüş Değeri

Bu öğe düzeni varsa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="isempty"></a>  CMFCDynamicLayout::IsEmpty

Dinamik düzen eklenen herhangi bir alt öğe pencerelerini sahip olup olmadığını denetler.

```
BOOL IsEmpty();
```

### <a name="return-value"></a>Dönüş Değeri

Düzen öğe varsa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="loadresource"></a>  CMFCDynamicLayout::LoadResource

Dinamik düzen AFX_DIALOG_LAYOUT kaynağından okur ve ana pencereyi düzeni uygular.

```
static BOOL LoadResource(CWnd* pHostWnd,
    LPVOID lpResource,
    DWORD dwSize);
```

### <a name="parameters"></a>Parametreler

*pHostWnd*<br/>
Ana pencere işaretçisi.

*lpResource*<br/>
Bir işaretçi AFX_DIALOG_LAYOUT kaynağı içeren arabellek.

*dwSize*<br/>
Arabellek boyutu bayt cinsinden.

### <a name="return-value"></a>Dönüş Değeri

Kaynak yüklendi ve ana pencereyi uygulanan gerekiyorsa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="movehorizontal"></a>  CMFCDynamicLayout::MoveHorizontal

Alır bir [MoveSettings](#movesettings_structure) değer kullanıcının kendi barındırma penceresi yeniden boyutlandırdığında ne kadar bir alt denetimin yatay olarak tanımlar.

```
static MoveSettings MoveHorizontal(int nRatio);
```

### <a name="parameters"></a>Parametreler

*nRatio*<br/>
Yüzde olarak kullanıcı konak penceresini yeniden boyutlandırdığında ne kadar bir alt denetimin yatay olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

A [MoveSettings](#movesettings_structure) istenen kapsülleyen değeri taşımak oranı.

### <a name="remarks"></a>Açıklamalar

##  <a name="movehorizontalandvertical"></a>  CMFCDynamicLayout::MoveHorizontalAndVertical

Alır bir [MoveSettings](#movesettings_structure) değer kullanıcının kendi barındırma penceresi yeniden boyutlandırdığında ne kadar bir alt denetimin yatay olarak tanımlar.

```
static MoveSettings MoveHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>Parametreler

*nXRatio*<br/>
Yüzde olarak kullanıcı konak penceresini yeniden boyutlandırdığında ne kadar bir alt denetimin yatay olarak tanımlar.

*nYRatio*<br/>
Yüzde olarak kullanıcı konak penceresini yeniden boyutlandırdığında ne kadar bir alt denetimin dikey olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

A [MoveSettings](#movesettings_structure) istenen kapsülleyen değeri taşımak oranı.

### <a name="remarks"></a>Açıklamalar

##  <a name="movenone"></a>  CMFCDynamicLayout::MoveNone

Alır bir [MoveSettings](#movesettings_structure) dikey veya yatay bir alt denetimin için hiçbir hareket gösteren bir değer.

```
static MoveSettings MoveNone();
```

### <a name="return-value"></a>Dönüş Değeri

A [MoveSettings](#movesettings_structure) denetim yerinde düzeltir ve böylece kullanıcı konak penceresini yeniden boyutlandırır gibi taşımaz değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="movesettings_structure"></a>  CMFCDynamicLayout::MoveSettings yapısı

Dinamik düzen denetimleri için veri taşıma kapsüller.

```
struct CMFCDynamicLayout::MoveSettings;
```

### <a name="remarks"></a>Açıklamalar

İç içe geçmiş bir sınıf içinde budur `CMFCDynamicLayout`.

## <a name="cmfcdynamiclayoutmovesettingsishorizontal"></a>CMFCDynamicLayout::MoveSettings::IsHorizontal

Veri taşıma sıfır olmayan bir yatay hareket belirtirse denetleyin.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Dönüş Değeri

TRUE ise `MoveSettings` sıfır olmayan bir yatay hareket nesnesini belirtir.

## <a name="cmfcdynamiclayoutmovesettingsisnone"></a>CMFCDynamicLayout::MoveSettings::IsNone

Veri taşıma hiçbir taşıma belirtirse denetleyin.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Dönüş Değeri

TRUE ise `MoveSettings` hiçbir taşıma nesnesini belirtir.

## <a name="cmfcdynamiclayoutmovesettingsisvertical"></a>CMFCDynamicLayout::MoveSettings::IsVertical

  Veri taşıma sıfır olmayan bir dikey taşıma belirtirse denetleyin.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Dönüş Değeri

TRUE ise `MoveSettings` sıfır olmayan bir dikey taşıma nesnesini belirtir.

##  <a name="movevertical"></a>  CMFCDynamicLayout::MoveVertical

Alır bir [MoveSettings](#movesettings_structure) değer kullanıcının kendi barındırma penceresi yeniden boyutlandırdığında ne kadar bir alt denetimin dikey olarak tanımlar.

```
static MoveSettings MoveVertical(int nRatio);
```

### <a name="parameters"></a>Parametreler

*nRatio*<br/>
Yüzde olarak kullanıcı konak penceresini yeniden boyutlandırdığında ne kadar bir alt denetimin dikey olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

A [MoveSettings](#movesettings_structure) istenen kapsülleyen değeri taşımak oranı.

### <a name="remarks"></a>Açıklamalar

##  <a name="setminsize"></a>  CMFCDynamicLayout::SetMinSize

Hangi düzenin aşağıda pencere boyutu ayarlanamadı ayarlar.

```
void SetMinSize(const CSize& size);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
İstenen boyut altında Düzen değil ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bir alt denetimin boyutunu ve konumunu değiştiğinde dinamik barındırma penceresi yeniden boyutlandırılıyor, ancak en az boyutu altında Düzen değil ayarlanır. Kullanıcı pencereyi daha küçük bir boyuta yeniden boyutlandırabilirsiniz, ancak pencere bölümlerini ardından görünümünden gizlenen.

##  <a name="sizehorizontal"></a>  CMFCDynamicLayout::SizeHorizontal

Alır bir [SizeSettings](#sizesettings_structure) kullanıcı kendi barındırma penceresi yeniden boyutlandırdığında ne kadar bir alt denetimin yatay olarak yeniden boyutlandırıldığını tanımlar değeri.

```
static SizeSettings SizeHorizontal(int nRatio);
```

### <a name="parameters"></a>Parametreler

*nRatio*<br/>
Yüzde olarak kullanıcı konak penceresini yeniden boyutlandırdığında ne kadar bir alt denetimin yatay olarak yeniden boyutlandırıldığını tanımlar.

### <a name="return-value"></a>Dönüş Değeri

A [SizeSettings](#sizesettings_structure) istenen boyutu oranı kapsülleyen bir değer.

### <a name="remarks"></a>Açıklamalar

##  <a name="sizehorizontalandvertical"></a>  CMFCDynamicLayout::SizeHorizontalAndVertical

Alır bir [SizeSettings](#sizesettings_structure) kullanıcı kendi barındırma penceresi yeniden boyutlandırdığında ne kadar bir alt denetimin yatay olarak yeniden boyutlandırıldığını tanımlar değeri.

```
static SizeSettings SizeHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>Parametreler

*nXRatio*<br/>
Yüzde olarak kullanıcı konak penceresini yeniden boyutlandırdığında ne kadar bir alt denetimin yatay olarak yeniden boyutlandırıldığını tanımlar.

*nYRatio*<br/>
Yüzde olarak kullanıcı konak penceresini yeniden boyutlandırdığında ne kadar bir alt denetimin dikey olarak yeniden boyutlandırıldığını tanımlar.

### <a name="return-value"></a>Dönüş Değeri

A [SizeSettings](#sizesettings_structure) istenen boyutu oranı kapsülleyen bir değer.

### <a name="remarks"></a>Açıklamalar

##  <a name="sizenone"></a>  CMFCDynamicLayout::SizeNone

Alır bir [SizeSettings](#sizesettings_structure) bir alt denetimin boyutunu değişiklik gösteren bir değer.

```
static SizeSettings SizeNone();
```

### <a name="return-value"></a>Dönüş Değeri

A [SizeSettings](#sizesettings_structure) denetimin belirli bir boyutta düzeltir ve böylece kullanıcı konak penceresini yeniden boyutlandırır gibi boyut değişmez değer.

### <a name="remarks"></a>Açıklamalar

##  <a name="sizesettings_structure"></a>  CMFCDynamicLayout::SizeSettings yapısı

Dinamik düzen denetimleri boyutu değişiklik verilerini kapsüller.

```
struct CMFCDynamicLayout::SizeSettings;
```

### <a name="remarks"></a>Açıklamalar

İç içe geçmiş bir sınıf içinde budur `CMFCDynamicLayout`.

## <a name="cmfcdynamiclayoutsizesettingsishorizontal"></a>CMFCDynamicLayout::SizeSettings::IsHorizontal

Yeniden boyutlandırma verilerini bir sıfır olmayan yatay yeniden boyutlandırma belirtirse denetler.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Dönüş Değeri

TRUE ise `SizeSettings` nesnesini bir sıfır olmayan yatay yeniden boyutlandırma belirtir.

## <a name="cmfcdynamiclayoutsizesettingsisnone"></a>CMFCDynamicLayout::SizeSettings::IsNone

Yeniden boyutlandırma veri, yeniden boyutlandırma belirtirse denetler.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Dönüş Değeri

TRUE ise `SizeSettings` nesneyi yeniden boyutlandırma belirtir.

## <a name="cmfcdynamiclayoutsizesettingsisvertical"></a>CMFCDynamicLayout::SizeSettings::IsVertical

Yeniden boyutlandırma verilerini bir sıfır olmayan dikey yeniden boyutlandırma belirtirse denetler.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Dönüş Değeri

TRUE ise `SizeSettings` nesnesini bir sıfır olmayan dikey yeniden boyutlandırma belirtir.

##  <a name="sizevertical"></a>  CMFCDynamicLayout::SizeVertical

Alır bir [SizeSettings](#sizesettings_structure) kullanıcı kendi barındırma penceresi yeniden boyutlandırdığında ne kadar bir alt denetimin dikey olarak yeniden boyutlandırıldığını tanımlar değeri.

```
static SizeSettings SizeVertical(int nRatio);
```

### <a name="parameters"></a>Parametreler

*nRatio*<br/>
Yüzde olarak kullanıcı konak penceresini yeniden boyutlandırdığında ne kadar bir alt denetimin dikey olarak yeniden boyutlandırıldığını tanımlar.

### <a name="return-value"></a>Dönüş Değeri

A [SizeSettings](#sizesettings_structure) istenen boyutu oranı kapsülleyen bir değer.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
