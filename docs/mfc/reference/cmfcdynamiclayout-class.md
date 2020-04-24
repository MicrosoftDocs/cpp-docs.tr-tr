---
title: CMFCDynamicLayout Sınıfı
ms.date: 08/29/2019
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
ms.openlocfilehash: 77dd3a84a0c76b92495bb062eeb83ff013933087
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752394"
---
# <a name="cmfcdynamiclayout-class"></a>CMFCDynamicLayout Sınıfı

Kullanıcı pencereyi yeniden boyutlandırırken penceredeki denetimlerin nasıl taşınıp yeniden boyutlandırıldığını belirtir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDynamicLayout : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCDynamicLayout::CMFCDynamicLayout`|Bir `CMFCDynamicLayout` nesne inşa eder.|
|`CMFCDynamicLayout::~CMFCDynamicLayout`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCDynamicLayout::AddItem](#additem)|Dinamik düzen yöneticisi tarafından denetlenir pencereler listesine genellikle bir denetim olan bir alt pencere ekler.|
|[CMFCDynamicLayout::Ayarla](#adjust)|Dinamik düzen yöneticisi tarafından denetlenir pencereler listesine genellikle bir denetim olan bir alt pencere ekler.|
|[CMFCDynamicLayout::Oluştur](#create)|Ana bilgisayar penceresini depolar ve doğrular.|
|[CMFCDynamicLayout::GetHostWnd](#gethostwnd)|Bir işaretçiyi ana bilgisayar penceresine döndürür.|
|[CMFCDynamicLayout::GetMinSize](#getminsize)|Düzenin ayarlanmadığı pencere boyutunu aşağıda döndürür.|
|[CMFCDynamicLayout::GetWindowRect](#getwindowrect)|Pencerenin geçerli istemci alanıiçin dikdörtgeni alır.|
|[CMFCDynamicLayout::HasItem](#hasitem)|Dinamik düzene bir alt denetim ekilip eklenmedi denetler.|
|[CMFCDynamicLayout::Boş](#isempty)|Dinamik bir düzende alt pencere eklenmediğini denetler.|
|[CMFCDynamicLayout::LoadResource](#loadresource)|AFX_DIALOG_LAYOUT kaynağından dinamik düzeni okur ve ardından düzeni ana bilgisayar penceresine uygular.|
|statik [CMFCDynamicLayout::MoveHorizontal](#movehorizontal)|Kullanıcı barındırma penceresini yeniden boyutlandırdığında alt denetimin yatay olarak ne kadar taşındığını tanımlayan bir [MoveSettings](#movesettings_structure) değeri alır.|
|statik [CMFCDynamicLayout::MoveHorizontalAndVertical](#movehorizontalandvertical)|Kullanıcı barındırma penceresini yeniden boyutlandırdığında alt denetimin yatay olarak ne kadar taşındığını tanımlayan bir [MoveSettings](#movesettings_structure) değeri alır.|
|statik [CMFCDynamicLayout::MoveNone](#movenone)|Bir alt denetim için hiçbir hareket, dikey veya yatay temsil eden bir [MoveSettings](#movesettings_structure) değeri alır.|
|statik [CMFCDynamicLayout::MoveVertical](#movevertical)|Kullanıcı barındırma penceresini yeniden boyutlandırdığında alt denetimin dikey olarak ne kadar taşındığını tanımlayan bir [MoveSettings](#movesettings_structure) değeri alır.|
|[CMFCDynamicLayout::SetMinSize](#setminsize)|Düzenin ayarlanmadığı pencere boyutunu aşağıda ayarlar.|
|statik [CMFCDynamicLayout::SizeHorizontal](#sizehorizontal)|Kullanıcı barındırma penceresini yeniden boyutlandırdığında alt denetimin yatay olarak ne kadar yeniden boyutlandırılabildiğini tanımlayan bir [Boyut Ayarları](#sizesettings_structure) değeri alır.|
|statik [CMFCDynamicLayout::SizeHorizontalAndVertical](#sizehorizontalandvertical)|Kullanıcı barındırma penceresini yeniden boyutlandırdığında alt denetimin yatay olarak ne kadar yeniden boyutlandırılabildiğini tanımlayan bir [Boyut Ayarları](#sizesettings_structure) değeri alır.|
|statik [CMFCDynamicLayout::SizeNone](#sizenone)|Bir alt denetim için boyutunda değişiklik olmayan bir [Boyut Ayarları](#sizesettings_structure) değeri alır.|
|statik [CMFCDynamicLayout::SizeVertical](#sizevertical)|Kullanıcı barındırma penceresini yeniden boyutlandırdığında alt denetimin dikey olarak ne kadar yeniden boyutlandırılabildiğini tanımlayan bir [Boyut Ayarları](#sizesettings_structure) değeri alır.|

## <a name="nested-types"></a>İç içe Geçmiş Türler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCDynamicLayout::MoveSettings Yapısı](#movesettings_structure)|Kapsüller dinamik bir düzende denetimler için veri taşıma.|
|[CMFCDynamicLayout::Boyut ayarları yapısı](#sizesettings_structure)|Dinamik bir düzendeki denetimler için boyut değişikliği verilerini kapsüller.|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxlayout.h

## <a name="cmfcdynamiclayoutadditem"></a><a name="additem"></a>CMFCDynamicLayout::AddItem

Dinamik düzen yöneticisi tarafından denetlenir pencereler listesine genellikle bir denetim olan bir alt pencere ekler.

```
BOOL AddItem(
    HWND hwnd,
    MoveSettings moveSettings SizeSettings sizeSettings);

