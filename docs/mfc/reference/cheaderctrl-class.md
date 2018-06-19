---
title: CHeaderCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHeaderCtrl
- AFXCMN/CHeaderCtrl
- AFXCMN/CHeaderCtrl::CHeaderCtrl
- AFXCMN/CHeaderCtrl::ClearAllFilters
- AFXCMN/CHeaderCtrl::ClearFilter
- AFXCMN/CHeaderCtrl::Create
- AFXCMN/CHeaderCtrl::CreateDragImage
- AFXCMN/CHeaderCtrl::CreateEx
- AFXCMN/CHeaderCtrl::DeleteItem
- AFXCMN/CHeaderCtrl::DrawItem
- AFXCMN/CHeaderCtrl::EditFilter
- AFXCMN/CHeaderCtrl::GetBitmapMargin
- AFXCMN/CHeaderCtrl::GetFocusedItem
- AFXCMN/CHeaderCtrl::GetImageList
- AFXCMN/CHeaderCtrl::GetItem
- AFXCMN/CHeaderCtrl::GetItemCount
- AFXCMN/CHeaderCtrl::GetItemDropDownRect
- AFXCMN/CHeaderCtrl::GetItemRect
- AFXCMN/CHeaderCtrl::GetOrderArray
- AFXCMN/CHeaderCtrl::GetOverflowRect
- AFXCMN/CHeaderCtrl::HitTest
- AFXCMN/CHeaderCtrl::InsertItem
- AFXCMN/CHeaderCtrl::Layout
- AFXCMN/CHeaderCtrl::OrderToIndex
- AFXCMN/CHeaderCtrl::SetBitmapMargin
- AFXCMN/CHeaderCtrl::SetFilterChangeTimeout
- AFXCMN/CHeaderCtrl::SetFocusedItem
- AFXCMN/CHeaderCtrl::SetHotDivider
- AFXCMN/CHeaderCtrl::SetImageList
- AFXCMN/CHeaderCtrl::SetItem
- AFXCMN/CHeaderCtrl::SetOrderArray
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl [MFC], CHeaderCtrl
- CHeaderCtrl [MFC], ClearAllFilters
- CHeaderCtrl [MFC], ClearFilter
- CHeaderCtrl [MFC], Create
- CHeaderCtrl [MFC], CreateDragImage
- CHeaderCtrl [MFC], CreateEx
- CHeaderCtrl [MFC], DeleteItem
- CHeaderCtrl [MFC], DrawItem
- CHeaderCtrl [MFC], EditFilter
- CHeaderCtrl [MFC], GetBitmapMargin
- CHeaderCtrl [MFC], GetFocusedItem
- CHeaderCtrl [MFC], GetImageList
- CHeaderCtrl [MFC], GetItem
- CHeaderCtrl [MFC], GetItemCount
- CHeaderCtrl [MFC], GetItemDropDownRect
- CHeaderCtrl [MFC], GetItemRect
- CHeaderCtrl [MFC], GetOrderArray
- CHeaderCtrl [MFC], GetOverflowRect
- CHeaderCtrl [MFC], HitTest
- CHeaderCtrl [MFC], InsertItem
- CHeaderCtrl [MFC], Layout
- CHeaderCtrl [MFC], OrderToIndex
- CHeaderCtrl [MFC], SetBitmapMargin
- CHeaderCtrl [MFC], SetFilterChangeTimeout
- CHeaderCtrl [MFC], SetFocusedItem
- CHeaderCtrl [MFC], SetHotDivider
- CHeaderCtrl [MFC], SetImageList
- CHeaderCtrl [MFC], SetItem
- CHeaderCtrl [MFC], SetOrderArray
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 582ffffc4461edd41078f1a89844bdc260b2dd40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376027"
---
# <a name="cheaderctrl-class"></a>CHeaderCtrl sınıfı
Windows ortak üstbilgi denetimi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CHeaderCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|Oluşturan bir `CHeaderCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|Üstbilgi denetimi için tüm filtreleri kaldırır.|  
|[CHeaderCtrl::ClearFilter](#clearfilter)|Üstbilgi denetimi için filtre temizler.|  
|[CHeaderCtrl::Create](#create)|Üstbilgi denetimi oluşturur ve ona ekler bir `CHeaderCtrl` nesnesi.|  
|[CHeaderCtrl::CreateDragImage](#createdragimage)|Üstbilgi denetimi içinde bir öğenin resmi saydam bir sürümünü oluşturur.|  
|[CHeaderCtrl::CreateEx](#createex)|Üstbilgi denetimi belirtilen Windows genişletilmiş stilleri oluşturur ve ekler bir `CListCtrl` nesnesi.|  
|[CHeaderCtrl::DeleteItem](#deleteitem)|Öğenin başlığı denetimden siler.|  
|[CHeaderCtrl::DrawItem](#drawitem)|Üstbilgi denetimi belirtilen öğeyi çizer.|  
|[CHeaderCtrl::EditFilter](#editfilter)|Üstbilgi denetimi belirtilen filtreyi düzenleme başlatır.|  
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|Üstbilgi denetimindeki bir bit eşlem kenar genişliğini alır.|  
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|Odaklanmış geçerli üstbilgi denetimi öğesinin tanımlayıcısını alır.|  
|[CHeaderCtrl::GetImageList](#getimagelist)|Üstbilgi denetimindeki çizim üstbilgi öğeleri için kullanılan bir görüntü listesi işleyicisini alır.|  
|[CHeaderCtrl::GetItem](#getitem)|Üstbilgi denetimindeki bir öğesiyle ilgili bilgileri alır.|  
|[CHeaderCtrl::GetItemCount](#getitemcount)|Üstbilgi denetimindeki öğeleri sayısını alır.|  
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|Üstbilgi denetimindeki belirtilen açılan düğmesine sınırlayıcı dikdörtgen bilgilerini alır.|  
|[CHeaderCtrl::GetItemRect](#getitemrect)|Üstbilgi denetimindeki belirli bir öğe için sınırlayıcı dikdörtgenini alır.|  
|[CHeaderCtrl::GetOrderArray](#getorderarray)|Üstbilgi denetimindeki öğeleri soldan sağa sırasını alır.|  
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|Taşma düğmesinin sınırlayıcı dikdörtgenini geçerli üstbilgi denetimi için alır.|  
|[CHeaderCtrl::HitTest](#hittest)|Hangi üstbilgi öğesi, varsa, belirli bir noktada bulunduğunu belirler.|  
|[CHeaderCtrl::InsertItem](#insertitem)|Üstbilgi denetimine yeni bir öğe ekler.|  
|[CHeaderCtrl::Layout](#layout)|Boyut ve belirli bir dikdörtgen üstbilgi denetimine konumunu alır.|  
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|Üstbilgi denetimi kendi sırayla temel alınarak bir öğenin dizini değerini alır.|  
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|Üstbilgi denetimindeki bir bit eşlem kenar genişliğini ayarlar.|  
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|Bir değişiklik filtre öznitelikleri yerinde süresini deftere arasındaki zaman aşımı aralığı ayarlar bir `HDN_FILTERCHANGE` bildirim.|  
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|Geçerli üstbilgi denetimindeki belirtilen üstbilgi öğesine odağı ayarlar.|  
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|Değişiklikleri el ile belirtmek için üstbilgi öğeleri arasındaki ayırıcıyı sürükleyin ve bir üstbilgi öğesinin bırak.|  
|[CHeaderCtrl::SetImageList](#setimagelist)|Görüntü listesi bir üstbilgi denetimine atar.|  
|[CHeaderCtrl::SetItem](#setitem)|Belirtilen öğe özniteliklerini üstbilgi denetimindeki ayarlar.|  
|[CHeaderCtrl::SetOrderArray](#setorderarray)|Üstbilgi denetimindeki öğeleri soldan sağa sırasını ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Üstbilgi denetimi metin veya sayı sütun kümesini genellikle konumlandırılmış bir penceredir. Her sütun için bir başlık içerir ve bölümlere ayrılabilir. Kullanıcı, her sütunun genişliği ayarlamak için bölümleri ayrı Bölücü sürükleyebilirsiniz. Üstbilgi denetimi çizim için bkz: [üstbilgi denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb775238).  
  
 Bu denetim (ve bu nedenle `CHeaderCtrl` sınıfı) Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programları için kullanılabilir ve üzerinde desteklenir.  
  
 Windows 95/Internet Explorer 4.0 ortak denetimleri için eklenen işlevler şunlardır:  
  
-   Üstbilgi öğesi özel sıralaması.  
  
-   Üstbilgi öğesi sürükleyin ve bırakın, üstbilgi öğelerinin yeniden sıralanmasını için. Kullanım `HDS_DRAGDROP` stil oluşturduğunuzda `CHeaderCtrl` nesnesi.  
  
-   Üstbilgi sütun metni sütun yeniden boyutlandırma sırasında sürekli olarak görüntülenebilir. Kullanım `HDS_FULLDRAG` stil oluşturduğunuzda bir `CHeaderCtrl` nesnesi.  
  
-   İşaretçinin üzerine getirildiğinde, üstbilgi öğesi vurgular üstbilgi etkin izleme. Kullanım `HDS_HOTTRACK` stil oluşturduğunuzda `CHeaderCtrl` nesnesi.  
  
-   Resim listesi desteği. Üstbilgi öğeleri depolanan görüntüleri içeren bir `CImageList` nesne veya metni.  
  
 Kullanma hakkında daha fazla bilgi için `CHeaderCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak CHeaderCtrl](../../mfc/using-cheaderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHeaderCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="cheaderctrl"></a>  CHeaderCtrl::CHeaderCtrl  
 Oluşturan bir `CHeaderCtrl` nesnesi.  
  
```  
CHeaderCtrl();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]  
  
##  <a name="clearallfilters"></a>  CHeaderCtrl::ClearAllFilters  
 Üstbilgi denetimi için tüm filtreleri kaldırır.  
  
```  
BOOL ClearAllFilters();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem Win32 iletisinin davranışını uygulayan [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306) -1, Windows SDK'ın açıklandığı gibi bir sütun değerine sahip.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]  
  
##  <a name="clearfilter"></a>  CHeaderCtrl::ClearFilter  
 Üstbilgi denetimi için filtre temizler.  
  
```  
BOOL ClearFilter(int nColumn);
```  
  
### <a name="parameters"></a>Parametreler  
 `nColumn`  
 Hangi temizlemek için filtre gösteren sütun değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem Win32 iletisinin davranışını uygulayan [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]  
  
##  <a name="create"></a>  CHeaderCtrl::Create  
 Üstbilgi denetimi oluşturur ve ona ekler bir `CHeaderCtrl` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Üstbilgi denetim stilini belirtir. Üstbilgi denetim stilleri açıklaması için bkz: [üstbilgi denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775241) Windows SDK.  
  
 `rect`  
 Üstbilgi denetim boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı.  
  
 `pParentWnd`  
 Üstbilgi denetim ana penceresinde, genellikle belirtir bir `CDialog`. Değil olmalıdır **NULL**.  
  
 `nID`  
 Üstbilgi denetim kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlatma başarılı olduğunda sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CHeaderCtrl` iki adımda nesne. İlk olarak, Oluşturucusu arayın ve ardından arama **oluşturma**, üstbilgi denetimi oluşturur ve ekler `CHeaderCtrl` nesnesi.  
  
 Üstbilgi denetim stilleri yanı sıra nasıl üstbilgi denetimi yerleştirir ve kendisini yeniden boyutlandırır belirlemek için aşağıdaki ortak denetim stilleri kullanabilirsiniz (bkz [ortak denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775498) daha fazla bilgi için):  
  
- `CCS_BOTTOM` Kendi üst pencerenin istemci alanı altındaki konumlandırmak denetimi neden olur ve üst ile aynı olacak şekilde genişliği pencerenin genişliğini belirler.  
  
- `CCS_NODIVIDER` İki piksel Vurgu denetimi üstünde çizilmiş engeller.  
  
- `CCS_NOMOVEY` Yeniden boyutlandırma ve kendisini yatay ancak değil dikey olarak yanıt olarak taşımak denetim neden olan bir `WM_SIZE` ileti. Varsa `CCS_NORESIZE` stili kullanılır, bu stili geçerli değildir. Üstbilgi denetimleri varsayılan olarak bu stili sahiptir.  
  
- `CCS_NOPARENTALIGN` Denetim üst veya alt üst kısmında otomatik olarak geçmesini önler. Bunun yerine, Denetim değişiklikleri rağmen üst pencere içindeki konumunun üst pencere boyutunu tutar. Varsa `CCS_TOP` veya `CCS_BOTTOM` stili de kullanıldığında, yüksekliği varsayılan olarak ayarlanır, ancak konum ve genişlik değişmeden kalır.  
  
- `CCS_NORESIZE` Denetimin varsayılan genişlik ve yükseklik ilk boyutu veya yeni bir boyut ayarlarken kullanmalarını engeller. Bunun yerine, genişlik ve yükseklik oluşturma veya boyutlandırma için istekte belirtilen denetimi kullanır.  
  
- `CCS_TOP` Kendi üst pencerenin istemci alanının üstünde konumlandırmak denetimi neden olur ve üst ile aynı olacak şekilde genişliği pencerenin genişliğini belirler.  
  
 Üstbilgi denetimi için de aşağıdaki pencere stilleri uygulayabilirsiniz (bkz [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) daha fazla bilgi için):  
  
- **WS_CHILD** alt pencere oluşturur. Kullanılamaz `WS_POPUP` stili.  
  
- **Ws_vısıble** başlangıçta görünür bir pencere oluşturur.  
  
- **Ws_dısabled** başlangıçta devre dışı bir pencere oluşturur.  
  
- **WS_GROUP** denetimleri içinde kullanıcı taşıyabilirsiniz bir denetimden yanındaki ok tuşlarını kullanarak grubunun ilk denetim belirtir. İle tanımlanmış tüm denetimler **WS_GROUP** ilk denetim ait sonra aynı gruba stili. Sonraki denetimiyle **WS_GROUP** stili Stil grubu sona erer ve sonraki grubu (sonraki başladığı diğer bir deyişle, bir grup uçları) başlatır.  
  
- **WS_TABSTOP** belirtir herhangi bir sayı birini üzerinden kullanıcı taşımak için SEKME tuşunu kullanarak denetimlerin. Sekme tuşuna kullanıcı tarafından belirtilen bir sonraki denetime gider **WS_TABSTOP** stili.  
  
 Genişletilmiş windows stilleri denetimi ile kullanmak istiyorsanız, çağrı [CreateEx](#createex) yerine **oluşturma**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]  
  
##  <a name="createex"></a>  CHeaderCtrl::CreateEx  
 Bir denetimi (alt pencere) oluşturur ve bu ilişkilendirmeyi `CHeaderCtrl` nesnesi.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwExStyle`  
 Oluşturulan denetim genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri listesi için bkz: `dwExStyle` parametresi için [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK'sındaki.  
  
 `dwStyle`  
 Üstbilgi denetim stili. Üstbilgi denetim stilleri açıklaması için bkz: [üstbilgi denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775241) Windows SDK. Bkz: [oluşturma](#create) ek stilleri listesi.  
  
 `rect`  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) boyutunu ve konumunu, istemci koordinatları oluşturulacak penceresinin açıklayan yapısı `pParentWnd`.  
  
 `pParentWnd`  
 Denetimin üst penceresi için bir işaretçi.  
  
 `nID`  
 Denetimin alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine **oluşturma** Windows genişletilmiş stili önsöz tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için **WS_EX_**.  
  
##  <a name="createdragimage"></a>  CHeaderCtrl::CreateDragImage  
 Üstbilgi denetimi içinde bir öğenin resmi saydam bir sürümünü oluşturur.  
  
```  
CImageList* CreateDragImage(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Üstbilgi denetimi içinde öğenin sıfır tabanlı dizini. Bu öğeye atanan resmin saydam görüntü temelini oluşturur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) nesne başarılı; Aksi takdirde **NULL**. Döndürülen listede yalnızca bir görüntü içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [HDM_CREATEDRAGIMAGE](http://msdn.microsoft.com/library/windows/desktop/bb775308), Windows SDK'ın açıklandığı gibi. Üstbilgi öğesi sürükle ve bırak desteği sağlanır.  
  
 `CImageList` Döndürülen işaretçi noktaları geçici bir nesne ve sonraki boşta kalma süresi işleme, silinen nesne.  
  
##  <a name="deleteitem"></a>  CHeaderCtrl::DeleteItem  
 Öğenin başlığı denetimden siler.  
  
```  
BOOL DeleteItem(int nPos);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPos`  
 Silmek istediğiniz öğeyi sıfır tabanlı dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]  
  
##  <a name="drawitem"></a>  CHeaderCtrl::DrawItem  
 Bir sahip çizim üstbilgi denetim değişikliklerini visual yönünü zaman çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDrawItemStruct`  
 Bir işaretçi bir [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) şekilde öğesi açıklayan yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 **İtemAction** üyesi `DRAWITEMSTRUCT` yapısı gerçekleştirilecek çizim eylemi tanımlar.  
  
 Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Çizim sahibi çizim için uygulamak için bu üye işlevi geçersiz kılma `CHeaderCtrl` nesnesi.  
  
 Tüm grafik cihaz arabirimi (GDI) nesneleri görüntüleme bağlamı içinde sağlanan için seçilen uygulama kurtarmalısınız `lpDrawItemStruct` önce bu üye fonksiyonu sonlandırır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]  
  
##  <a name="editfilter"></a>  CHeaderCtrl::EditFilter  
 Üstbilgi denetimi belirtilen filtre düzenleme yapmaya başlar.  
  
```  
BOOL EditFilter(
    int nColumn,  
    BOOL bDiscardChanges);
```  
  
### <a name="parameters"></a>Parametreler  
 `nColumn`  
 Düzenlemek için sütun.  
  
 `bDiscardChanges`  
 Kullanıcı filtresi düzenleme sürecinde ise kullanıcı ne yapılacağını belirten bir değer düzenleme değişiklikleri zaman [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312) ileti gönderilir.  
  
 Belirtin `true` kullanıcı tarafından yapılan değişiklikleri atmak için veya `false` kullanıcı tarafından yapılan değişiklikleri kabul etmek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem Win32 iletisinin davranışını uygulayan [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]  
  
##  <a name="getbitmapmargin"></a>  CHeaderCtrl::GetBitmapMargin  
 Üstbilgi denetimindeki bir bit eşlem kenar genişliğini alır.  
  
```  
int GetBitmapMargin() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit eşlem kenar boşluğunu piksel cinsinden genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [HDM_GETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775314), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]  
  
##  <a name="getfocuseditem"></a>  CHeaderCtrl::GetFocusedItem  
 Geçerli üstbilgi denetimindeki odağa sahip öğenin dizinini alır.  
  
```  
int GetFocusedItem() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Odaklanmış üstbilgi öğesinin sıfır tabanlı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [HDM_GETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775330) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_headerCtrl`, yani geçerli üstbilgi denetimi erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde gösterilmektedir `SetFocusedItem` ve `GetFocusedItem` yöntemleri. Önceki kod bölümünde beş sütunlarla üstbilgi denetimi oluşturduk. Ancak, böylece sütun görünür değil sütun ayırıcı sürükleyebilirsiniz. Aşağıdaki örnek, ayarlar ve ardından son sütun başlığını odak öğesi olarak onaylar.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="getimagelist"></a>  CHeaderCtrl::GetImageList  
 Üstbilgi denetimindeki çizim üstbilgi öğeleri için kullanılan bir görüntü listesi işleyicisini alır.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [HDM_GETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775332), Windows SDK'ın açıklandığı gibi. `CImageList` Döndürülen işaretçi noktaları geçici bir nesne ve sonraki boşta kalma süresi işleme, silinen nesne.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]  
  
##  <a name="getitem"></a>  CHeaderCtrl::GetItem  
 Üstbilgi denetim öğesi ilgili bilgileri alır.  
  
```  
BOOL GetItem(
    int nPos,  
    HDITEM* pHeaderItem) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nPos`  
 Alınacak öğenin sıfır tabanlı dizini belirtir.  
  
 `pHeaderItem`  
 İşaretçi bir [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) yapısı yeni öğesini alır. Bu yapı kullanılır `InsertItem` ve `SetItem` üye işlevleri. Herhangi bir bayrağı kümesinde **maskesi** öğesi olun karşılık gelen öğeleri değerleri düzgün return doldurulduğundan. Varsa **maskesi** öğesi sıfır olarak ayarlandığında, diğer yapı öğeleri değerler anlamsız.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]  
  
##  <a name="getitemcount"></a>  CHeaderCtrl::GetItemCount  
 Üstbilgi denetimindeki öğeleri sayısını alır.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üstbilgi denetim öğeleri başarılı olursa sayısı; Aksi takdirde - 1.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CHeaderCtrl::DeleteItem](#deleteitem).  
  
##  <a name="getitemdropdownrect"></a>  CHeaderCtrl::GetItemDropDownRect  
 Geçerli üstbilgi denetimindeki üstbilgi öğesi için açılan düğmesine sınırlayıcı dikdörtgenini alır.  
  
```  
BOOL GetItemDropDownRect(
    int iItem,   
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `iItem`|Stilini olduğu üstbilgi öğesinin sıfır tabanlı dizin `HDF_SPLITBUTTON`. Daha fazla bilgi için bkz: `fmt` üyesi [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) yapısı.|  
|[out] `lpRect`|İşaretçi bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) sınırlayıcı dikdörtgen bilgilerini almak için yapısı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Bu işlev başarılıysa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [HDM_GETITEMDROPDOWNRECT](http://msdn.microsoft.com/library/windows/desktop/bb775339) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_headerCtrl`, yani geçerli üstbilgi denetimi erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde gösterilmektedir `GetItemDropDownRect` yöntemi. Önceki kod bölümünde beş sütunlarla üstbilgi denetimi oluşturduk. Aşağıdaki kod örneğinde 3B dikdörtgen konum üstbilgisi açılan düğmesine için ayrılmış ilk sütun alır.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]  
  
##  <a name="getitemrect"></a>  CHeaderCtrl::GetItemRect  
 Üstbilgi denetimindeki belirli bir öğe için sınırlayıcı dikdörtgenini alır.  
  
```  
BOOL GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Üstbilgi denetimi öğesinin sıfır tabanlı dizini.  
  
 `lpRect`  
 Adresine bir işaretçi bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı sınırlayıcı dikdörtgen bilgilerini alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem Win32 iletisinin davranışını uygulayan [HDM_GETITEMRECT](http://msdn.microsoft.com/library/windows/desktop/bb775341), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="getorderarray"></a>  CHeaderCtrl::GetOrderArray  
 Üstbilgi denetimindeki öğeleri soldan sağa sırasını alır.  
  
```  
BOOL GetOrderArray(
    LPINT piArray,  
    int iCount);
```  
  
### <a name="parameters"></a>Parametreler  
 `piArray`  
 Üstbilgi denetimindeki soldan sağa göründükleri sırada öğelerinin dizin değerini alan bir arabellek adresini gösteren bir işaretçi.  
  
 `iCount`  
 Üstbilgi denetim öğeleri sayısı. Negatif olmalıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [HDM_GETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775343), Windows SDK'ın açıklandığı gibi. Üstbilgi öğesi sıralama desteklemek için sağlanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]  
  
##  <a name="getoverflowrect"></a>  CHeaderCtrl::GetOverflowRect  
 Geçerli üstbilgi denetimi taşma düğmesinin sınırlayıcı dikdörtgenini alır.  
  
```  
BOOL GetOverflowRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[out] `lpRect`|İşaretçi bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı sınırlayıcı dikdörtgen bilgilerini alır.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Bu işlev başarılıysa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Üstbilgi denetimi aynı anda görüntülenebilenden daha fazla öğe içeriyorsa, denetim kayan taşma düğmesini görünür olmayan öğeler görüntüleyebilirsiniz. Üstbilgi denetimi olmalıdır `HDS_OVERFLOW` ve `HDF_SPLITBUTTON` taşma düğmesini görüntülemek için stilleri. Sınırlayıcı dikdörtgenini taşma düğmesini alır ve yalnızca taşma düğmesini görüntülendiğinde bulunmaktadır. Daha fazla bilgi için bkz: [üstbilgi denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775241).  
  
 Bu yöntem gönderir [HDM_GETOVERFLOWRECT](http://msdn.microsoft.com/library/windows/desktop/bb775345) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_headerCtrl`, yani geçerli üstbilgi denetimi erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde gösterilmektedir `GetOverflowRect` yöntemi. Önceki kod bölümünde beş sütunlarla üstbilgi denetimi oluşturduk. Ancak, böylece sütun görünür değil sütun ayırıcı sürükleyebilirsiniz. Bazı sütunları görünür değilse, üstbilgi denetimi taşma düğmesini çizer. Aşağıdaki kod örneğinde taşma düğmesini konumunu 3B bir dikdörtgen çizer.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]  
  
##  <a name="hittest"></a>  CHeaderCtrl::HitTest  
 Hangi üstbilgi öğesi, varsa, belirli bir noktada bulunduğunu belirler.  
  
```  
int HitTest(LPHDHITTESTINFO* phdhti);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[içinde out] `phdhti`|İşaretçi bir [HDHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb775245) test etmek için noktasını belirtir ve test sonuçlarını alan yapısı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üstbilgi öğesi, varsa, belirli bir konumda sıfır tabanlı dizini; Aksi durumda, -1.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [HDM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb775349) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_headerCtrl`, yani geçerli üstbilgi denetimi erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde gösterilmektedir `HitTest` yöntemi. Bu kod örneği önceki bölümünde, beş sütunlarla üstbilgi denetimi oluşturduk. Ancak, böylece sütun görünür değil sütun ayırıcı sürükleyebilirsiniz. Bu örnek görünür durumdaysa sütun dizini raporları ve sütun görünmüyorsa -1.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]  
  
##  <a name="insertitem"></a>  CHeaderCtrl::InsertItem  
 Belirtilen dizindeki üstbilgi denetimine yeni bir öğe ekler.  
  
```  
int InsertItem(
    int nPos,  
    HDITEM* phdi);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPos`  
 Eklenecek öğenin sıfır tabanlı dizini. Değerin sıfır ise, öğenin üstbilgi denetimi başında eklenir. Değeri en yüksek değerden daha büyükse, öğe üstbilgi denetimi sonuna eklenir.  
  
 *phdi*  
 İşaretçi bir [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) eklenecek öğe hakkında bilgi içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa yeni öğenin dizini; Aksi takdirde - 1.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]  
  
##  <a name="layout"></a>  CHeaderCtrl::Layout  
 Boyut ve belirli bir dikdörtgen üstbilgi denetimine konumunu alır.  
  
```  
BOOL Layout(HDLAYOUT* pHeaderLayout);
```  
  
### <a name="parameters"></a>Parametreler  
 *pHeaderLayout*  
 İşaretçi bir [HDLAYOUT](http://msdn.microsoft.com/library/windows/desktop/bb775249) yapısını üstbilgi denetiminin konumunu ve boyutunu ayarlamak için kullanılan bilgileri içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, verilen dikdörtgen kaplar için yeni bir üstbilgi denetimi için uygun boyutları belirlemek için kullanılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]  
  
##  <a name="ordertoindex"></a>  CHeaderCtrl::OrderToIndex  
 Üstbilgi denetimi kendi sırayla temel alınarak bir öğenin dizini değerini alır.  
  
```  
int OrderToIndex(int nOrder) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nOrder*  
 Soldan sağa üstbilgi denetimine öğe görünür sıfır tabanlı sıra.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üstbilgi denetimi kendi sırasına göre öğenin dizini. Dizin soldan sağa, 0 ile başlayan sayar.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 makrosu davranışını uygulayan [HDM_ORDERTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb775355), Windows SDK'ın açıklandığı gibi. Üstbilgi öğesi sıralama desteklemek için sağlanır.  
  
##  <a name="setbitmapmargin"></a>  CHeaderCtrl::SetBitmapMargin  
 Üstbilgi denetimindeki bir bit eşlem kenar genişliğini ayarlar.  
  
```  
int SetBitmapMargin(int nWidth);
```  
  
### <a name="parameters"></a>Parametreler  
 `nWidth`  
 Varolan bir üstbilgi denetimi içinde bir bit eşlem çevreleyen kenar boşluğu piksel cinsinden belirtilen genişlik.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit eşlem kenar boşluğunu piksel cinsinden genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [HDM_SETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775357), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]  
  
##  <a name="setfilterchangetimeout"></a>  CHeaderCtrl::SetFilterChangeTimeout  
 Bir değişiklik filtre öznitelikleri yerinde süresini deftere arasındaki zaman aşımı aralığı ayarlar bir [HDN_FILTERCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb775277) bildirim.  
  
```  
int SetFilterChangeTimeout(DWORD dwTimeOut);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwTimeOut*  
 Milisaniye cinsinden zaman aşımı değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değiştirilen filtre denetimi dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [HDM_SETFILTERCHANGETIMEOUT](http://msdn.microsoft.com/library/windows/desktop/bb775359), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]  
  
##  <a name="setfocuseditem"></a>  CHeaderCtrl::SetFocusedItem  
 Geçerli üstbilgi denetimindeki belirtilen üstbilgi öğesine odağı ayarlar.  
  
```  
BOOL SetFocusedItem(int iItem);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `iItem`|Üstbilgi öğesi sıfır tabanlı dizini.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [HDM_SETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775361) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_headerCtrl`, yani geçerli üstbilgi denetimi erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde gösterilmektedir `SetFocusedItem` ve `GetFocusedItem` yöntemleri. Önceki kod bölümünde beş sütunlarla üstbilgi denetimi oluşturduk. Ancak, böylece sütun görünür değil sütun ayırıcı sürükleyebilirsiniz. Aşağıdaki örnek, ayarlar ve ardından son sütun başlığını odak öğesi olarak onaylar.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="sethotdivider"></a>  CHeaderCtrl::SetHotDivider  
 Değişiklikleri el ile belirtmek için üstbilgi öğeleri arasındaki ayırıcıyı sürükleyin ve bir üstbilgi öğesinin bırak.  
  
```  
int SetHotDivider(CPoint pt);  
int SetHotDivider(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `pt`  
 İşaretçinin konumu. Üstbilgi denetimi işaretçinin konumuna göre uygun ayırıcı vurgular.  
  
 `nIndex`  
 Vurgulanan ayırıcı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Vurgulanan ayırıcı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [HDM_SETHOTDIVIDER](http://msdn.microsoft.com/library/windows/desktop/bb775363), Windows SDK'ın açıklandığı gibi. Üstbilgi öğesi sürükle ve bırak desteği sağlanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]  
  
##  <a name="setimagelist"></a>  CHeaderCtrl::SetImageList  
 Görüntü listesi bir üstbilgi denetimine atar.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parametreler  
 `pImageList`  
 Bir işaretçi bir `CImageList` üstbilgi denetimine atanan resim listesi içeren bir nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [Cımagelist](../../mfc/reference/cimagelist-class.md) daha önce üstbilgi denetimine atanan nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [HDM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775365), Windows SDK'ın açıklandığı gibi. `CImageList` Döndürülen işaretçi noktaları geçici bir nesne ve sonraki boşta kalma süresi işleme, silinen nesne.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CHeaderCtrl::GetImageList](#getimagelist).  
  
##  <a name="setitem"></a>  CHeaderCtrl::SetItem  
 Belirtilen öğe özniteliklerini üstbilgi denetimindeki ayarlar.  
  
```  
BOOL SetItem(
    int nPos,  
    HDITEM* pHeaderItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPos`  
 Yönetilebilmesini öğenin sıfır tabanlı dizini.  
  
 `pHeaderItem`  
 İşaretçi bir [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) yeni öğe hakkında bilgi içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CHeaderCtrl::GetItem](#getitem).  
  
##  <a name="setorderarray"></a>  CHeaderCtrl::SetOrderArray  
 Üstbilgi denetimindeki öğeleri soldan sağa sırasını ayarlar.  
  
```  
BOOL SetOrderArray(
    int iCount,  
    LPINT piArray);
```  
  
### <a name="parameters"></a>Parametreler  
 `iCount`  
 Üstbilgi denetim öğeleri sayısı.  
  
 `piArray`  
 Üstbilgi denetimindeki soldan sağa göründükleri sırada öğelerinin dizin değerini alan bir arabellek adresini gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 makrosu davranışını uygulayan [HDM_SETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775369), Windows SDK'ın açıklandığı gibi. Üstbilgi öğesi sıralama desteklemek için sağlanır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CHeaderCtrl::GetOrderArray](#getorderarray).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CTabCtrl sınıfı](../../mfc/reference/ctabctrl-class.md)   
 [CListCtrl sınıfı](../../mfc/reference/clistctrl-class.md)   
 [CImageList Sınıfı](../../mfc/reference/cimagelist-class.md)
