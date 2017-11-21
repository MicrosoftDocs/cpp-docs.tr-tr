---
title: "CTabCtrl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTabCtrl
- AFXCMN/CTabCtrl
- AFXCMN/CTabCtrl::CTabCtrl
- AFXCMN/CTabCtrl::AdjustRect
- AFXCMN/CTabCtrl::Create
- AFXCMN/CTabCtrl::CreateEx
- AFXCMN/CTabCtrl::DeleteAllItems
- AFXCMN/CTabCtrl::DeleteItem
- AFXCMN/CTabCtrl::DeselectAll
- AFXCMN/CTabCtrl::DrawItem
- AFXCMN/CTabCtrl::GetCurFocus
- AFXCMN/CTabCtrl::GetCurSel
- AFXCMN/CTabCtrl::GetExtendedStyle
- AFXCMN/CTabCtrl::GetImageList
- AFXCMN/CTabCtrl::GetItem
- AFXCMN/CTabCtrl::GetItemCount
- AFXCMN/CTabCtrl::GetItemRect
- AFXCMN/CTabCtrl::GetItemState
- AFXCMN/CTabCtrl::GetRowCount
- AFXCMN/CTabCtrl::GetToolTips
- AFXCMN/CTabCtrl::HighlightItem
- AFXCMN/CTabCtrl::HitTest
- AFXCMN/CTabCtrl::InsertItem
- AFXCMN/CTabCtrl::RemoveImage
- AFXCMN/CTabCtrl::SetCurFocus
- AFXCMN/CTabCtrl::SetCurSel
- AFXCMN/CTabCtrl::SetExtendedStyle
- AFXCMN/CTabCtrl::SetImageList
- AFXCMN/CTabCtrl::SetItem
- AFXCMN/CTabCtrl::SetItemExtra
- AFXCMN/CTabCtrl::SetItemSize
- AFXCMN/CTabCtrl::SetItemState
- AFXCMN/CTabCtrl::SetMinTabWidth
- AFXCMN/CTabCtrl::SetPadding
- AFXCMN/CTabCtrl::SetToolTips
dev_langs: C++
helpviewer_keywords:
- CTabCtrl [MFC], CTabCtrl
- CTabCtrl [MFC], AdjustRect
- CTabCtrl [MFC], Create
- CTabCtrl [MFC], CreateEx
- CTabCtrl [MFC], DeleteAllItems
- CTabCtrl [MFC], DeleteItem
- CTabCtrl [MFC], DeselectAll
- CTabCtrl [MFC], DrawItem
- CTabCtrl [MFC], GetCurFocus
- CTabCtrl [MFC], GetCurSel
- CTabCtrl [MFC], GetExtendedStyle
- CTabCtrl [MFC], GetImageList
- CTabCtrl [MFC], GetItem
- CTabCtrl [MFC], GetItemCount
- CTabCtrl [MFC], GetItemRect
- CTabCtrl [MFC], GetItemState
- CTabCtrl [MFC], GetRowCount
- CTabCtrl [MFC], GetToolTips
- CTabCtrl [MFC], HighlightItem
- CTabCtrl [MFC], HitTest
- CTabCtrl [MFC], InsertItem
- CTabCtrl [MFC], RemoveImage
- CTabCtrl [MFC], SetCurFocus
- CTabCtrl [MFC], SetCurSel
- CTabCtrl [MFC], SetExtendedStyle
- CTabCtrl [MFC], SetImageList
- CTabCtrl [MFC], SetItem
- CTabCtrl [MFC], SetItemExtra
- CTabCtrl [MFC], SetItemSize
- CTabCtrl [MFC], SetItemState
- CTabCtrl [MFC], SetMinTabWidth
- CTabCtrl [MFC], SetPadding
- CTabCtrl [MFC], SetToolTips
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e9720d407fb13b5a87335da08eb40c2886fdcdb3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ctabctrl-class"></a>CTabCtrl sınıfı
Windows ortak sekme denetimi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CTabCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTabCtrl::CTabCtrl](#ctabctrl)|Oluşturan bir `CTabCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTabCtrl::AdjustRect](#adjustrect)|Sekme denetimi görüntüleme alanı Pencere dikdörtgeni verilen hesaplar veya belirtilen görüntü alanına karşılık gelir Pencere dikdörtgeni hesaplar.|  
|[CTabCtrl::Create](#create)|Sekme denetimi oluşturur ve bunları bir örneğine ekler bir `CTabCtrl` nesnesi.|  
|[CTabCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri sekme denetimi oluşturur ve bir örneğine iliştirir bir `CTabCtrl` nesnesi.|  
|[CTabCtrl::DeleteAllItems](#deleteallitems)|Sekme denetimi tüm öğeleri kaldırır.|  
|[CTabCtrl::DeleteItem](#deleteitem)|Bir öğeyi sekmesini denetimden kaldırır.|  
|[CTabCtrl::DeselectAll](#deselectall)|Temizleme basılmış herhangi bir sekme denetimi öğelerde sıfırlar.|  
|[CTabCtrl::DrawItem](#drawitem)|Belirtilen öğe bir sekme denetimi çizer.|  
|[CTabCtrl::GetCurFocus](#getcurfocus)|Sekme denetimi geçerli odağa sahip sekmesini alır.|  
|[CTabCtrl::GetCurSel](#getcursel)|Sekme denetimi şu anda seçili sekmede belirler.|  
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|Sekme denetimi için kullanılan genişletilmiş stili alır.|  
|[CTabCtrl::GetImageList](#getimagelist)|Sekme denetimiyle ilişkili resim listesi alır.|  
|[CTabCtrl::GetItem](#getitem)|Sekme denetimi bir sekmede ilgili bilgileri alır.|  
|[CTabCtrl::GetItemCount](#getitemcount)|Sekme denetimine sekmeler sayısını alır.|  
|[CTabCtrl::GetItemRect](#getitemrect)|Sekme denetimi bir sekmede için sınırlayıcı dikdörtgenini alır.|  
|[CTabCtrl::GetItemState](#getitemstate)|Belirtilen sekme denetimi öğesi durumunu alır.|  
|[CTabCtrl::GetRowCount](#getrowcount)|Sekme denetimine sekmeler satır geçerli sayısını alır.|  
|[CTabCtrl::GetToolTips](#gettooltips)|Sekme denetimiyle ilişkili araç ipucunu denetimini işleyicisini alır.|  
|[CTabCtrl::HighlightItem](#highlightitem)|Sekme öğesi Vurgu durumunu ayarlar.|  
|[CTabCtrl::HitTest](#hittest)|Hangi sekmeyi varsa, belirtilen ekran konumunda belirler.|  
|[CTabCtrl::InsertItem](#insertitem)|Yeni bir sekme içinde Sekme denetimini ekler.|  
|[CTabCtrl::RemoveImage](#removeimage)|Görüntüyü bir sekme denetimi görüntü listesinden kaldırır.|  
|[CTabCtrl::SetCurFocus](#setcurfocus)|Sekme denetimi içinde belirtilen bir sekmeye odağı ayarlar.|  
|[CTabCtrl::SetCurSel](#setcursel)|Sekme bir sekme denetimi seçer.|  
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|Sekme denetimi için genişletilmiş stiller ayarlar.|  
|[CTabCtrl::SetImageList](#setimagelist)|Görüntü listesi Sekme denetimine atar.|  
|[CTabCtrl::SetItem](#setitem)|Bazılarını veya tümünü bir sekmenin öznitelikleri ayarlar.|  
|[CTabCtrl::SetItemExtra](#setitemextra)|Sekme denetimi uygulama tanımlı verilerde ayrılmış sekmesini başına bayt sayısını ayarlar.|  
|[CTabCtrl::SetItemSize](#setitemsize)|Öğenin yüksekliğini ve genişliğini ayarlar.|  
|[CTabCtrl::SetItemState](#setitemstate)|Belirtilen sekme denetimi öğesi durumunu ayarlar.|  
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|En küçük genişliği öğelerinin bir sekme denetimi ayarlar.|  
|[CTabCtrl::SetPadding](#setpadding)|(Her sekmenin simgesini ve sekme denetimi etiketinde etrafında doldurma) alan miktarını belirler.|  
|[CTabCtrl::SetToolTips](#settooltips)|Bir araç ipucunu denetimini Sekme denetimine atar.|  
  
## <a name="remarks"></a>Açıklamalar  
 "Sekme denetimi" Bölücü bir dizüstü bilgisayarın veya bir dosya dolabı etiketler benzerdir. Sekme denetimi kullanarak, bir uygulama penceresi veya iletişim kutusu aynı alanı için birden çok sayfa tanımlayabilirsiniz. Her bir sayfa bilgi veya bir uygulamanın kullanıcı ilgili sekmeyi seçtiğinde görüntüleyen denetim grubu kümesinden oluşur. Sekme denetimi özel bir tür düğmeleri gibi ara sekmeleri görüntüler. Bir düğmeye tıklanması hemen bir sayfa görüntüleme yerine bir komut gerçekleştirmeniz gerekir.  
  
 Bu denetim (ve bu nedenle `CTabCtrl` sınıfı) yalnızca Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programları için kullanılabilir ve üzerinde desteklenir.  
  
 Kullanma hakkında daha fazla bilgi için `CTabCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak CTabCtrl](../../mfc/using-ctabctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTabCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="adjustrect"></a>CTabCtrl::AdjustRect  
 Sekme denetimi görüntüleme alanı Pencere dikdörtgeni verilen hesaplar veya belirtilen görüntü alanına karşılık gelir Pencere dikdörtgeni hesaplar.  
  
```  
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parametreler  
 `bLarger`  
 Hangi işlemin gerçekleştirileceğini gösterir. Bu parametre ise **TRUE**, `lpRect` bir görüntü dikdörtgen belirtir ve karşılık gelen Pencere dikdörtgeni alır. Bu parametre ise **FALSE**, `lpRect` Pencere dikdörtgeni belirtir ve karşılık gelen görüntü dikdörtgen alır.  
  
 `lpRect`  
 İşaretçi bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) verilen dikdörtgen belirtir ve hesaplanan dikdörtgen alan yapısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]  
  
##  <a name="create"></a>CTabCtrl::Create  
 Sekme denetimi oluşturur ve bunları bir örneğine ekler bir `CTabCtrl` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Sekme denetiminin stilini belirtir. Herhangi bir bileşimini uygulamak [sekmesinde denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760549), Windows SDK'sındaki açıklanmıştır. Bkz: **açıklamalar** denetime de uygulayabilirsiniz pencere stilleri listesi.  
  
 `rect`  
 Sekme denetiminin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı.  
  
 `pParentWnd`  
 Sekme denetiminin ana penceresinde, genellikle belirtir bir `CDialog`. Değil olmalıdır **NULL**.  
  
 `nID`  
 Sekme denetiminin kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** nesnesinin başlatma olduysa başarılıysa **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CTabCtrl` iki adımda nesne. İlk olarak, Oluşturucusu arayın ve sonra çağırın **oluşturma**, sekme denetimi oluşturur ve ekler `CTabCtrl` nesnesi.  
  
 Sekme denetim stilleri ek olarak, aşağıdaki pencere stilleri Sekme denetimine uygulayabilirsiniz:  
  
- **WS_CHILD** Sekme denetimini temsil eden alt pencere oluşturur. Kullanılamaz `WS_POPUP` stili.  
  
- **Ws_vısıble** başlangıçta görünür bir sekme denetimi oluşturur.  
  
- **Ws_dısabled** başlangıçta devre dışı bir pencere oluşturur.  
  
- **WS_GROUP** denetimleri içinde kullanıcı taşıyabilirsiniz bir denetimden yanındaki ok tuşlarını kullanarak grubunun ilk denetim belirtir. İle tanımlanmış tüm denetimler **WS_GROUP** ilk denetim ait sonra aynı gruba stili. Sonraki denetimiyle **WS_GROUP** stili Stil grubu sona erer ve sonraki grubu (sonraki başladığı diğer bir deyişle, bir grup uçları) başlatır.  
  
- **WS_TABSTOP** belirtir herhangi bir sayı birini üzerinden kullanıcı taşımak için SEKME tuşunu kullanarak denetimlerin. Sekme tuşuna kullanıcı tarafından belirtilen bir sonraki denetime gider **WS_TABSTOP** stili.  
  
 Genişletilmiş pencere stilleri ile sekme denetimi oluşturma çağrısı [CTabCtrl::CreateEx](#createex) yerine **oluşturma**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]  
  
##  <a name="createex"></a>CTabCtrl::CreateEx  
 Bir denetimi (alt pencere) oluşturur ve bunu ile ilişkilendirir `CTabCtrl` nesnesi.  
  
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
 Sekme denetiminin stilini belirtir. Herhangi bir bileşimini uygulamak [sekmesinde denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760549), Windows SDK'sındaki açıklanmıştır. Bkz: **açıklamalar** içinde [Oluştur](#create) denetime de uygulayabilirsiniz pencere stilleri listesi.  
  
 `rect`  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) boyutunu ve konumunu, istemci koordinatları oluşturulacak penceresinin açıklayan yapısı `pParentWnd`.  
  
 `pParentWnd`  
 Denetimin üst penceresi için bir işaretçi.  
  
 `nID`  
 Denetimin alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır değilse 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine [oluşturma](#create) Windows genişletilmiş stili önsöz tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için **WS_EX_**.  
  
 `CreateEx`Denetim tarafından belirtilen Genişletilmiş Windows stillerini oluşturur `dwExStyle`. Stil kullanarak bir denetimi belirli genişletilmiş kümesi [SetExtendedStyle](#setextendedstyle). Örneğin, `CreateEx` böyle stilleri olarak ayarlamak için **WS_EX_CONTEXTHELP**, ancak `SetExtendedStyle` böyle stilleri olarak ayarlamak için **TCS_EX_FLATSEPARATORS**. Daha fazla bilgi için bkz. bölümünde açıklanan stilleri [sekme denetimi genişletilmiş stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760546) Windows SDK.  
  
##  <a name="ctabctrl"></a>CTabCtrl::CTabCtrl  
 Oluşturan bir `CTabCtrl` nesnesi.  
  
```  
CTabCtrl();
```  
  
##  <a name="deleteallitems"></a>CTabCtrl::DeleteAllItems  
 Sekme denetimi tüm öğeleri kaldırır.  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="deleteitem"></a>CTabCtrl::DeleteItem  
 Belirtilen öğe bir sekme denetimden kaldırır.  
  
```  
BOOL DeleteItem(int nItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `nItem`  
 Silinecek öğenin sıfır tabanlı değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]  
  
##  <a name="deselectall"></a>CTabCtrl::DeselectAll  
 Temizleme basılmış herhangi bir sekme denetimi öğelerde sıfırlar.  
  
```  
void DeselectAll(BOOL fExcludeFocus);
```  
  
### <a name="parameters"></a>Parametreler  
 *fExcludeFocus*  
 Öğe deselection kapsamını belirten bayrak. Bu parametre ayarlanmışsa **yanlış**, tüm sekmesini düğmeleri sıfırlanır. Bu ayarlanırsa **TRUE**, sonra da şu anda seçili biri hariç tüm sekme öğeleri sıfırlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TCM_DESELECTALL](http://msdn.microsoft.com/library/windows/desktop/bb760579), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="drawitem"></a>CTabCtrl::DrawItem  
 Bir sahip çizim sekme denetimi değişiklikleri visual yönünü zaman çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDrawItemStruct`  
 Bir işaretçi bir [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) şekilde öğesi açıklayan yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 **İtemAction** üyesi `DRAWITEMSTRUCT` yapısı gerçekleştirilecek çizim eylemi tanımlar.  
  
 Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Çizim sahibi çizim için uygulamak için bu üye işlevi geçersiz kılma `CTabCtrl` nesnesi.  
  
 Tüm grafik cihaz arabirimi (GDI) nesneleri görüntüleme bağlamı içinde sağlanan için seçilen uygulama kurtarmalısınız `lpDrawItemStruct` önce bu üye fonksiyonu sonlandırır.  
  
##  <a name="getcurfocus"></a>CTabCtrl::GetCurFocus  
 Geçerli odağa sahip sekmesini dizinini alır.  
  
```  
int GetCurFocus() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli odağa sahip sekmesini sıfır tabanlı dizini.  
  
##  <a name="getcursel"></a>CTabCtrl::GetCurSel  
 Sekme denetimi şu anda seçili sekmede alır.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa seçili sekme veya - 1 hiçbir sekmesi seçili olduğunda sıfır tabanlı dizini.  
  
##  <a name="getextendedstyle"></a>CTabCtrl::GetExtendedStyle  
 Sekme denetimi için kullanılan genişletilmiş stili alır.  
  
```  
DWORD GetExtendedStyle();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sekme denetimi için kullanılmakta genişletilmiş stilleri temsil eder. Bu değer birleşimidir [sekmesinde stilleri genişletilmiş denetim](http://msdn.microsoft.com/library/windows/desktop/bb760546), Windows SDK'ın açıklandığı gibi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TCM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760585), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="getimagelist"></a>CTabCtrl::GetImageList  
 Sekme denetimiyle ilişkili resim listesi alır.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, sekmenin resim listesi için bir işaretçi kontrol; Aksi takdirde, **NULL**.  
  
##  <a name="getitem"></a>CTabCtrl::GetItem  
 Sekme denetimi bir sekmede ilgili bilgileri alır.  
  
```  
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nItem`  
 Sekme sıfır tabanlı dizini.  
  
 `pTabCtrlItem`  
 İşaretçi bir [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) yapısı, almak için bilgileri belirtmek için kullanılır. Sekme hakkında bilgi almak için de kullanılır. Bu yapı kullanılır `InsertItem`, `GetItem`, ve `SetItem` üye işlevleri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılıysa; **FALSE** Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 İleti gönderildiğinde **maskesi** üye hangi özniteliklerin döndürüleceğini belirtir. Varsa **maskesi** üye belirtir `TCIF_TEXT` değeri **pszText** üye öğesi metni alır arabellek adresi içermesi gerekir ve **cchTextMax** üye arabellek boyutu belirtmeniz gerekir.  
  
 **maskesi**  
 Hangi belirten değeri `TCITEM` Yapı üyeleri alınamıyor veya ayarlanamıyor. Bu üye, sıfır veya bir bileşimiyle aşağıdaki değerlerden biri olabilir:  
  
- `TCIF_TEXT`**PszText** üye geçerlidir.  
  
- `TCIF_IMAGE``iImage` Üye geçerlidir.  
  
- `TCIF_PARAM`**LParam** üye geçerlidir.  
  
- `TCIF_RTLREADING`Metnin **pszText** İbranice veya Arapça sistemlerinde sağdan sola okuma sırası kullanılarak görüntülenir.  
  
- `TCIF_STATE`**DwState** üye geçerlidir.  
  
 **pszText**  
 Yapısı bir sekmesi hakkında bilgi içeriyorsa sekme metni içeren null ile sonlandırılmış bir dize işaretçi. Yapı bilgileri alıyorsa, bu üye sekmesini metni alır arabellek adresini belirtir.  
  
 **cchTextMax**  
 Tarafından için arabellek boyutu işaret **pszText**. Bu üye yapısı bilgileri almıyor yoksayılır.  
  
 `iImage`  
 Sekme için hiçbir resim ise sekme denetimi resim listesi veya 1 - dizin.  
  
 **lParam**  
 Sekme ile ilişkili uygulama tanımlı veriler. Uygulama tanımlı veri sekmesi başına dört bayttan fazla varsa, uygulamanın bir yapı tanımlamak ve bunun yerine kullanmanız gerekir `TCITEM` yapısı. Uygulama tanımlı yapısı ilk üyesi olmalıdır bir [TCITEMHEADER](http://msdn.microsoft.com/library/windows/desktop/bb760556)yapısı. **TCITEMHEADER** yapısı aynıdır `TCITEM` yapısı, olmadan **lParam** üyesi. Yapınızı boyutunu ve boyutu arasındaki fark **TCITEMHEADER** yapısı sekmesi başına fazladan bayt sayısını eşit.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]  
  
##  <a name="getitemcount"></a>CTabCtrl::GetItemCount  
 Sekme denetimine sekmeler sayısını alır.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sekme denetimi öğelerin sayısı.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="getitemrect"></a>CTabCtrl::GetItemRect  
 Sekme denetimi belirtilen sekmede için sınırlayıcı dikdörtgenini alır.  
  
```  
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nItem`  
 Sekme öğesi sıfır tabanlı dizini.  
  
 `lpRect`  
 İşaretçi bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) sekmenin sınırlayıcı dikdörtgenini alır yapısı. Bu koordinatları görünüm penceresinin'ın geçerli eşleme modunu kullanın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="getitemstate"></a>CTabCtrl::GetItemState  
 Sekme denetim öğesi tarafından tanımlanan durumunu alır `nItem`.  
  
```  
DWORD GetItemState(
    int nItem,  
    DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nItem`  
 Durum bilgilerini almak üzere öğenin sıfır tabanlı dizin numarası.  
  
 `dwMask`  
 Maske, öğenin durumu döndürülecek bayrakları belirtme. Maske üyesi değerlerinin listesi için bkz: [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) , Windows SDK'ın açıklandığı gibi yapılandırın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru bir `DWORD` durum bilgilerini alma değeri. Aşağıdaki değerlerden biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|Sekme denetim öğesi seçilir.|  
|**TCIS_HIGHLIGHTED**|Sekme denetim öğesi vurgulanır ve sekmesi ve metin geçerli vurgulama renk kullanarak çizilir. Vurgulama renk kullanırken, bu bir Titremeli renk doğru bir ilişkilendirme olacaktır.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğenin durumu tarafından belirtilen **dwState** üyesi `TCITEM` yapısı.  
  
##  <a name="getrowcount"></a>CTabCtrl::GetRowCount  
 Geçerli sekme denetiminde satır sayısını alır.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sekme denetimine sekmeler satırların sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca sahip denetimlerin sekme **TCS_MULTILINE** stili sekmelerinin birden çok satır sahip olabilir.  
  
##  <a name="gettooltips"></a>CTabCtrl::GetToolTips  
 Sekme denetimiyle ilişkili araç ipucunu denetimini işleyicisini alır.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araç İpucu denetimi başarılı olursa tanıtıcısı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa bir sekme denetimi bir araç ipucunu denetimini oluşturur **TCS_TOOLTIPS** stili. Kullanarak bir sekme denetimi için bir araç ipucunu denetimini atayabilirsiniz `SetToolTips` üye işlevi.  
  
##  <a name="highlightitem"></a>CTabCtrl::HighlightItem  
 Sekme öğesi Vurgu durumunu ayarlar.  
  
```  
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `idItem`  
 Sekme denetim öğesi sıfır tabanlı dizini.  
  
 `fHighlight`  
 Ayarlanacak Vurgu durumunu belirten değer. Bu değer ise **TRUE**, sekme; varsa vurgulanır **yanlış**, sekmesindeki varsayılan durumuna ayarlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti uygulayan [TCM_HIGHLIGHTITEM](http://msdn.microsoft.com/library/windows/desktop/bb760602), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="hittest"></a>CTabCtrl::HitTest  
 Hangi sekmeyi varsa, belirtilen ekran konumunda belirler.  
  
```  
int HitTest(TCHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pHitTestInfo`  
 İşaretçi bir [TCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760553) test etmek için ekran konumunu belirten Windows SDK içinde açıklandığı gibi yapılandırın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sekme belirtilen konumda sıfır tabanlı dizini sekme veya - 1 döndürür.  
  
##  <a name="insertitem"></a>CTabCtrl::InsertItem  
 Yeni bir sekme içinde varolan bir sekme denetimini ekler.  
  
```  
LONG InsertItem(
    int nItem,
    TCITEM* pTabCtrlItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem,
    int nImage);

 
LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam);

 
LONG InsertItem(
    UINT nMask,  
    int nItem,  
    LPCTSTR lpszItem,  
    int nImage,  
    LPARAM lParam,  
    DWORD dwState,  
    DWORD dwStateMask);
```  
  
### <a name="parameters"></a>Parametreler  
 `nItem`  
 Yeni sekmede sıfır tabanlı dizini.  
  
 `pTabCtrlItem`  
 İşaretçi bir [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) sekmesini özniteliklerini belirtir yapısı.  
  
 `lpszItem`  
 Sekmenin metin içeren bir null ile sonlandırılmış dize adresidir.  
  
 `nImage`  
 Resim listesinden resim eklemek için bir görüntü sıfır tabanlı dizini.  
  
 `nMask`  
 Belirten `TCITEM` yapısı ayarlamak için öznitelikler. Sıfır veya bir birleşimi aşağıdaki değerlerden biri olabilir:  
  
- `TCIF_TEXT`**PszText** üye geçerlidir.  
  
- `TCIF_IMAGE``iImage` Üye geçerlidir.  
  
- `TCIF_PARAM`**LParam** üye geçerlidir.  
  
- `TCIF_RTLREADING`Metnin **pszText** İbranice veya Arapça sistemlerinde sağdan sola okuma sırası kullanılarak görüntülenir.  
  
- `TCIF_STATE`**DwState** üye geçerlidir.  
  
 `lParam`  
 Sekme ile ilişkili uygulama tanımlı veriler.  
  
 `dwState`  
 Öğenin durumlar için değerler belirtir. Daha fazla bilgi için bkz: [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Windows SDK'sındaki.  
  
 *dwStateMask*  
 Hangi durumları için ayarlanacak belirtir. Daha fazla bilgi için bkz: [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Windows SDK'sındaki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni bir sekme başarılıysa sıfır tabanlı dizini; Aksi takdirde - 1.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]  
  
##  <a name="removeimage"></a>CTabCtrl::RemoveImage  
 Belirtilen görüntü sekmesini denetimin görüntü listesinden kaldırır.  
  
```  
void RemoveImage(int nImage);
```  
  
### <a name="parameters"></a>Parametreler  
 `nImage`  
 Görüntünün kaldırmak için sıfır tabanlı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Her sekme aynı görüntüsüyle ilişkili kalmayacak şekilde sekme denetimi her sekmenin görüntü dizini güncelleştirir.  
  
##  <a name="setcurfocus"></a>CTabCtrl::SetCurFocus  
 Sekme denetimi içinde belirtilen bir sekmeye odağı ayarlar.  
  
```  
void SetCurFocus(int nItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `nItem`  
 Odağı alır sekmesini dizinini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TCM_SETCURFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb760610), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="setcursel"></a>CTabCtrl::SetCurSel  
 Sekme bir sekme denetimi seçer.  
  
```  
int SetCurSel(int nItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `nItem`  
 Seçilecek öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, daha önce seçilen sekmenin sıfır tabanlı dizin yoksa - 1.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekme denetimi göndermemek bir **TCN_SELCHANGING** veya **TCN_SELCHANGE** bu işlevini kullanarak bir sekme seçildiğinde bildirim iletisi. Bu bildirimler, kullanılarak gönderilen **wm_notıfy**, kullanıcı tıklattığında ya da sekmeler değiştirmek için klavyeyi kullanır.  
  
##  <a name="setextendedstyle"></a>CTabCtrl::SetExtendedStyle  
 Sekme denetimi için genişletilmiş stiller ayarlar.  
  
```  
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwNewStyle`  
 Sekme bileşimini belirten değeri genişletilmiş stilleri kontrol eder.  
  
 `dwExMask`  
 A `DWORD` hangi stillerde gösteren değer `dwNewStyle` etkilenecek üzeresiniz. Yalnızca genişletilmiş stillerde `dwExMask` değiştirilecek. Diğer tüm stilleri olarak korunur. Bu parametre sıfır sonra tüm stillerde ise `dwNewStyle` etkilenecek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `DWORD` önceki içeren değer [sekmesinde stilleri genişletilmiş denetim](http://msdn.microsoft.com/library/windows/desktop/bb760546), Windows SDK'ın açıklandığı gibi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TCM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760627), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="setimagelist"></a>CTabCtrl::SetImageList  
 Görüntü listesi Sekme denetimine atar.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parametreler  
 `pImageList`  
 Sekme denetimine atanan resim listesi işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki resim listesi bir işaretçi döndürür veya **NULL** önceki bir resim listesi ise.  
  
##  <a name="setitem"></a>CTabCtrl::SetItem  
 Bazılarını veya tümünü bir sekmenin öznitelikleri ayarlar.  
  
```  
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `nItem`  
 Öğenin sıfır tabanlı dizini.  
  
 `pTabCtrlItem`  
 İşaretçi bir [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) yeni öğesi özniteliklerini içeren yapısı. **Maskesi** üye ayarlamak için hangi özniteliklerin belirtir. Varsa **maskesi** üye belirtir `TCIF_TEXT` değeri **pszText** üyesi null sonlandırılmış bir dize adresidir ve **cchTextMax** üye göz ardı edilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [GetItem](#getitem).  
  
##  <a name="setitemextra"></a>CTabCtrl::SetItemExtra  
 Sekme denetimi uygulama tanımlı verilerde ayrılmış sekmesini başına bayt sayısını ayarlar.  
  
```  
BOOL SetItemExtra(int nBytes);
```  
  
### <a name="parameters"></a>Parametreler  
 `nBytes`  
 Ayarlamak için ek bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TCM_SETITEMEXTRA](http://msdn.microsoft.com/library/windows/desktop/bb760633), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="setitemsize"></a>CTabCtrl::SetItemSize  
 Genişlik ve yükseklik sekme denetimi öğelerinin ayarlar.  
  
```  
CSize SetItemSize(CSize size);
```  
  
### <a name="parameters"></a>Parametreler  
 `size`  
 Yeni genişlik ve yükseklik piksel cinsinden sekme denetim öğeleri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eski genişlik ve yükseklik sekmesi denetim öğeleri döndürür.  
  
##  <a name="setitemstate"></a>CTabCtrl::SetItemState  
 Sekme denetim öğesi tarafından tanımlanan durumunu ayarlar `nItem`.  
  
```  
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```  
  
### <a name="parameters"></a>Parametreler  
 `nItem`  
 Durum bilgisi ayarlanacak öğenin sıfır tabanlı dizin numarası.  
  
 `dwMask`  
 Maske, öğenin durumunu ayarlamak için bayrakları belirtme. Maske üyesi değerlerinin listesi için bkz: [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) , Windows SDK'ın açıklandığı gibi yapılandırın.  
  
 `dwState`  
 Bir başvuru bir `DWORD` durum bilgisi içeren değeri. Aşağıdaki değerlerden biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|Sekme denetim öğesi seçilir.|  
|**TCIS_HIGHLIGHTED**|Sekme denetim öğesi vurgulanır ve sekmesi ve metin geçerli vurgulama renk kullanarak çizilir. Vurgulama renk kullanırken, bu bir Titremeli renk doğru bir ilişkilendirme olacaktır.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="setmintabwidth"></a>CTabCtrl::SetMinTabWidth  
 En küçük genişliği öğelerinin bir sekme denetimi ayarlar.  
  
```  
int SetMinTabWidth(int cx);
```  
  
### <a name="parameters"></a>Parametreler  
 `cx`  
 Sekme denetim öğesi için ayarlanacak en küçük genişliği. Bu parametre -1 olarak ayarlanırsa, varsayılan sekme genişliği denetimi kullanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki en düşük sekme genişliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu üye işlevi Win32 ileti davranışını uygulayan [TCM_SETMINTABWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760637), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="setpadding"></a>CTabCtrl::SetPadding  
 (Her sekmenin simgesini ve sekme denetimi etiketinde etrafında doldurma) alan miktarını belirler.  
  
```  
void SetPadding(CSize size);
```  
  
### <a name="parameters"></a>Parametreler  
 `size`  
 (Her sekmenin simgesini ve sekme denetimi etiketinde etrafında doldurma) alan miktarını belirler.  
  
##  <a name="settooltips"></a>CTabCtrl::SetToolTips  
 Bir araç ipucunu denetimini Sekme denetimine atar.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWndTip`  
 Araç ipucunu denetimini tanıtıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekme denetimiyle ilişkili bir çağrı yaparak araç ipucunu denetimini alabilirsiniz `GetToolTips`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CHeaderCtrl sınıfı](../../mfc/reference/cheaderctrl-class.md)   
 [CListCtrl sınıfı](../../mfc/reference/clistctrl-class.md)