BOOL AddItem(
    int nID,
    MoveSettings moveSettings SizeSettings sizeSettings);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
Eklemek için pencerenin tutamacı.

*Nıd*<br/>
Eklenecek alt denetimin kimliği.

*moveAyarlar*<br/>
Pencere boyutu değiştikçe denetimin nasıl taşınması gerektiğini açıklayan bir yapı.

*boyutAyarlar*<br/>
Pencere boyutu değiştikçe denetimin nasıl yeniden boyutlandırılması gerektiğini açıklayan bir yapı.

### <a name="return-value"></a>Dönüş Değeri

Madde başarıyla eklenmiştirsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Barındırma penceresi yeniden boyutlandırılırken, çocuk denetiminin konumu ve boyutu dinamik olarak değiştirilir.

## <a name="cmfcdynamiclayoutadjust"></a><a name="adjust"></a>CMFCDynamicLayout::Ayarla

Dinamik düzen yöneticisi tarafından denetlenir pencereler listesine genellikle bir denetim olan bir alt pencere ekler.

```cpp
void Adjust();
```

### <a name="remarks"></a>Açıklamalar

Barındırma penceresi yeniden boyutlandırılırken, çocuk denetiminin konumu ve boyutu dinamik olarak değiştirilir.

## <a name="cmfcdynamiclayoutcreate"></a><a name="create"></a>CMFCDynamicLayout::Oluştur

Ana bilgisayar penceresini depolar ve doğrular.

```
BOOL Create(CWnd* pHostWnd);
```

### <a name="parameters"></a>Parametreler

*pHostWnd*<br/>
Ana bilgisayar penceresine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yaratılış başarılı olduysa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdynamiclayoutgethostwnd"></a><a name="gethostwnd"></a>CMFCDynamicLayout::GetHostWnd

Bir işaretçiyi ana bilgisayar penceresine döndürür.

```
CWnd* GetHostWnd();
```

### <a name="return-value"></a>Dönüş Değeri

Ana bilgisayar penceresine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tüm alt denetim pozisyonları bu pencereye göre yeniden hesaplanır.

## <a name="cmfcdynamiclayoutgetminsize"></a><a name="getminsize"></a>CMFCDynamicLayout::GetMinSize

Düzenin ayarlanmadığı pencere boyutunu aşağıda döndürür.

```
CSize GetMinSize();
```

### <a name="return-value"></a>Dönüş Değeri

Düzenin ayarlanmadığı aşağıdaki pencere boyutu.

