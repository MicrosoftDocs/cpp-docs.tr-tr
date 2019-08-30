---
title: CMFCDynamicLayout sınıfı
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
ms.openlocfilehash: f1ddf35b514d9b89f53d5f1307a6ecb7132d2854
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177518"
---
# <a name="cmfcdynamiclayout-class"></a>CMFCDynamicLayout sınıfı

Kullanıcı pencereyi yeniden boyutlandırdığında penceredeki denetimlerin nasıl taşındığını ve yeniden boyutlandırılacağını belirtir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDynamicLayout : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCDynamicLayout::CMFCDynamicLayout`|Bir `CMFCDynamicLayout` nesnesi oluşturur.|
|`CMFCDynamicLayout::~CMFCDynamicLayout`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDynamicLayout:: AddItem](#additem)|Dinamik düzen yöneticisi tarafından denetlenen pencereler listesine bir alt pencere (genellikle bir denetim) ekler.|
|[CMFCDynamicLayout:: ayarla](#adjust)|Dinamik düzen yöneticisi tarafından denetlenen pencereler listesine bir alt pencere (genellikle bir denetim) ekler.|
|[CMFCDynamicLayout:: Create](#create)|Konak penceresini depolar ve doğrular.|
|[CMFCDynamicLayout:: GetHostWnd](#gethostwnd)|Ana bilgisayar penceresine bir işaretçi döndürür.|
|[CMFCDynamicLayout:: GetMinSize](#getminsize)|Düzenin ayarlandığı pencere boyutunu döndürür.|
|[CMFCDynamicLayout:: GetWindowRect](#getwindowrect)|Pencerenin geçerli istemci alanı için dikdörtgeni alır.|
|[CMFCDynamicLayout:: HasItem](#hasitem)|Dinamik düzene bir alt denetim eklenip eklenmediğini denetler.|
|[CMFCDynamicLayout:: IsEmpty](#isempty)|Dinamik bir düzenin alt pencereleri eklenip eklenmediğini denetler.|
|[CMFCDynamicLayout:: LoadResource](#loadresource)|AFX_DIALOG_LAYOUT kaynağından dinamik düzeni okur ve sonra düzeni ana bilgisayar penceresine uygular.|
|statik [CMFCDynamicLayout:: Moveyatay](#movehorizontal)|Kullanıcı barındırma penceresini yeniden boyutlandırdığında bir alt denetimin yatay olarak ne kadar taşındığını tanımlayan bir [MoveSettings](#movesettings_structure) değeri alır.|
|statik [CMFCDynamicLayout:: MoveHorizontalAndVertical](#movehorizontalandvertical)|Kullanıcı barındırma penceresini yeniden boyutlandırdığında bir alt denetimin yatay olarak ne kadar taşındığını tanımlayan bir [MoveSettings](#movesettings_structure) değeri alır.|
|statik [CMFCDynamicLayout:: MoveNone](#movenone)|Alt denetim için hareket, dikey veya yatay olarak temsil eden bir [MoveSettings](#movesettings_structure) değeri alır.|
|statik [CMFCDynamicLayout:: MoveVertical](#movevertical)|Kullanıcı barındırma penceresini yeniden boyutlandırdığında bir alt denetimin dikey olarak ne kadar taşındığını tanımlayan bir [MoveSettings](#movesettings_structure) değeri alır.|
|[CMFCDynamicLayout:: SetMinSize](#setminsize)|Düzenin ayarlanmayan pencere boyutunu ayarlar.|
|statik [CMFCDynamicLayout:: Sizeyatay](#sizehorizontal)|Kullanıcı barındırma penceresini yeniden boyutlandırdığında bir alt denetimin yatay olarak ne kadar yeniden boyutlandırıldığını tanımlayan bir [SizeSettings](#sizesettings_structure) değeri alır.|
|statik [CMFCDynamicLayout:: SizeHorizontalAndVertical](#sizehorizontalandvertical)|Kullanıcı barındırma penceresini yeniden boyutlandırdığında bir alt denetimin yatay olarak ne kadar yeniden boyutlandırıldığını tanımlayan bir [SizeSettings](#sizesettings_structure) değeri alır.|
|statik [CMFCDynamicLayout:: SizeNone](#sizenone)|Bir alt denetim için boyut değişikliğini temsil eden bir [SizeSettings](#sizesettings_structure) değeri alır.|
|statik [CMFCDynamicLayout:: SizeVertical](#sizevertical)|Kullanıcı barındırma penceresini yeniden boyutlandırdığında bir alt denetimin dikey olarak ne kadar yeniden boyutlandırıldığını tanımlayan bir [SizeSettings](#sizesettings_structure) değeri alır.|

## <a name="nested-types"></a>İç içe Geçmiş Türler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDynamicLayout:: MoveSettings yapısı](#movesettings_structure)|Dinamik bir düzende denetimlerin verilerini taşıma ' yı kapsüller.|
|[CMFCDynamicLayout:: SizeSettings yapısı](#sizesettings_structure)|Dinamik düzendeki denetimlerin boyut değişiklik verilerini kapsüller.|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxlayout. h

##  <a name="additem"></a>CMFCDynamicLayout:: AddItem

Dinamik düzen yöneticisi tarafından denetlenen pencereler listesine bir alt pencere (genellikle bir denetim) ekler.

```
BOOL AddItem(
    HWND hwnd,
    MoveSettings moveSettings SizeSettings sizeSettings);

