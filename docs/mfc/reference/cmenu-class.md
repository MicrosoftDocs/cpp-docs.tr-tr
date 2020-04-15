---
title: CMenu Sınıfı
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
ms.openlocfilehash: 5ec97d8cf039034078f29b38fb6a41d6ff9a5e53
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369976"
---
# <a name="cmenu-class"></a>CMenu Sınıfı

Windows'un `HMENU`kapsülletisi.

## <a name="syntax"></a>Sözdizimi

```
class CMenu : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMenü::CMenu](#cmenu)|Bir `CMenu` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMenu::AppendMenu](#appendmenu)|Bu menünün sonuna yeni bir öğe ekler.|
|[CMenu::Ekle](#attach)|Bir `CMenu` nesneye Windows menü tutamacı bağlar.|
|[CMenu::CheckMenuItem](#checkmenuitem)|Açılan menüde bir menü öğesinin yanına onay işareti yerleştirir veya onay işaretini kaldırır.|
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|Bir menü öğesinin yanına bir radyo düğmesi yerleştirir ve radyo düğmesini gruptaki diğer tüm menü öğelerinden kaldırır.|
|[CMenu::CreateMenu](#createmenu)|Boş bir menü oluşturur ve nesneye `CMenu` bağlar.|
|[CMenu::CreatePopupMenu](#createpopupmenu)|Boş bir açılır menü oluşturur ve bir `CMenu` nesneye bağlar.|
|[CMenu::DeleteMenü](#deletemenu)|Belirtilen bir öğeyi menüden siler. Menü öğesinin ilişkili bir açılır menüsü varsa, açılan menüye açılan menüdeki tutamacı yok eder ve kullandığı belleği serbest hale getirir.|
|[CMenu::DeleteTempMap](#deletetempmap)|Üye işlev `CMenu` tarafından oluşturulan geçici nesneleri siler. `FromHandle`|
|[CMenu::DestroyMenü](#destroymenu)|Bir `CMenu` nesneye iliştirilen menüyü yok eder ve menünün kapta olduğu tüm belleği serbest bırakmaz.|
|[CMenü::Detach](#detach)|Windows menü tutamacını bir `CMenu` nesneden ayırır ve tutamacı döndürür.|
|[CMenu::DrawItem](#drawitem)|Sahip tarafından çizilen bir menünün görsel yönü değiştiğinde çerçeve tarafından çağrılır.|
|[CMenu::EnableMenuItem](#enablemenuitem)|Menü öğesini etkinleştirin, devre dışı kılabilir veya karartır (griler).|
|[CMenu::FromHandle](#fromhandle)|Bir işaretçiyi `CMenu` Windows menü tutamacı verilen bir nesneye döndürür.|
|[CMenu::GetDefaultItem](#getdefaultitem)|Belirtilen menüdeki varsayılan menü öğesini belirler.|
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|Menüyle ilişkili yardım bağlamı kimliğini alır.|
|[CMenu::GetMenuInfo](#getmenuinfo)|Belirli bir menüdeki bilgileri alır.|
|[CMenu::GetMenuItemCount](#getmenuitemcount)|Açılır pencere veya üst düzey menüdeki öğelerin sayısını belirler.|
|[CMenu::GetMenuItemID](#getmenuitemid)|Belirtilen konumda bulunan bir menü öğesi için menü öğesi tanımlayıcısını alır.|
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|Menü öğesi hakkındaki bilgileri alır.|
|[CMenu::GetMenuState](#getmenustate)|Belirtilen menü öğesinin durumunu veya açılır menüdeki öğe sayısını döndürür.|
|[CMenu::GetMenuString](#getmenustring)|Belirtilen menü öğesinin etiketini alır.|
|[CMenu::GetSafeHmenu](#getsafehmenu)|Bu `CMenu` `m_hMenu` nesne tarafından sarılmış döndürür.|
|[CMenu::GetSubMenu](#getsubmenu)|Açılır menü için bir işaretçi alır.|
|[CMenu::InsertMenu](#insertmenu)|Belirtilen konuma yeni bir menü öğesi ekler ve diğer öğeleri menüden aşağı doğru hareket ettirer.|
|[CMenu::EkleMenuItem](#insertmenuitem)|Menüde belirtilen konuma yeni bir menü öğesi ekler.|
|[CMenü::LoadMenu](#loadmenu)|Yürütülebilir dosyadan bir menü kaynağı yükler `CMenu` ve bir nesneye bağlar.|
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|Menüyü bellekteki menü şablonundan yükler ve `CMenu` bir nesneye ekler.|
|[CMenu::MeasureItem](#measureitem)|Sahip tarafından çizilmiş bir menü oluşturulduğunda menü boyutlarını belirlemek için çerçeve tarafından çağrılır.|
|[CMenu::ModifyMenu](#modifymenu)|Varolan bir menü öğesini belirtilen konumda değiştirir.|
|[CMenu::RemoveMenu](#removemenu)|Belirtilen menüden ilişkili açılır menü içeren bir menü öğesini siler.|
|[CMenu::SetDefaultItem](#setdefaultitem)|Belirtilen menü için varsayılan menü öğesini ayarlar.|
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|Yardım bağlamı kimliğini menüyle ilişkilendirilecek şekilde ayarlar.|
|[CMenu::SetMenuInfo](#setmenuinfo)|Belirli bir menüdeki bilgileri ayarlar.|
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|Belirtilen onay işareti bit eşlemlerini bir menü öğesiyle ilişkilendirer.|
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|Menü öğesi hakkındaki bilgileri değiştirir.|
|[CMenu::TrackPopupMenu](#trackpopupmenu)|Belirtilen konumda kayan bir açılır menü görüntüler ve açılır menüdeki öğelerin seçimini izler.|
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|Belirtilen konumda kayan bir açılır menü görüntüler ve açılır menüdeki öğelerin seçimini izler.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CMenu::operatör HMENU](#operator_hmenu)|Menü nesnesinin tutamacını alır.|
|[CMenu::operatör !=](#operator_neq)|İki menü nesnesi eşit değilse belirler.|
|[CMenu::operatör ==](#operator_eq_eq)|İki menü nesnesi eşit olup olmadığını belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMenü::m_hMenu](#m_hmenu)|Nesneye iliştirilen Windows menüsüne `CMenu` tutamacı belirtir.|

## <a name="remarks"></a>Açıklamalar

Bir menü oluşturmak, izlemek, güncelleştirmek ve yok etmek için üye işlevler sağlar.

Yığın `CMenu` çerçevesi üzerinde yerel olarak bir nesne `CMenu`oluşturun ve ardından gerektiğinde yeni menüyü işlemek için 'üye işlevleri' çağırın. Ardından, menüyü bir pencereye ayarlamak için [CWnd::SetMenu'u](../../mfc/reference/cwnd-class.md#setmenu) `CMenu` arayın ve hemen ardından nesnenin [Detach](#detach) üye işlevine bir çağrı yapın. `CWnd::SetMenu` Üye işlev pencerenin menüsünü yeni menüye ayarlar, pencerenin menü değişikliğini yansıtacak şekilde yeniden çizilmesine neden olur ve ayrıca menünün sahipliğini pencereye geçirir. Yerel `CMenu` değişken `Detach` kapsam dışına geçtiğinde nesne `CMenu` `CMenu` yıkıcının artık sahip olmadığı bir menüyü yok etmeye çalışmaması için HMENU'yi nesneden ayırma çağrısı. Pencere yok edildiğinde menünün kendisi otomatik olarak yok edilir.

[LoadMenuIndirect](#loadmenuindirect) üye işlevini bellekteki bir şablondan bir menü oluşturmak için kullanabilirsiniz, ancak [LoadMenu'a](#loadmenu) yapılan bir çağrı yla kaynaktan oluşturulan bir menü daha kolay korunur ve menü kaynağının kendisi menü düzenleyicisi tarafından oluşturulabilir ve değiştirilebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CMenu`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cmenuappendmenu"></a><a name="appendmenu"></a>CMenu::AppendMenu

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

