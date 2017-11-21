---
title: "CMenu sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMenu
- AFXWIN/CMenu
- AFXWIN/CMenu::CMenu
- AFXWIN/CMenu::AppendMenu
- AFXWIN/CMenu::Attach
- AFXWIN/CMenu::CheckMenuItem
- AFXWIN/CMenu::CheckMenuRadioItem
- AFXWIN/CMenu::CreateMenu
- AFXWIN/CMenu::CreatePopupMenu
- AFXWIN/CMenu::DeleteMenu
- AFXWIN/CMenu::DeleteTempMap
- AFXWIN/CMenu::DestroyMenu
- AFXWIN/CMenu::Detach
- AFXWIN/CMenu::DrawItem
- AFXWIN/CMenu::EnableMenuItem
- AFXWIN/CMenu::FromHandle
- AFXWIN/CMenu::GetDefaultItem
- AFXWIN/CMenu::GetMenuContextHelpId
- AFXWIN/CMenu::GetMenuInfo
- AFXWIN/CMenu::GetMenuItemCount
- AFXWIN/CMenu::GetMenuItemID
- AFXWIN/CMenu::GetMenuItemInfo
- AFXWIN/CMenu::GetMenuState
- AFXWIN/CMenu::GetMenuString
- AFXWIN/CMenu::GetSafeHmenu
- AFXWIN/CMenu::GetSubMenu
- AFXWIN/CMenu::InsertMenu
- AFXWIN/CMenu::InsertMenuItem
- AFXWIN/CMenu::LoadMenu
- AFXWIN/CMenu::LoadMenuIndirect
- AFXWIN/CMenu::MeasureItem
- AFXWIN/CMenu::ModifyMenu
- AFXWIN/CMenu::RemoveMenu
- AFXWIN/CMenu::SetDefaultItem
- AFXWIN/CMenu::SetMenuContextHelpId
- AFXWIN/CMenu::SetMenuInfo
- AFXWIN/CMenu::SetMenuItemBitmaps
- AFXWIN/CMenu::SetMenuItemInfo
- AFXWIN/CMenu::TrackPopupMenu
- AFXWIN/CMenu::TrackPopupMenuEx
- AFXWIN/CMenu::m_hMenu
dev_langs: C++
helpviewer_keywords:
- CMenu [MFC], CMenu
- CMenu [MFC], AppendMenu
- CMenu [MFC], Attach
- CMenu [MFC], CheckMenuItem
- CMenu [MFC], CheckMenuRadioItem
- CMenu [MFC], CreateMenu
- CMenu [MFC], CreatePopupMenu
- CMenu [MFC], DeleteMenu
- CMenu [MFC], DeleteTempMap
- CMenu [MFC], DestroyMenu
- CMenu [MFC], Detach
- CMenu [MFC], DrawItem
- CMenu [MFC], EnableMenuItem
- CMenu [MFC], FromHandle
- CMenu [MFC], GetDefaultItem
- CMenu [MFC], GetMenuContextHelpId
- CMenu [MFC], GetMenuInfo
- CMenu [MFC], GetMenuItemCount
- CMenu [MFC], GetMenuItemID
- CMenu [MFC], GetMenuItemInfo
- CMenu [MFC], GetMenuState
- CMenu [MFC], GetMenuString
- CMenu [MFC], GetSafeHmenu
- CMenu [MFC], GetSubMenu
- CMenu [MFC], InsertMenu
- CMenu [MFC], InsertMenuItem
- CMenu [MFC], LoadMenu
- CMenu [MFC], LoadMenuIndirect
- CMenu [MFC], MeasureItem
- CMenu [MFC], ModifyMenu
- CMenu [MFC], RemoveMenu
- CMenu [MFC], SetDefaultItem
- CMenu [MFC], SetMenuContextHelpId
- CMenu [MFC], SetMenuInfo
- CMenu [MFC], SetMenuItemBitmaps
- CMenu [MFC], SetMenuItemInfo
- CMenu [MFC], TrackPopupMenu
- CMenu [MFC], TrackPopupMenuEx
- CMenu [MFC], m_hMenu
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b54a2cecf6ae091680582a3997cc8ee9c1c625d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmenu-class"></a>CMenu sınıfı
Windows bir kapsüllemeyi `HMENU`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMenu : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMenu::CMenu](#cmenu)|Oluşturan bir `CMenu` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMenu::AppendMenu](#appendmenu)|Yeni bir öğe bu menü sonuna ekler.|  
|[CMenu::Attach](#attach)|Ekler için Windows menüsü tanıtıcı bir `CMenu` nesnesi.|  
|[CMenu::CheckMenuItem](#checkmenuitem)|Bir onay işareti yanına yerleştirir veya menü öğesi açılır menüsünde bir onay işareti kaldırır.|  
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|Menü öğesinin yanındaki radyo düğmesi yerleştirir ve radyo düğmesi grubundaki diğer menü öğelerinin tümünün kaldırır.|  
|[CMenu::CreateMenu](#createmenu)|Boş bir menü oluşturur ve ona ekler bir `CMenu` nesnesi.|  
|[CMenu::CreatePopupMenu](#createpopupmenu)|Boş bir açılır menü oluşturur ve ona ekler bir `CMenu` nesnesi.|  
|[CMenu::DeleteMenu](#deletemenu)|Belirli bir öğeyi menüden siler. Menü öğesi ilişkilendirilmiş bir açılır menü varsa, açılır menüde tanıtıcısını bozar ve tarafından kullanılan bellek boşaltır.|  
|[CMenu::DeleteTempMap](#deletetempmap)|Tüm geçici siler `CMenu` tarafından oluşturulan nesneler `FromHandle` üye işlevi.|  
|[CMenu::DestroyMenu](#destroymenu)|Bağlı menü bozar bir `CMenu` nesne ve menü kapladığı belleği serbest bırakır.|  
|[CMenu::Detach](#detach)|Windows menüsü tanıtıcı gelen ayırır bir `CMenu` nesne ve işleyicisini döndürür.|  
|[CMenu::DrawItem](#drawitem)|Sahip tarafından çizilmiş menü değişikliklerini visual yönünü zaman çerçevesi tarafından çağrılır.|  
|[CMenu::EnableMenuItem](#enablemenuitem)|Etkinleştirir, devre dışı bırakır veya (grileri) karartır menü öğesi.|  
|[CMenu::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CMenu` Windows menü işleci verilen nesnesi.|  
|[CMenu::GetDefaultItem](#getdefaultitem)|Belirtilen menüsündeki varsayılan menü öğesi belirler.|  
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|Menü ile ilişkili Yardım bağlam Kimliğini alır.|  
|[CMenu::GetMenuInfo](#getmenuinfo)|Belirli bir menüsünde bilgilerini alır.|  
|[CMenu::GetMenuItemCount](#getmenuitemcount)|Açılır veya üst düzey menü öğelerinin sayısını belirler.|  
|[CMenu::GetMenuItemID](#getmenuitemid)|Belirtilen konumda bulunan bir menü öğesini menü öğesi tanımlayıcısını alır.|  
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|Menü öğesi ilgili bilgileri alır.|  
|[CMenu::GetMenuState](#getmenustate)|Açılır menüde bir durumu belirtilen menü öğesi veya öğe sayısını döndürür.|  
|[CMenu::GetMenuString](#getmenustring)|Belirtilen menü öğesi etiketini alır.|  
|[CMenu::GetSafeHmenu](#getsafehmenu)|Döndürür `m_hMenu` bu tarafından Sarmalanan `CMenu` nesnesi.|  
|[CMenu::GetSubMenu](#getsubmenu)|Açılır menü için bir işaretçi alır.|  
|[CMenu::InsertMenu](#insertmenu)|Diğer öğeleri menüyü taşıma belirtilen konumda yeni menü öğesi ekler.|  
|[CMenu::InsertMenuItem](#insertmenuitem)|Bir menüdeki belirli bir konumda yeni menü öğesi ekler.|  
|[CMenu::LoadMenu](#loadmenu)|Menü kaynağı yürütülebilir dosyayı yükler ve ekleninceye bir `CMenu` nesnesi.|  
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|Menü şablondan bellekte bir menü yükler ve ekleninceye bir `CMenu` nesnesi.|  
|[CMenu::MeasureItem](#measureitem)|Sahip tarafından çizilmiş menü oluşturulduğunda menü boyutları belirlemek için çerçevesi tarafından çağrılır.|  
|[CMenu::ModifyMenu](#modifymenu)|Belirli bir konumda var olan bir menü öğesini değiştirir.|  
|[CMenu::RemoveMenu](#removemenu)|Menü öğesi ilişkilendirilmiş bir açılır menü ile belirtilen menüsünden siler.|  
|[CMenu::SetDefaultItem](#setdefaultitem)|Varsayılan menü öğesi için belirtilen menü ayarlar.|  
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|Menü ile ilişkilendirilecek Yardım bağlam Kimliğini ayarlar.|  
|[CMenu::SetMenuInfo](#setmenuinfo)|Belirli bir menüsünde bilgilerini ayarlar.|  
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|Belirtilen onay işareti bit eşlemler Menü öğesiyle ilişkilendirir.|  
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|Menü öğesi hakkında bilgileri değiştirir.|  
|[CMenu::TrackPopupMenu](#trackpopupmenu)|Belirtilen konumda kayan açılır menü görüntüler ve açılır menüsünden öğelerin seçimini izler.|  
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|Belirtilen konumda kayan açılır menü görüntüler ve açılır menüsünden öğelerin seçimini izler.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMenu::operator HMENU](#operator_hmenu)|Menü nesne tanıtıcısını alır.|  
|[CMenu::operator! =](#operator_neq)|İki menü nesnenin eşit olup olmadığını belirler.|  
|[CMenu::operator ==](#operator_eq_eq)|İki menü nesnenin eşit olup olmadığını belirler.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMenu::m_hMenu](#m_hmenu)|Bağlı Windows menüsü tanıtıcısını belirtir `CMenu` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturma, izleme, güncelleştirme ve menü yok etme için üye işlevleri sağlar.  
  
 Oluşturma bir `CMenu` nesnesi olarak yerel bir yığın çerçevesi üzerinde'ı çağırın `CMenu`'s gerektiği gibi yeni menü işlemek için üye işlevleri. Ardından, çağrı [CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu) bir pencere için menü ayarlamak için hemen çağrı tarafından izlenen bir `CMenu` nesnenin [ayırma](#detach) üye işlevi. `CWnd::SetMenu` Üye işlevi Pencere menüsü yeni menüsüne ayarlar, Pencere menüsünden değişikliği yansıtacak şekilde çizilmesi neden olur ve ayrıca menü sahipliğini penceresine geçirir. Çağrısı **ayırma** ayırır `HMENU` gelen `CMenu` nesnesi, bunu olduğunda yerel `CMenu` değişken kapsamı dışında geçirir `CMenu` nesne yıkıcı bir menü yok etmek denemez onu yok artık sahip olur. Pencere bozulduğunda menü otomatik olarak yok.  
  
 Kullanabileceğiniz [LoadMenuIndirect](#loadmenuindirect) bellek şablonunda menüden, ancak bir kaynaktan bir çağrı tarafından oluşturulan bir menü oluşturmak için üye işlevi [LoadMenu](#loadmenu) daha kolay korunur ve menü kaynağı oluşturulan ve menü Düzenleyicisi tarafından değiştirilebilir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenu`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="appendmenu"></a>CMenu::AppendMenu  
 Menü öğesinin sonuna yeni bir öğe ekler.  
  
```  
BOOL AppendMenu(
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL AppendMenu(
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>Parametreler  
 `nFlags`  
 Menüye eklendiğinde, yeni menü öğesinin durumu hakkındaki bilgileri belirtir. Bir veya daha fazla açıklamalar bölümünde listelenen değerlerden oluşur.  
  
 `nIDNewItem`  
 Yeni menü öğesi komut Kimliğini belirtir veya `nFlags` ayarlanır **MF_POPUP**, menü işleci ( `HMENU`) açılır menüsünün. `nIDNewItem` Parametresi sayılır (gerekli değil) `nFlags` ayarlanır **MF_SEPARATOR**.  
  
 `lpszNewItem`  
 Yeni menü öğesi içeriğini belirtir. `nFlags` Parametresi yorumlamak için kullanılan `lpszNewItem` şu şekilde:  
  
|nFlags|LpszNewItem yorumu|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|Uygulama Menü öğesiyle ilişkilendirilmiş ek verileri korumak için kullanabileceğiniz bir uygulama tarafından sağlanan 32-bit değeri içeriyor. Bunu işlediğinde, bu 32-bit değeri uygulama için kullanılabilir `WM_MEASUREITEM` ve `WM_DRAWITEM` iletileri. Değer depolanan **ItemData** bu iletiler sağlanan yapısı üyesi.|  
|**MF_STRING**|Sonlandırılmış bir dize için bir işaretçi içeriyor. Varsayılan yorumu budur.|  
|**MF_SEPARATOR**|`lpszNewItem` Parametresi göz ardı edilir (gerekli).|  
  
 *pBmp*  
 İşaret eden bir `CBitmap` menü öğesi olarak kullanılan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama içinde değerlerini ayarlayarak menü öğesi durumunu belirtebilirsiniz `nFlags`. Zaman `nIDNewItem` bir açılır menü belirtir, eklenmiş menü parçası haline gelir. Menüye yok, eklenmiş menü ayrıca yok. Gelen eklenmiş bir menü ayrılmış bir `CMenu` çakışmayı önlemek için nesne. Unutmayın **MF_STRING** ve `MF_OWNERDRAW` bit eşlem sürümü için geçerli olmayan `AppendMenu`.  
  
 Aşağıdaki liste de ayarlanabilir bayrakları açıklar `nFlags`:  
  
- **MF_CHECKED** ile geçiş olarak görev yapan **MF_UNCHECKED** öğesinin yanındaki varsayılan onay işareti için. Uygulama onay işareti bit eşlemler zaman sağlar (bkz [SetMenuItemBitmaps](#setmenuitembitmaps) üye işlevi), "üzerinde onay işareti" bit eşlem görüntülenir.  
  
- **MF_UNCHECKED** ile geçiş olarak görev yapan **MF_CHECKED** öğesinin yanındaki onay işaretini kaldırın. Uygulama onay işareti bit eşlemler zaman sağlar (bkz `SetMenuItemBitmaps` üye işlevi), "devre dışı onay işareti" bit eşlem görüntülenir.  
  
- **MF_DISABLED** böylece seçilemez ancak onu dim değil menü öğesini devre dışı bırakır.  
  
- `MF_ENABLED`Böylece seçilebilir ve devre dışı durumuna geri yükler menü öğesi sağlar.  
  
- **MF_GRAYED** seçilemez ve onu karartır menü öğesini devre dışı bırakır.  
  
- **MF_MENUBARBREAK** statik menüleri veya yeni bir sütun açılır menüler içinde yeni bir satıra öğeyi yerleştirir. Yeni bir açılır menü sütun eski sütunu Dikey bölme çizgiyle ayrılacaktır.  
  
- **MF_MENUBREAK** statik menüleri veya yeni bir sütun açılır menüler içinde yeni bir satıra öğeyi yerleştirir. Hiçbir bölme çizgisi sütunlar arasında yerleştirilir.  
  
- `MF_OWNERDRAW`Öğe sahip çizim öğeyi olduğunu belirtir. Menü sahip Pencere menüsü ilk kez görüntülendiğinde alır bir `WM_MEASUREITEM` menü öğesinin genişliği ve yüksekliği alır ileti. `WM_DRAWITEM` Sahibi menü öğesi görsel görünümünü güncelleştirdiğinizde gerekir gönderilen bir iletidir. Bu seçenek en üst düzey menü öğesi için geçerli değil.  
  
- **MF_POPUP** menü öğesi kendisiyle ilişkili bir açılır menü olduğunu belirtir. ID parametresi öğeyle ilişkilendirilecek bir açılır menü için bir tanıtıcı belirtir. Bu, en üst düzey bir açılır menü veya hiyerarşik bir açılır menüyü açılır menü öğesine eklemek için kullanılır.  
  
- **MF_SEPARATOR** yatay bölme çizgisi çizer. Yalnızca bir açılır menüde kullanılabilir. Bu satırı görünüyorsa, devre dışı, vurgulanmış veya silinemez. Diğer parametreler göz ardı edilir.  
  
- **MF_STRING** menü öğesi bir karakter dizesi olduğunu belirtir.  
  
 Aşağıdaki grupların her biri, karşılıklı olarak birbirini dışlar ve birlikte kullanılamaz bayrakları listeler:  
  
- **MF_DISABLED**, `MF_ENABLED`, ve **MF_GRAYED**  
  
- **MF_STRING**, `MF_OWNERDRAW`, **MF_SEPARATOR**hem de bit eşlem  
  
- **MF_MENUBARBREAK** ve **MF_MENUBREAK**  
  
- **MF_CHECKED** ve **MF_UNCHECKED**  
  
 İçinde bulunan bir menü her (penceresi görüntülenir olsun veya olmasın) bir penceresi değiştirildiğinde, uygulama çağırmalıdır [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::CreateMenu](#createmenu).  
  
##  <a name="attach"></a>CMenu::Attach  
 Varolan bir Windows menüsü bağlayan bir `CMenu` nesnesi.  
  
```  
BOOL Attach(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 `hMenu`  
 Windows menüsü için bir tanıtıcı belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü için zaten bağlıysa, bu işlev çağrılmamalıdır `CMenu` nesnesi. Menü işleci depolanan `m_hMenu` veri üyesi.  
  
 İşlemek istediğiniz menünün zaten bir pencere ile ilişkili ise, kullanabileceğiniz [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu) menüsüne bir tanıtıcı almak için işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="checkmenuitem"></a>CMenu::CheckMenuItem  
 Onay işaretleri ekler veya menü öğeleri açılır menüde onay işaretleri kaldırır.  
  
```  
UINT CheckMenuItem(
    UINT nIDCheckItem,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDCheckItem`  
 Tarafından belirlenen denetlenmesi için menü öğesini belirtir `nCheck`.  
  
 `nCheck`  
 Menü öğesi denetleme ve menü öğesi'nin konumu belirleme belirtir. `nCheck` Parametresi bir bileşimi olabilir **MF_CHECKED** veya **MF_UNCHECKED** ile **MF_BYPOSITION** veya **MF_BYCOMMAND** bayraklar. Bu bayrakların bit düzeyinde OR işleci kullanılarak birleştirilebilir. Bunlar şu anlama gelir:  
  
- **MF_BYCOMMAND** parametresi varolan menü öğesini komut Kimliğini verdiğini belirtir. Bu varsayılandır.  
  
- **MF_BYPOSITION** parametresi varolan menü öğesini konumunu verdiğini belirtir. İlk öğeyi 0 konumundadır.  
  
- **MF_CHECKED** ile geçiş olarak görev yapan **MF_UNCHECKED** öğesinin yanındaki varsayılan onay işareti için.  
  
- **MF_UNCHECKED** ile geçiş olarak görev yapan **MF_CHECKED** öğesinin yanındaki onay işaretini kaldırın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesinin önceki durumunu: **MF_CHECKED** veya **MF_UNCHECKED**, veya menü öğesi mevcut değilse 0xFFFFFFFF.  
  
### <a name="remarks"></a>Açıklamalar  
 `nIDCheckItem` Parametresi, değiştirilecek öğenin belirtir.  
  
 `nIDCheckItem` Parametresi menü öğesi yanı sıra bir açılır menü öğesini tanımlamak. Hiçbir özel adım bir açılır menü öğesini denetlemek için gereklidir. Üst düzey menü öğeleri denetlenemez. Kendisiyle ilişkili bir menü öğesi tanımlayıcısı olmadığından bir açılır menü öğesini konuma göre denetlenmesi gerekir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::GetMenuState](#getmenustate).  
  
##  <a name="checkmenuradioitem"></a>CMenu::CheckMenuRadioItem  
 Belirtilen menü öğesi denetler ve bir seçenek öğesi kolaylaştırır.  
  
```  
BOOL CheckMenuRadioItem(
    UINT nIDFirst,  
    UINT nIDLast,  
    UINT nIDItem,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDFirst`  
 Belirtir (kimliği veya değerine bağlı olarak uzaklık olarak `nFlags`) radyo düğmesi grubunda ilk menü öğesi.  
  
 `nIDLast`  
 Belirtir (kimliği veya değerine bağlı olarak uzaklık olarak `nFlags`) radyo düğmesi grubunda son menü öğesi.  
  
 `nIDItem`  
 Belirtir (kimliği veya değerine bağlı olarak uzaklık olarak `nFlags`) öğesi grubunda bulunan ve bir radyo düğmesi ile denetlenir.  
  
 `nFlags`  
 Yorumu belirtir `nIDFirst`, `nIDLast`, ve `nIDItem` şu şekilde:  
  
|nFlags|Yorumu|  
|------------|--------------------|  
|**MF_BYCOMMAND**|Parametresi varolan menü öğesini komut Kimliğini verdiğini belirtir. Bu varsayılan hiçbiri ise **MF_BYCOMMAND** ya da **MF_BYPOSITION** ayarlanır.|  
|**MF_BYPOSITION**|Parametresi varolan menü öğesini konumunu verdiğini belirtir. İlk öğeyi 0 konumundadır.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0  
  
### <a name="remarks"></a>Açıklamalar  
 Aynı anda işlevi ilişkili gruptaki diğer tüm menü öğeleri temizler ve bu öğeler için radyo öğesi türü bayrağını temizler. Checked öğesi, bir onay işareti bit eşlem yerine bir radyo düğmesi (veya madde işareti) bit eşlem kullanarak görüntülenir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range).  
  
##  <a name="cmenu"></a>CMenu::CMenu  
 Boş bir menü oluşturur ve ona ekler bir `CMenu` nesnesi.  
  
```  
CMenu();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Menü oluşturma veya yük üye işlevlerini birini çağrısı tamamlanana kadar oluşturulmaz **CMenu:**  
  
- [CreateMenu](#createmenu)  
  
- [CreatePopupMenu](#createpopupmenu)  
  
- [LoadMenu](#loadmenu)  
  
- [LoadMenuIndirect](#loadmenuindirect)  
  
- [Ekleme](#attach)  
  
##  <a name="createmenu"></a>CMenu::CreateMenu  
 Bir menüyü oluşturur ve ona ekler `CMenu` nesnesi.  
  
```  
BOOL CreateMenu();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Menü başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Menüsü başlangıçta boş olur. Menü öğeleri kullanılarak eklenebilir `AppendMenu` veya `InsertMenu` üye işlevi.  
  
 Pencere menü atanırsa, pencere bozulduğunda otomatik olarak kaldırıldığı.  
  
 Çıkmadan önce bir uygulama menüsü pencere atanmamışsa bir menü ile ilişkili sistem kaynakları serbest gerekir. Bir uygulama bir menü çağırarak boşaltır [DestroyMenu](#destroymenu) üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]  
  
##  <a name="createpopupmenu"></a>CMenu::CreatePopupMenu  
 Açılır menü oluşturur ve ona ekler `CMenu` nesnesi.  
  
```  
BOOL CreatePopupMenu();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açılır menü başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Menüsü başlangıçta boş olur. Menü öğeleri kullanılarak eklenebilir `AppendMenu` veya `InsertMenu` üye işlevi. Uygulama açılan menüden bir varolan menüsünden veya açılır menüsünden ekleyebilirsiniz. `TrackPopupMenu` Üye işlevi bu menüsünü kayan açılır menü olarak görüntüleme ve seçimleri açılır menüsünden izlemek için kullanılabilir.  
  
 Pencere menü atanırsa, pencere bozulduğunda otomatik olarak kaldırıldığı. Varolan bir menüye menü eklediyseniz, menüye kaldırıldığı zaman otomatik olarak kaldırıldığı.  
  
 Çıkmadan önce bir uygulama menüsü pencere atanmamışsa bir açılır menü ile ilişkili sistem kaynakları serbest gerekir. Bir uygulama bir menü çağırarak boşaltır [DestroyMenu](#destroymenu) üye işlevi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::CreateMenu](#createmenu).  
  
##  <a name="deletemenu"></a>CMenu::DeleteMenu  
 Bir öğeyi menüden siler.  
  
```  
BOOL DeleteMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPosition`  
 Tarafından belirlenen silinecek olan menü öğesi belirtir `nFlags`.  
  
 `nFlags`  
 Yorumlamak için kullanılan `nPosition` şu şekilde:  
  
|nFlags|NPosition yorumu|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Parametresi varolan menü öğesini komut Kimliğini verdiğini belirtir. Bu varsayılan hiçbiri ise **MF_BYCOMMAND** ya da **MF_BYPOSITION** ayarlanır.|  
|**MF_BYPOSITION**|Parametresi varolan menü öğesini konumunu verdiğini belirtir. İlk öğeyi 0 konumundadır.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü öğesi ilişkilendirilmiş bir açılır menü varsa `DeleteMenu` açılır menü için tanıtıcı yok eder ve açılan menü tarafından kullanılan belleği serbest bırakır.  
  
 İçinde bulunan bir menü her (penceresi görüntülenir olsun veya olmasın) bir penceresi değiştirildiğinde, uygulamayı çağırması gerekir [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).  
  
##  <a name="deletetempmap"></a>CMenu::DeleteTempMap  
 Tarafından otomatik olarak çağrılır `CWinApp` boşta kalma süresi işleyici, hiçbir geçici siler `CMenu` tarafından oluşturulan nesneler [FromHandle](#fromhandle) üye işlevi.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `DeleteTempMap`geçici bir iliştirilmiş Windows menüsü nesne ayırır `CMenu` silmeden önce nesne `CMenu` nesne.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]  
  
##  <a name="destroymenu"></a>CMenu::DestroyMenu  
 Menü ve kullanılan tüm Windows kaynakları bozar.  
  
```  
BOOL DestroyMenu();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Menü yok, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü bulunmuyor `CMenu` yok edilir önce nesne. Windows `DestroyMenu` işlevini çağırdı otomatik olarak `CMenu` yıkıcı.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::CreateMenu](#createmenu).  
  
##  <a name="detach"></a>CMenu::Detach  
 Bir Windows menüden ayırır bir `CMenu` nesne ve işleyicisini döndürür.  
  
```  
HMENU Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tür tanıtıcı `HMENU`, başarılı; Aksi takdirde, bir Windows menüsüne **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 `m_hMenu` Veri üyesi ayarlanmış **NULL**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="drawitem"></a>CMenu::DrawItem  
 Sahip tarafından çizilmiş menü değişikliklerini visual yönünü zaman çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDrawItemStruct`  
 Bir işaretçi bir [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) gerekli çizim türü hakkında bilgi içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `itemAction` Üyesi `DRAWITEMSTRUCT` yapısı gerçekleştirilecek çizim eylemi tanımlar. Çizim sahibi çizim için uygulamak için bu üye işlevi geçersiz kılma `CMenu` nesnesi. Tüm grafik cihaz arabirimi (GDI) nesneleri görüntüleme bağlamı içinde sağlanan için seçilen uygulama kurtarmalısınız `lpDrawItemStruct` bu üye işlevinin sona ermeden önce.  
  
 Bkz: [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) açıklaması `DRAWITEMSTRUCT` yapısı.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kodu MFC'den: [CTRLTEST](../../visual-cpp-samples.md) örnek:  
  
 [!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]  
  
##  <a name="enablemenuitem"></a>CMenu::EnableMenuItem  
 Etkinleştirir, devre dışı bırakır veya menü öğesi karartır.  
  
```  
UINT EnableMenuItem(
    UINT nIDEnableItem,  
    UINT nEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDEnableItem*  
 Tarafından belirlenen etkinleştirilmesi için menü öğesi belirtir `nEnable`. Bu parametre, açılan menü öğeleri ve bunun yanı sıra standart menü öğeleri belirtebilirsiniz.  
  
 `nEnable`  
 Gerçekleştirilecek eylemi belirtir. Bir bileşimi olabilir **MF_DISABLED**, `MF_ENABLED`, veya **MF_GRAYED**, ile **MF_BYCOMMAND** veya **MF_BYPOSITION**. Bu değerleri bit düzeyinde OR işleci kullanılarak birleştirilebilir. Bu değerleri şu anlama gelir:  
  
- **MF_BYCOMMAND** parametresi varolan menü öğesini komut Kimliğini verdiğini belirtir. Bu varsayılandır.  
  
- **MF_BYPOSITION** parametresi varolan menü öğesini konumunu verdiğini belirtir. İlk öğeyi 0 konumundadır.  
  
- **MF_DISABLED** böylece seçilemez ancak onu dim değil menü öğesini devre dışı bırakır.  
  
- `MF_ENABLED`Böylece seçilebilir ve devre dışı durumuna geri yükler menü öğesi sağlar.  
  
- **MF_GRAYED** seçilemez ve onu karartır menü öğesini devre dışı bırakır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki bir duruma ( **MF_DISABLED**, `MF_ENABLED`, veya **MF_GRAYED**) veya -1, geçerli değil.  
  
### <a name="remarks"></a>Açıklamalar  
 [CreateMenu](#createmenu), [InsertMenu](#insertmenu), [ModifyMenu](#modifymenu), ve [LoadMenuIndirect](#loadmenuindirect) üye işlevleri (etkin durumu de ayarlayabilirsiniz devre dışı veya soluk) menü öğesinin.  
  
 Kullanarak **MF_BYPOSITION** değer gerektiren doğru kullanmak için bir uygulama `CMenu`. Varsa `CMenu` menü çubuğu kullanıldığında, bir üst düzey menü öğesi (menü çubuğunda bir öğe) etkilenir. Açılır veya iç içe bir açılır menü konuma göre bir öğeyi durumunu ayarlamak için bir uygulama belirtilmesi gerekir `CMenu` açılır menüsünden.  
  
 Bir uygulama belirttiğinde **MF_BYCOMMAND** bayrağı, Windows, altındaki tüm açılır menü öğeleri denetler `CMenu`; bu nedenle, yinelenen menü öğeleri yoksa kullanarak `CMenu` menüsünü çubuk olur yeterli.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]  
  
##  <a name="fromhandle"></a>CMenu::FromHandle  
 Bir işaretçi döndüren bir `CMenu` Windows tanıtıcı menüye verilen nesnesi.  
  
```  
static CMenu* PASCAL FromHandle(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 `hMenu`  
 Windows tanıtıcı menüye.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CMenu` geçici veya kalıcı olabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa bir `CMenu` nesne zaten iliştirilmemiş Windows menüsü nesne geçici bir `CMenu` nesnesi oluşturulur ve bağlı.  
  
 Bu geçici `CMenu` nesnesidir yalnızca geçerli uygulama aynı zamanda tüm geçici nesneler silinir, olay döngüde boşta kalma süresi sahip zamana kadar.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::CreateMenu](#createmenu).  
  
##  <a name="getdefaultitem"></a>CMenu::GetDefaultItem  
 Belirtilen menüsündeki varsayılan menü öğesi belirler.  
  
```  
UINT GetDefaultItem(
    UINT gmdiFlags,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 *gmdiFlags*  
 İşlev menü öğelerinin nasıl arayacağını belirten değer. Bu parametre yok, veya bir bileşimiyle aşağıdaki değerlerden biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|**GMDI_GOINTOPOPUPS**|Varsayılan öğesi bir alt açan ise, işlev karşılık gelen alt yinelemeli olarak aramak için belirtir. Alt varsayılan öğe varsa, alt açılır öğe dönüş değerini tanımlar.<br /><br /> Varsayılan olarak, bir alt menü açılır bir öğe olmasına bakılmaksızın belirtilen menüsünde ilk varsayılan öğesi işlevi döndürür.|  
|**GMDI_USEDISABLED**|Devre dışı olsa bile işlevi varsayılan öğesi döndürmek için olduğunu belirtir.<br /><br /> Varsayılan olarak devre dışı bırakılmış veya gri öğeler işlevi atlar.|  
  
 `fByPos`  
 Menü öğesinin tanımlayıcısı veya konumunu almak olup olmayacağını belirten değer. Bu parametre ise **yanlış**, tanıtıcısı döndürülür. Aksi takdirde, konumu döndürülür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri tanımlayıcısı'nı veya menü öğesi konumunu ' dir. İşlev başarısız olursa, dönüş değeri olur - 1.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 işlevi davranışını uygulayan [GetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647976), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getmenucontexthelpid"></a>CMenu::GetMenuContextHelpId  
 Kimliği ile ilişkili Bağlam Yardımı alır `CMenu`.  
  
```  
DWORD GetMenuContextHelpId() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda kimliği ilişkili Bağlam Yardımı `CMenu` ; varsa, aksi takdirde sıfır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getmenuinfo"></a>CMenu::GetMenuInfo  
 Bir menüye ilişkin bilgileri alır.  
  
```  
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpcmi`  
 Bir işaretçi bir [MENUINFO](http://msdn.microsoft.com/library/windows/desktop/ms647575) menü ilgili bilgileri içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri sıfır olmayan; Aksi takdirde, dönüş değeri sıfır olur.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü hakkında bilgi almak için bu işlevini çağırın.  
  
##  <a name="getmenuitemcount"></a>CMenu::GetMenuItemCount  
 Açılır veya üst düzey menü öğelerinin sayısını belirler.  
  
```  
UINT GetMenuItemCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa menüdeki öğeler sayısı; Aksi takdirde-1.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).  
  
##  <a name="getmenuitemid"></a>CMenu::GetMenuItemID  
 Menü öğesi tanımlayıcısı tarafından tanımlanan bir konumda yer menü öğesi için edinir `nPos`.  
  
```  
UINT GetMenuItemID(int nPos) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nPos`  
 Kimliğine alınan konumunu (sıfır tabanlı) menü öğesini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen işlev başarılı olursa bir açılır menü öğesi için öğe kimliği. Belirtilen öğe bir açılır menü (aksine, açılır menü içinde öğe) ise, dönüş değeri -1'dir. Varsa `nPos` karşılık gelen bir **AYIRICI** menü öğesi, dönüş değeri: 0.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getmenuiteminfo"></a>CMenu::GetMenuItemInfo  
 Menü öğesi ilgili bilgileri alır.  
  
```  
BOOL GetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `uItem`  
 Tanımlayıcı veya hakkında bilgi almak için menü öğesi konumu. Bu parametre anlamını değerine bağlıdır `ByPos`.  
  
 `lpMenuItemInfo`  
 Bir işaretçi bir [MENUITEMINFO](http://msdn.microsoft.com/library/windows/desktop/ms647578)menü hakkında bilgi içeren Windows SDK, açıklandığı gibi.  
  
 `fByPos`  
 Anlamını belirten değeri `nIDItem`. Varsayılan olarak, `ByPos` olan **yanlış**, o uItem belirten bir menü öğesi tanımlayıcısıdır. Varsa `ByPos` ayarlanmazsa **yanlış**, menü öğesi konumu gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri sıfır olmayan bir değer. İşlev başarısız olursa, dönüş değeri sıfır olur. Genişletilmiş hata bilgilerini için Win32 işlevini [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360), Windows SDK'ın açıklandığı gibi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi davranışını uygulayan Win32 işlevinin [GetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms647980), Windows SDK'ın açıklandığı gibi. MFC uygulamasında unutmayın `GetMenuItemInfo`, menü için bir tanıtıcı kullanmayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]  
  
##  <a name="getmenustate"></a>CMenu::GetMenuState  
 Açılır menüde bir durumu belirtilen menü öğesi veya öğe sayısını döndürür.  
  
```  
UINT GetMenuState(
    UINT nID,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Menü öğesi kimliği tarafından belirlenen belirtir `nFlags`.  
  
 `nFlags`  
 Doğası belirtir `nID`. Aşağıdaki değerlerden biri olabilir:  
  
- **MF_BYCOMMAND** parametresi varolan menü öğesini komut Kimliğini verdiğini belirtir. Bu varsayılandır.  
  
- **MF_BYPOSITION** parametresi varolan menü öğesini konumunu verdiğini belirtir. İlk öğeyi 0 konumundadır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen öğe yoksa, 0xFFFFFFFF değeri. Varsa *nId* bir açılır menü tanımlayan yüksek düzey bayt açılır menüde öğe sayısı ve açılır menü ile ilişkili menü bayrakları düşük düzey bayt içerir. Aksi takdirde dönüş değeri bir (Boole veya) aşağıdaki listeden değerlerin maskesidir (Bu maskesi menü durumunu açıklar öğesi *nId* tanımlar):  
  
- **MF_CHECKED** ile geçiş olarak görev yapan **MF_UNCHECKED** öğesinin yanındaki varsayılan onay işareti için. Uygulama onay işareti bit eşlemler zaman sağlar (bkz `SetMenuItemBitmaps` üye işlevi), "üzerinde onay işareti" bit eşlem görüntülenir.  
  
- **MF_DISABLED** böylece seçilemez ancak onu dim değil menü öğesini devre dışı bırakır.  
  
- `MF_ENABLED`Böylece seçilebilir ve devre dışı durumuna geri yükler menü öğesi sağlar. Bu sabit değeri 0 olduğunu unutmayın; bir uygulama hatası için 0 karşı bu değeri kullanılırken sınamalısınız değil.  
  
- **MF_GRAYED** seçilemez ve onu karartır menü öğesini devre dışı bırakır.  
  
- **MF_MENUBARBREAK** statik menüleri veya yeni bir sütun açılır menüler içinde yeni bir satıra öğeyi yerleştirir. Yeni bir açılır menü sütun eski sütunu Dikey bölme çizgiyle ayrılacaktır.  
  
- **MF_MENUBREAK** statik menüleri veya yeni bir sütun açılır menüler içinde yeni bir satıra öğeyi yerleştirir. Hiçbir bölme çizgisi sütunlar arasında yerleştirilir.  
  
- **MF_SEPARATOR** yatay bölme çizgisi çizer. Yalnızca bir açılır menüde kullanılabilir. Bu satırı görünüyorsa, devre dışı, vurgulanmış veya silinemez. Diğer parametreler göz ardı edilir.  
  
- **MF_UNCHECKED** ile geçiş olarak görev yapan **MF_CHECKED** öğesinin yanındaki onay işaretini kaldırın. Uygulama onay işareti bit eşlemler zaman sağlar (bkz `SetMenuItemBitmaps` üye işlevi), "devre dışı onay işareti" bit eşlem görüntülenir. Bu sabit değeri 0 olduğunu unutmayın; bir uygulama hatası için 0 karşı bu değeri kullanılırken sınamalısınız değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]  
  
##  <a name="getmenustring"></a>CMenu::GetMenuString  
 Belirtilen menü öğesi etiketini belirtilen arabellek kopyalar.  
  
```  
int GetMenuString(
    UINT nIDItem,  
    LPTSTR lpString,  
    int nMaxCount,  
    UINT nFlags) const;  
  
int GetMenuString(
    UINT nIDItem,  
    CString& rString,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDItem`  
 Menüde değerine bağlı olarak menü öğesi tamsayı tanıtıcısı veya menü öğesi uzaklığını belirtir `nFlags`.  
  
 `lpString`  
 Etiket alacak arabellek noktalarına.  
  
 `rString`  
 Bir başvuru bir `CString` kopyalanan menü dizeyi almak için nesne.  
  
 `nMaxCount`  
 Kopyalanacak etiketi maksimum uzunluğu (karakter cinsinden) belirtir. Etiket belirtilen maksimum uzunsa `nMaxCount`, fazladan karakterler kesiliyor.  
  
 `nFlags`  
 Yorumu belirtir `nIDItem` parametresi. Aşağıdaki değerlerden biri olabilir:  
  
|nFlags|NIDItem yorumu|  
|------------|-------------------------------|  
|**MF_BYCOMMAND**|Parametresi varolan menü öğesini komut Kimliğini verdiğini belirtir. Bu varsayılan hiçbiri ise **MF_BYCOMMAND** ya da **MF_BYPOSITION** ayarlanır.|  
|**MF_BYPOSITION**|Parametresi varolan menü öğesini konumunu verdiğini belirtir. İlk öğeyi 0 konumundadır.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerçek arabelleğine null Sonlandırıcı dahil değil, kopyalanan karakter sayısını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 `nMaxCount` Parametresi bir dize sonlandırır null karakteri uyum sağlayacak şekilde etiket karakter sayısından büyük olmalıdır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getsafehmenu"></a>CMenu::GetSafeHmenu  
 Döndürür `HMENU` bu tarafından Sarmalanan `CMenu` nesnesi veya bir **NULL** `CMenu` işaretçi.  
  
```  
HMENU GetSafeHmenu() const;  
```  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::LoadMenu](#loadmenu).  
  
##  <a name="getsubmenu"></a>CMenu::GetSubMenu  
 Alır `CMenu` açılır menü nesnesi.  
  
```  
CMenu* GetSubMenu(int nPos) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nPos`  
 Menüde bulunan açılır menü konumunu belirtir. Konum değerleri 0 ilk menü öğesi için başlangıç. Açılır menünün tanımlayıcı bu işlevi kullanılamaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CMenu` nesnesindeki `m_hMenu` üyeyi içeren açılır menü için bir tanıtıcı belirli konumunda; açılır menü varsa, aksi takdirde **NULL**. Varsa bir `CMenu` nesnesi yok ve geçici bir tane oluşturulur. `CMenu` Döndürülen işaretçisi değil depolanmalıdır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::TrackPopupMenu](#trackpopupmenu).  
  
##  <a name="insertmenu"></a>CMenu::InsertMenu  
 Yeni menü öğesi tarafından belirtilen konumdaki ekler `nPosition` ve diğer öğeleri menüyü taşır.  
  
```  
BOOL InsertMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL InsertMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPosition`  
 Önce yeni menü öğesi eklenecek olduğu menü öğesi belirtir. `nFlags` Parametresi yorumlamak için kullanılabilir `nPosition` aşağıdaki yollarla:  
  
|nFlags|NPosition yorumu|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Parametresi varolan menü öğesini komut Kimliğini verdiğini belirtir. Bu varsayılan hiçbiri ise **MF_BYCOMMAND** ya da **MF_BYPOSITION** ayarlanır.|  
|**MF_BYPOSITION**|Parametresi varolan menü öğesini konumunu verdiğini belirtir. İlk öğeyi 0 konumundadır. Varsa `nPosition` -1 ' dir yeni menü öğesini menü sonuna eklenir.|  
  
 `nFlags`  
 Belirtir nasıl `nPosition` yorumlanır ve menüsüne eklenen yeni menü öğesinin durumu hakkındaki bilgileri belirtir. Ayarlanamaz bayraklar listesi için bkz: [döndürmesini](#appendmenu) üye işlevi. Birden fazla değer belirtmek için bunları birleştirmek için bit düzeyinde OR işleci kullanın **MF_BYCOMMAND** veya **MF_BYPOSITION** bayrağı.  
  
 `nIDNewItem`  
 Yeni menü öğesi komut Kimliğini belirtir veya `nFlags` ayarlanır **MF_POPUP**, menü işleci ( `HMENU`) açılır menüsünden. `nIDNewItem` Parametresi sayılır (gerekli değil) `nFlags` ayarlanır **MF_SEPARATOR**.  
  
 `lpszNewItem`  
 Yeni menü öğesi içeriğini belirtir. `nFlags`bilgilerini yorumlamak için kullanılacak `lpszNewItem` aşağıdaki yollarla:  
  
|nFlags|LpszNewItem yorumu|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|Uygulama Menü öğesiyle ilişkilendirilmiş ek verileri korumak için kullanabileceğiniz bir uygulama tarafından sağlanan 32-bit değeri içeriyor. Bu 32-bit değeri uygulama için kullanılabilir **ItemData** tarafından sağlanan yapısı üyesi [WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925) ve [WM_DRAWITEM](http://msdn.microsoft.com/library/windows/desktop/bb775923) iletileri. Bu iletiler, menü öğesi başlangıçta görüntülenir veya değiştirildiğinde gönderilir.|  
|**MF_STRING**|Sonlandırılmış bir dizeye uzun bir işaretçi içeriyor. Varsayılan yorumu budur.|  
|**MF_SEPARATOR**|`lpszNewItem` Parametresi göz ardı edilir (gerekli).|  
  
 *pBmp*  
 İşaret eden bir `CBitmap` menü öğesi olarak kullanılan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama içinde değerlerini ayarlayarak menü öğesi durumunu belirtebilirsiniz `nFlags`.  
  
 İçinde bulunan bir menü her (penceresi görüntülenir olsun veya olmasın) bir penceresi değiştirildiğinde, uygulama çağırmalıdır `CWnd::DrawMenuBar`.  
  
 Zaman `nIDNewItem` bir açılır menü belirtir, eklenen menü parçası haline gelir. Menüye yok, eklenen menü ayrıca yok. Eklenen bir menü ayrılmış bir `CMenu` çakışmayı önlemek için nesne.  
  
 Birden çok belge arabirimi (MDI) alt penceresi ekranı etkin ve bir uygulama ekliyorsa açılır menü MDI uygulamanın menüsüne bu işlevi çağırmak ve belirterek **MF_BYPOSITION** bayrağı, menü eklenir bir konum uzağa beklenenden kalmadı. Etkin MDI alt pencere Denetim menüsünü MDI çerçeve pencere menü çubuğu ilk konumunu eklenen çünkü bu gerçekleşir. Menü düzgün konumlandırmak için uygulama, aksi takdirde kullanılacak konum değeri 1 eklemeniz gerekir. Bir uygulamanın kullanabileceği **WM_MDIGETACTIVE** şu anda etkin alt pencere ekranı olup olmadığını belirlemek için ileti.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]  
  
##  <a name="insertmenuitem"></a>CMenu::InsertMenuItem  
 Bir menüdeki belirli bir konumda yeni menü öğesi ekler.  
  
```  
BOOL InsertMenuItem(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `uItem`  
 Açıklamasını görmek `uItem` içinde [InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988) Windows SDK'sındaki.  
  
 `lpMenuItemInfo`  
 Açıklamasını görmek `lpmii` içinde **InsertMenuItem** Windows SDK'sındaki.  
  
 `fByPos`  
 Açıklamasını görmek `fByPosition` içinde **InsertMenuItem** Windows SDK'sındaki.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevi sarmalar [InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988), Windows SDK'sındaki açıklanmıştır.  
  
##  <a name="loadmenu"></a>CMenu::LoadMenu  
 Menü kaynağı uygulamanın yürütülebilir dosyadan yükler ve ekleninceye `CMenu` nesnesi.  
  
```  
BOOL LoadMenu(LPCTSTR lpszResourceName);  
BOOL LoadMenu(UINT nIDResource);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszResourceName`  
 Yüklemek için menü kaynağın adını içeren null ile sonlandırılmış bir dize noktalarına.  
  
 `nIDResource`  
 Yüklemek için menü kaynağı menü Kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Menü kaynağı başarıyla yüklendiyse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çıkmadan önce bir uygulama menüsü pencere atanmamışsa bir menü ile ilişkili sistem kaynakları serbest gerekir. Bir uygulama bir menü çağırarak boşaltır [DestroyMenu](#destroymenu) üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]  
  
##  <a name="loadmenuindirect"></a>CMenu::LoadMenuIndirect  
 Menü şablondan bellekte bir kaynak yükler ve ekleninceye `CMenu` nesnesi.  
  
```  
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpMenuTemplate*  
 İşaret eden bir menü şablonu (tek bir olduğu [MENUITEMTEMPLATEHEADER](http://msdn.microsoft.com/library/windows/desktop/ms647583) yapısı ve bir veya daha fazla koleksiyonu [MENUITEMTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms647581) yapıları). Bu iki yapıları hakkında daha fazla bilgi için Windows SDK'sı bakın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Menü kaynağı başarıyla yüklendiyse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazla koleksiyon tarafından izlenen bir üstbilgi menü şablonudur [MENUITEMTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms647581) yapıları, her biri içerebileceği bir veya daha fazla menü öğeleri ve açılır menüler.  
  
 Sürüm numarası 0 olmalıdır.  
  
 **MtOption** bayrakları içermelidir **MF_END** ana listesindeki son öğeyi ve açılır listesindeki son öğeyi için. Bkz: `AppendMenu` üye işlevi için diğer bayraklar. **MtId** member atlandığından, gelen **MENUITEMTEMPLATE** ne zaman yapısı **MF_POPUP** belirtilen **mtOption**.  
  
 İçin ayrılan alanı **MENUITEMTEMPLATE** yapısı için yeterince büyük olmalıdır **mtString** null ile sonlandırılmış bir dize olarak menü öğesinin adı içeriyor.  
  
 Çıkmadan önce bir uygulama menüsü pencere atanmamışsa bir menü ile ilişkili sistem kaynakları serbest gerekir. Bir uygulama bir menü çağırarak boşaltır [DestroyMenu](#destroymenu) üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]  
  
##  <a name="m_hmenu"></a>CMenu::m_hMenu  
 Belirtir `HMENU` Windows menüsü tanıtıcısı iliştirilmiş `CMenu` nesnesi.  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::LoadMenu](#loadmenu).  
  
##  <a name="measureitem"></a>CMenu::MeasureItem  
 Sahibi çizim stili menüsüyle oluşturulduğunda çerçevesi tarafından çağrılır.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpMeasureItemStruct`  
 Bir işaretçi bir `MEASUREITEMSTRUCT` yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bu üye işlevi geçersiz kılma ve doldurmak `MEASUREITEMSTRUCT` Windows'a menünün boyutlarının bildirmek için yapısı.  
  
 Bkz: [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) açıklaması `MEASUREITEMSTRUCT` yapısı.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kodu MFC'den: [CTRLTEST](../../visual-cpp-samples.md) örnek:  
  
 [!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]  
  
##  <a name="modifymenu"></a>CMenu::ModifyMenu  
 Varolan bir menü öğesi tarafından belirtilen konumdaki değişiklikler `nPosition`.  
  
```  
BOOL ModifyMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL ModifyMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPosition`  
 Değiştirilecek menü öğesi belirtir. `nFlags` Parametresi yorumlamak için kullanılabilir `nPosition` aşağıdaki yollarla:  
  
|nFlags|NPosition yorumu|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Parametresi varolan menü öğesini komut Kimliğini verdiğini belirtir. Bu varsayılan hiçbiri ise **MF_BYCOMMAND** ya da **MF_BYPOSITION** ayarlanır.|  
|**MF_BYPOSITION**|Parametresi varolan menü öğesini konumunu verdiğini belirtir. İlk öğeyi 0 konumundadır.|  
  
 `nFlags`  
 Belirtir nasıl `nPosition` yorumlanır ve menü öğesine yapılacak değişiklikler hakkında bilgi verir. Ayarlanamaz bayraklar listesi için bkz: [döndürmesini](#appendmenu) üye işlevi.  
  
 `nIDNewItem`  
 Değiştirilen menü öğesi komut Kimliğini belirtir veya `nFlags` ayarlanır **MF_POPUP**, menü işleci ( `HMENU`) açılır menüsünün. `nIDNewItem` Parametresi sayılır (gerekli değil) `nFlags` ayarlanır **MF_SEPARATOR**.  
  
 `lpszNewItem`  
 Yeni menü öğesi içeriğini belirtir. `nFlags` Parametresi yorumlamak için kullanılabilir `lpszNewItem` aşağıdaki yollarla:  
  
|nFlags|LpszNewItem yorumu|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|Uygulama Menü öğesiyle ilişkilendirilmiş ek verileri korumak için kullanabileceğiniz bir uygulama tarafından sağlanan 32-bit değeri içeriyor. Bunu işlediğinde, bu 32-bit değeri uygulama için kullanılabilir **MF_MEASUREITEM** ve **MF_DRAWITEM**.|  
|**MF_STRING**|Sonlandırılmış bir dize veya çok uzun bir işaretçi içeriyor bir `CString`.|  
|**MF_SEPARATOR**|`lpszNewItem` Parametresi göz ardı edilir (gerekli).|  
  
 *pBmp*  
 İşaret eden bir `CBitmap` menü öğesi olarak kullanılan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama içinde değerlerini ayarlayarak menü öğesi'nin yeni durumunu belirtir. `nFlags`. Bu işlev Menü öğesiyle ilişkili bir açılır menü değiştirirse, eski açılır menü bozar ve açılan menü tarafından kullanılan bellek boşaltır.  
  
 Zaman `nIDNewItem` bir açılır menü belirtir, eklenen menü parçası haline gelir. Menüye yok, eklenen menü ayrıca yok. Eklenen bir menü ayrılmış bir `CMenu` çakışmayı önlemek için nesne.  
  
 İçinde bulunan bir menü her (penceresi görüntülenir olsun veya olmasın) bir penceresi değiştirildiğinde, uygulama çağırmalıdır `CWnd::DrawMenuBar`. Varolan menü öğelerini özniteliklerini değiştirmek için bunu kullanmak için çok daha hızlıdır `CheckMenuItem` ve `EnableMenuItem` üye işlevleri.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="operator_hmenu"></a>CMenu::operator HMENU  
 İşleyicisini almak için bu işleci kullanın `CMenu` nesnesi.  
  
```  
operator HMENU() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, işleyicisini `CMenu` nesne; Aksi halde, **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows API'larını doğrudan çağırmak için tanıtıcı kullanabilirsiniz.  
  
##  <a name="operator_neq"></a>CMenu::operator! =  
 İki menüleri eşit değilse mantıksal olarak belirler.  
  
```  
BOOL operator!=(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `menu`  
 A `CMenu` nesne karşılaştırma için.  
  
### <a name="remarks"></a>Açıklamalar  
 Sol tarafta menu nesnesini sağ tarafında menü nesnesine eşit değilse testleri.  
  
##  <a name="operator_eq_eq"></a>CMenu::operator ==  
 İki menüleri mantıksal olarak eşit olup olmadığını belirler.  
  
```  
BOOL operator==(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `menu`  
 A `CMenu` nesne karşılaştırma için.  
  
### <a name="remarks"></a>Açıklamalar  
 Sol tarafta menü nesnesi eşitse sınar (cinsinden `HMENU` değeri) menü nesnesine sağ tarafında.  
  
##  <a name="removemenu"></a>CMenu::RemoveMenu  
 İlişkili bir açılır menü ile menü öğesi menüden siler.  
  
```  
BOOL RemoveMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPosition`  
 Kaldırılacak menü öğesi belirtir. `nFlags` Parametresi yorumlamak için kullanılabilir `nPosition` aşağıdaki yollarla:  
  
|nFlags|NPosition yorumu|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Parametresi varolan menü öğesini komut Kimliğini verdiğini belirtir. Bu varsayılan hiçbiri ise **MF_BYCOMMAND** ya da **MF_BYPOSITION** ayarlanır.|  
|**MF_BYPOSITION**|Parametresi varolan menü öğesini konumunu verdiğini belirtir. İlk öğeyi 0 konumundadır.|  
  
 `nFlags`  
 Belirtir nasıl `nPosition` yorumlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü tekrar kullanılabilmesi için bir açılır menü için işleyici yok. Bu işlevi çağrılmadan önce uygulama çağırabilir `GetSubMenu` açılır almak için üye işlevi `CMenu` yeniden kullanım için nesne.  
  
 İçinde bulunan bir menü her (penceresi görüntülenir olsun veya olmasın) bir penceresi değiştirildiğinde, uygulamayı çağırması gerekir `CWnd::DrawMenuBar`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="setdefaultitem"></a>CMenu::SetDefaultItem  
 Varsayılan menü öğesi için belirtilen menü ayarlar.  
  
```  
BOOL SetDefaultItem(
    UINT uItem,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `uItem`  
 Tanımlayıcı veya yeni varsayılan menü öğesi veya - 1 varsayılan öğe için konumu. Bu parametre anlamını değerine bağlıdır `fByPos`.  
  
 `fByPos`  
 Anlamını belirten değeri `uItem`. Bu parametre ise **FALSE**, `uItem` menü öğesi tanımlayıcısıdır. Aksi takdirde, menü öğesi konumu olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri sıfır olmayan bir değer. İşlev başarısız olursa, dönüş değeri sıfır olur. Genişletilmiş hata bilgilerini için Win32 işlevini [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360), Windows SDK'ın açıklandığı gibi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 işlevi davranışını uygulayan [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996), Windows SDK'ın açıklandığı gibi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="setmenucontexthelpid"></a>CMenu::SetMenuContextHelpId  
 Bir bağlam Yardım kimliği ile ilişkilendirir `CMenu`.  
  
```  
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwContextHelpId`  
 Bağlam Yardımı kimliği ile ilişkilendirilecek `CMenu`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tanımlayıcı menüde tüm öğelerini paylaşma — bir Yardım Bağlam tanıtıcısı tek tek menü öğelerini eklemek mümkün değildir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="setmenuinfo"></a>CMenu::SetMenuInfo  
 Bir menüyü bilgilerini ayarlar.  
  
```  
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpcmi`  
 Bir işaretçi bir [MENUINFO](http://msdn.microsoft.com/library/windows/desktop/ms647575) menü ilgili bilgileri içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri sıfır olmayan; Aksi takdirde, dönüş değeri sıfır olur.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü hakkındaki belirli bilgileri ayarlamak için bu işlevini çağırın.  
  
##  <a name="setmenuitembitmaps"></a>CMenu::SetMenuItemBitmaps  
 Belirtilen bit eşlemler Menü öğesiyle ilişkilendirir.  
  
```  
BOOL SetMenuItemBitmaps(
    UINT nPosition,  
    UINT nFlags,  
    const CBitmap* pBmpUnchecked,  
    const CBitmap* pBmpChecked);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPosition`  
 Değiştirilecek menü öğesi belirtir. `nFlags` Parametresi yorumlamak için kullanılabilir `nPosition` aşağıdaki yollarla:  
  
|nFlags|NPosition yorumu|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Parametresi varolan menü öğesini komut Kimliğini verdiğini belirtir. Bu varsayılan hiçbiri ise **MF_BYCOMMAND** ya da **MF_BYPOSITION** ayarlanır.|  
|**MF_BYPOSITION**|Parametresi varolan menü öğesini konumunu verdiğini belirtir. İlk öğeyi 0 konumundadır.|  
  
 `nFlags`  
 Belirtir nasıl `nPosition` yorumlanır.  
  
 `pBmpUnchecked`  
 İşaretli değildir menü öğeleri için kullanılacak bit eşlem belirtir.  
  
 `pBmpChecked`  
 Denetlenir menü öğeleri için kullanılacak bit eşlem belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü öğesinin işaretli veya işaretsiz olup Windows menü öğesinin yanındaki uygun bit eşlem görüntüler.  
  
 Her iki `pBmpUnchecked` veya `pBmpChecked` olan **NULL**, Windows karşılık gelen bir öznitelik için menü öğesinin yanında bir şey görüntüler. Her iki parametre olması durumunda **NULL**, Windows'un kullandığı varsayılan onay işareti madde işaretli ve madde işaretli olmadığında onay işaretini kaldırır.  
  
 Menü kaldırıldığı zaman bu bit eşlemler yok edilmez; Uygulama bunları destroy gerekir.  
  
 Windows **GetMenuCheckMarkDimensions** işlevi menü öğeleri için kullanılan varsayılan onay işareti boyutlarını alır. Uygulama bu değerleri bu işlev ile sağlanan bit eşlemler uygun boyutunu belirlemek için kullanır. Boyutu almak, bit eşlemler oluşturun ve bunları ayarlayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]  
  
##  <a name="setmenuiteminfo"></a>CMenu::SetMenuItemInfo  
 Menü öğesi hakkında bilgileri değiştirir.  
  
```  
BOOL SetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `uItem`  
 Açıklamasını görmek `uItem` içinde [SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001) Windows SDK'sındaki.  
  
 `lpMenuItemInfo`  
 Açıklamasını görmek `lpmii` içinde **SetMenuItemInfo** Windows SDK'sındaki.  
  
 `fByPos`  
 Açıklamasını görmek `fByPosition` içinde **SetMenuItemInfo** Windows SDK'sındaki.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevi sarmalar [SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001), Windows SDK'sındaki açıklanmıştır.  
  
##  <a name="trackpopupmenu"></a>CMenu::TrackPopupMenu  
 Belirtilen konumda kayan açılır menü görüntüler ve açılır menüsünden öğelerin seçimini izler.  
  
```  
BOOL TrackPopupMenu(
    UINT nFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPCRECT lpRect = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `nFlags`  
 Ekran konumunu ve fare konumuna bayrakları belirtir. Bkz: [TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) kullanılabilir bayrakları listesi.  
  
 *x*  
 Açılır menüsünün ekran koordinatları yatay konumu belirtir. Değerine bağlı olarak `nFlags` parametresi, menü sola hizalı, sağa hizalı veya bu konuma göre ortalanmış olabilir.  
  
 *y*  
 Ekran koordinatları dikey konumu menüsünün üstünde, ekranda belirtir.  
  
 `pWnd`  
 Açılır menü sahibi penceresi tanımlar. Bu parametre olamaz **NULL**olsa bile **TPM_NONOTIFY** bayrağı belirtildi. Bu pencere tüm alan **WM_COMMAND** menüsünde iletileri. Windows 3.1 ve sonraki sürümleri, değil alma penceresi **WM_COMMAND** kadar iletileri `TrackPopupMenu` döndürür. Windows 3. 0'da, pencerenin alır **WM_COMMAND** önce iletileri `TrackPopupMenu` döndürür.  
  
 `lpRect`  
 Yoksayıldı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntemin çağrılması sonucunu döndürür [TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) Windows SDK'sındaki.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayan açılır menü ekranda herhangi bir yerde görünebilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]  
  
##  <a name="trackpopupmenuex"></a>CMenu::TrackPopupMenuEx  
 Belirtilen konumda kayan açılır menü görüntüler ve açılır menüsünden öğelerin seçimini izler.  
  
```  
BOOL TrackPopupMenuEx(
    UINT fuFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPTPMPARAMS lptpm);
```  
  
### <a name="parameters"></a>Parametreler  
 `fuFlags`  
 Genişletilmiş menüsü çeşitli işlevleri belirtir. Tüm değerler listesini ve anlamları için bkz: [TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003).  
  
 *x*  
 Açılır menüsünün ekran koordinatları yatay konumu belirtir.  
  
 *y*  
 Ekran koordinatları dikey konumu menüsünün üstünde, ekranda belirtir.  
  
 `pWnd`  
 Bir işaretçi penceresine oluşturulan menüsünden ileti alma ve açılan menüden yapamaz. Bu pencere herhangi bir geçerli uygulama pencereden olabilir ancak olamaz **NULL**. Belirtirseniz **TPM_NONOTIFY** içinde `fuFlags` parametresi, işlev iletiler göndermez `pWnd`. İşlev gösterdiği penceresi döndürmelidir `pWnd` almak için **WM_COMMAND** ileti.  
  
 *lptpm*  
 İşaretçi bir [TPMPARAMS](http://msdn.microsoft.com/library/windows/desktop/ms647586) menüsünün ekran alanı belirtir yapısı çakışmamalıdır. Bu parametre olabilir **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtirseniz **TPM_RETURNCMD** içinde `fuFlags` dönüş değeri parametresidir kullanıcı seçilen öğeyi menü öğesi tanıtıcısı. Seçim yapmadan kullanıcı menü iptal ederse veya bir hata oluşursa, dönüş değeri 0'dır.  
  
 Belirtmezseniz, **TPM_RETURNCMD** içinde `fuFlags` parametresi, dönüş değeri işlevi başarılı olursa sıfır olmayan ve 0 başarısız olursa. Genişletilmiş hata bilgilerini için arama [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Açıklamalar  
 Kayan açılır menü ekranda herhangi bir yerde görünebilir. Açılır menü oluşturma sırasında hata işleme ile ilgili daha fazla bilgi için bkz: [TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CTRLTEST](../../visual-cpp-samples.md)   
 [MFC örnek DYNAMENU](../../visual-cpp-samples.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)
