---
title: "CMFCDynamicLayout sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 29b161d889aefc55e818a16233212a55bdcb45de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcdynamiclayout-class"></a>CMFCDynamicLayout sınıfı
Bir pencere denetimlerinde nasıl taşınır ve kullanıcı yeniden boyutlandırır gibi yeniden boyutlandırılan belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCDynamicLayout : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCDynamicLayout::CMFCDynamicLayout`|Oluşturan bir `CMFCDynamicLayout` nesnesi.|  
|`CMFCDynamicLayout::~CMFCDynamicLayout`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCDynamicLayout::AddItem](#additem)|Alt pencere, genellikle bir denetim, dinamik düzen yönetici tarafından denetlenen windows listesine ekler.|  
|[CMFCDynamicLayout::Adjust](#adjust)|Alt pencere, genellikle bir denetim, dinamik düzen yönetici tarafından denetlenen windows listesine ekler.|  
|[CMFCDynamicLayout::Create](#create)|Depolar ve konak penceresinin doğrular.|  
|[CMFCDynamicLayout::GetHostWnd](#gethostwnd)|Bir işaretçi bir konak penceresine döndürür.|  
|[CMFCDynamicLayout::GetMinSize](#getminsize)|Hangi düzenin aşağıda pencere boyutu değil ayarlanır döndürür.|  
|[CMFCDynamicLayout::GetWindowRect](#getwindowrect)|Pencerenin geçerli istemci alanını için dikdörtgen alır.|  
|[CMFCDynamicLayout::HasItem](#hasitem)|Bir alt denetim dinamik düzen eklendiyse denetler.|  
|[CMFCDynamicLayout::IsEmpty](#isempty)|Dinamik düzen eklenen hiç alt öğe pencerelerini sahip olup olmadığını denetler.|  
|[CMFCDynamicLayout::LoadResource](#loadresource)|Dinamik düzen AFX_DIALOG_LAYOUT kaynağından okur ve sonra ana pencereyi düzeni uygular.|  
|statik [CMFCDynamicLayout::MoveHorizontal](#movehorizontal)|Alır bir [MoveSettings](#movesettings_structure) kullanıcı kendi barındırma yeniden boyutlandırır olduğunda ne kadar bir alt denetim yatay olarak taşınır tanımlayan değeri.|  
|statik [CMFCDynamicLayout::MoveHorizontalAndVertical](#movehorizontalandvertical)|Alır bir [MoveSettings](#movesettings_structure) kullanıcı kendi barındırma yeniden boyutlandırır olduğunda ne kadar bir alt denetim yatay olarak taşınır tanımlayan değeri.|  
|statik [CMFCDynamicLayout::MoveNone](#movenone)|Alır bir [MoveSettings](#movesettings_structure) dikey veya yatay bir alt denetim için hiçbir hareket gösteren bir değer.|  
|statik [CMFCDynamicLayout::MoveVertical](#movevertical)|Alır bir [MoveSettings](#movesettings_structure) kullanıcı kendi barındırma yeniden boyutlandırır olduğunda ne kadar bir alt denetim dikey olarak taşınır tanımlayan değeri.|  
|[CMFCDynamicLayout::SetMinSize](#setminsize)|Hangi düzenin aşağıda pencere boyutu değil ayarlanır ayarlar.|  
|statik [CMFCDynamicLayout::SizeHorizontal](#sizehorizontal)|Alır bir [SizeSettings](#sizesettings_structure) kullanıcı kendi barındırma yeniden boyutlandırır olduğunda ne kadar bir alt denetim yatay olarak boyutlandırılır tanımlayan değeri.|  
|statik [CMFCDynamicLayout::SizeHorizontalAndVertical](#sizehorizontalandvertical)|Alır bir [SizeSettings](#sizesettings_structure) kullanıcı kendi barındırma yeniden boyutlandırır olduğunda ne kadar bir alt denetim yatay olarak boyutlandırılır tanımlayan değeri.|  
|statik [CMFCDynamicLayout::SizeNone](#sizenone)|Alır bir [SizeSettings](#sizesettings_structure) boyutu alt denetimi için hiçbir değişiklik gösteren bir değer.|  
|statik [CMFCDynamicLayout::SizeVertical](#sizevertical)|Alır bir [SizeSettings](#sizesettings_structure) kullanıcı kendi barındırma yeniden boyutlandırır olduğunda ne kadar bir alt denetim dikey olarak boyutlandırılır tanımlayan değeri.|  
  
## <a name="nested-types"></a>İç içe Geçmiş Türler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCDynamicLayout::MoveSettings yapısı](#movesettings_structure)|Dinamik düzen denetimlerinde verileri saklar.|  
|[CMFCDynamicLayout::SizeSettings yapısı](#sizesettings_structure)|Dinamik düzen denetimler için boyutu değişiklik verilerini yansıtır.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxlayout.h  
  
##  <a name="additem"></a>CMFCDynamicLayout::AddItem  
 Alt pencere, genellikle bir denetim, dinamik düzen yönetici tarafından denetlenen windows listesine ekler.  
  
```  
BOOL AddItem(
    HWND hwnd,
    MoveSettings moveSettings SizeSettings sizeSettings);

 