*Nflags*<br/>
Menüye eklendiğinde yeni menü öğesinin durumu yla ilgili bilgileri belirtir. Açıklamalar bölümünde listelenen değerlerden bir veya birkaçını oluşur.

*nIDNewItem*<br/>
Yeni menü öğesinin komut kimliğini veya *nFlags* MF_POPUP ayarlanmışsa, açılan menünün menü tutamacını ( `HMENU`) belirtir. *nFlags* MF_SEPARATOR ayarlanmışsa *nIDNewItem* parametresi yoksayılır (gerekli değildir).

*lpszNewItem*<br/>
Yeni menü öğesinin içeriğini belirtir. *nFlags* parametresi aşağıdaki şekilde *lpszNewItem* yorumlamak için kullanılır:

|Nflags|lpszNewItem yorumu|
|------------|-----------------------------------|
|MF_OWNERDRAW|Uygulamanın menü öğesiyle ilişkili ek verileri korumak için kullanabileceği uygulama tarafından sağlanan 32 bit lik bir değer içerir. Bu 32 bit lik değer, WM_MEASUREITEM ve WM_DRAWITEM iletileri işlerken uygulama için kullanılabilir. Değer, bu iletilerle `itemData` birlikte verilen yapının üyesinde depolanır.|
|MF_STRING|Null-sonlandırılan dize için bir işaretçi içerir. Bu varsayılan yorumdur.|
|MF_SEPARATOR|*lpszNewItem* parametresi yoksayılır (gerekli değildir).|

*pBmp*<br/>
Menü öğesi `CBitmap` olarak kullanılacak bir nesneye işaret edin.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulama *nFlags*değerleri ayarlayarak menü öğesinin durumunu belirtebilirsiniz. *nIDNewItem* bir açılır menü belirttiğinde, eklendiği menünün bir parçası olur. Bu menü yok edilirse, eklenen menü de yok edilir. Çakışmayı önlemek için eklenen `CMenu` bir menü nesneden ayrılmalıdır. MF_STRING ve MF_OWNERDRAW bitmap sürümü için geçerli `AppendMenu`olmadığını unutmayın.

Aşağıdaki liste *nFlags*ayarlanabilecek bayrakları açıklar:

- MF_CHECKED Varsayılan onay işaretini öğenin yanına yerleştirmek için MF_UNCHECKED ile geçiş görevi görür. Uygulama onay işareti bit eşlemleri sağladığında [(SetMenuItemBitmaps](#setmenuitembitmaps) üye işlevine bakın), "onay işareti üzerinde" bit eşlemi görüntülenir.

- MF_UNCHECKED Maddenin yanındaki onay işaretini kaldırmak için MF_CHECKED geçiş görevi görür. Uygulama onay işareti bit eşlerini sağladığında (üye işlevine `SetMenuItemBitmaps` bakın), "onay işareti" bit eşlemi görüntülenir.

- MF_DISABLED menü öğesini seçilemeyecek, ancak karartmayacak şekilde devre dışı kılabilir.

- MF_ENABLED Menü öğesini seçilebilmesini sağlar ve soluk durumundan geri getirir.

- MF_GRAYED menü öğesini seçilemesin diye devre dışı bırakıp karartır.

- MF_MENUBARBREAK Öğeyi statik menülerde yeni bir satıra veya açılır menülerde yeni bir sütuna yerleştirir. Yeni açılır menü sütunu, dikey bir bölme satırı ile eski sütundan ayrılır.

- MF_MENUBREAK Öğeyi statik menülerde yeni bir satıra veya açılır menülerde yeni bir sütuna yerleştirir. Sütunlar arasına bölme satırı yerleştirilmez.

- MF_OWNERDRAW Maddenin bir sahip çizim öğesi olduğunu belirtir. Menü ilk kez görüntülendiğinde, menünün sahibi olan pencere, menü öğesinin yüksekliğini ve genişliğini alan bir WM_MEASUREITEM iletisi alır. WM_DRAWITEM iletisi, sahibinin menü öğesinin görsel görünümünü güncelleştirmesi gerektiğinde gönderilen iletidir. Bu seçenek üst düzey bir menü öğesi için geçerli değildir.

- MF_POPUP Menü öğesinin onunla ilişkili bir açılır menüsü olduğunu belirtir. Kimlik parametresi, öğeyle ilişkilendirilecek açılır menüiçin bir tanıtıcı belirtir. Bu, açılır menü öğesine üst düzey açılır menü veya hiyerarşik açılır menü eklemek için kullanılır.

- MF_SEPARATOR Yatay bir bölme çizgisi çizer. Yalnızca açılır menüde kullanılabilir. Bu satır soluk, devre dışı veya vurgulanamaz. Diğer parametreler yoksayılır.

- MF_STRING Menü öğesinin bir karakter dizesi olduğunu belirtir.

Aşağıdaki grupların her biri, birbirini dışlayan ve birlikte kullanılamayacak bayrakları listeler:

- MF_DISABLED, MF_ENABLED ve MF_GRAYED

- MF_STRING, MF_OWNERDRAW, MF_SEPARATOR ve bitmap sürümü

- MF_MENUBARBREAK ve MF_MENUBREAK

- MF_CHECKED ve MF_UNCHECKED

Bir pencerede bulunan bir menü değiştirildiğinde (pencere görüntülense de görüntülenmese de), uygulama [CWnd::DrawMenuBar.](../../mfc/reference/cwnd-class.md#drawmenubar)

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:CreateMenu](#createmenu).

## <a name="cmenuattach"></a><a name="attach"></a>CMenu::Ekle

Varolan bir Windows menüsünü bir `CMenu` nesneye bağlar.

```
BOOL Attach(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

*Hmenu*<br/>
Windows menüsünde bir tanıtıcı belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CMenu` Nesneye zaten bir menü eklenmişse, bu işlev çağrılmamalıdır. Menü tutamacı veri üyesinde `m_hMenu` depolanır.

Işlemek istediğiniz menü zaten bir pencereyle ilişkiliyse, menüye bir tanıtıcı almak için [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu) işlevini kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

## <a name="cmenucheckmenuitem"></a><a name="checkmenuitem"></a>CMenu::CheckMenuItem

Açılan menüdeki menü öğelerine onay işaretleri ekler veya kaldırır.

```
UINT CheckMenuItem(
    UINT nIDCheckItem,
    UINT nCheck);
```

### <a name="parameters"></a>Parametreler

*nIDCheckItem*<br/>
nCheck tarafından belirlendiği gibi, işaretlenecek menü *öğesini*belirtir.

*nCheck*<br/>
Menü öğesinin nasıl denetlenebildiğini ve öğenin menüdeki konumunu nasıl belirleyip belirleyeceklerini belirtir. *nCheck* parametresi, MF_BYPOSITION veya MF_BYCOMMAND bayraklarıyla MF_CHECKED veya MF_UNCHECKED birleşimi olabilir. Bu bayraklar bitwise OR işleci kullanılarak birleştirilebilir. Onlar aşağıdaki anlamları vardır:

- MF_BYCOMMAND Parametrenin varolan menü öğesinin komut kimliğini verdiğini belirtir. Bu varsayılandır.

- MF_BYPOSITION Parametrenin varolan menü öğesinin konumunu verdiğini belirtir. İlk madde 0 konumundadır.

- MF_CHECKED Varsayılan onay işaretini öğenin yanına yerleştirmek için MF_UNCHECKED ile geçiş görevi görür.

- MF_UNCHECKED Maddenin yanındaki onay işaretini kaldırmak için MF_CHECKED geçiş görevi görür.

### <a name="return-value"></a>Dönüş Değeri

Öğenin önceki durumu: MF_CHECKED veya MF_UNCHECKED veya menü öğesi yoksa 0xFFFFFFFF.

### <a name="remarks"></a>Açıklamalar

*nIDCheckItem* parametresi değiştirilecek öğeyi belirtir.

*nIDCheckItem* parametresi bir açılır menü öğesinin yanı sıra bir menü öğesini de tanımlayabilir. Açılır menü öğesini denetlemek için özel adımlar gerekmez. Üst düzey menü öğeleri denetlenemez. Açılır menü öğesi, onunla ilişkili bir menü öğesi tanımlayıcısı olmadığından konuma göre denetlenmelidir.

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:GetMenuState](#getmenustate).

## <a name="cmenucheckmenuradioitem"></a><a name="checkmenuradioitem"></a>CMenu::CheckMenuRadioItem

Belirtilen bir menü öğeyi denetler ve radyo öğesi yapar.

```
BOOL CheckMenuRadioItem(
    UINT nIDFirst,
    UINT nIDLast,
    UINT nIDItem,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

*nIDFirst*<br/>
Radyo düğme grubundaki ilk menü öğesini *(nFlags'in*değerine bağlı olarak kimlik veya ofset olarak) belirtir.

*nIDSon*<br/>
Radyo düğme grubundaki son menü öğesini *(nFlags'in*değerine bağlı olarak kimlik veya ofset olarak) belirtir.

*nIDItem*<br/>
Gruptaki bir radyo düğmesiyle kontrol edilecek öğeyi *(nFlags'in*değerine bağlı olarak kimlik veya ofset olarak) belirtir.

*Nflags*<br/>
*NIDFirst*, *nIDLast*ve *nIDItem'in* yorumunu aşağıdaki şekilde belirtir:

|Nflags|Yorum|
|------------|--------------------|
|MF_BYCOMMAND|Parametrenin varolan menü öğesinin komut kimliğini verdiğini belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmazsa bu varsayılandır.|
|Mf_byposıtıon|Parametrenin varolan menü öğesinin konumunu verdiğini belirtir. İlk madde 0 konumundadır.|

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0

### <a name="remarks"></a>Açıklamalar

Aynı zamanda, işlev ilişkili gruptaki diğer tüm menü öğelerinin denetimini geri alır ve bu öğeler için radyo öğesi türü bayrağını temizler. İşaretlenen öğe, onay işareti bit eşlemi yerine bir radyo düğmesi (veya madde işareti) bit eşlemi kullanılarak görüntülenir.

### <a name="example"></a>Örnek

  [ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range)için örneğe bakın.

## <a name="cmenucmenu"></a><a name="cmenu"></a>CMenü::CMenu

Boş bir menü oluşturur ve nesneye `CMenu` bağlar.

```
CMenu();
```

### <a name="remarks"></a>Açıklamalar

Menü, üye oluşturma veya yükleme işlevlerinden birini arayana kadar oluşturulmaz`CMenu:`

- [Oluşturma Menüsü](#createmenu)

- [CreatePopupMenu](#createpopupmenu)

- [LoadMenu](#loadmenu)

- [LoadMenuIndirect](#loadmenuindirect)

- [İliştir](#attach)

## <a name="cmenucreatemenu"></a><a name="createmenu"></a>CMenu::CreateMenu

Bir menü oluşturur ve `CMenu` nesneye bağlar.

```
BOOL CreateMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Menü başarıyla oluşturulduysa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Menü başlangıçta boş. Menü öğeleri `AppendMenu` veya `InsertMenu` üye işlevi kullanılarak eklenebilir.

Menü bir pencereye atanırsa, pencere yok edildiğinde otomatik olarak yok edilir.

Çıkmadan önce, menü bir pencereye atanmamışsa, bir uygulamanın menüyle ilişkili sistem kaynaklarını serbest çemesi gerekir. Uygulama, [DestroyMenu](#destroymenu) üye işlevini arayarak menüyü boşaltıyor.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]

## <a name="cmenucreatepopupmenu"></a><a name="createpopupmenu"></a>CMenu::CreatePopupMenu

Açılır menü oluşturur ve `CMenu` nesneye bağlar.

```
BOOL CreatePopupMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Açılır menü başarıyla oluşturulduysa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Menü başlangıçta boş. Menü öğeleri `AppendMenu` veya `InsertMenu` üye işlevi kullanılarak eklenebilir. Uygulama, açılır menüyü varolan bir menüye veya açılır menüye ekleyebilir. Üye `TrackPopupMenu` işlevi, bu menüyü kayan açılır menü olarak görüntülemek ve açılır menüdeki seçimleri izlemek için kullanılabilir.

Menü bir pencereye atanırsa, pencere yok edildiğinde otomatik olarak yok edilir. Menü varolan bir menüye eklenirse, bu menü yok edildiğinde otomatik olarak yok edilir.

Çıkıştan önce, menü bir pencereye atanmamışsa, bir uygulama açılır menüyle ilişkili sistem kaynaklarını serbest etmelidir. Uygulama, [DestroyMenu](#destroymenu) üye işlevini arayarak menüyü boşaltıyor.

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:CreateMenu](#createmenu).

## <a name="cmenudeletemenu"></a><a name="deletemenu"></a>CMenu::DeleteMenü

Menüden bir öğeyi siler.

```
BOOL DeleteMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

*nPosition*<br/>
*nFlags*tarafından belirlendiği gibi silinecek menü öğesini belirtir.

*Nflags*<br/>
*nPosition'ı* aşağıdaki şekilde yorumlamak için kullanılır:

|Nflags|nPosition yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametrenin varolan menü öğesinin komut kimliğini verdiğini belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmazsa bu varsayılandır.|
|Mf_byposıtıon|Parametrenin varolan menü öğesinin konumunu verdiğini belirtir. İlk madde 0 konumundadır.|

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Menü öğesinin ilişkili bir açılır menüsü `DeleteMenu` varsa, açılan menüdeki tutamacı yok eder ve açılır menü tarafından kullanılan belleği boşaltın.

Bir pencerede bulunan bir menü değiştirildiğinde (pencere görüntülense de görüntülenmese de), uygulama [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).

### <a name="example"></a>Örnek

  CWnd örneğine [bakın:GetMenu](../../mfc/reference/cwnd-class.md#getmenu).

## <a name="cmenudeletetempmap"></a><a name="deletetempmap"></a>CMenu::DeleteTempMap

Boşta kalan `CWinApp` zaman işleyicisi tarafından otomatik `CMenu` olarak çağrılır, [FromHandle](#fromhandle) üye işlevi tarafından oluşturulan geçici nesneleri siler.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Açıklamalar

`DeleteTempMap`nesneyi silmeden önce geçici `CMenu` bir nesneye eklenen Windows `CMenu` menü nesnesini ayırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]

## <a name="cmenudestroymenu"></a><a name="destroymenu"></a>CMenu::DestroyMenü

Menüyü ve kullanılan tüm Windows kaynaklarını yok eder.

```
BOOL DestroyMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Menü yok edilirse sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Menü yok edilmeden `CMenu` önce nesneden ayrılır. Windows `DestroyMenu` işlevi `CMenu` otomatik olarak yıkıcı olarak adlandırılır.

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:CreateMenu](#createmenu).

## <a name="cmenudetach"></a><a name="detach"></a>CMenü::Detach

Windows menüsünü bir `CMenu` nesneden ayırır ve tutamacı döndürür.

```
HMENU Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, Windows menüsüne HMENU türünden tutamaç; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Veri `m_hMenu` üyesi NULL olarak ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

## <a name="cmenudrawitem"></a><a name="drawitem"></a>CMenu::DrawItem

Sahip tarafından çizilen bir menünün görsel yönü değiştiğinde çerçeve tarafından çağrılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Gerekli çizim türü hakkında bilgi içeren [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısıiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Yapının `itemAction` `DRAWITEMSTRUCT` üyesi, gerçekleştirilecek çizim eylemini tanımlar. Bir sahip çizim `CMenu` nesnesi için çizim uygulamak için bu üye işlevi geçersiz kılın. Uygulama, bu üye işlevin sonlandırılmasından önce *lpDrawItemStruct'ta* sağlanan ekran bağlamı için seçilen tüm grafik aygıtı arabirimi (GDI) nesnelerini geri yüklemelidir.

Bkz. [CWnd::Yapının](../../mfc/reference/cwnd-class.md#ondrawitem) `DRAWITEMSTRUCT` açıklaması için OnDrawItem.

### <a name="example"></a>Örnek

Aşağıdaki kod MFC [CTRLTEST](../../overview/visual-cpp-samples.md) örneğindendir:

[!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]

## <a name="cmenuenablemenuitem"></a><a name="enablemenuitem"></a>CMenu::EnableMenuItem

Menü öğesini etkinleştirer, devre dışı eder veya karartır.

```
UINT EnableMenuItem(
    UINT nIDEnableItem,
    UINT nEnable);
```

### <a name="parameters"></a>Parametreler

*nIDEnableItem*<br/>
*nEnable*tarafından belirlendiği gibi, etkinleştirilecek menü öğesini belirtir. Bu parametre açılır menü öğelerinin yanı sıra standart menü öğelerini de belirtebilir.

*nEtkinleştir*<br/>
Yapılacak eylemi belirtir. MF_BYCOMMAND veya MF_BYPOSITION ile MF_DISABLED, MF_ENABLED veya MF_GRAYED bir kombinasyonu olabilir. Bu değerler bitwise OR işleci kullanılarak birleştirilebilir. Bu değerlerin şu anlamları vardır:

- MF_BYCOMMAND Parametrenin varolan menü öğesinin komut kimliğini verdiğini belirtir. Bu varsayılandır.

- MF_BYPOSITION Parametrenin varolan menü öğesinin konumunu verdiğini belirtir. İlk madde 0 konumundadır.

- MF_DISABLED menü öğesini seçilemeyecek, ancak karartmayacak şekilde devre dışı kılabilir.

- MF_ENABLED Menü öğesini seçilebilmesini sağlar ve soluk durumundan geri getirir.

- MF_GRAYED menü öğesini seçilemesin diye devre dışı bırakıp karartır.

### <a name="return-value"></a>Dönüş Değeri

Önceki durum (MF_DISABLED, MF_ENABLED veya MF_GRAYED) veya -1 geçerli değilse.

### <a name="remarks"></a>Açıklamalar

[CreateMenu](#createmenu), [InsertMenu](#insertmenu), [ModifyMenu](#modifymenu)ve [LoadMenuIndirect](#loadmenuindirect) üye işlevleri de bir menü öğesinin durumunu (etkin, devre dışı veya soluk) ayarlayabilir.

MF_BYPOSITION değerini kullanmak için bir uygulama `CMenu`nın doğru yutması gerekiyor. Menü `CMenu` çubuğunun kullanılması durumunda, üst düzey bir menü öğesi (menü çubuğundaki bir öğe) etkilenir. Bir öğenin durumunu açılır veya iç içe açılan menüdeki bir öğenin durumunu `CMenu` konuma göre ayarlamak için, bir uygulamanın açılır menüyü belirtmesi gerekir.

Bir uygulama MF_BYCOMMAND bayrağını belirttiğinde, Windows alt tasnif edilen `CMenu`tüm açılır menü öğelerini denetler; bu nedenle, yinelenen menü öğeleri `CMenu` yoksa, menü çubuğunun kullanımı yeterlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]

## <a name="cmenufromhandle"></a><a name="fromhandle"></a>CMenu::FromHandle

Bir etüye `CMenu` Windows tutamacı verilen bir nesneye işaretçiyi döndürür.

```
static CMenu* PASCAL FromHandle(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

*Hmenu*<br/>
Bir menü için bir Windows tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Geçici veya `CMenu` kalıcı olabilecek bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Windows `CMenu` menü nesnesine zaten bir nesne eklenmemişse, geçici `CMenu` bir nesne oluşturulur ve eklenir.

Bu `CMenu` geçici nesne yalnızca, uygulamanın olay döngüsünde boşta kalma süresine sahip olduğu ve tüm geçici nesnelerin silindiği bir sonraki zamana kadar geçerlidir.

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:CreateMenu](#createmenu).

## <a name="cmenugetdefaultitem"></a><a name="getdefaultitem"></a>CMenu::GetDefaultItem

Belirtilen menüdeki varsayılan menü öğesini belirler.

```
UINT GetDefaultItem(
    UINT gmdiFlags,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*gmdiBayraklar*<br/>
İşlevin menü öğelerini nasıl aradığını belirten değer. Bu parametre aşağıdaki değerlerin hiçbiri, bir veya bir arada olabilir:

|Değer|Anlamı|
|-----------|-------------|
|GMDI_GOINTOPOPUPS|Varsayılan öğe bir alt menü yü açan öğeyse, işlevin ilgili alt menüde özyinelemeli olarak arama yapmak olduğunu belirtir. Alt menüde varsayılan öğe yoksa, iade değeri alt menüyü açan öğeyi tanımlar.<br /><br /> Varsayılan olarak, işlev, alt menüyü açan bir öğe olup olmadığına bakılmaksızın, belirtilen menüdeki ilk varsayılan öğeyi döndürür.|
|GMDI_USEDISABLED|Devre dışı bırakılmış olsa bile işlevin varsayılan bir öğeyi döndürmek olduğunu belirtir.<br /><br /> Varsayılan olarak, işlev devre dışı bırakılan veya gri leştirilmiş öğeleri atlar.|

*fByPos*<br/>
Menü öğesinin tanımlayıcısını mı yoksa konumunu mu alınyoksa" öğesini belirten değer. Bu parametre FALSE ise, tanımlayıcı döndürülür. Aksi takdirde, pozisyon döndürülür.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, iade değeri menü öğesinin tanımlayıcısı veya konumudur. İşlev başarısız olursa, iade değeri - 1'dir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 işlevinin [GetMenuDefaultItem](/windows/win32/api/winuser/nf-winuser-getmenudefaultitem)davranışını uygular.

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:InsertMenu](#insertmenu).

## <a name="cmenugetmenucontexthelpid"></a><a name="getmenucontexthelpid"></a>CMenu::GetMenuContextHelpId

`CMenu`İlişkili bağlam yardım kimliğini alır.

```
DWORD GetMenuContextHelpId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bağlam yardım kimliği şu `CMenu` anda ilişkili varsa; sıfır aksi takdirde.

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:InsertMenu](#insertmenu).

## <a name="cmenugetmenuinfo"></a><a name="getmenuinfo"></a>CMenu::GetMenuInfo

Menü için bilgi alır.

```
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;
```

### <a name="parameters"></a>Parametreler

*lpcmi*<br/>
Menü için bilgi içeren bir [MENUINFO](/windows/win32/api/winuser/ns-winuser-menuinfo) yapısıiçin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, geri dönüş değeri sıfırdeğildir; aksi takdirde, iade değeri sıfırdır.

### <a name="remarks"></a>Açıklamalar

Menü hakkında bilgi almak için bu işlevi arayın.

## <a name="cmenugetmenuitemcount"></a><a name="getmenuitemcount"></a>CMenu::GetMenuItemCount

Açılır pencere veya üst düzey menüdeki öğelerin sayısını belirler.

```
UINT GetMenuItemCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa menüdeki öğe sayısı; aksi takdirde -1.

### <a name="example"></a>Örnek

  CWnd örneğine [bakın:GetMenu](../../mfc/reference/cwnd-class.md#getmenu).

## <a name="cmenugetmenuitemid"></a><a name="getmenuitemid"></a>CMenu::GetMenuItemID

*nPos*tarafından tanımlanan konumda bulunan bir menü öğesi için menü öğesi tanımlayıcısını alır.

```
UINT GetMenuItemID(int nPos) const;
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Kimliği alınan menü öğesinin konumunu (sıfır tabanlı) belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa açılır menüde belirtilen öğenin madde kimliği. Belirtilen öğe açılır menüise (açılır menüdeki bir öğenin aksine), iade değeri -1'dir. *nPos* bir AYıRıcı menü öğesine karşılık gelirse, iade değeri 0'dır.

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:InsertMenu](#insertmenu).

## <a name="cmenugetmenuiteminfo"></a><a name="getmenuiteminfo"></a>CMenu::GetMenuItemInfo

Menü öğesi hakkındaki bilgileri alır.

```
BOOL GetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*uÖğe*<br/>
Hakkında bilgi almak için menü öğesinin tanımlayıcısı veya konumu. Bu parametrenin anlamı `ByPos`.

*lpMenuItemInfo*<br/>
Windows SDK'da açıklandığı gibi, menü hakkında bilgi içeren bir [MENUITEMINFO](/windows/win32/api/winuser/ns-winuser-menuiteminfow)işaretçisi.

*fByPos*<br/>
Değerini ' nin `nIDItem`anlamını belirten. Varsayılan olarak, `ByPos` uItem bir menü öğesi tanımlayıcısı olduğunu gösterir FALSE olduğunu. FALSE `ByPos` olarak ayarlanmazsa, menü öğesi konumunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, geri dönüş değeri sıfırsız dır. İşlev başarısız olursa, geri dönüş değeri sıfırdır. Genişletilmiş hata bilgilerini almak için, Windows SDK'da açıklandığı gibi Win32 işlevini [getlasterror'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)kullanın.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 işlevinin [GetMenuItemInfo](/windows/win32/api/winuser/nf-winuser-getmenuiteminfow)davranışını uygular. MFC `GetMenuItemInfo`uygulamasında, bir menüye tutamacı kullanmadığınızı unutmayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]

## <a name="cmenugetmenustate"></a><a name="getmenustate"></a>CMenu::GetMenuState

Belirtilen menü öğesinin durumunu veya açılır menüdeki öğe sayısını döndürür.

```
UINT GetMenuState(
    UINT nID,
    UINT nFlags) const;
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
*nFlags*tarafından belirlenen menü öğesi kimliğini belirtir.

*Nflags*<br/>
*nID'nin*doğasını belirtir. Aşağıdaki değerlerden biri olabilir:

- MF_BYCOMMAND Parametrenin varolan menü öğesinin komut kimliğini verdiğini belirtir. Bu varsayılandır.

- MF_BYPOSITION Parametrenin varolan menü öğesinin konumunu verdiğini belirtir. İlk madde 0 konumundadır.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe yoksa 0xFFFFFFFF değeri. *nId* bir açılır menü tanımlıyorsa, yüksek sıralı bayt açılır menüdeki öğe sayısını içerir ve düşük sıralı bayt açılır menüyle ilişkili menü bayraklarını içerir. Aksi takdirde iade değeri aşağıdaki listedeki değerlerin bir maskesidir (Boolean OR) (bu maske *nId'in* tanımladığı menü öğesinin durumunu açıklar):

- MF_CHECKED Varsayılan onay işaretini öğenin yanına yerleştirmek için MF_UNCHECKED ile geçiş görevi görür. Uygulama onay işareti bit eşlerini sağladığında (üye işlevine `SetMenuItemBitmaps` bakın), "onay işareti üzerinde" bit eşlem görüntülenir.

- MF_DISABLED menü öğesini seçilemeyecek, ancak karartmayacak şekilde devre dışı kılabilir.

- MF_ENABLED Menü öğesini seçilebilmesini sağlar ve soluk durumundan geri getirir. Bu sabitin değerinin 0 olduğunu unutmayın; bir uygulama bu değeri kullanırken hata için 0'a karşı test etmemelidir.

- MF_GRAYED menü öğesini seçilemesin diye devre dışı bırakıp karartır.

- MF_MENUBARBREAK Öğeyi statik menülerde yeni bir satıra veya açılır menülerde yeni bir sütuna yerleştirir. Yeni açılır menü sütunu, dikey bir bölme satırı ile eski sütundan ayrılır.

- MF_MENUBREAK Öğeyi statik menülerde yeni bir satıra veya açılır menülerde yeni bir sütuna yerleştirir. Sütunlar arasına bölme satırı yerleştirilmez.

- MF_SEPARATOR Yatay bir bölme çizgisi çizer. Yalnızca açılır menüde kullanılabilir. Bu satır soluk, devre dışı veya vurgulanamaz. Diğer parametreler yoksayılır.

- MF_UNCHECKED Maddenin yanındaki onay işaretini kaldırmak için MF_CHECKED geçiş görevi görür. Uygulama onay işareti bit eşlerini sağladığında (üye işlevine `SetMenuItemBitmaps` bakın), "onay işareti" bit eşlemi görüntülenir. Bu sabitin değerinin 0 olduğunu unutmayın; bir uygulama bu değeri kullanırken hata için 0'a karşı test etmemelidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]

## <a name="cmenugetmenustring"></a><a name="getmenustring"></a>CMenu::GetMenuString

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

*nIDItem*<br/>
*nFlags*değerine bağlı olarak menü öğesinin veya menüdeki menü öğesinin ofsetinin veya sonlu tanımlayıcısını belirtir.

*lpString*<br/>
Etiketi almak için arabelleğe işaret ediyor.

*rString*<br/>
Kopyalanan menü `CString` dizesini almak için bir nesneye başvuru.

*nMaxCount*<br/>
Kopyalanacak etiketin en büyük uzunluğunu (karakterlerde) belirtir. Etiket *nMaxCount'da*belirtilen maksimumdan uzunsa, ek karakterler kesilir.

*Nflags*<br/>
*nIDItem* parametresinin yorumunu belirtir. Aşağıdaki değerlerden biri olabilir:

|Nflags|nIDItem yorumu|
|------------|-------------------------------|
|MF_BYCOMMAND|Parametrenin varolan menü öğesinin komut kimliğini verdiğini belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmazsa bu varsayılandır.|
|Mf_byposıtıon|Parametrenin varolan menü öğesinin konumunu verdiğini belirtir. İlk madde 0 konumundadır.|

### <a name="return-value"></a>Dönüş Değeri

Null sonlandırıcı dahil değil, arabelleğe kopyalanan karakterlerin gerçek sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

*nMaxCount* parametresi, bir dizeyi sonlandıran null karakterini yerleştirmek için etiketteki karakter sayısından daha büyük olmalıdır.

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:InsertMenu](#insertmenu).

## <a name="cmenugetsafehmenu"></a><a name="getsafehmenu"></a>CMenu::GetSafeHmenu

Bu `CMenu` nesne tarafından sarılmış HMENU'yi`CMenu` veya NULL işaretçisini döndürür.

```
HMENU GetSafeHmenu() const;
```

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:LoadMenu](#loadmenu).

## <a name="cmenugetsubmenu"></a><a name="getsubmenu"></a>CMenu::GetSubMenu

Açılır menü `CMenu` nesnesini alır.

```
CMenu* GetSubMenu(int nPos) const;
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Menüde bulunan açılır menünün konumunu belirtir. Konum değerleri ilk menü öğesi için 0'dan başlar. Açılır menünün tanımlayıcısı bu işlevde kullanılamaz.

### <a name="return-value"></a>Dönüş Değeri

Verilen konumda `CMenu` açılır `m_hMenu` menü varsa, üye açılır menüde tutamacı bulunan bir nesneye işaretçi; aksi takdirde NULL. Bir `CMenu` nesne yoksa, geçici bir nesne oluşturulur. Döndürülen `CMenu` işaretçi depolanmamalıdır.

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:TrackPopupMenu](#trackpopupmenu).

## <a name="cmenuinsertmenu"></a><a name="insertmenu"></a>CMenu::InsertMenu

*nPosition* tarafından belirtilen konuma yeni bir menü öğesi ekler ve diğer öğeleri menüye taşır.

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

*nPosition*<br/>
Yeni menü öğesinin eklenmeden önce ekleneceğini menü öğesini belirtir. *nFlags* parametresi, *nPosition'ı* aşağıdaki şekillerde yorumlamak için kullanılabilir:

|Nflags|nPosition yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametrenin varolan menü öğesinin komut kimliğini verdiğini belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmazsa bu varsayılandır.|
|Mf_byposıtıon|Parametrenin varolan menü öğesinin konumunu verdiğini belirtir. İlk madde 0 konumundadır. *nPosition* -1 ise, yeni menü öğesi menünün sonuna eklenir.|

*Nflags*<br/>
*nPosition'un* nasıl yorumlandığını belirtir ve menüye eklendiğinde yeni menü öğesinin durumu yla ilgili bilgileri belirtir. Ayarlanabilecek bayrakların listesi için [AppendMenu](#appendmenu) üye işlevine bakın. Birden fazla değer belirtmek için, bityönünde veya işleci kullanarak bunları MF_BYCOMMAND veya MF_BYPOSITION bayrağıyla birleştirin.

*nIDNewItem*<br/>
Yeni menü öğesinin komut kimliğini veya *nFlags* MF_POPUP ayarlanmışsa, açılır menünün menü tutamacını (HMENU) belirtir. *nFlags* MF_SEPARATOR ayarlanmışsa *nIDNewItem* parametresi yoksayılır (gerekli değildir).

*lpszNewItem*<br/>
Yeni menü öğesinin içeriğini belirtir. *nFlags* aşağıdaki şekillerde *lpszNewItem* yorumlamak için kullanılabilir:

|Nflags|lpszNewItem yorumu|
|------------|-----------------------------------|
|MF_OWNERDRAW|Uygulamanın menü öğesiyle ilişkili ek verileri korumak için kullanabileceği uygulama tarafından sağlanan 32 bit lik bir değer içerir. Bu 32 bit lik değer, `itemData` [WM_MEASUREITEM](/windows/win32/Controls/wm-measureitem) ve [WM_DRAWITEM](/windows/win32/Controls/wm-drawitem) iletileri tarafından sağlanan yapının üyesinde uygulama için kullanılabilir. Bu iletiler, menü öğesi başlangıçta görüntülendiğinde veya değiştirildiğinde gönderilir.|
|MF_STRING|Null-sonlandırılan dize için uzun bir işaretçi içerir. Bu varsayılan yorumdur.|
|MF_SEPARATOR|*lpszNewItem* parametresi yoksayılır (gerekli değildir).|

*pBmp*<br/>
Menü öğesi `CBitmap` olarak kullanılacak bir nesneye işaret edin.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulama *nFlags*değerleri ayarlayarak menü öğesinin durumunu belirtebilirsiniz.

Bir pencerede bulunan bir menü değiştirildiğinde (pencere görüntülenip görüntülenmemesi), `CWnd::DrawMenuBar`uygulama .

*nIDNewItem* açılır menü belirttiğinde, eklendiği menünün bir parçası olur. Bu menü yok edilirse, eklenen menü de yok edilir. Eklenen bir menü çakışma `CMenu` önlemek için bir nesneden ayrılmalıdır.

Etkin çoklu belge arabirimi (MDI) alt penceresi en üst düzeye çıkarsa ve bir uygulama bu işlevi arayarak ve MF_BYPOSITION bayrağını belirterek MDI uygulamasının menüsüne bir açılır menü eklerse, menü beklenenden daha sola bir konum eklenir. Bunun nedeni, etkin MDI alt penceresinin Denetim menüsünün MDI çerçeve penceresinin menü çubuğunun ilk konumuna eklenmesinden olur. Menüyü düzgün konumlandırmak için, uygulamanın başka türlü kullanılacak konum değerine 1 eklemesi gerekir. Bir uygulama, şu anda etkin olan alt pencerenin en üst düzeye çıkarılıp çıkarılmadığını belirlemek için WM_MDIGETACTIVE iletisini kullanabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]

## <a name="cmenuinsertmenuitem"></a><a name="insertmenuitem"></a>CMenu::EkleMenuItem

Menüde belirtilen konuma yeni bir menü öğesi ekler.

```
BOOL InsertMenuItem(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*uÖğe*<br/>
Windows SDK'daki [InsertMenuItem'deki](/windows/win32/api/winuser/nf-winuser-insertmenuitemw) *uItem* açıklamasına bakın.

*lpMenuItemInfo*<br/>
Windows SDK'daki `InsertMenuItem` *lpmii* açıklamasına bakın.

*fByPos*<br/>
Windows SDK'daki `InsertMenuItem` *fByPosition* açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Windows SDK'da açıklanan [InsertMenuItem'i](/windows/win32/api/winuser/nf-winuser-insertmenuitemw)sarar.

## <a name="cmenuloadmenu"></a><a name="loadmenu"></a>CMenü::LoadMenu

Uygulamanın yürütülebilir dosyasından bir menü kaynağı yükler `CMenu` ve nesneye bağlar.

```
BOOL LoadMenu(LPCTSTR lpszResourceName);
BOOL LoadMenu(UINT nIDResource);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Yüklenmesi gereken menü kaynağının adını içeren null-sonlandırılan dizeyi işaret edin.

*nIDKaynak*<br/>
Yüklenmesi gereken menü kaynağının menü kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Menü kaynağı başarıyla yüklenmişse sıfıra inmez; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çıkmadan önce, menü bir pencereye atanmamışsa, bir uygulamanın menüyle ilişkili sistem kaynaklarını serbest çemesi gerekir. Uygulama, [DestroyMenu](#destroymenu) üye işlevini arayarak menüyü boşaltıyor.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]

## <a name="cmenuloadmenuindirect"></a><a name="loadmenuindirect"></a>CMenu::LoadMenuIndirect

Bir kaynağı bellekteki bir menü şablonundan `CMenu` yükler ve nesneye bağlar.

```
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```

### <a name="parameters"></a>Parametreler

*lpMenuTemplate*<br/>
Menü şablonuna işaret eder (tek bir [MENUITEMTEMPLATEHEADER](/windows/win32/api/winuser/ns-winuser-menuitemtemplateheader) yapısı ve bir veya daha fazla [MENUITEMTEMPLATE](/windows/win32/api/winuser/ns-winuser-menuitemtemplate) yapısından oluşan bir koleksiyondur). Bu iki yapı hakkında daha fazla bilgi için Windows SDK'ya bakın.

### <a name="return-value"></a>Dönüş Değeri

Menü kaynağı başarıyla yüklenmişse sıfıra inmez; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Menü şablonu, her biri bir veya daha fazla menü öğesi ve açılır menü içerebilecek bir veya daha fazla [MENUITEMTEMPLATE](/windows/win32/api/winuser/ns-winuser-menuitemtemplate) yapısından oluşan bir koleksiyonun izlediği bir üstbilgidir.

Sürüm numarası 0 olmalıdır.

Bayraklar, `mtOption` açılır listedeki son öğe ve ana listedeki son öğe için MF_END içermelidir. Diğer `AppendMenu` bayraklar için üye işlevine bakın. Üye, `mtId` MF_POPUP belirtildiğinde MENUITEMTEMPLATE yapısından `mtOption`çıkarılmalıdır.

MENUITEMTEMPLATE yapısı için ayrılan alan, menü `mtString` öğesinin adını null-sonlandırılan dize olarak içerecek kadar büyük olmalıdır.

Çıkmadan önce, menü bir pencereye atanmamışsa, bir uygulamanın menüyle ilişkili sistem kaynaklarını serbest çemesi gerekir. Uygulama, [DestroyMenu](#destroymenu) üye işlevini arayarak menüyü boşaltıyor.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]

## <a name="cmenum_hmenu"></a><a name="m_hmenu"></a>CMenü::m_hMenu

Nesneye iliştirilen Windows menüsünün HMENU tutamacını `CMenu` belirtir.

```
HMENU m_hMenu;
```

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:LoadMenu](#loadmenu).

## <a name="cmenumeasureitem"></a><a name="measureitem"></a>CMenu::MeasureItem

Sahip çizim stiline sahip bir menü oluşturulduğunda çerçeve tarafından çağrılır.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpMeasureItemStruct*<br/>
Bir yapıiçin `MEASUREITEMSTRUCT` bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Bu üye işlevi geçersiz kılın `MEASUREITEMSTRUCT` ve Windows'u menünün boyutları hakkında bilgilendirmek için yapıyı doldurun.

Bkz. [CWnd::Yapının](../../mfc/reference/cwnd-class.md#onmeasureitem) `MEASUREITEMSTRUCT` açıklaması için OnMeasureItem.

### <a name="example"></a>Örnek

Aşağıdaki kod MFC [CTRLTEST](../../overview/visual-cpp-samples.md) örneğindendir:

[!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]

## <a name="cmenumodifymenu"></a><a name="modifymenu"></a>CMenu::ModifyMenu

Varolan bir menü öğesini *nPosition*tarafından belirtilen konumda değiştirir.

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

*nPosition*<br/>
Değiştirilecek menü öğesini belirtir. *nFlags* parametresi, *nPosition'ı* aşağıdaki şekillerde yorumlamak için kullanılabilir:

|Nflags|nPosition yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametrenin varolan menü öğesinin komut kimliğini verdiğini belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmazsa bu varsayılandır.|
|Mf_byposıtıon|Parametrenin varolan menü öğesinin konumunu verdiğini belirtir. İlk madde 0 konumundadır.|

*Nflags*<br/>
*nPosition'un* nasıl yorumlandığını belirtir ve menü öğesinde yapılacak değişiklikler hakkında bilgi verir. Ayarlanabilecek bayrakların listesi için [AppendMenu](#appendmenu) üye işlevine bakın.

*nIDNewItem*<br/>
Değiştirilen menü öğesinin komut kimliğini veya *nFlags* MF_POPUP ayarlanmışsa, açılır menünün menü tutamacını (HMENU) belirtir. *nFlags* MF_SEPARATOR ayarlanmışsa *nIDNewItem* parametresi yoksayılır (gerekli değildir).

*lpszNewItem*<br/>
Yeni menü öğesinin içeriğini belirtir. *nFlags* parametresi aşağıdaki şekillerde *lpszNewItem* yorumlamak için kullanılabilir:

|Nflags|lpszNewItem yorumu|
|------------|-----------------------------------|
|MF_OWNERDRAW|Uygulamanın menü öğesiyle ilişkili ek verileri korumak için kullanabileceği uygulama tarafından sağlanan 32 bit lik bir değer içerir. Bu 32 bit lik değer, MF_MEASUREITEM ve MF_DRAWITEM işlerken uygulama için kullanılabilir.|
|MF_STRING|Null-sonlandırılan dize veya bir `CString`' ye uzun bir işaretçi içerir.|
|MF_SEPARATOR|*lpszNewItem* parametresi yoksayılır (gerekli değildir).|

*pBmp*<br/>
Menü öğesi `CBitmap` olarak kullanılacak bir nesneye işaret edin.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulama, *nFlags'deki*değerleri ayarlayarak menü öğesinin yeni durumunu belirtir. Bu işlev menü öğesiyle ilişkili bir açılır menü yerine alırsa, eski açılır menüyü yok eder ve açılır menü tarafından kullanılan belleği boşaltıyor.

*nIDNewItem* açılır menü belirttiğinde, eklendiği menünün bir parçası olur. Bu menü yok edilirse, eklenen menü de yok edilir. Eklenen bir menü çakışma `CMenu` önlemek için bir nesneden ayrılmalıdır.

Bir pencerede bulunan bir menü değiştirildiğinde (pencere görüntülenip görüntülenmemesi), `CWnd::DrawMenuBar`uygulama . Varolan menü öğelerinin özniteliklerini değiştirmek için, `CheckMenuItem` `EnableMenuItem` ve üye işlevleri kullanmak çok daha hızlıdır.

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:InsertMenu](#insertmenu).

## <a name="cmenuoperator-hmenu"></a><a name="operator_hmenu"></a>CMenu::operatör HMENU

`CMenu` Nesnenin tutamacını almak için bu işleci kullanın.

```
operator HMENU() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, nesnenin `CMenu` tutamacı; aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Windows API'lerini doğrudan aramak için tutamacı kullanabilirsiniz.

## <a name="cmenuoperator-"></a><a name="operator_neq"></a>CMenu::operatör !=

İki menü mantıksal olarak eşit değilse belirler.

```
BOOL operator!=(const CMenu& menu) const;
```

### <a name="parameters"></a>Parametreler

*Menü*<br/>
Karşılaştırma `CMenu` için bir nesne.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir menü nesnesi sağ taraftaki menü nesnesine eşit değilse test edin.

## <a name="cmenuoperator-"></a><a name="operator_eq_eq"></a>CMenu::operatör ==

İki menü mantıksal olarak eşit olup olmadığını belirler.

```
BOOL operator==(const CMenu& menu) const;
```

### <a name="parameters"></a>Parametreler

*Menü*<br/>
Karşılaştırma `CMenu` için bir nesne.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir menü nesnesinin sağ taraftaki menü nesnesine eşit sayılsa (HMENU değeri açısından) test eder.

## <a name="cmenuremovemenu"></a><a name="removemenu"></a>CMenu::RemoveMenu

Menüden ilişkili açılır menü içeren bir menü öğesini siler.

```
BOOL RemoveMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

*nPosition*<br/>
Kaldırılacak menü öğesini belirtir. *nFlags* parametresi, *nPosition'ı* aşağıdaki şekillerde yorumlamak için kullanılabilir:

|Nflags|nPosition yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametrenin varolan menü öğesinin komut kimliğini verdiğini belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmazsa bu varsayılandır.|
|Mf_byposıtıon|Parametrenin varolan menü öğesinin konumunu verdiğini belirtir. İlk madde 0 konumundadır.|

*Nflags*<br/>
*nPosition'un* nasıl yorumlandığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Açılır menü için tutamacı yok etmez, böylece menü yeniden kullanılabilir. Bu işlevi aramadan önce, `GetSubMenu` uygulama yeniden kullanmak üzere `CMenu` açılır nesnealmak için üye işlevi çağırabilir.

Bir pencerede bulunan bir menü değiştirildiğinde (pencere görüntülenip görüntülenmemesi), `CWnd::DrawMenuBar`uygulamanın .

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:InsertMenu](#insertmenu).

## <a name="cmenusetdefaultitem"></a><a name="setdefaultitem"></a>CMenu::SetDefaultItem

Belirtilen menü için varsayılan menü öğesini ayarlar.

```
BOOL SetDefaultItem(
    UINT uItem,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*uÖğe*<br/>
Yeni varsayılan menü öğesinin tanımlayıcısı veya konumu veya - 1 varsayılan öğe için. Bu parametrenin anlamı *fByPos*değerine bağlıdır.

*fByPos*<br/>
*uÖğenin*anlamını belirten değer . Bu parametre FALSE ise, *uItem* bir menü öğesi tanımlayıcısın. Aksi takdirde, bir menü öğesi konumudur.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, geri dönüş değeri sıfırsız dır. İşlev başarısız olursa, geri dönüş değeri sıfırdır. Genişletilmiş hata bilgilerini almak için, Windows SDK'da açıklandığı gibi Win32 işlevini [getlasterror'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)kullanın.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 işlevi [SetMenuDefaultItem'in](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem)davranışını uygular.

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:InsertMenu](#insertmenu).

## <a name="cmenusetmenucontexthelpid"></a><a name="setmenucontexthelpid"></a>CMenu::SetMenuContextHelpId

Bir bağlam yardım `CMenu`kimliğini .

```
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```

### <a name="parameters"></a>Parametreler

*dwContextHelpId*<br/>
Bağlam yardım kimliği `CMenu`ile ilişkilendirmek için .

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0

### <a name="remarks"></a>Açıklamalar

Menüdeki tüm öğeler bu tanımlayıcıyı paylaşır — tek tek menü öğelerine yardım bağlamı tanımlayıcısı eklemek mümkün değildir.

### <a name="example"></a>Örnek

  CMenu örneğine [bakın:InsertMenu](#insertmenu).

## <a name="cmenusetmenuinfo"></a><a name="setmenuinfo"></a>CMenu::SetMenuInfo

Menü için bilgileri ayarlar.

```
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```

### <a name="parameters"></a>Parametreler

*lpcmi*<br/>
Menü için bilgi içeren bir [MENUINFO](/windows/win32/api/winuser/ns-winuser-menuinfo) yapısıiçin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, geri dönüş değeri sıfırdeğildir; aksi takdirde, iade değeri sıfırdır.

### <a name="remarks"></a>Açıklamalar

Menü hakkında belirli bilgileri ayarlamak için bu işlevi arayın.

## <a name="cmenusetmenuitembitmaps"></a><a name="setmenuitembitmaps"></a>CMenu::SetMenuItemBitmaps

Belirtilen bit eşlemleri bir menü öğesiyle ilişkilendirer.

```
BOOL SetMenuItemBitmaps(
    UINT nPosition,
    UINT nFlags,
    const CBitmap* pBmpUnchecked,
    const CBitmap* pBmpChecked);
```

### <a name="parameters"></a>Parametreler

*nPosition*<br/>
Değiştirilecek menü öğesini belirtir. *nFlags* parametresi, *nPosition'ı* aşağıdaki şekillerde yorumlamak için kullanılabilir:

|Nflags|nPosition yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametrenin varolan menü öğesinin komut kimliğini verdiğini belirtir. Ne MF_BYCOMMAND ne de MF_BYPOSITION ayarlanmazsa bu varsayılandır.|
|Mf_byposıtıon|Parametrenin varolan menü öğesinin konumunu verdiğini belirtir. İlk madde 0 konumundadır.|

*Nflags*<br/>
*nPosition'un* nasıl yorumlandığını belirtir.

*pBmpUnchecked*<br/>
Denetlenmeyen menü öğeleri için kullanılacak bit eşlemi belirtir.

*pBmpKontroled*<br/>
Denetlenen menü öğeleri için kullanılacak bit eşlemi belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Menü öğesi işaretli veya işaretli olsun, Windows menü öğesinin yanında uygun bit eşlemi görüntüler.

*PBmpUnchecked* veya *pBmpChecked* null ise, Windows ilgili öznitelik için menü öğesinin yanında hiçbir şey görüntüler. Her iki parametre de NULL ise, öğe işaretlendiğinde Windows varsayılan onay işaretini kullanır ve öğe işaretlenmediğinde onay işaretini kaldırır.

Menü yok edildiğinde, bu bit eşlemler yok edilmez; uygulama onları yok etmelidir.

Windows `GetMenuCheckMarkDimensions` işlevi menü öğeleri için kullanılan varsayılan onay işaretinin boyutlarını alır. Uygulama, bu işlevle birlikte verilen bit eşlemleri için uygun boyutu belirlemek için bu değerleri kullanır. Boyutu alın, bit eşlerinizi oluşturun ve sonra ayarlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]

[!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]

## <a name="cmenusetmenuiteminfo"></a><a name="setmenuiteminfo"></a>CMenu::SetMenuItemInfo

Menü öğesi hakkındaki bilgileri değiştirir.

```
BOOL SetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*uÖğe*<br/>
Windows SDK'daki [SetMenuItemInfo'daki](/windows/win32/api/winuser/nf-winuser-setmenuiteminfow) *uItem* açıklamasına bakın.

*lpMenuItemInfo*<br/>
Windows SDK'daki `SetMenuItemInfo` *lpmii* açıklamasına bakın.

*fByPos*<br/>
Windows SDK'daki `SetMenuItemInfo` *fByPosition* açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Windows SDK'da açıklanan [SetMenuItemInfo'yu](/windows/win32/api/winuser/nf-winuser-setmenuiteminfow)sarar.

## <a name="cmenutrackpopupmenu"></a><a name="trackpopupmenu"></a>CMenu::TrackPopupMenu

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

*Nflags*<br/>
Ekran konumu ve fare konumu bayraklarını belirtir. Kullanılabilir bayrakların listesi için [TrackPopupMenu'a](/windows/win32/api/winuser/nf-winuser-trackpopupmenu) bakın.

*X*<br/>
Açılır menünün ekran koordinatlarında yatay konumu belirtir. *nFlags* parametresinin değerine bağlı olarak, menü sol ait, sağa hizalanmış veya bu konuma göre ortalanmış olabilir.

*Y*<br/>
Ekrandaki menünün üst kısmındaki ekran koordinatlarında dikey konumu belirtir.

*Pwnd*<br/>
Açılır menüsünün sahibi olan pencereyi tanımlar. bu parametre, TPM_NONOTIFY bayrağı belirtilmiş olsa bile NULL olamaz. Bu pencere, menüden tüm WM_COMMAND iletileri alır. Windows sürümleri 3.1 ve sonraki sürümlerde, pencere `TrackPopupMenu` döndürülene kadar WM_COMMAND iletileri almaz. Windows 3.0'da, pencere iade `TrackPopupMenu` edilmeden önce WM_COMMAND iletileri alır.

*Lprect*<br/>
Göz ardı.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem, Windows SDK'da [TrackPopupMenu'u](/windows/win32/api/winuser/nf-winuser-trackpopupmenu) arama nın sonucunu döndürür.

### <a name="remarks"></a>Açıklamalar

Kayan açılır menü ekranın herhangi bir yerinde görünebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]

## <a name="cmenutrackpopupmenuex"></a><a name="trackpopupmenuex"></a>CMenu::TrackPopupMenuEx

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
Genişletilmiş menü için çeşitli işlevleri belirtir. Tüm değerlerin ve anlamlarının bir listesi için [TrackPopupMenuEx](/windows/win32/api/winuser/nf-winuser-trackpopupmenuex)bölümüne bakın.

*X*<br/>
Açılır menünün ekran koordinatlarında yatay konumu belirtir.

*Y*<br/>
Ekrandaki menünün üst kısmındaki ekran koordinatlarında dikey konumu belirtir.

*Pwnd*<br/>
Açılan menüye sahip olan ve oluşturulan menüden iletileri alan pencereye işaretçi. Bu pencere geçerli uygulamadan herhangi bir pencere olabilir, ancak NULL olamaz. *fuFlags* parametresinde TPM_NONOTIFY belirtirseniz, işlev *pWnd'ye*herhangi bir ileti göndermez. İşlev, WM_COMMAND iletisini almak için *pWnd* tarafından işaret edilen pencere için döndürülmelidir.

*lptpm*<br/>
Ekranın bir alanını belirten bir [TPMPARAMS](/windows/win32/api/winuser/ns-winuser-tpmparams) yapısına işaretçi, menünün çakışmaması gerekir. Bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

*fuFlags* parametresinde TPM_RETURNCMD belirtirseniz, iade değeri kullanıcının seçtiği öğenin menü öğesi tanımlayıcısı olur. Kullanıcı seçim yapmadan menüyü iptal ederse veya bir hata oluşursa, iade değeri 0 olur.

*fuFlags* parametresinde TPM_RETURNCMD belirtmezseniz, işlev başarılı olursa dönüş değeri sıfırsız, başarısız olursa 0 olur. Genişletilmiş hata bilgilerini almak için [GetLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)arayın.

### <a name="remarks"></a>Açıklamalar

Kayan açılır menü ekranın herhangi bir yerinde görünebilir. Açılır menü oluşturulurken işleme hataları hakkında daha fazla bilgi için [TrackPopupMenuEx'e](/windows/win32/api/winuser/nf-winuser-trackpopupmenuex)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek DYNAMENU](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)