### <a name="remarks"></a>Açıklamalar

Barındırma penceresi yeniden boyutlandırılırken bir alt denetimin konumu ve boyutu dinamik olarak değiştirilir, ancak aşağıda düzenin ayarlanmadığı minimum bir boyut vardır. Kullanıcı pencereyi daha küçük bir boyuta yeniden boyutlandırabilir, ancak pencerenin bölümleri görünümden gizlenir.

## <a name="cmfcdynamiclayoutgetwindowrect"></a><a name="getwindowrect"></a>CMFCDynamicLayout::GetWindowRect

Pencerenin geçerli istemci alanıiçin dikdörtgeni alır.

```cpp
void GetHostWndRect(CRect& rect,);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
İşlev döndükten sonra, bu parametre düzen alanının sınırlayıcı dikdörtgenini içerir. Bu bir çıkış parametresi; giriş değeri üzerine yazılır.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdynamiclayouthasitem"></a><a name="hasitem"></a>CMFCDynamicLayout::HasItem

Dinamik düzene bir alt denetim ekilip eklenmedi denetler.

```
BOOL HasItem(HWND hwnd);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
Denetim için pencere tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Düzende bu öğe zaten varsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdynamiclayoutisempty"></a><a name="isempty"></a>CMFCDynamicLayout::Boş

Dinamik bir düzende alt pencere eklenmediğini denetler.

```
BOOL IsEmpty();
```

### <a name="return-value"></a>Dönüş Değeri

Düzende öğe yoksa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdynamiclayoutloadresource"></a><a name="loadresource"></a>CMFCDynamicLayout::LoadResource

AFX_DIALOG_LAYOUT kaynağından dinamik düzeni okur ve ardından düzeni ana bilgisayar penceresine uygular.

```
static BOOL LoadResource(CWnd* pHostWnd,
    LPVOID lpResource,
    DWORD dwSize);
```

### <a name="parameters"></a>Parametreler

*pHostWnd*<br/>
Ana bilgisayar penceresine bir işaretçi.

*lpResource*<br/>
AFX_DIALOG_LAYOUT kaynağı içeren arabellek için bir işaretçi.

*dwSize*<br/>
Arabellek boyutu baytlar içinde.

### <a name="return-value"></a>Dönüş Değeri

Kaynak yüklenir ve ana bilgisayar penceresine uygulanırsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdynamiclayoutmovehorizontal"></a><a name="movehorizontal"></a>CMFCDynamicLayout::MoveHorizontal