BOOL AddItem(
    int nID,
    MoveSettings moveSettings SizeSettings sizeSettings);
```  
  
### <a name="parameters"></a>Parametreler  
 `hwnd`  
 Eklemek için penceresine işleci.  
  
 `nID`  
 Eklemek için alt denetim kimliği.  
  
 `moveSettings`  
 Pencere boyutu değiştikçe denetimi nasıl taşınacağını açıklar yapısı.  
  
 `sizeSettings`  
 Denetim pencere boyutu değiştikçe nasıl boyutlandırılmasını açıklar yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe başarıyla eklenmişse TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Alt denetim boyutunu ve konumunu değiştirildiğinde dinamik olarak bir barındırma penceresi boyutlandırıldığında.  
  
##  <a name="adjust"></a>CMFCDynamicLayout::Adjust  
 Alt pencere, genellikle bir denetim, dinamik düzen yönetici tarafından denetlenen windows listesine ekler.  
  
```  
void Adjust();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Alt denetim boyutunu ve konumunu değiştirildiğinde dinamik olarak bir barındırma penceresi boyutlandırıldığında.  
  
##  <a name="create"></a>CMFCDynamicLayout::Create  
 Depolar ve konak penceresinin doğrular.  
  
```  
BOOL Create(CWnd* pHostWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 pHostWnd  
 Konak penceresi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Oluşturma başarılı olursa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gethostwnd"></a>CMFCDynamicLayout::GetHostWnd  
 Bir işaretçi bir konak penceresine döndürür.  
  
```  
CWnd* GetHostWnd();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Konak penceresi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu pencereyi göre tüm alt denetim konumlar yeniden hesaplanması.  
  
##  <a name="getminsize"></a>CMFCDynamicLayout::GetMinSize  
 Hangi düzenin aşağıda pencere boyutu değil ayarlanır döndürür.  
  
```  
CSize GetMinSize();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencere boyutu, altında düzeni değil ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Alt denetim boyutunu ve konumunu değiştirildiğinde dinamik olarak bir barındırma penceresi yeniden boyutlandırılabilir ancak altında düzeni değil ayarlanır en az bir boyutu vardır. Kullanıcı pencereyi daha küçük bir boyuta genişletebilir, ancak pencere bölümlerini sonra görünümünden gizlenir.  
  
##  <a name="getwindowrect"></a>CMFCDynamicLayout::GetWindowRect  
 Pencerenin geçerli istemci alanını için dikdörtgen alır.  
  
```  
void GetHostWndRect(CRect& rect,);
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 İşlev döndükten sonra bu parametre düzen alanına sınırlayıcı dikdörtgenini içerir. Out parametresi budur; giriş değeri üzerine yazılır.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hasitem"></a>CMFCDynamicLayout::HasItem  
 Bir alt denetim dinamik düzen eklendiyse denetler.  
  
```  
BOOL HasItem(HWND hwnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `hwnd`  
 Denetimi için Pencere işleyicisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düzen bu öğe zaten varsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isempty"></a>CMFCDynamicLayout::IsEmpty  
 Dinamik düzen eklenen hiç alt öğe pencerelerini sahip olup olmadığını denetler.  
  
```  
BOOL IsEmpty();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düzen hiçbir öğe varsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="loadresource"></a>CMFCDynamicLayout::LoadResource  
 Dinamik düzen AFX_DIALOG_LAYOUT kaynağından okur ve sonra ana pencereyi düzeni uygular.  
  