BOOL AddItem(
    int nID,
    MoveSettings moveSettings SizeSettings sizeSettings);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
Eklenecek pencerenin tutamacı.

*NID*<br/>
Eklenecek alt denetimin KIMLIĞI.

*moveSettings*<br/>
Pencere boyutu değiştiğinde denetimin nasıl taşınacağını açıklayan bir yapı.

*sizeSettings*<br/>
Pencere boyutu değiştiğinde denetimin nasıl yeniden boyutlandırılacağını açıklayan bir yapı.

### <a name="return-value"></a>Dönüş Değeri

Öğe başarıyla eklendiyse doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bir barındırma penceresi yeniden boyutlandırılırken bir alt denetimin konumu ve boyutu dinamik olarak değiştirilir.

##  <a name="adjust"></a>CMFCDynamicLayout:: ayarla

Dinamik düzen yöneticisi tarafından denetlenen pencereler listesine bir alt pencere (genellikle bir denetim) ekler.

```
void Adjust();
```

### <a name="remarks"></a>Açıklamalar

Bir barındırma penceresi yeniden boyutlandırılırken bir alt denetimin konumu ve boyutu dinamik olarak değiştirilir.

##  <a name="create"></a>CMFCDynamicLayout:: Create

Konak penceresini depolar ve doğrular.

```
BOOL Create(CWnd* pHostWnd);
```

### <a name="parameters"></a>Parametreler

*Fostwnd*<br/>
Ana bilgisayar penceresine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Oluşturma başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

##  <a name="gethostwnd"></a>CMFCDynamicLayout:: GetHostWnd

Ana bilgisayar penceresine bir işaretçi döndürür.

```
CWnd* GetHostWnd();
```

### <a name="return-value"></a>Dönüş Değeri

Ana bilgisayar penceresine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tüm alt denetim konumları bu pencereye göre yeniden hesaplanır.

##  <a name="getminsize"></a>CMFCDynamicLayout:: GetMinSize

Düzenin ayarlandığı pencere boyutunu döndürür.

```
CSize GetMinSize();
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki düzenin ayarlandığı pencere boyutu.

### <a name="remarks"></a>Açıklamalar

Bir barındırma penceresi yeniden boyutlandırılırken bir alt denetimin konumu ve boyutu dinamik olarak değiştirilir, ancak en düşük bir boyut aşağıda ayarlanır. Kullanıcı pencereyi daha küçük bir boyutla yeniden boyutlandırabilir, ancak pencerenin parçaları görünümden gizlenir.

##  <a name="getwindowrect"></a>CMFCDynamicLayout:: GetWindowRect

Pencerenin geçerli istemci alanı için dikdörtgeni alır.

```
void GetHostWndRect(CRect& rect,);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
İşlev döndüğünde, bu parametre düzen alanının sınırlayıcı dikdörtgenini içerir. Bu bir out parametresidir; giriş değerinin üzerine yazılır.

### <a name="remarks"></a>Açıklamalar

##  <a name="hasitem"></a>CMFCDynamicLayout:: HasItem

Dinamik düzene bir alt denetim eklenip eklenmediğini denetler.

```
BOOL HasItem(HWND hwnd);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
Denetim için pencere tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Düzen zaten bu öğeye sahipse TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

##  <a name="isempty"></a>CMFCDynamicLayout:: IsEmpty

Dinamik bir düzenin alt pencereleri eklenip eklenmediğini denetler.

```
BOOL IsEmpty();
```

### <a name="return-value"></a>Dönüş Değeri

Mizanpajda öğe yoksa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

##  <a name="loadresource"></a>CMFCDynamicLayout:: LoadResource

AFX_DIALOG_LAYOUT kaynağından dinamik düzeni okur ve sonra düzeni ana bilgisayar penceresine uygular.

```
static BOOL LoadResource(CWnd* pHostWnd,
    LPVOID lpResource,
    DWORD dwSize);
