---
title: CMenu sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c13b4d5c3779d6c4b57ff53a1016b344ed097099
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083366"
---
# <a name="cmenu-class"></a>CMenu sınıfı

Windows sarmalanmasını `HMENU`.

## <a name="syntax"></a>Sözdizimi

```
class CMenu : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMenu::CMenu](#cmenu)|Oluşturur bir `CMenu` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMenu::AppendMenu](#appendmenu)|Bu menü sonuna yeni bir öğe ekler.|
|[CMenu::Attach](#attach)|Windows menüsü işleyici ekler bir `CMenu` nesne.|
|[CMenu::CheckMenuItem](#checkmenuitem)|Yanında bir onay işareti yerleştirir veya bir menü öğesi açılır menüde bir onay işareti kaldırır.|
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|Bir menü öğesinin yanındaki radyo düğmesini yerleştirir ve radyo düğmesi grubundaki diğer menü öğelerinin tümünün kaldırır.|
|[CMenu::CreateMenu](#createmenu)|Boş bir menüye oluşturur ve ona bağlanan bir `CMenu` nesne.|
|[CMenu::CreatePopupMenu](#createpopupmenu)|Boş bir açılır menü oluşturur ve ona bağlanan bir `CMenu` nesne.|
|[CMenu::DeleteMenu](#deletemenu)|Belirtilen bir öğe Menüsü'nden siler. Menü öğesi ilişkili bir açılır menü varsa, açılır menüsüne tanıtıcısı yok eder ve tarafından kullanılan belleği serbest bırakır.|
|[CMenu::DeleteTempMap](#deletetempmap)|Herhangi bir geçici siler `CMenu` tarafından oluşturulmuş nesneleri `FromHandle` üye işlevi.|
|[CMenu::DestroyMenu](#destroymenu)|Bağlı menü yok eder bir `CMenu` nesne ve menü kapladığı herhangi bir belleği serbest bırakır.|
|[CMenu::Detach](#detach)|Windows menüsü tanıtıcıdan ayırır bir `CMenu` nesne ve tanıtıcısını döndürür.|
|[CMenu::DrawItem](#drawitem)|Görsel bir özelliği bir sahip tarafından çizilmiş menü değişiklik olduğunda framework tarafından çağırılır.|
|[CMenu::EnableMenuItem](#enablemenuitem)|Etkinleştirir, devre dışı bırakır veya (grileri) karartır menü öğesi.|
|[CMenu::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CMenu` Windows menü tanıtıcısı verilen nesne.|
|[CMenu::GetDefaultItem](#getdefaultitem)|Belirtilen menüsünde varsayılan menü öğesini belirler.|
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|Menü ile ilişkili Yardım içeriği kimliği alır.|
|[CMenu::GetMenuInfo](#getmenuinfo)|Belirli bir menüsünde bilgilerini alır.|
|[CMenu::GetMenuItemCount](#getmenuitemcount)|Açılan veya üst düzey bir menüdeki öğelerin sayısını belirler.|
|[CMenu::GetMenuItemID](#getmenuitemid)|Belirtilen konumda bulunan bir menü öğesi için menü öğesi tanımlayıcısını alır.|
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|Bir menü öğesi hakkındaki bilgileri alır.|
|[CMenu::GetMenuState](#getmenustate)|Açılır menüde belirtilen menü öğesi ya da öğe sayısını döndürür.|
|[CMenu::GetMenuString](#getmenustring)|Belirtilen bir menü öğesinin etiketini alır.|
|[CMenu::GetSafeHmenu](#getsafehmenu)|Döndürür `m_hMenu` bu tarafından Sarmalanan `CMenu` nesne.|
|[CMenu::GetSubMenu](#getsubmenu)|Açılır menü için bir işaretçi alır.|
|[CMenu::InsertMenu](#insertmenu)|Belirli bir konumda menüsünün diğer öğeleri taşıma, yeni bir menü öğesi ekler.|
|[CMenu::InsertMenuItem](#insertmenuitem)|Bir menü belirtilen konumda yeni bir menü öğesi ekler.|
|[CMenu::LoadMenu](#loadmenu)|Bir menü kaynağı yürütülebilir dosyayı yükler ve ekler bir `CMenu` nesne.|
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|Bellek menü şablonunda bir menüyü yükler ve ekler bir `CMenu` nesne.|
|[CMenu::MeasureItem](#measureitem)|Sahip tarafından çizilmiş bir menü oluşturulduğunda menü boyutları belirlemek için framework tarafından çağırılır.|
|[CMenu::ModifyMenu](#modifymenu)|Belirli bir konumda var olan bir menü öğesini değiştirir.|
|[CMenu::RemoveMenu](#removemenu)|İlişkili bir açılır menü ile menü öğesi belirtilen menüsünden siler.|
|[CMenu::SetDefaultItem](#setdefaultitem)|Varsayılan menü öğesi için belirtilen menüsünde ayarlar.|
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|Yardım içeriği kimliği menüsü ile ilişkilendirilecek ayarlar.|
|[CMenu::SetMenuInfo](#setmenuinfo)|Belirli bir menüsünde bilgilerini ayarlar.|
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|Belirtilen onay işareti bit eşlemler Menü öğesiyle ilişkilendirir.|
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|Bir menü öğesinin bilgilerini değiştirir.|
|[CMenu::TrackPopupMenu](#trackpopupmenu)|Belirtilen bir konuma kayan bir açılır menü görüntüler ve açılır menüde öğelerinin seçimini izler.|
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|Belirtilen bir konuma kayan bir açılır menü görüntüler ve açılır menüde öğelerinin seçimini izler.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CMenu::operator HMENU](#operator_hmenu)|Menü nesnesini tanıtıcısını alır.|
|[CMenu::operator! =](#operator_neq)|İki menü nesnenin eşit olup olmadığını belirler.|
|[CMenu::operator ==](#operator_eq_eq)|İki menü nesnenin eşit olup olmadığını belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMenu::m_hMenu](#m_hmenu)|Bağlı Windows menüsüne tanıtıcı belirtir `CMenu` nesne.|

## <a name="remarks"></a>Açıklamalar

Oluşturma, izleme, güncelleştirme ve bir menü yok etme için üye işlevleri sağlar.

Oluşturma bir `CMenu` nesnesi olarak yerel bir yığın çerçevesi üzerinde'ı çağırın `CMenu`ait yeni menü gerektiği şekilde yönlendirmek üzere öğe işlevleri. Ardından, arama [CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu) bir pencereye menüsünü ayarlamak için hemen ardından bir çağrı tarafından `CMenu` nesnenin [ayırma](#detach) üye işlevi. `CWnd::SetMenu` Üye işlevi için yeni menü Pencere menüsünde ayarlar, menü değişikliği yansıtacak şekilde çizilmesini pencerenin neden olur ve ayrıca menü sahipliğini penceresine geçirir. Çağrı `Detach` HMENU öğesinden ayırır `CMenu` nesnesi, bunu olduğunda yerel `CMenu` değişken kapsam dışına geçirir `CMenu` artık sahip menü yok edilecek nesne yokedici denemez. Pencere yok edildiğinde menüsü otomatik olarak yok edilir.

Kullanabileceğiniz [LoadMenuIndirect](#loadmenuindirect) bellekte bir şablondan bir menü, ancak bir kaynaktan bir çağrı tarafından oluşturulan bir menü oluşturmak için üye işlevi [LoadMenu](#loadmenu) daha kolay korunur ve menü kaynağı oluşturulan ve menü düzenleyici tarafından değiştirilmiş.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMenu`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="appendmenu"></a>  CMenu::AppendMenu

Yeni öğe menü sonuna ekler.

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
Menüye eklendiğinde Yeni menü öğesinin durumu hakkındaki bilgileri belirtir. Bir veya daha fazla açıklamalar bölümünde listelenen değerlerden oluşur.

*nIDNewItem*<br/>
Yeni menü öğesinin komut Kimliğini belirtir veya *nFlags* MF_POPUP, menü tanıtıcısı ayarlayın ( `HMENU`) açılan menüsünün. *NIDNewItem* parametresi yok sayıldı (gerekli değil), *nFlags* MF_SEPARATOR için ayarlanır.

*lpszNewItem*<br/>
Yeni menü öğesinin içeriğini belirtir. *NFlags* yorumlamak için kullanılan parametre *lpszNewItem* şu şekilde:

|nFlags|LpszNewItem yorumu|
|------------|-----------------------------------|
|MF_OWNERDRAW|Uygulama Menü öğesiyle ilişkili ek verileri korumak için kullanabileceğiniz bir uygulama tarafından sağlanan 32-bit değeri içeriyor. WM_MEASUREITEM ve WM_DRAWITEM iletilerini işlerken bu 32 bit değeri uygulama için kullanılabilir. Bir değeri depolanan `itemData` bu iletileri ile sağlanan yapı üyesi.|
|MF_STRING|Null ile sonlandırılmış dizeye bir işaretçi içerir. Bu varsayılan yorumlamasıdır.|
|MF_SEPARATOR|*LpszNewItem* parametresi yok sayıldı (gerekli).|

*pBmp*<br/>
İşaret eden bir `CBitmap` menü öğesi olarak kullanılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulama durumu menü öğesinin değerleri ayarlayarak belirtebilirsiniz *nFlags*. Zaman *nIDNewItem* bir açılır menü belirtir, eklenmeden menüsünde bir parçası olur. Bu menü yok, eklenmiş menüsünü de yok edilir. Eklenmiş bir menü ayrılmış bir `CMenu` çakışmayı önlemek için nesne. MF_STRING ve MF_OWNERDRAW bit eşlem sürümü için geçerli olmadığını unutmayın `AppendMenu`.

Aşağıdaki listede, içinde ayarlanabilir bayrakların açıklanmaktadır *nFlags*:

- Öğesinin yanındaki işareti yerleştirmek MF_UNCHECKED ile geçiş olarak görev yapar MF_CHECKED denetleyin. Ne zaman uygulama onay işareti bit eşlemler sağlar (bkz [SetMenuItemBitmaps](#setmenuitembitmaps) üye işlevi), "üzerinde onay işareti" bit eşlem görüntülenir.

- Geçiş MF_UNCHECKED görür ile MF_CHECKED bir öğesinin yanındaki onay işaretini kaldırın. Ne zaman uygulama onay işareti bit eşlemler sağlar (bkz `SetMenuItemBitmaps` üye işlevi), "devre dışı onay işareti" bit eşlem görüntülenir.

- Böylece seçilemez ancak bu dim değil MF_DISABLED menü öğesi devre dışı bırakır.

- MF_ENABLED seçilebilir ve kendi devre dışı durumundan geri yükler menü öğesini etkinleştirir.

- Böylece seçilemez ve onu karartır MF_GRAYED menü öğesi devre dışı bırakır.

- MF_MENUBARBREAK statik menüler ya da yeni bir sütun açılır menüler içinde yeni bir satır öğesi yerleştirir. Yeni bir açılır menü sütun eski sütunu Dikey bölme bir çizgiyle ayrılacaktır.

- MF_MENUBREAK statik menüler ya da yeni bir sütun açılır menüler içinde yeni bir satır öğesi yerleştirir. Hiçbir çizgi sütunlar arasında yer alır.

- MF_OWNERDRAW öğesi bir özelleştirilmiş çizimli öğesi olduğunu belirtir. Menü ilk kez görüntülendiğinde, menü sahibi pencerenin yüksekliğini ve genişliğini menü öğesinin alır bir WM_MEASUREITEM ileti alır. WM_DRAWITEM menü öğesi öğesinin görsel görünümüne sahip gerekir güncelleştirdiğinizde gönderilen bir iletidir. Bu seçenek, bir üst düzey menü öğesi için geçerli değildir.

- MF_POPUP kendisiyle ilişkilendirilmiş bir açılır menü menü öğesi olan belirtir. ID parametresi için açılır menü öğesiyle ilişkilendirilmiş olan bir tanıtıcı belirtir. Bu, üst düzey bir açılır menü ya da hiyerarşik bir açılır menü açılır menü öğesine eklemek için kullanılır.

- MF_SEPARATOR yatay bir çizgi çizer. Yalnızca bir açılır menüde kullanılabilir. Bu satırı soluk, vurgulanan veya devreden çıkarılamaz. Diğer parametreler yok sayılır.

- MF_STRING menü öğesi bir karakter dizesi belirtir.

Aşağıdaki grupların her biri, karşılıklı olarak birbirini dışlar ve birlikte kullanılamaz bayrakları listeler:

- MF_DISABLED MF_ENABLED ve MF_GRAYED

- MF_STRING, MF_OWNERDRAW, MF_SEPARATOR ve bit eşlem sürümü

- MF_MENUBARBREAK ve MF_MENUBREAK

- MF_CHECKED ve MF_UNCHECKED

Bir menü içinde bulunan her bir pencere (penceresinde görüntülenen olup olmadığını) değiştirilir, uygulamayı çağırması gerekir [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::CreateMenu](#createmenu).

##  <a name="attach"></a>  CMenu::Attach

Mevcut bir Windows menüsüne ekler bir `CMenu` nesne.

```
BOOL Attach(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

*hMenu*<br/>
Windows menüsü için bir tanıtıcı belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir menü zaten ekli ise bu işlev çağrılmamalıdır `CMenu` nesne. Menü tanıtıcısı depolanan `m_hMenu` veri üyesi.

İşlemek istediğiniz menü zaten bir pencere ile ilişkili ise, kullanabileceğiniz [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu) menüsüne bir tanıtıcı almak için işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

##  <a name="checkmenuitem"></a>  CMenu::CheckMenuItem

Onay işareti ekler veya onay işaretleri açılır menüyü menü öğeleri kaldırır.

```
UINT CheckMenuItem(
    UINT nIDCheckItem,
    UINT nCheck);
```

### <a name="parameters"></a>Parametreler

*nIDCheckItem*<br/>
Denetlenecek, menü öğesi tarafından belirlenen belirtir *Nbakım*.

*Nbakım*<br/>
Menü öğesi denetleyin ve menüsünde öğenin konumunu belirlemek belirtir. *Nbakım* parametre birleşimi MF_CHECKED veya MF_UNCHECKED MF_BYPOSITION veya MF_BYCOMMAND bayrağı ile olabilir. Bu bayrak bit düzeyinde OR işleci kullanılarak birleştirilebilir. Bunlar, aşağıdaki anlamlara sahip:

- Parametresi varolan menü öğesinin komut kimliği verir MF_BYCOMMAND belirtir. Bu varsayılandır.

- MF_BYPOSITION parametresi mevcut menü öğesinin konumunu verdiğini belirtir. İlk öğesi 0 konumundadır.

- Öğesinin yanındaki işareti yerleştirmek MF_UNCHECKED ile geçiş olarak görev yapar MF_CHECKED denetleyin.

- Geçiş MF_UNCHECKED görür ile MF_CHECKED bir öğesinin yanındaki onay işaretini kaldırın.

### <a name="return-value"></a>Dönüş Değeri

Öğesinin önceki durumunu: MF_CHECKED veya MF_UNCHECKED, ya da menü öğesi mevcut değilse 0xFFFFFFFF.

### <a name="remarks"></a>Açıklamalar

*NIDCheckItem* parametresi değiştirilecek öğesi belirtir.

*NIDCheckItem* menü öğesi yanı sıra bir açılır menü öğesi parametreyi tanımlamak. Bir açılır menü öğesini denetlemek için hiçbir özel adım gereklidir. Üst düzey menü öğeleri iade edilemez. Kendisiyle ilişkili bir menü öğesini tanımlayıcısı olmadığından bir açılır menü öğesi konuma göre denetlenmesi gerekir.

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::GetMenuState](#getmenustate).

##  <a name="checkmenuradioitem"></a>  CMenu::CheckMenuRadioItem

Belirtilen menü öğesi denetler ve bir seçenek öğesi kolaylaştırır.

```
BOOL CheckMenuRadioItem(
    UINT nIDFirst,
    UINT nIDLast,
    UINT nIDItem,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

*nIDFirst*<br/>
Belirtir (kimliği veya değerine göre bir uzaklık olarak *nFlags*) radyo düğmesi grubunda ilk menü öğesi.

*nIDLast*<br/>
Belirtir (kimliği veya değerine göre bir uzaklık olarak *nFlags*) radyo düğmesi grubunda son menü öğesi.

*nIDItem*<br/>
Belirtir (kimliği veya değerine göre bir uzaklık olarak *nFlags*) öğe grubundaki bir radyo düğmesi ile denetlenir.

*nFlags*<br/>
Yorumu belirtir *nIDFirst*, *nIDLast*, ve *nIDItem* şu şekilde:

|nFlags|Yorumu|
|------------|--------------------|
|MF_BYCOMMAND|Parametresi mevcut menü öğesinin komut kimliği verdiğini belirtir. MF_BYCOMMAND ne MF_BYPOSITION ayarlanmışsa varsayılan değer budur.|
|MF_BYPOSITION|Parametresi mevcut menü öğesinin konumunu verdiğini belirtir. İlk öğesi 0 konumundadır.|

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0

### <a name="remarks"></a>Açıklamalar

Aynı anda işlevi ilişkili grubundaki diğer tüm menü öğeleri temizler ve bu öğeler için radyo öğe türü bayrağını kaldırır. Bir onay işareti bit eşlem yerine bir radyo düğmesi (veya madde işareti) bit eşlemi kullanılarak işaretlenmiş öğe görüntülenir.

### <a name="example"></a>Örnek

  Örneğin bakın [ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range).

##  <a name="cmenu"></a>  CMenu::CMenu

Boş bir menüye oluşturur ve ona bağlanan bir `CMenu` nesne.

```
CMenu();
```

### <a name="remarks"></a>Açıklamalar

Menü oluşturma birini çağırın ya da üye işlevleri yüklemek kadar oluşturulmaz `CMenu:`

- [CreateMenu](#createmenu)

- [CreatePopupMenu](#createpopupmenu)

- [LoadMenu](#loadmenu)

- [LoadMenuIndirect](#loadmenuindirect)

- [Attach](#attach)

##  <a name="createmenu"></a>  CMenu::CreateMenu

Bir menü oluşturur ve ona ekler `CMenu` nesne.

```
BOOL CreateMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Menü başarıyla oluşturuldu olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Menü başlangıçta boş kalır. Menü öğelerini kullanarak eklenebilir `AppendMenu` veya `InsertMenu` üye işlevi.

Pencere menüsü atanırsa, pencerenin kaldırıldığında otomatik olarak edilir.

Çıkmadan önce uygulamaya sahip bir menüyü menü pencere uygulanmamışsa ilişkili sistem kaynaklarının boşaltmanız gerekir. Uygulamanın çağırarak bir menü boşaltır [DestroyMenu](#destroymenu) üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]

##  <a name="createpopupmenu"></a>  CMenu::CreatePopupMenu

Açılır menü oluşturur ve ona ekler `CMenu` nesne.

```
BOOL CreatePopupMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Açılır menü başarıyla oluşturuldu olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Menü başlangıçta boş kalır. Menü öğelerini kullanarak eklenebilir `AppendMenu` veya `InsertMenu` üye işlevi. Uygulama, var olan bir menü veya açılır menü açılır menüyü ekleyebilirsiniz. `TrackPopupMenu` Üye işlevi bu menü kayan bir açılır menü olarak görüntüleme ve açılır menüden seçim izlemek için kullanılabilir.

Pencere menüsü atanırsa, pencerenin kaldırıldığında otomatik olarak edilir. Varolan bir menüye menü eklenirse, bu menü yok edildiğinde otomatik olarak edilir.

Çıkmadan önce bir uygulama bir pencere menü atanmamışsa bir açılır menü ile ilişkili sistem kaynakları boşaltmanız gerekir. Uygulamanın çağırarak bir menü boşaltır [DestroyMenu](#destroymenu) üye işlevi.

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::CreateMenu](#createmenu).

##  <a name="deletemenu"></a>  CMenu::DeleteMenu

Menüden bir öğeyi siler.

```
BOOL DeleteMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

*Nsürdürür*<br/>
Menü öğesi tarafından belirlenen silinecek olan belirtir *nFlags*.

*nFlags*<br/>
Yorumlamak için kullanılan *Nsürdürür* şu şekilde:

|nFlags|Nsürdürür yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametresi mevcut menü öğesinin komut kimliği verdiğini belirtir. MF_BYCOMMAND ne MF_BYPOSITION ayarlanmışsa varsayılan değer budur.|
|MF_BYPOSITION|Parametresi mevcut menü öğesinin konumunu verdiğini belirtir. İlk öğesi 0 konumundadır.|

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Menü öğesi ilişkili bir açılır menü varsa `DeleteMenu` açılır menüsüne tanıtıcısı yok eder ve açılan menü tarafından kullanılan belleği serbest bırakır.

Zaman içinde bulunan bir menü (penceresinde görüntülenen olup olmadığını) bir penceresi değiştirildiğinde, uygulamayı çağırması gerekir [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).

### <a name="example"></a>Örnek

  Örneğin bakın [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).

##  <a name="deletetempmap"></a>  CMenu::DeleteTempMap

Tarafından otomatik olarak adlandırılan `CWinApp` boşta kalma süresi işleyici, hiçbir geçici siler `CMenu` tarafından oluşturulmuş nesneleri [FromHandle](#fromhandle) üye işlevi.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Açıklamalar

`DeleteTempMap` geçici bir eklenmiş Windows menü nesnesini ayırır `CMenu` silmeden önce nesne `CMenu` nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]

##  <a name="destroymenu"></a>  CMenu::DestroyMenu

Menü ve kullanılan herhangi bir Windows kaynağa yok eder.

```
BOOL DestroyMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Menü yok olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Menü alanından ayrılmış `CMenu` yok edilir önce nesne. Windows `DestroyMenu` işlevini çağırdı otomatik olarak `CMenu` yıkıcı.

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::CreateMenu](#createmenu).

##  <a name="detach"></a>  CMenu::Detach

Windows Menüsü'nden ayırır bir `CMenu` nesne ve tanıtıcısını döndürür.

```
HMENU Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bir Windows menüsü HMENU, türünün tanıtıcısı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

`m_hMenu` Veri üyesi NULL olarak ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

##  <a name="drawitem"></a>  CMenu::DrawItem

Görsel bir özelliği bir sahip tarafından çizilmiş menü değişiklik olduğunda framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Bir işaretçi bir [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) gerekli çizim türü hakkında bilgi içeren yapısı.

### <a name="remarks"></a>Açıklamalar

`itemAction` Üyesi `DRAWITEMSTRUCT` gerçekleştirilecek çizim eylemi yapısını tanımlar. Sahip çizim için çizim uygulamak için bu üye işlevi geçersiz kılma `CMenu` nesne. Uygulama görünen bağlam sağlanan için seçilen tüm grafik cihaz arabirimi (GDI) nesneleri geri yüklemeniz gerekir *lpDrawItemStruct* bu üye işlevinin sona ermeden önce.

Bkz: [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) açıklamasını `DRAWITEMSTRUCT` yapısı.

### <a name="example"></a>Örnek

Aşağıdaki kod MFC'den olan [CTRLTEST](../../visual-cpp-samples.md) örnek:

[!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]

##  <a name="enablemenuitem"></a>  CMenu::EnableMenuItem

Etkinleştirir, devre dışı bırakır veya bir menü öğesi karartır.

```
UINT EnableMenuItem(
    UINT nIDEnableItem,
    UINT nEnable);
```

### <a name="parameters"></a>Parametreler

*nIDEnableItem*<br/>
Etkinleştirilmesi için menü öğesi tarafından belirlenen belirtir *nEnable*. Bu parametre, açılan menü öğeleri, hem de standart menü öğeleri belirtebilirsiniz.

*nEnable*<br/>
Gerçekleştirilecek eylemi belirtir. Bu MF_DISABLED, MF_ENABLED veya MF_GRAYED, MF_BYCOMMAND veya MF_BYPOSITION bir birleşimi olabilir. Bu değerler bit düzeyinde OR işleci kullanılarak birleştirilebilir. Bu değerler, aşağıdaki anlamlara sahip:

- Parametresi varolan menü öğesinin komut kimliği verir MF_BYCOMMAND belirtir. Bu varsayılandır.

- MF_BYPOSITION parametresi mevcut menü öğesinin konumunu verdiğini belirtir. İlk öğesi 0 konumundadır.

- Böylece seçilemez ancak bu dim değil MF_DISABLED menü öğesi devre dışı bırakır.

- MF_ENABLED seçilebilir ve kendi devre dışı durumundan geri yükler menü öğesini etkinleştirir.

- Böylece seçilemez ve onu karartır MF_GRAYED menü öğesi devre dışı bırakır.

### <a name="return-value"></a>Dönüş Değeri

Önceki bir durumuna (MF_DISABLED, MF_ENABLED veya MF_GRAYED) veya -1, geçerli değil.

### <a name="remarks"></a>Açıklamalar

[CreateMenu](#createmenu), [InsertMenu](#insertmenu), [ModifyMenu](#modifymenu), ve [LoadMenuIndirect](#loadmenuindirect) üye işlevleri de (etkin durumuna ayarlayın soluk veya devre dışı) bir menü öğesinin.

MF_BYPOSITION değerini kullanarak bir uygulamayı doğru kullanmak için gerektirir `CMenu`. Varsa `CMenu` menü çubuğu kullanılır, üst düzey menü öğesi (menü çubuğunda bir öğe) etkilenir. Konuma göre bir açılır veya iç içe açılır menüsündeki bir öğeyi durumunu ayarlamak için bir uygulama belirtmeniz gerekir `CMenu` açılır menüsünden.

Bir uygulama MF_BYCOMMAND bayrağını belirttiğinde, Windows için bağımlı olan tüm açılır menü öğeleri denetler. `CMenu`; bu nedenle, yinelenen menü öğelerini olmadıkça kullanarak `CMenu` menü çubuğu yeterlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]

##  <a name="fromhandle"></a>  CMenu::FromHandle

Bir işaretçi döndüren bir `CMenu` menüye bir Windows belirli nesne.

```
static CMenu* PASCAL FromHandle(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

*hMenu*<br/>
Bir menüye Windows tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CMenu` geçici veya kalıcı olabilir.

### <a name="remarks"></a>Açıklamalar

Varsa bir `CMenu` nesne zaten iliştirilmemiş Windows menü nesnesini geçici `CMenu` nesnesi oluşturulur ve bağlı.

Bu geçici `CMenu` nesne, yalnızca geçerli uygulama aynı zamanda tüm geçici nesneler silinir kendi olay döngüsü içinde boşta kalma süresi olan zamana kadar.

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::CreateMenu](#createmenu).

##  <a name="getdefaultitem"></a>  CMenu::GetDefaultItem

Belirtilen menüsünde varsayılan menü öğesini belirler.

```
UINT GetDefaultItem(
    UINT gmdiFlags,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*gmdiFlags*<br/>
İşlev menü öğelerinin nasıl arama belirten değer. Bu parametre, none, bir veya bir birleşimi aşağıdaki değerlerden biri olabilir:

|Değer|Açıklama|
|-----------|-------------|
|GMDI_GOINTOPOPUPS|Varsayılan öğe, alt menüyü açılır ise, işlev karşılık gelen alt yinelemeli olarak aramak için belirtir. Alt varsayılan öğe varsa, dönüş değeri alt menü açılır öğesi tanımlar.<br /><br /> Varsayılan olarak, işlev bir alt menü açılır öğenin olmasına bakılmaksızın belirtilen menüsünde varsayılan ilk öğeyi döndürür.|
|GMDI_USEDISABLED|Devre dışı bırakılsa bile işlevi bir varsayılan öğe döndürmek için olduğunu belirtir.<br /><br /> Varsayılan olarak, işlev devre dışı bırakılmış veya gri öğeleri atlar.|

*fByPos*<br/>
Menü öğesinin tanımlayıcı veya konumunu almak etkinleştirilip etkinleştirilmeyeceğini belirten değeri. Bu parametre FALSE ise, tanımlayıcının döndürülür. Aksi takdirde, konumu döndürülür.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri tanımlayıcı veya menü öğesinin konumunu ' dir. İşlev başarısız olursa, dönüş değeri olduğu - 1.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 işlevinin davranışı uygulayan [GetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-getmenudefaultitem)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::InsertMenu](#insertmenu).

##  <a name="getmenucontexthelpid"></a>  CMenu::GetMenuContextHelpId

Kimliği ile ilişkili Bağlam Yardımı alır `CMenu`.

```
DWORD GetMenuContextHelpId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kimliği şu anda ilişkili Bağlam Yardımı `CMenu` ; varsa sıfır, aksi takdirde.

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::InsertMenu](#insertmenu).

##  <a name="getmenuinfo"></a>  CMenu::GetMenuInfo

Bir menünün bilgilerini alır.

```
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;
```

### <a name="parameters"></a>Parametreler

*lpcmi*<br/>
Bir işaretçi bir [MENUINFO](/windows/desktop/api/winuser/ns-winuser-tagmenuinfo) menüsüne ilişkin bilgi içeren yapıya.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri, sıfır olmayan; Aksi takdirde, dönüş değeri sıfırdır.

### <a name="remarks"></a>Açıklamalar

Menü hakkında bilgi almak için bu işlevi çağırın.

##  <a name="getmenuitemcount"></a>  CMenu::GetMenuItemCount

Açılan veya üst düzey bir menüdeki öğelerin sayısını belirler.

```
UINT GetMenuItemCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa menüdeki öğelerin sayısı; Aksi takdirde-1.

### <a name="example"></a>Örnek

  Örneğin bakın [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).

##  <a name="getmenuitemid"></a>  CMenu::GetMenuItemID

Tarafından tanımlanan bir konumda yer alan bir menü öğesi için menü öğesi tanımlayıcısını alır *nPos*.

```
UINT GetMenuItemID(int nPos) const;
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Kimliğine alınan konumunu (sıfır tabanlı) menü öğesi belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa açılır menüsünde belirtilen öğenin öğe kimliği. Belirtilen öğe bir açılır menü (aksine, bir öğe içinde açılır menü) ise, dönüş değeri -1'dir. Varsa *nPos* karşılık gelen bir AYIRICI menü öğesine dönüş değeri 0'dır.

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::InsertMenu](#insertmenu).

##  <a name="getmenuiteminfo"></a>  CMenu::GetMenuItemInfo

Bir menü öğesi hakkındaki bilgileri alır.

```
BOOL GetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*uItem*<br/>
Tanımlayıcı veya hakkında bilgi almak için menü öğesinin konumu. Bu parametre anlamını değerine bağlıdır `ByPos`.

*lpMenuItemInfo*<br/>
Bir işaretçi bir [MENUITEMINFO](/windows/desktop/api/winuser/ns-winuser-tagmenuiteminfoa)menü hakkında bilgi içeren Windows SDK, anlatılan şekilde.

*fByPos*<br/>
Anlamını belirten değeri `nIDItem`. Varsayılan olarak, `ByPos` bu uItem gösteren bir menü öğesini tanımlayıcısı yanlış. Varsa `ByPos` ayarlanmadı isteğe bağlı olarak FALSE olarak, bir menü öğesi konumu gösterir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri sıfır. İşlev başarısız olursa, dönüş değeri sıfırdır. Genişletilmiş hata bilgilerini almak için Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)Windows SDK içinde açıklandığı gibi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi davranışını uygulayan Win32 işlevin [GetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-getmenuiteminfoa)Windows SDK içinde açıklandığı gibi. Öğesinin MFC uygulamasında dikkat `GetMenuItemInfo`, bir tanıtıcı bir menüye kullanmayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]

##  <a name="getmenustate"></a>  CMenu::GetMenuState

Açılır menüde belirtilen menü öğesi ya da öğe sayısını döndürür.

```
UINT GetMenuState(
    UINT nID,
    UINT nFlags) const;
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Menü öğesi kimliği tarafından belirlenen belirtir *nFlags*.

*nFlags*<br/>
Yapısını belirtir *nID*. Aşağıdaki değerlerden biri olabilir:

- Parametresi varolan menü öğesinin komut kimliği verir MF_BYCOMMAND belirtir. Bu varsayılandır.

- MF_BYPOSITION parametresi mevcut menü öğesinin konumunu verdiğini belirtir. İlk öğesi 0 konumundadır.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe yoksa 0xFFFFFFFF değeri. Varsa *nId* tanımlayan bir açılır menü yüksek düzeyli bayt açılır menüdeki öğe sayısını ve açılır menü ile ilişkili menü bayrakları düşük düzey bayt içerir. Aksi takdirde dönüş değeri değerleri aşağıdaki listeden bir maskesi (mantıksal veya) mi (Bu maskesi menü durumunu açıklar öğesi *nId* tanımlar):

- Öğesinin yanındaki işareti yerleştirmek MF_UNCHECKED ile geçiş olarak görev yapar MF_CHECKED denetleyin. Ne zaman uygulama onay işareti bit eşlemler sağlar (bkz `SetMenuItemBitmaps` üye işlevi), "üzerinde onay işareti" bit eşlem görüntülenir.

- Böylece seçilemez ancak bu dim değil MF_DISABLED menü öğesi devre dışı bırakır.

- MF_ENABLED seçilebilir ve kendi devre dışı durumundan geri yükler menü öğesini etkinleştirir. Bu sabitin değeri 0 olduğuna dikkat edin; bir uygulama 0 hatasına karşı bu değeri kullanırken sınamalısınız değil.

- Böylece seçilemez ve onu karartır MF_GRAYED menü öğesi devre dışı bırakır.

- MF_MENUBARBREAK statik menüler ya da yeni bir sütun açılır menüler içinde yeni bir satır öğesi yerleştirir. Yeni bir açılır menü sütun eski sütunu Dikey bölme bir çizgiyle ayrılacaktır.

- MF_MENUBREAK statik menüler ya da yeni bir sütun açılır menüler içinde yeni bir satır öğesi yerleştirir. Hiçbir çizgi sütunlar arasında yer alır.

- MF_SEPARATOR yatay bir çizgi çizer. Yalnızca bir açılır menüde kullanılabilir. Bu satırı soluk, vurgulanan veya devreden çıkarılamaz. Diğer parametreler yok sayılır.

- Geçiş MF_UNCHECKED görür ile MF_CHECKED bir öğesinin yanındaki onay işaretini kaldırın. Ne zaman uygulama onay işareti bit eşlemler sağlar (bkz `SetMenuItemBitmaps` üye işlevi), "devre dışı onay işareti" bit eşlem görüntülenir. Bu sabitin değeri 0 olduğuna dikkat edin; bir uygulama 0 hatasına karşı bu değeri kullanırken sınamalısınız değil.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]

##  <a name="getmenustring"></a>  CMenu::GetMenuString

Belirtilen bir menü öğesinin etiket belirtilen arabelleğe kopyalar.

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
Menü öğesinin tamsayı tanımlayıcısı veya offset menü öğesinin değerine bağlı olarak menü belirtir *nFlags*.

*lpString*<br/>
Etiket alacak arabellek işaret eder.

*rString*<br/>
Bir başvuru bir `CString` kopyalanan menü dizeyi almak için olan nesne.

*nMaxCount*<br/>
Kopyalanacak etiketi maksimum uzunluğunu (karakter cinsinden) belirtir. Etiket belirtilen maksimum uzunsa *nMaxCount*, ek karakterler kesildi.

*nFlags*<br/>
Yorumu belirtir *nIDItem* parametresi. Aşağıdaki değerlerden biri olabilir:

|nFlags|NIDItem yorumu|
|------------|-------------------------------|
|MF_BYCOMMAND|Parametresi mevcut menü öğesinin komut kimliği verdiğini belirtir. MF_BYCOMMAND ne MF_BYPOSITION ayarlanmışsa varsayılan değer budur.|
|MF_BYPOSITION|Parametresi mevcut menü öğesinin konumunu verdiğini belirtir. İlk öğesi 0 konumundadır.|

### <a name="return-value"></a>Dönüş Değeri

Arabelleğe Sonlandırıcı null içermeden, kopyalanan karakterlerle gerçek sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

*NMaxCount* parametresi bir etiketi bir dizeyi sonlandıran null karakteri uyum sağlamak için karakter sayısından daha büyük olmalıdır.

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::InsertMenu](#insertmenu).

##  <a name="getsafehmenu"></a>  CMenu::GetSafeHmenu

Bu tarafından Sarmalanan HMENU döndürür `CMenu` nesne ya da bir NULL`CMenu` işaretçi.

```
HMENU GetSafeHmenu() const;
```

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::LoadMenu](#loadmenu).

##  <a name="getsubmenu"></a>  CMenu::GetSubMenu

Alır `CMenu` açılır menü nesne.

```
CMenu* GetSubMenu(int nPos) const;
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Menüde yer alan açılır menü konumunu belirtir. Konum değerleri 0 ilk menü öğesi için başlangıç. Açılır menünün tanımlayıcısını Bu işlevde kullanılamaz.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CMenu` nesnesi `m_hMenu` üye belirtilen konumda bir açılır menü varsa, açılır menüde bir işleç içeriyor; bulunmazsa null değerini DÖNDÜRÜR. Varsa bir `CMenu` nesne mevcut değil ve ardından geçici bir tane oluşturulur. `CMenu` Döndürülen işaretçi değil depolanmalıdır.

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::TrackPopupMenu](#trackpopupmenu).

##  <a name="insertmenu"></a>  CMenu::InsertMenu

Yeni menü öğesi tarafından belirtilen konumda ekler *Nsürdürür* ve diğer öğeleri menüye taşır.

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

*Nsürdürür*<br/>
Eklenecek yeni menü öğesi olan önüne menü öğesi belirtir. *NFlags* parametresi yorumlamak için kullanılabilir *Nsürdürür* aşağıdaki yollarla:

|nFlags|Nsürdürür yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametresi mevcut menü öğesinin komut kimliği verdiğini belirtir. MF_BYCOMMAND ne MF_BYPOSITION ayarlanmışsa varsayılan değer budur.|
|MF_BYPOSITION|Parametresi mevcut menü öğesinin konumunu verdiğini belirtir. İlk öğesi 0 konumundadır. Varsa *Nsürdürür* -1, yeni menü öğesini menü sonuna eklenir.|

*nFlags*<br/>
Belirtir nasıl *Nsürdürür* yorumlanır ve bir menüye eklendiğinde Yeni menü öğesinin durumu hakkındaki bilgileri belirtir. Ayarlanabilir bayrakların listesi için bkz. [döndürmesini](#appendmenu) üye işlevi. Birden fazla değer belirtmek için bit düzeyinde OR işleci MF_BYCOMMAND veya MF_BYPOSITION bayrağı ile birleştirilecek kullanın.

*nIDNewItem*<br/>
Yeni menü öğesinin komut Kimliğini belirtir veya *nFlags* MF_POPUP, açılan menüyü menü tanıtıcısı (HMENU) ayarlanır. *NIDNewItem* parametresi yok sayıldı (gerekli değil), *nFlags* MF_SEPARATOR için ayarlanır.

*lpszNewItem*<br/>
Yeni menü öğesinin içeriğini belirtir. *nFlags* yorumlamak için kullanılan *lpszNewItem* aşağıdaki yollarla:

|nFlags|LpszNewItem yorumu|
|------------|-----------------------------------|
|MF_OWNERDRAW|Uygulama Menü öğesiyle ilişkili ek verileri korumak için kullanabileceğiniz bir uygulama tarafından sağlanan 32-bit değeri içeriyor. Bu 32 bit değeri uygulamada kullanılabilir `itemData` tarafından sağlanan yapı üyesi [WM_MEASUREITEM](/windows/desktop/Controls/wm-measureitem) ve [WM_DRAWITEM](/windows/desktop/Controls/wm-drawitem) iletileri. Bu iletiler, menü öğesi başlangıçta görüntülenir veya değiştirildiğinde ettiğinde gönderilir.|
|MF_STRING|Null ile sonlandırılmış dizeye uzun bir işaretçi içerir. Bu varsayılan yorumlamasıdır.|
|MF_SEPARATOR|*LpszNewItem* parametresi yok sayıldı (gerekli).|

*pBmp*<br/>
İşaret eden bir `CBitmap` menü öğesi olarak kullanılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulama durumu menü öğesinin değerleri ayarlayarak belirtebilirsiniz *nFlags*.

Bir menü içinde bulunan her bir pencere (penceresinde görüntülenen olup olmadığını) değiştirilir, uygulamayı çağırması gerekir `CWnd::DrawMenuBar`.

Zaman *nIDNewItem* bir açılır menü belirtir, eklenen menüsünde bir parçası olur. Bu menü yok, eklenen menüsünü de yok edilir. Eklenen bir menü ayrılmış bir `CMenu` çakışmayı önlemek için nesne.

Bir konum değerinden daha da esnetmenize sol eklediyseniz Çok Belgeli Arabirim (MDI) alt penceresi ekranı etkin ve bu işlevi çağırmak ve menü MF_BYPOSITION bayrağını belirterek MDI uygulamanın menüsüne açılır menüde olduğu bir uygulama ekler bekleniyor. Etkin MDI alt penceresinin denetim menüsünden MDI çerçeve penceresinin menü çubuğunu ilk konumunu eklenen çünkü bu gerçekleşir. Menü düzgün konumlandırmak için uygulama, aksi takdirde kullanılacak konumu değerine 1 eklemeniz gerekir. Bir uygulama WM_MDIGETACTIVE ileti şu anda etkin alt pencerenin ekranı olup olmadığını belirlemek için kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]

##  <a name="insertmenuitem"></a>  CMenu::InsertMenuItem

Bir menü belirtilen konumda yeni bir menü öğesi ekler.

```
BOOL InsertMenuItem(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*uItem*<br/>
Açıklamasını görmek *uItem* içinde [InsertMenuItem](/windows/desktop/api/winuser/nf-winuser-insertmenuitema) Windows SDK.

*lpMenuItemInfo*<br/>
Açıklamasını görmek *lpmii* içinde `InsertMenuItem` Windows SDK.

*fByPos*<br/>
Açıklamasını görmek *fByPosition* içinde `InsertMenuItem` Windows SDK.

### <a name="remarks"></a>Açıklamalar

Bu işlevi sarmalar [InsertMenuItem](/windows/desktop/api/winuser/nf-winuser-insertmenuitema)Windows SDK içinde açıklandığı gibi.

##  <a name="loadmenu"></a>  CMenu::LoadMenu

Bir menü kaynağı uygulamanın yürütülebilir dosyasını yükler ve ekler `CMenu` nesne.

```
BOOL LoadMenu(LPCTSTR lpszResourceName);
BOOL LoadMenu(UINT nIDResource);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Yüklemek için menü kaynağı adını içeren bir boş sonlandırılmış dizeye işaret eder.

*nIDResource*<br/>
Yüklemek için menü kaynağı menü Kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Menü kaynağı başarıyla yüklendi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çıkmadan önce uygulamaya sahip bir menüyü menü pencere uygulanmamışsa ilişkili sistem kaynaklarının boşaltmanız gerekir. Uygulamanın çağırarak bir menü boşaltır [DestroyMenu](#destroymenu) üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]

##  <a name="loadmenuindirect"></a>  CMenu::LoadMenuIndirect

Bellekte bir menü şablondan bir kaynak yükler ve ekler `CMenu` nesne.

```
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```

### <a name="parameters"></a>Parametreler

*lpMenuTemplate*<br/>
İşaret eden bir menü şablonuna (tek bir olduğu [MENUITEMTEMPLATEHEADER](/windows/desktop/api/winuser/ns-winuser-menuitemtemplateheader) yapısı ve bir veya daha fazla koleksiyonu [MENUITEMTEMPLATE](/windows/desktop/api/winuser/ns-winuser-menuitemtemplate) yapıları). Bu iki yapılar hakkında daha fazla bilgi için Windows SDK'sı bakın.

### <a name="return-value"></a>Dönüş Değeri

Menü kaynağı başarıyla yüklendi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir veya daha fazla koleksiyonu tarafından izlenen bir üst menü şablonudur [MENUITEMTEMPLATE](/windows/desktop/api/winuser/ns-winuser-menuitemtemplate) yapıları, her biri içerebilir bir veya daha fazla menü öğeleri ve açılır menüler.

Sürüm numarası 0 olmalıdır.

`mtOption` Açılır listedeki son öğeyi ve ana listedeki son öğeyi bayrakları MF_END içermelidir. Bkz: `AppendMenu` üye işlevi için diğer bayraklar. `mtId` Üye MF_POPUP belirtildiğinde MENUITEMTEMPLATE yapısından eklenmemelidir `mtOption`.

MENUITEMTEMPLATE yapısı için yeterince büyük ayrılan alan `mtString` null ile sonlandırılmış bir dize olarak menü öğesinin adı içeriyor.

Çıkmadan önce uygulamaya sahip bir menüyü menü pencere uygulanmamışsa ilişkili sistem kaynaklarının boşaltmanız gerekir. Uygulamanın çağırarak bir menü boşaltır [DestroyMenu](#destroymenu) üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]

##  <a name="m_hmenu"></a>  CMenu::m_hMenu

Bağlı Windows menüsünün HMENU tanıtıcı belirtir `CMenu` nesne.

```
HMENU m_hMenu;
```

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::LoadMenu](#loadmenu).

##  <a name="measureitem"></a>  CMenu::MeasureItem

Sahip çizim stili sahip bir menüyü oluşturulduğunda framework tarafından çağırılır.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpMeasureItemStruct*<br/>
Bir işaretçi bir `MEASUREITEMSTRUCT` yapısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Bu üye işlevini geçersiz kılabilir ve doldurun `MEASUREITEMSTRUCT` menünün boyutlarının Windows bildirmek için yapısı.

Bkz: [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) açıklamasını `MEASUREITEMSTRUCT` yapısı.

### <a name="example"></a>Örnek

Aşağıdaki kod MFC'den olan [CTRLTEST](../../visual-cpp-samples.md) örnek:

[!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]

##  <a name="modifymenu"></a>  CMenu::ModifyMenu

Var olan bir menü öğesi tarafından belirtilen konumdaki değişiklikleri *Nsürdürür*.

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

*Nsürdürür*<br/>
Değiştirilecek menü öğesi belirtir. *NFlags* parametresi yorumlamak için kullanılabilir *Nsürdürür* aşağıdaki yollarla:

|nFlags|Nsürdürür yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametresi mevcut menü öğesinin komut kimliği verdiğini belirtir. MF_BYCOMMAND ne MF_BYPOSITION ayarlanmışsa varsayılan değer budur.|
|MF_BYPOSITION|Parametresi mevcut menü öğesinin konumunu verdiğini belirtir. İlk öğesi 0 konumundadır.|

*nFlags*<br/>
Belirtir nasıl *Nsürdürür* yorumlanır ve bir menü öğesine yapılacak değişiklikler hakkında bilgi sağlar. Ayarlanabilir bayrakların listesi için bkz. [döndürmesini](#appendmenu) üye işlevi.

*nIDNewItem*<br/>
Değiştirilen menü öğesinin komut Kimliğini belirtir veya *nFlags* MF_POPUP, açılan menüyü menü tanıtıcısı (HMENU) ayarlanır. *NIDNewItem* parametresi yok sayıldı (gerekli değil), *nFlags* MF_SEPARATOR için ayarlanır.

*lpszNewItem*<br/>
Yeni menü öğesinin içeriğini belirtir. *NFlags* parametresi yorumlamak için kullanılabilir *lpszNewItem* aşağıdaki yollarla:

|nFlags|LpszNewItem yorumu|
|------------|-----------------------------------|
|MF_OWNERDRAW|Uygulama Menü öğesiyle ilişkili ek verileri korumak için kullanabileceğiniz bir uygulama tarafından sağlanan 32-bit değeri içeriyor. MF_MEASUREITEM ve MF_DRAWITEM işlediğinde, bu 32 bit değeri uygulama için kullanılabilir.|
|MF_STRING|Null ile sonlandırılmış bir dize veya çok uzun bir işaretçi içeren bir `CString`.|
|MF_SEPARATOR|*LpszNewItem* parametresi yok sayıldı (gerekli).|

*pBmp*<br/>
İşaret eden bir `CBitmap` menü öğesi olarak kullanılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulamayı menü öğesinin yeni durum değerleri ayarlayarak belirtir. *nFlags*. Bu işlev bir açılır menü öğesiyle ilişkili değiştirirse, eski açılır menü yok eder ve açılan menü tarafından kullanılan belleği serbest bırakır.

Zaman *nIDNewItem* bir açılır menü belirtir, eklenen menüsünde bir parçası olur. Bu menü yok, eklenen menüsünü de yok edilir. Eklenen bir menü ayrılmış bir `CMenu` çakışmayı önlemek için nesne.

Bir menü içinde bulunan her bir pencere (penceresinde görüntülenen olup olmadığını) değiştirilir, uygulamayı çağırması gerekir `CWnd::DrawMenuBar`. Mevcut menü öğelerinin özniteliklerini değiştirmek için bunu kullanmak için çok daha hızlıdır `CheckMenuItem` ve `EnableMenuItem` üye işlevleri.

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::InsertMenu](#insertmenu).

##  <a name="operator_hmenu"></a>  CMenu::operator HMENU

Tanıtıcısını almak için bu işleci kullanın `CMenu` nesne.

```
operator HMENU() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa tanıtıcısını `CMenu` nesne; Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Tanıtıcı, doğrudan Windows API çağırmak için kullanabilirsiniz.

##  <a name="operator_neq"></a>  CMenu::operator! =

İki menü eşit değilse mantıksal olarak belirler.

```
BOOL operator!=(const CMenu& menu) const;
```

### <a name="parameters"></a>Parametreler

*Menü*<br/>
A `CMenu` karşılaştırma için nesne.

### <a name="remarks"></a>Açıklamalar

İşlecin sol tarafındaki bir menü nesne işlecin sağ tarafındaki bir menü nesnesine eşit olup olmadığını sınar.

##  <a name="operator_eq_eq"></a>  CMenu::operator ==

İki menü mantıksal olarak eşit olup olmadığını belirler.

```
BOOL operator==(const CMenu& menu) const;
```

### <a name="parameters"></a>Parametreler

*Menü*<br/>
A `CMenu` karşılaştırma için nesne.

### <a name="remarks"></a>Açıklamalar

İşlecin sol tarafındaki bir menü nesne olup olmadığını sınar (HMENU açısından) işlecin sağ tarafındaki bir menü nesnesine eşit.

##  <a name="removemenu"></a>  CMenu::RemoveMenu

İlişkili bir açılır menü ile menü öğesi Menüsü'nden siler.

```
BOOL RemoveMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

*Nsürdürür*<br/>
Kaldırılacak menü öğesi belirtir. *NFlags* parametresi yorumlamak için kullanılabilir *Nsürdürür* aşağıdaki yollarla:

|nFlags|Nsürdürür yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametresi mevcut menü öğesinin komut kimliği verdiğini belirtir. MF_BYCOMMAND ne MF_BYPOSITION ayarlanmışsa varsayılan değer budur.|
|MF_BYPOSITION|Parametresi mevcut menü öğesinin konumunu verdiğini belirtir. İlk öğesi 0 konumundadır.|

*nFlags*<br/>
Belirtir nasıl *Nsürdürür* yorumlanır.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Menü tekrar kullanılabilmesi için bir açılan menünün işleyici yok. Bu işlevi çağırmadan önce uygulamayı çağırabilir `GetSubMenu` açılır almak için üye işlevi `CMenu` yeniden kullanım için nesne.

Zaman içinde bulunan bir menü (penceresinde görüntülenen olup olmadığını) bir penceresi değiştirildiğinde, uygulamayı çağırması gerekir `CWnd::DrawMenuBar`.

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::InsertMenu](#insertmenu).

##  <a name="setdefaultitem"></a>  CMenu::SetDefaultItem

Varsayılan menü öğesi için belirtilen menüsünde ayarlar.

```
BOOL SetDefaultItem(
    UINT uItem,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*uItem*<br/>
Tanımlayıcı veya yeni varsayılan menü öğesi veya - 1 için varsayılan öğe konumu. Bu parametre anlamını değerine bağlıdır *fByPos*.

*fByPos*<br/>
Anlamını belirten değeri *uItem*. Bu parametre FALSE ise *uItem* bir menü öğesini tanımlayıcısı. Aksi takdirde bir menü öğesi konumu olur.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri sıfır. İşlev başarısız olursa, dönüş değeri sıfırdır. Genişletilmiş hata bilgilerini almak için Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)Windows SDK içinde açıklandığı gibi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 işlevinin davranışı uygulayan [SetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-setmenudefaultitem)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::InsertMenu](#insertmenu).

##  <a name="setmenucontexthelpid"></a>  CMenu::SetMenuContextHelpId

Bağlam Yardımı kimliği ile ilişkilendirir `CMenu`.

```
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```

### <a name="parameters"></a>Parametreler

*dwContextHelpId*<br/>
Bağlam Yardımı kimliği ile ilişkilendirilecek `CMenu`.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0

### <a name="remarks"></a>Açıklamalar

Bu tanımlayıcı menüde tüm öğelerini paylaşma — tek tek menü öğeleri için bir Yardım içerik tanımlayıcısı eklemek mümkün değildir.

### <a name="example"></a>Örnek

  Örneğin bakın [CMenu::InsertMenu](#insertmenu).

##  <a name="setmenuinfo"></a>  CMenu::SetMenuInfo

Bir menü bilgilerini ayarlar.

```
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```

### <a name="parameters"></a>Parametreler

*lpcmi*<br/>
Bir işaretçi bir [MENUINFO](/windows/desktop/api/winuser/ns-winuser-tagmenuinfo) menüsüne ilişkin bilgi içeren yapıya.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri, sıfır olmayan; Aksi takdirde, dönüş değeri sıfırdır.

### <a name="remarks"></a>Açıklamalar

Menü hakkında belirli bilgi ayarlamak için bu işlevi çağırın.

##  <a name="setmenuitembitmaps"></a>  CMenu::SetMenuItemBitmaps

Belirtilen bit eşlemler Menü öğesiyle ilişkilendirir.

```
BOOL SetMenuItemBitmaps(
    UINT nPosition,
    UINT nFlags,
    const CBitmap* pBmpUnchecked,
    const CBitmap* pBmpChecked);
```

### <a name="parameters"></a>Parametreler

*Nsürdürür*<br/>
Değiştirilecek menü öğesi belirtir. *NFlags* parametresi yorumlamak için kullanılabilir *Nsürdürür* aşağıdaki yollarla:

|nFlags|Nsürdürür yorumu|
|------------|---------------------------------|
|MF_BYCOMMAND|Parametresi mevcut menü öğesinin komut kimliği verdiğini belirtir. MF_BYCOMMAND ne MF_BYPOSITION ayarlanmışsa varsayılan değer budur.|
|MF_BYPOSITION|Parametresi mevcut menü öğesinin konumunu verdiğini belirtir. İlk öğesi 0 konumundadır.|

*nFlags*<br/>
Belirtir nasıl *Nsürdürür* yorumlanır.

*pBmpUnchecked*<br/>
Bit eşlem değil denetlenir menü öğeleri için kullanılacak belirtir.

*pBmpChecked*<br/>
Bit eşlem denetlenir menü öğeleri için kullanılacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İşaretli veya işaretsiz menü öğesinin olmasına bakılmaksızın, Windows bit eşlem uygun menü öğesinin yanındaki görüntüler.

Ya da *pBmpUnchecked* veya *pBmpChecked* NULL ise, hiçbir şey menü öğesi için karşılık gelen özniteliğin yanındaki Windows görüntüler. Her iki parametre NULL ise madde işaretli ve madde işaretli olmadığında onay işaretini kaldırır Windows varsayılan onay işareti kullanır.

Menü yok edildiğinde, bu bit eşlemler yok edilmez; Uygulama bunları imha etmeniz gerekir.

Windows `GetMenuCheckMarkDimensions` işlevi menü öğeleri için kullanılan varsayılan işaret boyutlarını alır. Uygulama, bu işlevle sağlanan bit eşlemler uygun boyutunu belirlemek için bu değerleri kullanır. Boyutunu almak, bit eşlemleri oluşturmanıza ve bunları ayarlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]

[!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]

##  <a name="setmenuiteminfo"></a>  CMenu::SetMenuItemInfo

Bir menü öğesinin bilgilerini değiştirir.

```
BOOL SetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parametreler

*uItem*<br/>
Açıklamasını görmek *uItem* içinde [SetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-setmenuiteminfoa) Windows SDK.

*lpMenuItemInfo*<br/>
Açıklamasını görmek *lpmii* içinde `SetMenuItemInfo` Windows SDK.

*fByPos*<br/>
Açıklamasını görmek *fByPosition* içinde `SetMenuItemInfo` Windows SDK.

### <a name="remarks"></a>Açıklamalar

Bu işlevi sarmalar [SetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-setmenuiteminfoa)Windows SDK içinde açıklandığı gibi.

##  <a name="trackpopupmenu"></a>  CMenu::TrackPopupMenu

Belirtilen bir konuma kayan bir açılır menü görüntüler ve açılır menüde öğelerinin seçimini izler.

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
Ekran konumu ve fare konumu bayrakları belirtir. Bkz: [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) kullanılabilir bayrakların listesi için.

*x*<br/>
Açılır menü ekran koordinatlarında yatay konumu belirtir. Değerine bağlı olarak *nFlags* parametresi, menü sola hizalanmış, sağa hizalı veya bu konumuna göre ortalanmış olabilir.

*Y*<br/>
Ekranda ekran koordinatlarında menüsünün üstünde dikey konumu belirtir.

*pWnd*<br/>
Açılır menü sahip penceresi tanımlar. TPM_NONOTIFY bayrağı belirtilmiş olsa bile, bu parametre NULL olamaz. Bu pencere menüsünden tüm WM_COMMAND iletileri alır. WM_COMMAND iletileri kadar Windows 3.1 ve sonraki sürümlerde, pencerenin almaz `TrackPopupMenu` döndürür. Windows 3. 0'da, pencerenin önce WM_COMMAND iletileri alır. `TrackPopupMenu` döndürür.

*lpRect*<br/>
Yoksayıldı.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntemin çağrılması sonucunu döndürür [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) Windows SDK.

### <a name="remarks"></a>Açıklamalar

Kayan bir açılır menü, ekranda her yerde görünebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]

##  <a name="trackpopupmenuex"></a>  CMenu::TrackPopupMenuEx

Belirtilen bir konuma kayan bir açılır menü görüntüler ve açılır menüde öğelerinin seçimini izler.

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
Çeşitli işlevler için genişletilmiş menü belirtir. Tüm değerlerin bir listesini ve bunların anlamları için bkz. [TrackPopupMenuEx](/windows/desktop/api/winuser/nf-winuser-trackpopupmenuex).

*x*<br/>
Açılır menü ekran koordinatlarında yatay konumu belirtir.

*Y*<br/>
Ekranda ekran koordinatlarında menüsünün üstünde dikey konumu belirtir.

*pWnd*<br/>
Açılır menü sahip olan ve oluşturulan menüsünden iletileri alma penceresine bir işaretçi. Bu pencere, herhangi bir geçerli uygulama pencereden olabilir, ancak NULL olamaz. İçinde TPM_NONOTIFY belirtirseniz *fuFlags* parametresi, işlev tüm iletileri göndermez *pWnd*. İşlevi tarafından işaret penceresi için döndürmelidir *pWnd* WM_COMMAND ileti almak için.

*lptpm*<br/>
İşaretçi bir [TPMPARAMS](/windows/desktop/api/winuser/ns-winuser-tagtpmparams) menüsünün ekran alanını belirten yapısı çakışmamalıdır. Bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

İçinde TPM_RETURNCMD belirtirseniz *fuFlags* parametre, dönüş değeri, kullanıcının seçtiği öğesinin menü öğesi tanımlayıcısıdır. Seçim yapmadan kullanıcı menü iptal ederse veya bir hata oluşursa, dönüş değeri 0'dır.

İçinde TPM_RETURNCMD belirtmezseniz *fuFlags* parametre, dönüş değeri işlevin başarılı olursa sıfır dışı ve 0 başarısız olması durumunda. Genişletilmiş hata bilgilerini almak için arama [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360).

### <a name="remarks"></a>Açıklamalar

Kayan bir açılır menü, ekranda her yerde görünebilir. Açılır menü oluştururken, hataları işleme ile ilgili daha fazla bilgi için bkz: [TrackPopupMenuEx](/windows/desktop/api/winuser/nf-winuser-trackpopupmenuex).

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek CTRLTEST](../../visual-cpp-samples.md)<br/>
[MFC örnek DYNAMENU](../../visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)