```  
static BOOL LoadResource(CWnd* pHostWnd,
    LPVOID lpResource,
    DWORD dwSize);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pHostWnd`  
 Konak penceresi için bir işaretçi.  
  
 `lpResource`  
 AFX_DIALOG_LAYOUT kaynağı içeren arabellek için bir işaretçi.  
  
 `dwSize`  
 Bayt cinsinden arabellek boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynak yüklenen ve konak penceresine uyguladıysanız TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="movehorizontal"></a>CMFCDynamicLayout::MoveHorizontal  
 Alır bir [MoveSettings](#movesettings_structure) kullanıcı kendi barındırma yeniden boyutlandırır olduğunda ne kadar bir alt denetim yatay olarak taşınır tanımlayan değeri.  
  
```  
static MoveSettings MoveHorizontal(int nRatio);  
```  
  
### <a name="parameters"></a>Parametreler  
 `nRatio`  
 Kullanıcı konak boyutlandırır olduğunda ne kadar alt denetim yatay olarak taşınır yüzde olarak tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [MoveSettings](#movesettings_structure) istenen yalıtır değerini Taşı oranı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="movehorizontalandvertical"></a>CMFCDynamicLayout::MoveHorizontalAndVertical  
 Alır bir [MoveSettings](#movesettings_structure) kullanıcı kendi barındırma yeniden boyutlandırır olduğunda ne kadar bir alt denetim yatay olarak taşınır tanımlayan değeri.  
  
```  
static MoveSettings MoveHorizontalAndVertical(int nXRatio int nYRatio);  
```  
  
### <a name="parameters"></a>Parametreler  
 `nXRatio`  
 Kullanıcı konak boyutlandırır olduğunda ne kadar alt denetim yatay olarak taşınır yüzde olarak tanımlar.  
  
 `nYRatio`  
 Kullanıcı konak boyutlandırır olduğunda ne kadar alt denetim dikey olarak taşınır yüzde olarak tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [MoveSettings](#movesettings_structure) istenen yalıtır değerini Taşı oranı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="movenone"></a>CMFCDynamicLayout::MoveNone  
 Alır bir [MoveSettings](#movesettings_structure) dikey veya yatay bir alt denetim için hiçbir hareket gösteren bir değer.  
  
```  
static MoveSettings MoveNone();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [MoveSettings](#movesettings_structure) denetimi yerinde giderir ve böylece kullanıcının ana pencereyi yeniden boyutlandırır gibi taşımaz değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="movesettings_structure"></a>CMFCDynamicLayout::MoveSettings yapısı  
 Dinamik düzen denetimlerinde verileri saklar.  
  
```  
struct CMFCDynamicLayout::MoveSettings;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İç içe bir sınıf içinde budur `CMFCDynamicLayout`.  

## <a name="cmfcdynamiclayoutmovesettingsishorizontal"></a>CMFCDynamicLayout::MoveSettings::IsHorizontal
Taşıma veri sıfır olmayan bir yatay taşıma belirtirse denetleyin.  
  

```  
BOOL IsHorizontal() const 
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 TRUE ise `MoveSettings` nesne sıfır olmayan bir yatay taşıma belirtir.  

 ## <a name="cmfcdynamiclayoutmovesettingsisnone"></a>CMFCDynamicLayout::MoveSettings::IsNone
 Taşıma veri hiçbir taşıma belirtirse denetleyin.  
  
```  
BOOL IsNone() const 
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 TRUE ise `MoveSettings` nesnesini hiçbir taşıma belirtir.  

## <a name="cmfcdynamiclayoutmovesettingsisvertical"></a>CMFCDynamicLayout::MoveSettings::IsVertical
  Taşıma veri sıfır olmayan bir dikey taşıma belirtirse denetleyin.  
  
```  
BOOL IsVertical() const 
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 TRUE ise `MoveSettings` nesne sıfır olmayan bir dikey taşıma belirtir.  

##  <a name="movevertical"></a>CMFCDynamicLayout::MoveVertical  
 Alır bir [MoveSettings](#movesettings_structure) kullanıcı kendi barındırma yeniden boyutlandırır olduğunda ne kadar bir alt denetim dikey olarak taşınır tanımlayan değeri.  
  
```  
static MoveSettings MoveVertical(int nRatio);  
```  
  
### <a name="parameters"></a>Parametreler  
 `nRatio`  
 Kullanıcı konak boyutlandırır olduğunda ne kadar alt denetim dikey olarak taşınır yüzde olarak tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [MoveSettings](#movesettings_structure) istenen yalıtır değerini Taşı oranı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setminsize"></a>CMFCDynamicLayout::SetMinSize  
 Hangi düzenin aşağıda pencere boyutu değil ayarlanır ayarlar.  
  
```  
void SetMinSize(const CSize& size);
```  
  
### <a name="parameters"></a>Parametreler  
 `size`  
 İstenen boyut, altında düzeni değil ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Alt denetim boyutunu ve konumunu değiştirildiğinde dinamik olarak bir barındırma penceresi yeniden boyutlandırılabilir ancak altında düzeni değil ayarlanır en az bir boyutu vardır. Kullanıcı pencereyi daha küçük bir boyuta genişletebilir, ancak pencere bölümlerini sonra görünümünden gizlenir.  
  
##  <a name="sizehorizontal"></a>CMFCDynamicLayout::SizeHorizontal  
 Alır bir [SizeSettings](#sizesettings_structure) kullanıcı kendi barındırma yeniden boyutlandırır olduğunda ne kadar bir alt denetim yatay olarak boyutlandırılır tanımlayan değeri.  
  
```  
static SizeSettings SizeHorizontal(int nRatio);  
```  
  
### <a name="parameters"></a>Parametreler  
 `nRatio`  
 Kullanıcı konak boyutlandırır olduğunda ne kadar alt denetim yatay olarak yeniden boyutlandırılır yüzde olarak tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [SizeSettings](#sizesettings_structure) istenen boyuta oranı yalıtır değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sizehorizontalandvertical"></a>CMFCDynamicLayout::SizeHorizontalAndVertical  
 Alır bir [SizeSettings](#sizesettings_structure) kullanıcı kendi barındırma yeniden boyutlandırır olduğunda ne kadar bir alt denetim yatay olarak boyutlandırılır tanımlayan değeri.  
  
```  
static SizeSettings SizeHorizontalAndVertical(int nXRatio int nYRatio);  
```  
  
### <a name="parameters"></a>Parametreler  
 `nXRatio`  
 Kullanıcı konak boyutlandırır olduğunda ne kadar alt denetim yatay olarak yeniden boyutlandırılır yüzde olarak tanımlar.  
  
 `nYRatio`  
 Kullanıcı konak boyutlandırır olduğunda ne kadar alt denetim dikey olarak yeniden boyutlandırılır yüzde olarak tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [SizeSettings](#sizesettings_structure) istenen boyuta oranı yalıtır değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sizenone"></a>CMFCDynamicLayout::SizeNone  
 Alır bir [SizeSettings](#sizesettings_structure) boyutu alt denetimi için hiçbir değişiklik gösteren bir değer.  
  
```  
static SizeSettings SizeNone();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [SizeSettings](#sizesettings_structure) denetimi belirli bir boyutta giderir ve böylece kullanıcının ana pencereyi yeniden boyutlandırır gibi boyutu değişmez değer.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sizesettings_structure"></a>CMFCDynamicLayout::SizeSettings yapısı  
 Dinamik düzen denetimler için boyutu değişiklik verilerini yansıtır.  
  
```  
struct CMFCDynamicLayout::SizeSettings;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İç içe bir sınıf içinde budur `CMFCDynamicLayout`.  

## <a name="cmfcdynamiclayoutsizesettingsishorizontal"></a>CMFCDynamicLayout::SizeSettings::IsHorizontal
Yeniden boyutlandırma veri bir sıfır olmayan yatay yeniden boyutlandırma belirtirse denetler.  
  
```  
BOOL IsHorizontal() const 
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 TRUE ise `SizeSettings` nesnesini belirtir. bir sıfır olmayan yatay yeniden boyutlandırma. 

## <a name="cmfcdynamiclayoutsizesettingsisnone"></a>CMFCDynamicLayout::SizeSettings::IsNone
Yeniden boyutlandırma verileri yeniden boyutlandırma belirtirse denetler.  
  
```  
BOOL IsNone() const 
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 TRUE ise `SizeSettings` nesnesini belirtir. yeniden boyutlandırma yok.  

## <a name="cmfcdynamiclayoutsizesettingsisvertical"></a>CMFCDynamicLayout::SizeSettings::IsVertical
Yeniden boyutlandırma veri bir sıfır olmayan dikey yeniden boyutlandırma belirtirse denetler.  
  
```  
BOOL IsVertical() const 
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 TRUE ise `SizeSettings` nesnesini belirtir. bir sıfır olmayan dikey yeniden boyutlandırma.  

##  <a name="sizevertical"></a>CMFCDynamicLayout::SizeVertical  
 Alır bir [SizeSettings](#sizesettings_structure) kullanıcı kendi barındırma yeniden boyutlandırır olduğunda ne kadar bir alt denetim dikey olarak boyutlandırılır tanımlayan değeri.  
  
```  
static SizeSettings SizeVertical(int nRatio);  
```  
  
### <a name="parameters"></a>Parametreler  
 `nRatio`  
 Kullanıcı konak boyutlandırır olduğunda ne kadar alt denetim dikey olarak yeniden boyutlandırılır yüzde olarak tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [SizeSettings](#sizesettings_structure) istenen boyuta oranı yalıtır değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)