```

### <a name="parameters"></a>Parametreler

*Fostwnd*<br/>
Ana bilgisayar penceresine yönelik bir işaretçi.

*lpResource*<br/>
AFX_DIALOG_LAYOUT kaynağını içeren arabelleğin işaretçisi.

*dwSize*<br/>
Bayt cinsinden arabellek boyutu.

### <a name="return-value"></a>Dönüş Değeri

Kaynak yüklenip ana bilgisayar penceresine uygulanırsa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

##  <a name="movehorizontal"></a>CMFCDynamicLayout:: Moveyatay

Kullanıcı barındırma penceresini yeniden boyutlandırdığında bir alt denetimin yatay olarak ne kadar taşındığını tanımlayan bir [MoveSettings](#movesettings_structure) değeri alır.

```
static MoveSettings MoveHorizontal(int nRatio);
```

### <a name="parameters"></a>Parametreler

*Noran*<br/>
Kullanıcı konak penceresini yeniden boyutlandırdığında bir alt denetimin yatay olarak ne kadar taşındığını yüzde olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İstenen taşıma oranını kapsülleyen bir [MoveSettings](#movesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="movehorizontalandvertical"></a>CMFCDynamicLayout:: MoveHorizontalAndVertical

Kullanıcı barındırma penceresini yeniden boyutlandırdığında bir alt denetimin yatay olarak ne kadar taşındığını tanımlayan bir [MoveSettings](#movesettings_structure) değeri alır.

```
static MoveSettings MoveHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>Parametreler

*nXRatio*<br/>
Kullanıcı konak penceresini yeniden boyutlandırdığında bir alt denetimin yatay olarak ne kadar taşındığını yüzde olarak tanımlar.