Kullanıcı barındırma penceresini yeniden boyutlandırdığında alt denetimin yatay olarak ne kadar taşındığını tanımlayan bir [MoveSettings](#movesettings_structure) değeri alır.

```
static MoveSettings MoveHorizontal(int nRatio);
```

### <a name="parameters"></a>Parametreler

*nOranı*<br/>
Kullanıcı ana bilgisayar penceresini yeniden boyutlandırdığında alt denetimin yatay olarak ne kadar taşındığını yüzde olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İstenen taşıma oranını kapsayan [Bir MoveSettings](#movesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdynamiclayoutmovehorizontalandvertical"></a><a name="movehorizontalandvertical"></a>CMFCDynamicLayout::MovehorizontalandVertical

Kullanıcı barındırma penceresini yeniden boyutlandırdığında alt denetimin yatay olarak ne kadar taşındığını tanımlayan bir [MoveSettings](#movesettings_structure) değeri alır.

```
static MoveSettings MoveHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>Parametreler

*nXRatio*<br/>
Kullanıcı ana bilgisayar penceresini yeniden boyutlandırdığında alt denetimin yatay olarak ne kadar taşındığını yüzde olarak tanımlar.

*nYRatio*<br/>
Kullanıcı ana bilgisayar penceresini yeniden boyutlandırdığında alt denetimin dikey olarak ne kadar taşındığını yüzde olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İstenen taşıma oranını kapsayan [Bir MoveSettings](#movesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdynamiclayoutmovenone"></a><a name="movenone"></a>CMFCDynamicLayout::MoveNone

Bir alt denetim için hiçbir hareket, dikey veya yatay temsil eden bir [MoveSettings](#movesettings_structure) değeri alır.

```
static MoveSettings MoveNone();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı ana bilgisayar penceresini yeniden boyutlandırırken hareket etmemek için denetimi yerinde düzelten [MoveSettings](#movesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdynamiclayoutmovesettings-structure"></a><a name="movesettings_structure"></a>CMFCDynamicLayout::MoveSettings Yapısı

Kapsüller dinamik bir düzende denetimler için veri taşıma.

```
struct CMFCDynamicLayout::MoveSettings;
```

### <a name="remarks"></a>Açıklamalar

Bu iç `CMFCDynamicLayout`içe bir sınıf.

## <a name="cmfcdynamiclayoutmovesettingsishorizontal"></a>CMFCDynamicLayout::MoveSettings::Ishorizontal

Hareket verilerinin sıfır olmayan yatay bir hareket belirtip belirtmeyip belirtmeyip belirtmeyişmeyeciyi denetleyin.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Dönüş Değeri

Nesne sıfır `MoveSettings` olmayan yatay bir hareket belirtirse DOĞRU.

## <a name="cmfcdynamiclayoutmovesettingsisnone"></a>CMFCDynamicLayout::MoveSettings::IsNone

Hareket verilerinin hareket belirtip belirtmeyişmedığını denetleyin.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Dönüş Değeri

`MoveSettings` Nesne hiçbir hareket belirtmezse DOĞRU.

## <a name="cmfcdynamiclayoutmovesettingsisvertical"></a>CMFCDynamicLayout::MoveSettings::IsVertical

Taşıma verilerinin sıfır olmayan dikey bir hareket belirtip belirtmeyip belirtmeyip belirtmeyişip belirtmeyişmeyonu kontrol edin.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Dönüş Değeri

Nesne sıfır `MoveSettings` olmayan dikey bir hareket belirtirse DOĞRU.

## <a name="cmfcdynamiclayoutmovevertical"></a><a name="movevertical"></a>CMFCDynamicLayout::MoveVertical

Kullanıcı barındırma penceresini yeniden boyutlandırdığında alt denetimin dikey olarak ne kadar taşındığını tanımlayan bir [MoveSettings](#movesettings_structure) değeri alır.

```
static MoveSettings MoveVertical(int nRatio);
```

### <a name="parameters"></a>Parametreler

*nOranı*<br/>
Kullanıcı ana bilgisayar penceresini yeniden boyutlandırdığında alt denetimin dikey olarak ne kadar taşındığını yüzde olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İstenen taşıma oranını kapsayan [Bir MoveSettings](#movesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdynamiclayoutsetminsize"></a><a name="setminsize"></a>CMFCDynamicLayout::SetMinSize

Düzenin ayarlanmadığı pencere boyutunu aşağıda ayarlar.

```cpp
void SetMinSize(const CSize& size);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Hangi düzenin ayarlanmadığı aşağıda istenen boyut.

### <a name="remarks"></a>Açıklamalar

Barındırma penceresi yeniden boyutlandırılırken bir alt denetimin konumu ve boyutu dinamik olarak değiştirilir, ancak aşağıda düzenin ayarlanmadığı minimum bir boyut vardır. Kullanıcı pencereyi daha küçük bir boyuta yeniden boyutlandırabilir, ancak pencerenin bölümleri görünümden gizlenir.

## <a name="cmfcdynamiclayoutsizehorizontal"></a><a name="sizehorizontal"></a>CMFCDynamicLayout::SizeHorizontal

Kullanıcı barındırma penceresini yeniden boyutlandırdığında alt denetimin yatay olarak ne kadar yeniden boyutlandırılabildiğini tanımlayan bir [Boyut Ayarları](#sizesettings_structure) değeri alır.

```
static SizeSettings SizeHorizontal(int nRatio);
```

### <a name="parameters"></a>Parametreler

*nOranı*<br/>
Kullanıcı ana bilgisayar penceresini yeniden boyutlandırdığında alt denetimin yatay olarak ne kadar yeniden boyutlandırıldığını yüzde olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İstenen boyut oranını kapsayan [bir Boyut Ayarları](#sizesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdynamiclayoutsizehorizontalandvertical"></a><a name="sizehorizontalandvertical"></a>CMFCDynamicLayout::SizehorizontalandVertical

Kullanıcı barındırma penceresini yeniden boyutlandırdığında alt denetimin yatay olarak ne kadar yeniden boyutlandırılabildiğini tanımlayan bir [Boyut Ayarları](#sizesettings_structure) değeri alır.

```
static SizeSettings SizeHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>Parametreler

*nXRatio*<br/>
Kullanıcı ana bilgisayar penceresini yeniden boyutlandırdığında alt denetimin yatay olarak ne kadar yeniden boyutlandırıldığını yüzde olarak tanımlar.

*nYRatio*<br/>
Kullanıcı ana bilgisayar penceresini yeniden boyutlandırdığında alt denetimin dikey olarak ne kadar yeniden boyutlandırıldığını yüzde olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İstenen boyut oranını kapsayan [bir Boyut Ayarları](#sizesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdynamiclayoutsizenone"></a><a name="sizenone"></a>CMFCDynamicLayout::sizenone

Bir alt denetim için boyutunda değişiklik olmayan bir [Boyut Ayarları](#sizesettings_structure) değeri alır.

```
static SizeSettings SizeNone();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı ana bilgisayar penceresini yeniden boyutlandırırken boyutunu değiştirmemesi için denetimi belirli bir boyutta düzelten [Boyut Ayarları](#sizesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdynamiclayoutsizesettings-structure"></a><a name="sizesettings_structure"></a>CMFCDynamicLayout::Boyut ayarları yapısı

Dinamik bir düzendeki denetimler için boyut değişikliği verilerini kapsüller.

```
struct CMFCDynamicLayout::SizeSettings;
```

### <a name="remarks"></a>Açıklamalar

Bu iç `CMFCDynamicLayout`içe bir sınıf.

## <a name="cmfcdynamiclayoutsizesettingsishorizontal"></a>CMFCDynamicLayout::Boyut ayarları::Ishorizontal

Yeniden boyutlandırma verilerinin sıfır olmayan yatay yeniden boyutlandırma belirtip belirtolmadığını denetler.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Dönüş Değeri

Doğru nesne `SizeSettings` sıfır olmayan bir yatay yeniden boyutlandırma belirtirse.

## <a name="cmfcdynamiclayoutsizesettingsisnone"></a>CMFCDynamicLayout::Boyut ayarları::isnone

Yeniden boyutlandırma verilerinin yeniden boyutlandırma belirtilip belirtolmadığını denetler.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Dönüş Değeri

`SizeSettings` Doğru nesne hiçbir yeniden boyutlandırma belirtir.

## <a name="cmfcdynamiclayoutsizesettingsisvertical"></a>CMFCDynamicLayout::Boyut ayarları::Dikey

Yeniden boyutlandırma verilerinin sıfır olmayan dikey yeniden boyutlandırma belirtip belirtmeyişmeyip belirtolmadığını denetler.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Dönüş Değeri

Doğru nesne `SizeSettings` sıfır olmayan dikey yeniden boyutlandırma belirtirse.

## <a name="cmfcdynamiclayoutsizevertical"></a><a name="sizevertical"></a>CMFCDynamicLayout::SizeVertical

Kullanıcı barındırma penceresini yeniden boyutlandırdığında alt denetimin dikey olarak ne kadar yeniden boyutlandırılabildiğini tanımlayan bir [Boyut Ayarları](#sizesettings_structure) değeri alır.

```
static SizeSettings SizeVertical(int nRatio);
```

### <a name="parameters"></a>Parametreler

*nOranı*<br/>
Kullanıcı ana bilgisayar penceresini yeniden boyutlandırdığında alt denetimin dikey olarak ne kadar yeniden boyutlandırıldığını yüzde olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İstenen boyut oranını kapsayan [bir Boyut Ayarları](#sizesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
