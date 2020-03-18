---
title: CMenu sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 1cd7be72dc6c9a38fae4f5ccc1a15c184a2d4466
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79420808"
---
# <a name="cmenu-class"></a>CMenu sınıfı

Windows `HMENU`kapsülleme.

## <a name="syntax"></a>Sözdizimi

```
class CMenu : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CMenu:: CMenu](#cmenu)|`CMenu` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CMenu:: AppendMenu](#appendmenu)|Bu menünün sonuna yeni bir öğe ekler.|
|[CMenu:: Attach](#attach)|Bir `CMenu` nesnesine Windows menü tutamacı ekler.|
|[CMenu:: CheckMenuItem](#checkmenuitem)|Açılır menüdeki bir menü öğesinden yanına onay işareti koyar veya onay işareti kaldırır.|
|[CMenu:: Checkmenuradioıtem](#checkmenuradioitem)|Bir menü öğesinin yanına bir radyo düğmesi koyar ve radyo düğmesini gruptaki diğer tüm menü öğelerinden kaldırır.|
|[CMenu:: CreateMenu](#createmenu)|Boş bir menü oluşturur ve bunu bir `CMenu` nesnesine iliştirir.|
|[CMenu:: CreatePopupMenu](#createpopupmenu)|Boş bir açılır menü oluşturur ve bunu bir `CMenu` nesnesine iliştirir.|
|[CMenu::D eleteMenu](#deletemenu)|Menüden belirtilen öğeyi siler. Menü öğesinde ilişkili bir açılır menü varsa, bu tutamacı açılır menüye yok eder ve tarafından kullanılan belleği serbest bırakır.|
|[CMenu::D eleteTempMap](#deletetempmap)|`FromHandle` üye işlevi tarafından oluşturulan tüm geçici `CMenu` nesneleri siler.|
|[CMenu::D estroyMenu](#destroymenu)|`CMenu` nesnesine ekli menüyü yok eder ve menünün kapladığı belleği serbest bırakır.|
|[CMenu::D etach](#detach)|Bir `CMenu` nesnesinden Windows menü tutamacını ayırır ve tanıtıcıyı döndürür.|
|[CMenu::D rawItem](#drawitem)|Sahip tarafından çizilmiş bir menünün görsel bir yönü değiştiğinde Framework tarafından çağırılır.|
|[CMenu:: EnableMenuItem](#enablemenuitem)|Bir menü öğesini etkinleştirilir, devre dışı bırakır veya (griler).|
|[CMenu:: FromHandle](#fromhandle)|Windows menü tutamacı verilen bir `CMenu` nesnesine bir işaretçi döndürür.|
|[CMenu:: Getdefaultıtem](#getdefaultitem)|Belirtilen menüdeki varsayılan menü öğesini belirler.|
|[CMenu:: GetMenuContextHelpId](#getmenucontexthelpid)|Menüsüyle ilişkili Yardım bağlamı KIMLIĞINI alır.|
|[CMenu:: Getmenuınfo](#getmenuinfo)|Belirli bir menüdeki bilgileri alır.|
|[CMenu:: GetMenuItemCount](#getmenuitemcount)|Açılır veya üst düzey menüdeki öğelerin sayısını belirler.|
|[CMenu:: Getmenuıtemıd](#getmenuitemid)|Belirtilen konumda bulunan bir menü öğesi için menü öğesi tanımlayıcıyı edinir.|
|[CMenu:: Getmenuıiteınfo](#getmenuiteminfo)|Bir menü öğesi hakkında bilgi alır.|
|[CMenu:: GetMenuState](#getmenustate)|Belirtilen menü öğesinin durumunu veya açılan menüdeki öğe sayısını döndürür.|
|[CMenu:: GetMenuString](#getmenustring)|Belirtilen menü öğesinin etiketini alır.|
|[CMenu:: GetSafeHmenu](#getsafehmenu)|Bu `CMenu` nesnesi tarafından Sarmalanan `m_hMenu` döndürür.|
|[CMenu:: Getalt menüsü](#getsubmenu)|Açılır menüye yönelik bir işaretçi alır.|
|[CMenu:: InsertMenu](#insertmenu)|Belirtilen konumda yeni bir menü öğesi ekler ve diğer öğeleri menünün altına taşır.|
|[CMenu:: InsertMenuItem](#insertmenuitem)|Menüde belirtilen konuma yeni bir menü öğesi ekler.|
|[CMenu:: LoadMenu](#loadmenu)|Yürütülebilir dosyadan bir menü kaynağı yükler ve bir `CMenu` nesnesine ekler.|
|[CMenu:: Loadmenudolaylı](#loadmenuindirect)|Bellekteki bir menü şablonundan bir menü yükler ve bir `CMenu` nesnesine iliştirir.|
|[CMenu:: MeasureItem](#measureitem)|Sahip tarafından çizilmiş bir menü oluşturulduğunda menü boyutlarının belirlenmesi için Framework tarafından çağırılır.|
|[CMenu:: ModifyMenu](#modifymenu)|Belirtilen konumda varolan bir menü öğesini değiştirir.|
|[CMenu:: RemoveMenu](#removemenu)|Belirtilen menüden ilişkili bir açılır menü içeren bir menü öğesini siler.|
|[CMenu:: Setdefaultıtem](#setdefaultitem)|Belirtilen menü için varsayılan menü öğesini ayarlar.|
|[CMenu:: SetMenuContextHelpId](#setmenucontexthelpid)|Yardım bağlamı KIMLIĞINI menüsüyle ilişkilendirilecek şekilde ayarlar.|
|[CMenu:: Setmenuınfo](#setmenuinfo)|Belirli bir menüdeki bilgileri ayarlar.|
|[CMenu:: SetMenuItemBitmaps](#setmenuitembitmaps)|Belirtilen onay işareti bit eşlemlerini bir menü öğesiyle ilişkilendirir.|
|[CMenu:: Setmenuiteınfo](#setmenuiteminfo)|Bir menü öğesiyle ilgili bilgileri değiştirir.|
|[CMenu:: TrackPopupMenu](#trackpopupmenu)|Belirtilen konumda kayan bir açılır menü görüntüler ve açılır menüdeki öğelerin seçimini izler.|
|[CMenu:: TrackPopupMenuEx](#trackpopupmenuex)|Belirtilen konumda kayan bir açılır menü görüntüler ve açılır menüdeki öğelerin seçimini izler.|

### <a name="public-operators"></a>Ortak İşleçler

|Name|Açıklama|
|----------|-----------------|
|[CMenu:: operator HMENU](#operator_hmenu)|Menü nesnesinin tanıtıcısını alır.|
|[CMenu:: operator! =](#operator_neq)|İki menü nesnesinin eşit olup olmadığını belirler.|
|[CMenu:: operator = =](#operator_eq_eq)|İki menü nesnesinin eşit olup olmadığını belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Name|Açıklama|
|----------|-----------------|
|[CMenu:: m_hMenu](#m_hmenu)|`CMenu` nesnesine eklenen Windows menüsüne yönelik tanıtıcıyı belirtir.|

## <a name="remarks"></a>Açıklamalar

Bir menü oluşturmak, izlemek, güncelleştirmek ve yok etmek için üye işlevleri sağlar.

Yığın çerçevesinde yerel olarak bir `CMenu` nesnesi oluşturun, sonra yeni menüyü gerektiği gibi işlemek için `CMenu`üye işlevlerini çağırın. Sonra, menüyü bir pencereye ayarlamak için [CWnd:: SetMenu](../../mfc/reference/cwnd-class.md#setmenu) çağırın ve ardından `CMenu` nesnesinin [Detach](#detach) üye işlevine yapılan bir çağrı tarafından hemen izlenir. `CWnd::SetMenu` member işlevi pencerenin menüsünü yeni menüye ayarlar, pencerenin menü değişikliğini yansıtacak şekilde yeniden çizilmesini sağlar ve ayrıca menünün sahipliğini pencereye geçirir. `Detach` çağrısı HMENU 'yi `CMenu` nesnesinden ayırır, böylece yerel `CMenu` değişkeni kapsam dışına geçtiğinde, `CMenu` nesne yıkıcısı artık sahip olmadığı bir menüyü yok etmeye çalışmaz. Pencere yok edildiğinde menü otomatik olarak yok edilir.

Bellek içindeki bir şablondan bir menü oluşturmak için [Loadmenudolaylı](#loadmenuindirect) üye işlevini kullanabilirsiniz, ancak bir [LoadMenu](#loadmenu) çağrısıyla bir kaynaktan oluşturulmuş bir menü daha kolay korunabilir ve menü kaynağının kendisi Menü Düzenleyicisi tarafından oluşturulup değiştirilebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMenu`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="appendmenu"></a>CMenu:: AppendMenu