*nYRatio*<br/>
Kullanıcı konak penceresini yeniden boyutlandırdığında bir alt denetimin dikey olarak ne kadar ilerlemediğini yüzde olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İstenen taşıma oranını kapsülleyen bir [MoveSettings](#movesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="movenone"></a>CMFCDynamicLayout:: MoveNone

Alt denetim için hareket, dikey veya yatay olarak temsil eden bir [MoveSettings](#movesettings_structure) değeri alır.

```
static MoveSettings MoveNone();
```

### <a name="return-value"></a>Dönüş Değeri

Denetimi yerinde düzelten bir [MoveSettings](#movesettings_structure) değeri, Kullanıcı ana bilgisayar penceresini yeniden boyutlandırdığından hareket etmez.

### <a name="remarks"></a>Açıklamalar

##  <a name="movesettings_structure"></a>CMFCDynamicLayout:: MoveSettings yapısı

Dinamik bir düzende denetimlerin verilerini taşıma ' yı kapsüller.

```
struct CMFCDynamicLayout::MoveSettings;
```

### <a name="remarks"></a>Açıklamalar

Bu, içinde `CMFCDynamicLayout`iç içe yerleştirilmiş bir sınıftır.

## <a name="cmfcdynamiclayoutmovesettingsishorizontal"></a>CMFCDynamicLayout:: MoveSettings:: ısyatay

Taşıma verilerinin sıfır dışında yatay bir taşıma belirttiğinden emin olun.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Dönüş Değeri

`MoveSettings` Nesne sıfır dışında yatay taşıma belirtiyorsa doğru.

## <a name="cmfcdynamiclayoutmovesettingsisnone"></a>CMFCDynamicLayout:: MoveSettings:: IsNone

Taşıma verilerinde hareket olup olmadığını kontrol edin.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Dönüş Değeri

`MoveSettings` Nesne hiçbir hareket belirtiyorsa true.

## <a name="cmfcdynamiclayoutmovesettingsisvertical"></a>CMFCDynamicLayout:: MoveSettings:: IsVertical

Taşıma verilerinde sıfır dışında dikey bir hareket olup olmadığını kontrol edin.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Dönüş Değeri

`MoveSettings` Nesne sıfır olmayan dikey bir hareket belirtiyorsa doğru.

##  <a name="movevertical"></a>CMFCDynamicLayout:: MoveVertical

Kullanıcı barındırma penceresini yeniden boyutlandırdığında bir alt denetimin dikey olarak ne kadar taşındığını tanımlayan bir [MoveSettings](#movesettings_structure) değeri alır.

```
static MoveSettings MoveVertical(int nRatio);
```

### <a name="parameters"></a>Parametreler

*Noran*<br/>
Kullanıcı konak penceresini yeniden boyutlandırdığında bir alt denetimin dikey olarak ne kadar ilerlemediğini yüzde olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İstenen taşıma oranını kapsülleyen bir [MoveSettings](#movesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="setminsize"></a>CMFCDynamicLayout:: SetMinSize

Düzenin ayarlanmayan pencere boyutunu ayarlar.

```
void SetMinSize(const CSize& size);
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Aşağıdaki düzenin ayarlanmayacağı istenen boyut.

### <a name="remarks"></a>Açıklamalar

Bir barındırma penceresi yeniden boyutlandırılırken bir alt denetimin konumu ve boyutu dinamik olarak değiştirilir, ancak en düşük bir boyut aşağıda ayarlanır. Kullanıcı pencereyi daha küçük bir boyutla yeniden boyutlandırabilir, ancak pencerenin parçaları görünümden gizlenir.

##  <a name="sizehorizontal"></a>CMFCDynamicLayout:: Sizeyatay

Kullanıcı barındırma penceresini yeniden boyutlandırdığında bir alt denetimin yatay olarak ne kadar yeniden boyutlandırıldığını tanımlayan bir [SizeSettings](#sizesettings_structure) değeri alır.

```
static SizeSettings SizeHorizontal(int nRatio);
```

### <a name="parameters"></a>Parametreler

*Noran*<br/>
Kullanıcı konak penceresini yeniden boyutlandırdığında bir alt denetimin yatay olarak ne kadar yeniden boyutlandırıldığını yüzde olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İstenen boyut oranını kapsülleyen bir [SizeSettings](#sizesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="sizehorizontalandvertical"></a>CMFCDynamicLayout:: SizeHorizontalAndVertical

Kullanıcı barındırma penceresini yeniden boyutlandırdığında bir alt denetimin yatay olarak ne kadar yeniden boyutlandırıldığını tanımlayan bir [SizeSettings](#sizesettings_structure) değeri alır.

```
static SizeSettings SizeHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>Parametreler

*nXRatio*<br/>
Kullanıcı konak penceresini yeniden boyutlandırdığında bir alt denetimin yatay olarak ne kadar yeniden boyutlandırıldığını yüzde olarak tanımlar.

*nYRatio*<br/>
Kullanıcı konak penceresini yeniden boyutlandırdığında bir alt denetimin dikey olarak ne kadar yeniden boyutlandırıldığını yüzde olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İstenen boyut oranını kapsülleyen bir [SizeSettings](#sizesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="sizenone"></a>CMFCDynamicLayout:: SizeNone

Bir alt denetim için boyut değişikliğini temsil eden bir [SizeSettings](#sizesettings_structure) değeri alır.

```
static SizeSettings SizeNone();
```

### <a name="return-value"></a>Dönüş Değeri

Denetimi belirli bir boyutta düzelten bir [SizeSettings](#sizesettings_structure) değeri, Kullanıcı ana bilgisayar penceresini yeniden boyutlandırdığından boyutu değiştirmez.

### <a name="remarks"></a>Açıklamalar

##  <a name="sizesettings_structure"></a>CMFCDynamicLayout:: SizeSettings yapısı

Dinamik düzendeki denetimlerin boyut değişiklik verilerini kapsüller.

```
struct CMFCDynamicLayout::SizeSettings;
```

### <a name="remarks"></a>Açıklamalar

Bu, içinde `CMFCDynamicLayout`iç içe yerleştirilmiş bir sınıftır.

## <a name="cmfcdynamiclayoutsizesettingsishorizontal"></a>CMFCDynamicLayout:: SizeSettings:: ısyatay

Yeniden boyutlandırma verilerinin sıfır dışı bir yatay yeniden boyutlandırmayı belirtir olup olmadığını denetler.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Dönüş Değeri

`SizeSettings` Nesne sıfır dışında bir yatay yeniden boyutlandırma belirtiyorsa true.

## <a name="cmfcdynamiclayoutsizesettingsisnone"></a>CMFCDynamicLayout:: SizeSettings:: IsNone

Yeniden boyutlandırma verilerinin yeniden boyutlandırma olup olmadığını denetler.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Dönüş Değeri

`SizeSettings` Nesne yeniden boyutlandırma yoksa true.

## <a name="cmfcdynamiclayoutsizesettingsisvertical"></a>CMFCDynamicLayout:: SizeSettings:: IsVertical

Yeniden boyutlandırma verilerinde sıfır dışında dikey yeniden boyutlandırma olup olmadığını denetler.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Dönüş Değeri

`SizeSettings` Nesne sıfır olmayan dikey yeniden boyutlandırma belirtiyorsa true.

##  <a name="sizevertical"></a>CMFCDynamicLayout:: SizeVertical

Kullanıcı barındırma penceresini yeniden boyutlandırdığında bir alt denetimin dikey olarak ne kadar yeniden boyutlandırıldığını tanımlayan bir [SizeSettings](#sizesettings_structure) değeri alır.

```
static SizeSettings SizeVertical(int nRatio);
```

### <a name="parameters"></a>Parametreler

*Noran*<br/>
Kullanıcı konak penceresini yeniden boyutlandırdığında bir alt denetimin dikey olarak ne kadar yeniden boyutlandırıldığını yüzde olarak tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İstenen boyut oranını kapsülleyen bir [SizeSettings](#sizesettings_structure) değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