Menünün sonuna yeni bir öğe ekler.

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

*nFlags*<br/>
Menüye eklendiğinde yeni menü öğesinin durumu hakkında bilgi belirtir. Bu, açıklamalar bölümünde listelenen değerlerden birini veya daha fazlasını içerir.

*nIDNewItem*<br/>
Yeni menü öğesinin komut KIMLIĞINI ya da *nFlags* mf_popup, bir açılır menünün menü tutamacını (`HMENU`) belirler. *NFlags* MF_SEPARATOR olarak ayarlandıysa *nIDNewItem* parametresi yok sayılır (gerekli değildir).

*lpszNewItem*<br/>
Yeni menü öğesinin içeriğini belirtir. *NFlags* parametresi, *lpszNewItem* aşağıdaki şekilde yorumlamak için kullanılır:

|nFlags|LpszNewItem yorumu|
|------------|-----------------------------------|
|MF_OWNERDRAW|Uygulamanın menü öğesiyle ilişkili ek verileri sürdürmek için kullanabileceği, uygulama tarafından sağlanan 32 bitlik bir değer içerir. Bu 32 bit değeri, WM_MEASUREITEM ve WM_DRAWITEM iletileri işlerken uygulama tarafından kullanılabilir. Değer, bu iletilerle sağlanan yapının `itemData` üyesinde saklanır.|
|MF_STRING|Null ile sonlandırılmış bir dizeye yönelik bir işaretçi içerir. Bu, varsayılan yorumlamasıdır.|
|MF_SEPARATOR|*LpszNewItem* parametresi yok sayılır (gerekli değildir).|

*pBmp*<br/>
Menü öğesi olarak kullanılacak bir `CBitmap` nesnesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulama, *nFlags*içindeki değerleri ayarlayarak menü öğesinin durumunu belirtebilir. *NIDNewItem* bir açılan menüyü belirttiğinde, eklendiği menünün bir parçası haline gelir. Bu menü yok edildiğinde, eklenen menü de yok edilir. Çakışmayı önlemek için eklenen menünün bir `CMenu` nesnesinden ayrılması gerekir. MF_STRING ve MF_OWNERDRAW `AppendMenu`bit eşlem sürümü için geçerli değildir.

Aşağıdaki listede, *nFlags*içinde ayarlanmakta olabilecek bayraklar açıklanmaktadır:

- MF_CHECKED, varsayılan onay işaretini öğenin yanına yerleştirmek için MF_UNCHECKED bir geçiş Işlevi görür. Uygulama Check-Mark bit eşlemler (bkz. [Setmenuitembitmaps](#setmenuitembitmaps) üye işlevine bakın), "onay işareti açık" bit eşlemi görüntülenir.

- MF_UNCHECKED öğenin yanındaki onay işaretini kaldırmak için MF_CHECKED bir geçiş Işlevi görür. Uygulama Check-Mark bit eşlemler (`SetMenuItemBitmaps` üye işlevine bakın), "onay işareti kapalı" bit eşlemi görüntülenir.

- MF_DISABLED menü öğesini devre dışı bırakarak seçilemez ancak onu göstermez.

- MF_ENABLED, menü öğesinin seçilebilmesi ve soluk durumundan geri yüklenmesi için etkinleştirilir.

- MF_GRAYED, menü öğesini seçilemeyecek ve onları belirleyemeyecek şekilde devre dışı bırakır.

- MF_MENUBARBREAK, öğeyi statik menülere veya açılan menülerde yeni bir sütuna yeni bir satıra koyar. Yeni açılan menü sütunu, bir dikey bölme çizgisi ile eski sütundan ayrılacaktır.

- MF_MENUBREAK, öğeyi statik menülere veya açılan menülerde yeni bir sütuna yeni bir satıra koyar. Sütunlar arasına bölme çizgisi yerleştirilmemiş.

- MF_OWNERDRAW, öğenin bir sahip çizim öğesi olduğunu belirtir. Menü ilk kez görüntülendiğinde, menünün sahibi olan pencere, menü öğesinin yüksekliğini ve genişliğini alan WM_MEASUREITEM bir ileti alır. WM_DRAWITEM ileti, sahibin menü öğesinin görsel görünümünü güncelleştirmesi gerektiğinde gönderilir. Bu seçenek, üst düzey menü öğesi için geçerli değildir.

- MF_POPUP, menü öğesinin onunla ilişkili bir açılır menü olduğunu belirtir. ID parametresi, öğe ile ilişkilendirilecek bir açılır menüye yönelik bir tanıtıcı belirtir. Bu, bir açılır menü öğesine bir üst düzey açılır menü veya hiyerarşik açılan menü eklemek için kullanılır.

- MF_SEPARATOR yatay bölme çizgisi çizer. Yalnızca bir açılır menüde kullanılabilir. Bu satır soluk, devre dışı veya vurgulanmış olamaz. Diğer parametreler yok sayılır.

- MF_STRING, menü öğesinin bir karakter dizesi olduğunu belirtir.

Aşağıdaki grupların her biri birbirini dışlayan ve birlikte kullanılamayan bayrakları listeler:

- MF_DISABLED, MF_ENABLED ve MF_GRAYED

- MF_STRING, MF_OWNERDRAW, MF_SEPARATOR ve bit eşlem sürümü

- MF_MENUBARBREAK ve MF_MENUBREAK

- MF_CHECKED ve MF_UNCHECKED

Pencerede bulunan bir menü değiştirildiğinde (pencerenin görüntülenip görüntülenmediğini belirtir), uygulama [CWnd::D rawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)öğesini çağırmalıdır.

### <a name="example"></a>Örnek

  [CMenu:: CreateMenu](#createmenu)örneğine bakın.

##  <a name="attach"></a>CMenu:: Attach

Varolan bir Windows menüsünü `CMenu` nesnesine iliştirir.

```
BOOL Attach(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

*hMenu*<br/>
Bir Windows menüsü için bir tanıtıcı belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `CMenu` nesnesine zaten bir menü eklenmişse kullanılmamalıdır. Menü tanıtıcısı `m_hMenu` veri üyesinde depolanır.

İşlemek istediğiniz menü zaten bir pencereyle ilişkili ise, bir menü tutamacı almak için [CWnd:: GetMenu](../../mfc/reference/cwnd-class.md#getmenu) işlevini kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

##  <a name="checkmenuitem"></a>CMenu:: CheckMenuItem

Açılır menüdeki menü öğelerinden onay işaretleri ekler veya onay işaretlerini kaldırır.

```
UINT CheckMenuItem(
    UINT nIDCheckItem,
    UINT nCheck);
```

### <a name="parameters"></a>Parametreler

*nIDCheckItem*<br/>
Denetlenecek menü öğesini, *nCheck*tarafından belirlendiği şekilde belirtir.

*Nhatayla*<br/>
Menü öğesini nasıl denetleyeceğini ve menüde öğenin konumunun nasıl belirleneceğini belirtir. *NCheck* parametresi, MF_BYPOSITION veya MF_BYCOMMAND bayraklarıyla bir MF_CHECKED veya MF_UNCHECKED birleşimi olabilir. Bu bayraklar bit düzeyinde OR işleci kullanılarak birleştirilebilir. Bunlar aşağıdaki anlamlara sahiptir:

- MF_BYCOMMAND, parametrenin mevcut menü öğesinin komut KIMLIĞINI verir olduğunu belirtir. Bu varsayılandır.

- MF_BYPOSITION, parametrenin mevcut menü öğesinin konumunu olduğunu belirtir. İlk öğe 0 konumundayken.

- MF_CHECKED, varsayılan onay işaretini öğenin yanına yerleştirmek için MF_UNCHECKED bir geçiş Işlevi görür.

- MF_UNCHECKED öğenin yanındaki onay işaretini kaldırmak için MF_CHECKED bir geçiş Işlevi görür.

### <a name="return-value"></a>Dönüş Değeri

Öğenin önceki durumu: MF_CHECKED veya MF_UNCHECKED ya da menü öğesi yoksa 0xFFFFFFFF.

### <a name="remarks"></a>Açıklamalar

*NIDCheckItem* parametresi değiştirilecek öğeyi belirtir.

*NIDCheckItem* parametresi bir açılır menü öğesini ve bir menü öğesini tanımlayabilir. Bir açılır menü öğesini denetlemek için özel bir adım gerekmez. Üst düzey menü öğeleri denetlenemiyor. Bir açılır menü öğesi kendisiyle ilişkilendirilmiş bir menü öğesi tanımlayıcısına sahip olmadığından konuma göre denetlenmelidir.

### <a name="example"></a>Örnek

  [CMenu:: GetMenuState](#getmenustate)örneğine bakın.

##  <a name="checkmenuradioitem"></a>CMenu:: Checkmenuradioıtem

Belirtilen bir menü öğesini denetler ve bunu bir radyo öğesi yapar.

```
BOOL CheckMenuRadioItem(
    UINT nIDFirst,
    UINT nIDLast,
    UINT nIDItem,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

*nIDFirst*<br/>
Radyo düğmesi grubundaki ilk menü öğesini, *nFlags*değerine bağlı olarak bir ID veya bir konum olarak belirtir.

*nIDLast*<br/>
Radyo düğmesi grubundaki son menü öğesini, *nFlags*değerine bağlı olarak bir ID veya bir konum olarak belirtir.

*Nidıtem*<br/>
Gruptaki bir radyo düğmesi ile denetlenecek olan öğeyi, *nFlags*değerine bağlı olarak bir ID veya bir konum olarak belirtir.

*nFlags*<br/>
*Nidfirst*, *nIDLast*ve *nidıtem* 'nin yorumunu aşağıdaki şekilde belirtir:

|nFlags|Yorum|
|------------|--------------------|
|MF_BYCOMMAND|Parametrenin mevcut menü öğesinin komut KIMLIĞINI verir olduğunu belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmamışsa bu varsayılandır.|
|MF_BYPOSITION|Parametrenin mevcut menü öğesinin konumunu olduğunu belirtir. İlk öğe 0 konumundayken.|

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde 0

### <a name="remarks"></a>Açıklamalar

Aynı zamanda, işlev ilişkili gruptaki diğer tüm menü öğelerini denetler ve bu öğeler için radyo öğesi türü bayrağını temizler. İşaretlenen öğe, onay işareti bit eşlemi yerine radyo düğmesi (veya madde işareti) kullanılarak görüntülenir.

### <a name="example"></a>Örnek

  [ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range)için örneğe bakın.

##  <a name="cmenu"></a>CMenu:: CMenu

Boş bir menü oluşturur ve bunu bir `CMenu` nesnesine iliştirir.

```
CMenu();
```

### <a name="remarks"></a>Açıklamalar

Menü, `CMenu:` oluşturma veya yükleme üyesi işlevlerinden birini çağırana kadar oluşturulmaz

- [CreateMenu](#createmenu)

- [CreatePopupMenu](#createpopupmenu)

- [LoadMenu](#loadmenu)

- [Loadmenudolaylı](#loadmenuindirect)

- [Attach](#attach)

##  <a name="createmenu"></a>CMenu:: CreateMenu

Bir menü oluşturur ve `CMenu` nesnesine iliştirir.

```
BOOL CreateMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Menü başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Menü başlangıçta boştur. Menü öğeleri `AppendMenu` veya `InsertMenu` member işlevi kullanılarak eklenebilir.

Menü bir pencereye atanırsa, pencere yok edildiğinde otomatik olarak yok edilir.

Çıkmadan önce, bir pencere bir pencereye atanmadığı takdirde bir menü ile ilişkili sistem kaynaklarını boş olmalıdır. Bir uygulama, [Destroyımenu](#destroymenu) üye işlevini çağırarak bir menüyü serbest bırakır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]

##  <a name="createpopupmenu"></a>CMenu:: CreatePopupMenu

Bir açılır menü oluşturur ve `CMenu` nesnesine iliştirir.

```
BOOL CreatePopupMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Açılır menü başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Menü başlangıçta boştur. Menü öğeleri `AppendMenu` veya `InsertMenu` member işlevi kullanılarak eklenebilir. Uygulama, varolan bir menü veya açılır menüye açılan menüyü ekleyebilir. `TrackPopupMenu` member işlevi, bu menüyü kayan bir açılır menü olarak göstermek ve açılır menüdeki seçimleri izlemek için kullanılabilir.

Menü bir pencereye atanırsa, pencere yok edildiğinde otomatik olarak yok edilir. Menü var olan bir menüye eklenirse, bu menü yok edildiğinde otomatik olarak yok edilir.

Çıkmadan önce, menü bir pencereye atanmadığı takdirde bir uygulamanın bir açılır menü ile ilişkili sistem kaynaklarını serbest olması gerekir. Bir uygulama, [Destroyımenu](#destroymenu) üye işlevini çağırarak bir menüyü serbest bırakır.

### <a name="example"></a>Örnek

  [CMenu:: CreateMenu](#createmenu)örneğine bakın.

##  <a name="deletemenu"></a>CMenu::D eleteMenu

Menüden bir öğeyi siler.

```
BOOL DeleteMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

*Sağda*<br/>
Silinecek menü öğesini, *nFlags*tarafından belirlendiği şekilde belirtir.

*nFlags*<br/>
, *NPosition* öğesini aşağıdaki şekilde yorumlamak için kullanılır:

|nFlags|NPosition yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametrenin mevcut menü öğesinin komut KIMLIĞINI verir olduğunu belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmamışsa bu varsayılandır.|
|MF_BYPOSITION|Parametrenin mevcut menü öğesinin konumunu olduğunu belirtir. İlk öğe 0 konumundayken.|

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Menü öğesi ilişkili bir açılır menü içeriyorsa, `DeleteMenu` açılır menüye tutamacı yok eder ve açılır menü tarafından kullanılan belleği serbest bırakır.

Pencerede bulunan bir menü değiştirildiğinde (pencerenin görüntülenip görüntülenmediğini belirtir), uygulamanın [CWnd::D rawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)çağrısı gerekir.

### <a name="example"></a>Örnek

  [CWnd:: GetMenu](../../mfc/reference/cwnd-class.md#getmenu)örneğine bakın.

##  <a name="deletetempmap"></a>CMenu::D eleteTempMap

`CWinApp` boşta zaman işleyicisi tarafından otomatik olarak çağırılır, [FromHandle](#fromhandle) üye işlevi tarafından oluşturulan geçici `CMenu` nesnelerini siler.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Açıklamalar

`DeleteTempMap`, `CMenu` nesne silinmeden önce geçici bir `CMenu` nesnesine eklenen Windows menü nesnesini ayırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]

##  <a name="destroymenu"></a>CMenu::D estroyMenu

Menüyü ve kullanılan tüm Windows kaynaklarını yok eder.

```
BOOL DestroyMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Menü yok edildiğinde sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Menü, yok edileceği için `CMenu` nesnesinden ayrılır. Windows `DestroyMenu` işlevi `CMenu` yıkıcısında otomatik olarak çağırılır.

### <a name="example"></a>Örnek

  [CMenu:: CreateMenu](#createmenu)örneğine bakın.

##  <a name="detach"></a>CMenu::D etach

Bir `CMenu` nesnesinden Windows menüsünü ayırır ve tanıtıcıyı döndürür.

```
HMENU Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, HMENU türündeki tanıtıcı bir Windows menüsüne; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

`m_hMenu` veri üyesi NULL olarak ayarlandı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

##  <a name="drawitem"></a>CMenu::D rawItem

Sahip tarafından çizilmiş bir menünün görsel bir yönü değiştiğinde Framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Gerekli çizim türü hakkında bilgi içeren [Drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`DRAWITEMSTRUCT` yapısının `itemAction` üyesi, gerçekleştirilecek çizim eylemini tanımlar. Sahip çizim `CMenu` nesnesi için çizim uygulamak üzere bu üye işlevini geçersiz kılın. Uygulamanın, bu üye işlevin sonlandırılması için *Lpdrawitemstruct* içinde sağlanan görüntüleme bağlamı için seçilen tüm grafik cihaz ARABIRIMI (GDI) nesnelerini geri yüklemesi gerekir.

`DRAWITEMSTRUCT` yapısının açıklaması için bkz. [CWnd:: OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) .

### <a name="example"></a>Örnek

Aşağıdaki kod MFC [ctrltest](../../overview/visual-cpp-samples.md) örneğinden verilmiştir:

[!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]

##  <a name="enablemenuitem"></a>CMenu:: EnableMenuItem

Bir menü öğesini etkinleştirilir, devre dışı bırakır veya bir şekilde dönüştürür.

```
UINT EnableMenuItem(
    UINT nIDEnableItem,
    UINT nEnable);
```

### <a name="parameters"></a>Parametreler

*Nıdenableıtem*<br/>
Etkinleştirilecek menü öğesini, *nEnable*tarafından belirlendiği şekilde belirtir. Bu parametre, açılan menü öğelerinin yanı sıra standart menü öğelerini belirtebilir.

*nEtkinleştir*<br/>
Gerçekleştirilecek eylemi belirtir. MF_BYCOMMAND veya MF_BYPOSITION ile MF_DISABLED, MF_ENABLED veya MF_GRAYED bir birleşimi olabilir. Bu değerler bit düzeyinde OR işleci kullanılarak birleştirilebilir. Bu değerler aşağıdaki anlamlara sahiptir:

- MF_BYCOMMAND, parametrenin mevcut menü öğesinin komut KIMLIĞINI verir olduğunu belirtir. Bu varsayılandır.

- MF_BYPOSITION, parametrenin mevcut menü öğesinin konumunu olduğunu belirtir. İlk öğe 0 konumundayken.

- MF_DISABLED menü öğesini devre dışı bırakarak seçilemez ancak onu göstermez.

- MF_ENABLED, menü öğesinin seçilebilmesi ve soluk durumundan geri yüklenmesi için etkinleştirilir.

- MF_GRAYED, menü öğesini seçilemeyecek ve onları belirleyemeyecek şekilde devre dışı bırakır.

### <a name="return-value"></a>Dönüş Değeri

Önceki durum (MF_DISABLED, MF_ENABLED veya MF_GRAYED) veya geçerli değilse-1.

### <a name="remarks"></a>Açıklamalar

[CreateMenu](#createmenu), [InsertMenu](#insertmenu), [ModifyMenu](#modifymenu)ve [loadmenudolaylı](#loadmenuindirect) üye işlevleri, bir menü öğesinin durumunu (etkin, devre dışı veya soluk) de ayarlayabilir.

MF_BYPOSITION değerinin kullanılması, uygulamanın doğru `CMenu`kullanmasını gerektirir. Menü çubuğunun `CMenu` kullanılırsa, üst düzey bir menü öğesi (menü çubuğundaki bir öğe) etkilenir. Bir açılır veya iç içe açılan menüdeki bir öğenin durumunu konuma göre ayarlamak için, bir uygulamanın açılır menünün `CMenu` belirtmesi gerekir.

Bir uygulama MF_BYCOMMAND bayrağını belirttiğinde, Windows, `CMenu`alt öğe olan tüm açılır menü öğelerini denetler; Bu nedenle, yinelenen menü öğeleri mevcut değilse, menü çubuğunun `CMenu` kullanımı yeterlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]

##  <a name="fromhandle"></a>CMenu:: FromHandle

Bir menüye Windows tutamacı verilen `CMenu` nesnesine yönelik bir işaretçi döndürür.

```
static CMenu* PASCAL FromHandle(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

*hMenu*<br/>
Bir menüye bir Windows tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Geçici veya kalıcı olabilecek bir `CMenu` işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir `CMenu` nesnesi Windows menü nesnesine zaten iliştirilmişse, geçici bir `CMenu` nesnesi oluşturulur ve eklenir.

Bu geçici `CMenu` nesnesi yalnızca uygulamanın olay döngüsünde bir sonraki kez boş kalma süresine kadar geçerlidir. bu süre, tüm geçici nesneler silinir.

### <a name="example"></a>Örnek

  [CMenu:: CreateMenu](#createmenu)örneğine bakın.

##  <a name="getdefaultitem"></a>CMenu:: Getdefaultıtem

Belirtilen menüdeki varsayılan menü öğesini belirler.

```
UINT GetDefaultItem(
    UINT gmdiFlags,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*Gmdıflags*<br/>
İşlevin menü öğelerini nasıl arayacağını belirten değer. Bu parametre None, One veya aşağıdaki değerlerin bir birleşimi olabilir:

|Değer|Açıklama|
|-----------|-------------|
|GMDI_GOINTOPOPUPS|Varsayılan öğe alt menüyü açan bir öğe ise, işlevin karşılık gelen alt menüde yinelemeli olarak aranacağını belirtir. Alt menüde varsayılan öğe yoksa, dönüş değeri alt menüyü açan öğeyi tanımlar.<br /><br /> Varsayılan olarak, işlev, alt menüyü açan bir öğe olup olmamasına bakılmaksızın, belirtilen menüdeki ilk varsayılan öğeyi döndürür.|
|GMDI_USEDISABLED|Devre dışı bırakılmış olsa bile, işlevin varsayılan bir öğe döndürmeme olduğunu belirtir.<br /><br /> Varsayılan olarak, işlev devre dışı veya gri öğeleri atlar.|

*fByPos*<br/>
Menü öğesinin tanımlayıcısının veya konumunun alınıp alınmayacağını belirten değer. Bu parametre FALSE ise, tanımlayıcı döndürülür. Aksi takdirde, konum döndürülür.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri, menü öğesinin tanımlayıcısıdır veya konumudur. İşlev başarısız olursa, dönüş değeri-1 ' dir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, [GetMenuDefaultItem](/windows/win32/api/winuser/nf-winuser-getmenudefaultitem)Win32 işlevinin davranışını uygular.

### <a name="example"></a>Örnek

  [CMenu:: InsertMenu](#insertmenu)örneğine bakın.

##  <a name="getmenucontexthelpid"></a>CMenu:: GetMenuContextHelpId

`CMenu`ilişkili bağlam yardım KIMLIĞINI alır.

```
DWORD GetMenuContextHelpId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bağlam yardım KIMLIĞI, şu anda varsa `CMenu` ile ilişkilidir; Aksi halde sıfır.

### <a name="example"></a>Örnek

  [CMenu:: InsertMenu](#insertmenu)örneğine bakın.

##  <a name="getmenuinfo"></a>CMenu:: Getmenuınfo

Bir menü için bilgileri alır.

```
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;
```

### <a name="parameters"></a>Parametreler

*lpcmı*<br/>
Menü bilgilerini içeren bir [MENUINFO](/windows/win32/api/winuser/ns-winuser-menuinfo) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri sıfır dışında olur; Aksi takdirde, dönüş değeri sıfırdır.

### <a name="remarks"></a>Açıklamalar

Menü hakkında bilgi almak için bu işlevi çağırın.

##  <a name="getmenuitemcount"></a>CMenu:: GetMenuItemCount

Açılır veya üst düzey menüdeki öğelerin sayısını belirler.

```
UINT GetMenuItemCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa menüdeki öğelerin sayısı; Aksi takdirde-1.

### <a name="example"></a>Örnek

  [CWnd:: GetMenu](../../mfc/reference/cwnd-class.md#getmenu)örneğine bakın.

##  <a name="getmenuitemid"></a>CMenu:: Getmenuıtemıd

*NPos*tarafından tanımlanan konumda bulunan bir menü öğesi için menü öğesi tanımlayıcısını alır.

```
UINT GetMenuItemID(int nPos) const;
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
KIMLIĞI alınmakta olan menü öğesinin konumunu (sıfır tabanlı) belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, bir açılır menüdeki belirtilen öğenin öğe KIMLIĞI. Belirtilen öğe bir açılır menü ise (açılır menüdeki bir öğeden farklı olarak), dönüş değeri-1 ' dir. *NPos* bir ayırıcı menü öğesine karşılık geliyorsa, dönüş değeri 0 ' dır.

### <a name="example"></a>Örnek

  [CMenu:: InsertMenu](#insertmenu)örneğine bakın.

##  <a name="getmenuiteminfo"></a>CMenu:: Getmenuıiteınfo

Bir menü öğesi hakkında bilgi alır.

```
BOOL GetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*uItem*<br/>
Hakkında bilgi almak için menü öğesinin tanımlayıcısı veya konumu. Bu parametrenin anlamı `ByPos`değerine bağlıdır.

*Lpmenuitemınfo*<br/>
Menü ile ilgili bilgiler içeren, Windows SDK bölümünde açıklandığı gibi bir [Menuiteınfo](/windows/win32/api/winuser/ns-winuser-menuiteminfow)işaretçisi.

*fByPos*<br/>
`nIDItem`anlamını belirten değer. Varsayılan olarak, `ByPos`, uItem 'ın bir menü öğesi tanımlayıcısı olduğunu gösterir. `ByPos` FALSE olarak ayarlanmamışsa, bir menü öğesi konumunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri sıfır dışında olur. İşlev başarısız olursa, dönüş değeri sıfırdır. Genişletilmiş hata bilgilerini almak için Windows SDK [Win32 işlevini kullanın](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror), burada açıklandığı gibi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, [Getmenuıiteınfo](/windows/win32/api/winuser/nf-winuser-getmenuiteminfow)Win32 işlevinin davranışını uygular. `GetMenuItemInfo`MFC uygulamasında, bir menü için tanıtıcı kullanacağınızı unutmayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]

##  <a name="getmenustate"></a>CMenu:: GetMenuState

Belirtilen menü öğesinin durumunu veya açılan menüdeki öğe sayısını döndürür.

```
UINT GetMenuState(
    UINT nID,
    UINT nFlags) const;
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
*NFlags*tarafından belirlendiği gibi menü öğesi kimliğini belirtir.

*nFlags*<br/>
*NID*'nin doğasını belirtir. Aşağıdaki değerlerden biri olabilir:

- MF_BYCOMMAND, parametrenin mevcut menü öğesinin komut KIMLIĞINI verir olduğunu belirtir. Bu varsayılandır.

- MF_BYPOSITION, parametrenin mevcut menü öğesinin konumunu olduğunu belirtir. İlk öğe 0 konumundayken.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe yoksa 0xFFFFFFFF değeri. *NID* bir açılan menüyü tanımlarsa, yüksek sıralı bayt açılır menüdeki öğelerin sayısını içerir ve düşük sıralı bayt açılır menü ile ilişkili menü bayraklarını içerir. Aksi takdirde, dönüş değeri aşağıdaki listedeki değerlerin bir maskesidir (Boolean veya) (Bu maske, *NID* tarafından tanımlanan menü öğesinin durumunu açıklar):

- MF_CHECKED, varsayılan onay işaretini öğenin yanına yerleştirmek için MF_UNCHECKED bir geçiş Işlevi görür. Uygulama Check-Mark bit eşlemler (`SetMenuItemBitmaps` üye işlevine bakın) olduğunda, "onay işareti açık" bit eşlem görüntülenir.

- MF_DISABLED menü öğesini devre dışı bırakarak seçilemez ancak onu göstermez.

- MF_ENABLED, menü öğesinin seçilebilmesi ve soluk durumundan geri yüklenmesi için etkinleştirilir. Bu sabitin değerinin 0 olduğunu unutmayın. Bu değer kullanılırken bir uygulamanın hata için 0 ile test edilmemesi gerekir.

- MF_GRAYED, menü öğesini seçilemeyecek ve onları belirleyemeyecek şekilde devre dışı bırakır.

- MF_MENUBARBREAK, öğeyi statik menülere veya açılan menülerde yeni bir sütuna yeni bir satıra koyar. Yeni açılan menü sütunu, bir dikey bölme çizgisi ile eski sütundan ayrılacaktır.

- MF_MENUBREAK, öğeyi statik menülere veya açılan menülerde yeni bir sütuna yeni bir satıra koyar. Sütunlar arasına bölme çizgisi yerleştirilmemiş.

- MF_SEPARATOR yatay bölme çizgisi çizer. Yalnızca bir açılır menüde kullanılabilir. Bu satır soluk, devre dışı veya vurgulanmış olamaz. Diğer parametreler yok sayılır.

- MF_UNCHECKED öğenin yanındaki onay işaretini kaldırmak için MF_CHECKED bir geçiş Işlevi görür. Uygulama Check-Mark bit eşlemler (`SetMenuItemBitmaps` üye işlevine bakın), "onay işareti kapalı" bit eşlemi görüntülenir. Bu sabitin değerinin 0 olduğunu unutmayın. Bu değer kullanılırken bir uygulamanın hata için 0 ile test edilmemesi gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]

##  <a name="getmenustring"></a>CMenu:: GetMenuString

Belirtilen menü öğesinin etiketini belirtilen arabelleğe kopyalar.

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

*Nidıtem*<br/>
Menü öğesinin tamsayı tanımlayıcısını veya menüdeki menü öğesinin, *nFlags*değerine bağlı olarak sapmasını belirtir.

*Lpstrıng*<br/>
Etiketi alacak olan arabelleğe işaret eder.

*rString*<br/>
Kopyalanmış menü dizesini almak için bir `CString` nesnesine başvuru.

*nMaxCount*<br/>
Kopyalanacak etiketin en büyük uzunluğunu (karakter olarak) belirtir. Etiket *nMaxCount*'da belirtilen en büyük boyuttan uzunsa, ek karakterler kesilir.

*nFlags*<br/>
*Nidıtem* parametresinin yorumunu belirtir. Aşağıdaki değerlerden biri olabilir:

|nFlags|Nidıtem yorumu|
|------------|-------------------------------|
|MF_BYCOMMAND|Parametrenin mevcut menü öğesinin komut KIMLIĞINI verir olduğunu belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmamışsa bu varsayılandır.|
|MF_BYPOSITION|Parametrenin mevcut menü öğesinin konumunu olduğunu belirtir. İlk öğe 0 konumundayken.|

### <a name="return-value"></a>Dönüş Değeri

Null Sonlandırıcı dahil değil, arabelleğe kopyalanmış olan gerçek karakter sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

*NMaxCount* parametresi, bir dizeyi sonlandıran null karaktere uyum sağlamak için Etiketteki karakter sayısından bir büyük olmalıdır.

### <a name="example"></a>Örnek

  [CMenu:: InsertMenu](#insertmenu)örneğine bakın.

##  <a name="getsafehmenu"></a>CMenu:: GetSafeHmenu

Bu `CMenu` nesne veya NULL`CMenu` işaretçisi tarafından Sarmalanan HMENU 'yi döndürür.

```
HMENU GetSafeHmenu() const;
```

### <a name="example"></a>Örnek

  [CMenu:: LoadMenu](#loadmenu)örneğine bakın.

##  <a name="getsubmenu"></a>CMenu:: Getalt menüsü

Bir açılır menünün `CMenu` nesnesini alır.

```
CMenu* GetSubMenu(int nPos) const;
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Menüde bulunan açılır menünün konumunu belirtir. İlk menü öğesi için konum değerleri 0 ' dan başlar. Açılan menünün tanımlayıcısı bu işlevde kullanılamaz.

### <a name="return-value"></a>Dönüş Değeri

Verilen konumda bir açılır menü varsa, `m_hMenu` üyesi, açılır menüye bir tanıtıcı içeren `CMenu` nesnesine yönelik bir işaretçi; Aksi takdirde NULL. `CMenu` nesne yoksa, geçici bir tane oluşturulur. Döndürülen `CMenu` işaretçi depolanmamalıdır.

### <a name="example"></a>Örnek

  [CMenu:: TrackPopupMenu](#trackpopupmenu)örneğine bakın.

##  <a name="insertmenu"></a>CMenu:: InsertMenu

*NPosition* tarafından belirtilen konuma yeni bir menü öğesi ekler ve diğer öğeleri menünün altına kaydırır.

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

*Sağda*<br/>
Yeni menü öğesinin ekleneceği menü öğesini belirtir. *NFlags* parametresi *nPosition* parametresini aşağıdaki yollarla yorumlamak için kullanılabilir:

|nFlags|NPosition yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametrenin mevcut menü öğesinin komut KIMLIĞINI verir olduğunu belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmamışsa bu varsayılandır.|
|MF_BYPOSITION|Parametrenin mevcut menü öğesinin konumunu olduğunu belirtir. İlk öğe 0 konumundayken. *NPosition* -1 ise, yeni menü öğesi menünün sonuna eklenir.|

*nFlags*<br/>
*NPosition* 'ın nasıl yorumlandığını belirtir ve menüye eklendiğinde yeni menü öğesinin durumu hakkındaki bilgileri belirtir. Ayarlanabilir bayrakların bir listesi için, [AppendMenu](#appendmenu) üye işlevine bakın. Birden çok değer belirtmek için, MF_BYCOMMAND veya MF_BYPOSITION bayrağıyla birleştirmek için bit düzeyinde OR işlecini kullanın.

*nIDNewItem*<br/>
Yeni menü öğesinin komut KIMLIĞINI ya da *nFlags* mf_popup, açılır menünün menü tutamacını (HMENU) belirler. *NFlags* MF_SEPARATOR olarak ayarlandıysa *nIDNewItem* parametresi yok sayılır (gerekli değildir).

*lpszNewItem*<br/>
Yeni menü öğesinin içeriğini belirtir. *nFlags* aşağıdaki yollarla *lpszNewItem* yorumlamak için kullanılabilir:

|nFlags|LpszNewItem yorumu|
|------------|-----------------------------------|
|MF_OWNERDRAW|Uygulamanın menü öğesiyle ilişkili ek verileri sürdürmek için kullanabileceği, uygulama tarafından sağlanan 32 bitlik bir değer içerir. Bu 32 bit değeri, [WM_MEASUREITEM](/windows/win32/Controls/wm-measureitem) ve [WM_DRAWITEM](/windows/win32/Controls/wm-drawitem) iletileri tarafından sağlanan yapının `itemData` üyesinde uygulama için kullanılabilir. Bu iletiler, menü öğesi başlangıçta görüntülendiğinde veya değiştirildiğinde gönderilir.|
|MF_STRING|Null ile sonlandırılmış bir dizeye yönelik uzun bir işaretçi içerir. Bu, varsayılan yorumlamasıdır.|
|MF_SEPARATOR|*LpszNewItem* parametresi yok sayılır (gerekli değildir).|

*pBmp*<br/>
Menü öğesi olarak kullanılacak bir `CBitmap` nesnesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulama, *nFlags*içindeki değerleri ayarlayarak menü öğesinin durumunu belirtebilir.

Pencerede bulunan bir menü değiştirildiğinde (pencerenin görüntülenip görüntülenmediğini belirtir), uygulama `CWnd::DrawMenuBar`çağırmalıdır.

*NIDNewItem* bir açılan menüyü belirttiğinde, eklendiği menünün bir parçası haline gelir. Bu menü yok edildiğinde, eklenen menü de yok edilir. Çakışmayı önlemek için, ekli bir menü `CMenu` nesnesinden ayrılmalıdır.

Etkin çoklu belge arabirimi (MDI) alt penceresi ekranı kapladıysa ve bir uygulama bu işlevi çağırarak ve MF_BYPOSITION bayrağını belirterek MDI uygulamasının menüsüne bir açılır menü ekler beklenen. Bu durum, etkin MDI alt penceresinin denetim menüsü MDI çerçevesi penceresinin menü çubuğunun ilk konumuna eklendiği için oluşur. Menüyü düzgün şekilde konumlandırmak için, uygulamanın, aksi durumda kullanılacak konum değerine 1 eklemesi gerekir. Bir uygulama, şu anda etkin olan alt pencerenin ekranı kaplamadığını anlamak için WM_MDIGETACTIVE iletisini kullanabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]

##  <a name="insertmenuitem"></a>CMenu:: InsertMenuItem

Menüde belirtilen konuma yeni bir menü öğesi ekler.

```
BOOL InsertMenuItem(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*uItem*<br/>
Windows SDK [InsertMenuItem](/windows/win32/api/winuser/nf-winuser-insertmenuitemw) Içindeki *uitem* açıklamasına bakın.

*Lpmenuitemınfo*<br/>
Windows SDK `InsertMenuItem` *lpmıı* 'nin açıklamasına bakın.

*fByPos*<br/>
Windows SDK `InsertMenuItem` içindeki *fByPosition* açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Windows SDK açıklanan [InsertMenuItem](/windows/win32/api/winuser/nf-winuser-insertmenuitemw)'ı sarmalanmış.

##  <a name="loadmenu"></a>CMenu:: LoadMenu

Uygulamanın yürütülebilir dosyasından bir menü kaynağı yükler ve `CMenu` nesnesine ekler.

```
BOOL LoadMenu(LPCTSTR lpszResourceName);
BOOL LoadMenu(UINT nIDResource);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Yüklenecek menü kaynağının adını içeren, null ile sonlandırılmış bir dizeye işaret eder.

*nIDResource*<br/>
Yüklenecek menü kaynağının menü KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Menü kaynağı başarıyla yüklenmişse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çıkmadan önce, bir pencere bir pencereye atanmadığı takdirde bir menü ile ilişkili sistem kaynaklarını boş olmalıdır. Bir uygulama, [Destroyımenu](#destroymenu) üye işlevini çağırarak bir menüyü serbest bırakır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]

##  <a name="loadmenuindirect"></a>CMenu:: Loadmenudolaylı

Bellekteki bir menü şablonundan bir kaynak yükler ve `CMenu` nesnesine iliştirir.

```
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```

### <a name="parameters"></a>Parametreler

*lpMenuTemplate*<br/>
Bir menü şablonuna işaret eder (tek bir [MENUITEMTEMPLATEHEADER](/windows/win32/api/winuser/ns-winuser-menuitemtemplateheader) yapısı ve bir veya daha fazla [menuııtemtemplate](/windows/win32/api/winuser/ns-winuser-menuitemtemplate) yapısının koleksiyonu). Bu iki yapı hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="return-value"></a>Dönüş Değeri

Menü kaynağı başarıyla yüklenmişse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir menü şablonu, her biri bir veya daha fazla menü öğesi ve açılır menüler içerebilen bir veya daha fazla [Menuııtemtemplate](/windows/win32/api/winuser/ns-winuser-menuitemtemplate) yapısı koleksiyonu tarafından izlenen bir üst bilgi.

Sürüm numarası 0 olmalıdır.

`mtOption` bayrakları, açılan listedeki son öğe için ve ana listedeki son öğe için MF_END içermelidir. Diğer bayraklar için `AppendMenu` üye işlevine bakın. `mtOption`MF_POPUP belirtildiğinde, `mtId` üyesinin MENUııTEMTEMPLATE yapısından atlanmalıdır.

MENUııTEMTEMPLATE yapısına ayrılan alan, `mtString`, null ile sonlandırılmış bir dize olarak menü öğesinin adını içermesi için yeterince büyük olmalıdır.

Çıkmadan önce, bir pencere bir pencereye atanmadığı takdirde bir menü ile ilişkili sistem kaynaklarını boş olmalıdır. Bir uygulama, [Destroyımenu](#destroymenu) üye işlevini çağırarak bir menüyü serbest bırakır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]

##  <a name="m_hmenu"></a>CMenu:: m_hMenu

`CMenu` nesnesine eklenen Windows menüsünün HMENU tanıtıcısını belirtir.

```
HMENU m_hMenu;
```

### <a name="example"></a>Örnek

  [CMenu:: LoadMenu](#loadmenu)örneğine bakın.

##  <a name="measureitem"></a>CMenu:: MeasureItem

Sahip çizimi stilinde bir menü oluşturulduğunda Framework tarafından çağırılır.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpMeasureItemStruct*<br/>
`MEASUREITEMSTRUCT` yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bu üye işlevini geçersiz kılın ve menü boyutlarının pencerelerini bilgilendirmek için `MEASUREITEMSTRUCT` yapısını girin.

`MEASUREITEMSTRUCT` yapısının açıklaması için bkz. [CWnd:: OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) .

### <a name="example"></a>Örnek

Aşağıdaki kod MFC [ctrltest](../../overview/visual-cpp-samples.md) örneğinden verilmiştir:

[!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]

##  <a name="modifymenu"></a>CMenu:: ModifyMenu

*NPosition*tarafından belirtilen konumdaki mevcut bir menü öğesini değiştirir.

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

*Sağda*<br/>
Değiştirilecek menü öğesini belirtir. *NFlags* parametresi *nPosition* parametresini aşağıdaki yollarla yorumlamak için kullanılabilir:

|nFlags|NPosition yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametrenin mevcut menü öğesinin komut KIMLIĞINI verir olduğunu belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmamışsa bu varsayılandır.|
|MF_BYPOSITION|Parametrenin mevcut menü öğesinin konumunu olduğunu belirtir. İlk öğe 0 konumundayken.|

*nFlags*<br/>
*NPosition* 'ın nasıl yorumlandığını belirtir ve menü öğesinde yapılacak değişiklikler hakkında bilgi verir. Ayarlanabilir bayrakların bir listesi için, bkz. [AppendMenu](#appendmenu) üye işlevi.

*nIDNewItem*<br/>
Değiştirilen menü öğesinin komut KIMLIĞINI ya da *nFlags* mf_popup, bir açılır menünün menü tutamacını (HMENU) belirler. *NFlags* MF_SEPARATOR olarak ayarlandıysa *nIDNewItem* parametresi yok sayılır (gerekli değildir).

*lpszNewItem*<br/>
Yeni menü öğesinin içeriğini belirtir. *NFlags* parametresi, aşağıdaki yollarla *lpszNewItem* yorumlamak için kullanılabilir:

|nFlags|LpszNewItem yorumu|
|------------|-----------------------------------|
|MF_OWNERDRAW|Uygulamanın menü öğesiyle ilişkili ek verileri sürdürmek için kullanabileceği, uygulama tarafından sağlanan 32 bitlik bir değer içerir. Bu 32 bit değeri MF_MEASUREITEM ve MF_DRAWITEM işlerken uygulama için kullanılabilir.|
|MF_STRING|Null ile sonlandırılmış bir dizeye veya `CString`yönelik uzun bir işaretçi içerir.|
|MF_SEPARATOR|*LpszNewItem* parametresi yok sayılır (gerekli değildir).|

*pBmp*<br/>
Menü öğesi olarak kullanılacak bir `CBitmap` nesnesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulama, *nFlags*içindeki değerleri ayarlayarak menü öğesinin yeni durumunu belirtir. Bu işlev menü öğesiyle ilişkili bir açılır menüyü değiştirirse, eski açılır menüyü yok eder ve açılır menü tarafından kullanılan belleği serbest bırakır.

*NIDNewItem* bir açılan menüyü belirttiğinde, eklendiği menünün bir parçası haline gelir. Bu menü yok edildiğinde, eklenen menü de yok edilir. Çakışmayı önlemek için, ekli bir menü `CMenu` nesnesinden ayrılmalıdır.

Pencerede bulunan bir menü değiştirildiğinde (pencerenin görüntülenip görüntülenmediğini belirtir), uygulama `CWnd::DrawMenuBar`çağırmalıdır. Mevcut menü öğelerinin özniteliklerini değiştirmek için, `CheckMenuItem` ve `EnableMenuItem` üye işlevlerini kullanmak çok daha hızlıdır.

### <a name="example"></a>Örnek

  [CMenu:: InsertMenu](#insertmenu)örneğine bakın.

##  <a name="operator_hmenu"></a>CMenu:: operator HMENU

`CMenu` nesnesinin tanıtıcısını almak için bu işleci kullanın.

```
operator HMENU() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CMenu` nesnesinin tanıtıcısı; Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

İşleyiciyi doğrudan Windows API 'Leri çağırmak için kullanabilirsiniz.

##  <a name="operator_neq"></a>CMenu:: operator! =

İki menülerin mantıksal olarak eşit olup olmadığını belirler.

```
BOOL operator!=(const CMenu& menu) const;
```

### <a name="parameters"></a>Parametreler

*Menü*<br/>
Karşılaştırma için bir `CMenu` nesnesi.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir menü nesnesinin sağ taraftaki bir menü nesnesine eşit olup olmadığını sınar.

##  <a name="operator_eq_eq"></a>CMenu:: operator = =

İki menülerin mantıksal olarak eşit olup olmadığını belirler.

```
BOOL operator==(const CMenu& menu) const;
```

### <a name="parameters"></a>Parametreler

*Menü*<br/>
Karşılaştırma için bir `CMenu` nesnesi.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir menü nesnesinin, sağ taraftaki bir menü nesnesine eşit (HMENU değeri) olarak eşit olup olmadığını sınar.

##  <a name="removemenu"></a>CMenu:: RemoveMenu

Menüden ilişkili bir açılır menü içeren bir menü öğesini siler.

```
BOOL RemoveMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

*Sağda*<br/>
Kaldırılacak menü öğesini belirtir. *NFlags* parametresi *nPosition* parametresini aşağıdaki yollarla yorumlamak için kullanılabilir:

|nFlags|NPosition yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametrenin mevcut menü öğesinin komut KIMLIĞINI verir olduğunu belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmamışsa bu varsayılandır.|
|MF_BYPOSITION|Parametrenin mevcut menü öğesinin konumunu olduğunu belirtir. İlk öğe 0 konumundayken.|

*nFlags*<br/>
*NPosition* 'ın nasıl yorumlandığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Açılır menünün tanıtıcısını yok etmez, bu nedenle menü yeniden kullanılabilir. Bu işlevi çağırmadan önce, uygulama `GetSubMenu` üye işlevini çağırarak açılır `CMenu` nesnesini yeniden kullanım için alabilir.

Pencerede bulunan bir menü değiştirildiğinde (pencerenin görüntülenip görüntülenmediğini belirtir), uygulamanın `CWnd::DrawMenuBar`çağırması gerekir.

### <a name="example"></a>Örnek

  [CMenu:: InsertMenu](#insertmenu)örneğine bakın.

##  <a name="setdefaultitem"></a>CMenu:: Setdefaultıtem

Belirtilen menü için varsayılan menü öğesini ayarlar.

```
BOOL SetDefaultItem(
    UINT uItem,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*uItem*<br/>
Varsayılan öğe için yeni varsayılan menü öğesinin tanımlayıcısı veya konumu veya-1. Bu parametrenin anlamı *fByPos*değerine bağlıdır.

*fByPos*<br/>
*Uitem*'in anlamını belirten değer. Bu parametre YANLıŞSA, *Uitem* bir menü öğesi tanımlayıcısıdır. Aksi takdirde, bir menü öğesi konumudur.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri sıfır dışında olur. İşlev başarısız olursa, dönüş değeri sıfırdır. Genişletilmiş hata bilgilerini almak için Windows SDK [Win32 işlevini kullanın](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror), burada açıklandığı gibi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, [SetMenuDefaultItem](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem)Win32 işlevinin davranışını uygular.

### <a name="example"></a>Örnek

  [CMenu:: InsertMenu](#insertmenu)örneğine bakın.

##  <a name="setmenucontexthelpid"></a>CMenu:: SetMenuContextHelpId

Bağlam yardım KIMLIĞINI `CMenu`ile ilişkilendirir.

```
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```

### <a name="parameters"></a>Parametreler

*dwContextHelpId*<br/>
`CMenu`ile ilişkilendirilecek bağlam yardım KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde 0

### <a name="remarks"></a>Açıklamalar

Menüdeki tüm öğeler bu tanımlayıcıyı paylaşır — bireysel menü öğelerine bir yardım bağlamı tanımlayıcısı eklemek mümkün değildir.

### <a name="example"></a>Örnek

  [CMenu:: InsertMenu](#insertmenu)örneğine bakın.

##  <a name="setmenuinfo"></a>CMenu:: Setmenuınfo

Bir menünün bilgilerini ayarlar.

```
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```

### <a name="parameters"></a>Parametreler

*lpcmı*<br/>
Menü bilgilerini içeren bir [MENUINFO](/windows/win32/api/winuser/ns-winuser-menuinfo) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri sıfır dışında olur; Aksi takdirde, dönüş değeri sıfırdır.

### <a name="remarks"></a>Açıklamalar

Menüsüyle ilgili belirli bilgileri ayarlamak için bu işlevi çağırın.

##  <a name="setmenuitembitmaps"></a>CMenu:: SetMenuItemBitmaps

Belirtilen bit eşlemleri bir menü öğesiyle ilişkilendirir.

```
BOOL SetMenuItemBitmaps(
    UINT nPosition,
    UINT nFlags,
    const CBitmap* pBmpUnchecked,
    const CBitmap* pBmpChecked);
```

### <a name="parameters"></a>Parametreler

*Sağda*<br/>
Değiştirilecek menü öğesini belirtir. *NFlags* parametresi *nPosition* parametresini aşağıdaki yollarla yorumlamak için kullanılabilir:

|nFlags|NPosition yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametrenin mevcut menü öğesinin komut KIMLIĞINI verir olduğunu belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmamışsa bu varsayılandır.|
|MF_BYPOSITION|Parametrenin mevcut menü öğesinin konumunu olduğunu belirtir. İlk öğe 0 konumundayken.|

*nFlags*<br/>
*NPosition* 'ın nasıl yorumlandığını belirtir.

*pBmpUnchecked*<br/>
İşaretli olmayan menü öğeleri için kullanılacak bit eşlemi belirtir.

*pBmpChecked*<br/>
Denetlenen menü öğeleri için kullanılacak bit eşlemi belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Menü öğesinin işaretli veya işaretlenmemiş olup olmadığı, Windows menü öğesinin yanında uygun bit eşlemi görüntüler.

*PBmpUnchecked* veya *PBMPCHECKED* null ise, Windows karşılık gelen öznitelik için menü öğesinin yanında hiçbir şey görüntülemez. Her iki parametre de NULL ise, Windows, öğe işaretlendiğinde varsayılan onay işaretini kullanır ve öğe işaretli değilken onay işaretini kaldırır.

Menü yok edildiğinde, bu bit eşlemler yok edilmez; uygulamanın onları yok etmeniz gerekir.

Windows `GetMenuCheckMarkDimensions` işlevi, menü öğeleri için kullanılan varsayılan onay işaretinin boyutlarını alır. Uygulama, bu işlevle sağlanan bit eşlemlere uygun boyutu belirlemede bu değerleri kullanır. Boyutu alın, bit eşlemlerinizi oluşturun ve bunları ayarlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]

[!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]

##  <a name="setmenuiteminfo"></a>CMenu:: Setmenuiteınfo

Bir menü öğesiyle ilgili bilgileri değiştirir.

```
BOOL SetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*uItem*<br/>
Windows SDK [SetMenuItemInfo](/windows/win32/api/winuser/nf-winuser-setmenuiteminfow) Içinde *uitem* açıklamasına bakın.

*Lpmenuitemınfo*<br/>
Windows SDK `SetMenuItemInfo` *lpmıı* 'nin açıklamasına bakın.

*fByPos*<br/>
Windows SDK `SetMenuItemInfo` içindeki *fByPosition* açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Windows SDK açıklanan [Setmenuiteınfo](/windows/win32/api/winuser/nf-winuser-setmenuiteminfow)öğesini sarmalanmış.

##  <a name="trackpopupmenu"></a>CMenu:: TrackPopupMenu

Belirtilen konumda kayan bir açılır menü görüntüler ve açılır menüdeki öğelerin seçimini izler.

```
BOOL TrackPopupMenu(
    UINT nFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPCRECT lpRect = 0);
```

### <a name="parameters"></a>Parametreler

*nFlags*<br/>
Ekran konumunu ve fare konumu bayraklarını belirtir. Kullanılabilir bayrakların listesi için [TrackPopupMenu](/windows/win32/api/winuser/nf-winuser-trackpopupmenu) öğesine bakın.

*sayı*<br/>
Açılır menünün Ekran koordinatlarındaki yatay konumu belirtir. *NFlags* parametresinin değerine bağlı olarak, menü sola hizalı, sağa hizalı veya bu konuma göre ortalanmış olabilir.

*Iz*<br/>
Ekrandaki menünün üst kısmında bulunan dikey konumu belirtir.

*pWnd*<br/>
Açılır menünün sahibi olan pencereyi tanımlar. TPM_NONOTIFY bayrağı belirtilmiş olsa bile bu parametre NULL olamaz. Bu pencere, menüden tüm WM_COMMAND iletilerini alır. Windows sürümleri 3,1 ve üzeri sürümlerde, `TrackPopupMenu` döndürülünceye kadar pencere WM_COMMAND iletileri almaz. Windows 3,0 ' de pencere, `TrackPopupMenu` döndürülmadan önce WM_COMMAND iletileri alır.

*lpRect*<br/>
LIP.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem, Windows SDK [TrackPopupMenu](/windows/win32/api/winuser/nf-winuser-trackpopupmenu) çağırmanın sonucunu döndürür.

### <a name="remarks"></a>Açıklamalar

Kayan bir açılır menü ekran üzerinde herhangi bir yerde görünebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]

##  <a name="trackpopupmenuex"></a>CMenu:: TrackPopupMenuEx

Belirtilen konumda kayan bir açılır menü görüntüler ve açılır menüdeki öğelerin seçimini izler.

```
BOOL TrackPopupMenuEx(
    UINT fuFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPTPMPARAMS lptpm);
```

### <a name="parameters"></a>Parametreler

*fuFlags*<br/>
Genişletilmiş menü için çeşitli işlevleri belirtir. Tüm değerlerin ve anlamının listesi için bkz. [TrackPopupMenuEx](/windows/win32/api/winuser/nf-winuser-trackpopupmenuex).

*sayı*<br/>
Açılır menünün Ekran koordinatlarındaki yatay konumu belirtir.

*Iz*<br/>
Ekrandaki menünün üst kısmında bulunan dikey konumu belirtir.

*pWnd*<br/>
Açılır menünün sahibi olan pencere için bir işaretçi ve oluşturulan menüden iletileri alma. Bu pencere geçerli uygulamadaki herhangi bir pencere olabilir, ancak NULL olamaz. *FuFlags* parametresinde TPM_NONOTIFY belirtirseniz, Işlev *pWnd*'e ileti göndermez. İşlev, WM_COMMAND iletisini almak için *pWnd* tarafından işaret edilen pencere için döndürmelidir.

*lptpm*<br/>
Ekranın bir alanını belirten bir [Tpmparams](/windows/win32/api/winuser/ns-winuser-tpmparams) yapısına yönelik işaretçi menü çakışmamalıdır. Bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

*FuFlags* parametresinde TPM_RETURNCMD belirtirseniz, dönüş değeri kullanıcının seçtiği öğenin menü öğesi tanımlayıcısıdır. Kullanıcı bir seçim yapmadan menüyü iptal ederse veya bir hata oluşursa, dönüş değeri 0 ' dır.

*FuFlags* parametresinde TPM_RETURNCMD belirtmezseniz, işlev başarılı olursa, dönüş değeri sıfır değildir ve başarısız olursa 0 olur. Genişletilmiş hata bilgilerini almak için [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)çağrısı yapın.

### <a name="remarks"></a>Açıklamalar

Kayan bir açılır menü ekran üzerinde herhangi bir yerde görünebilir. Açılır menüyü oluştururken hata işleme hakkında daha fazla bilgi için bkz. [TrackPopupMenuEx](/windows/win32/api/winuser/nf-winuser-trackpopupmenuex).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek DYNAMENU](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)
