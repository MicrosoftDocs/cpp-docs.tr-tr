---
title: CMFCToolBarsCustomizeDialog Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillAllCommandsList
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesComboBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesListBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCommandName
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCountInCategory
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetFlags
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::OnInitDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::PostNcDestroy
helpviewer_keywords:
- CMFCToolBarsCustomizeDialog [MFC], CMFCToolBarsCustomizeDialog
- CMFCToolBarsCustomizeDialog [MFC], FillAllCommandsList
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesComboBox
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesListBox
- CMFCToolBarsCustomizeDialog [MFC], GetCommandName
- CMFCToolBarsCustomizeDialog [MFC], GetCountInCategory
- CMFCToolBarsCustomizeDialog [MFC], GetFlags
- CMFCToolBarsCustomizeDialog [MFC], OnInitDialog
- CMFCToolBarsCustomizeDialog [MFC], PostNcDestroy
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
ms.openlocfilehash: d47ecf45a7bbfc563be0c05cd15ee84d430f502f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377358"
---
# <a name="cmfctoolbarscustomizedialog-class"></a>CMFCToolBarsCustomizeDialog Sınıfı

Kullanıcının bir uygulamadaki araç çubuklarını, menüleri, klavye kısayollarını, kullanıcı tanımlı araçları ve görsel stili özelleştirmesini sağlayan modeless sekme iletişim kutusu [(CPropertySheet Class).](../../mfc/reference/cpropertysheet-class.md) Genellikle, kullanıcı **Araçlar** menüsünden **Özelleştir'i** seçerek bu iletişim kutusuna erişir.

**Özelleştir** iletişim kutusunun altı sekmesi vardır: **Komutlar,** **Araç Çubukları,** **Araçlar,** **Klavye,** **Menü**ve **Seçenekler.**

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarsCustomizeDialog : public CPropertySheet
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|Bir `CMFCToolBarsCustomizeDialog` nesne inşa eder.|
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarsCustomizeDialog::AddButton](#addbutton)|**Komutlar** sayfasındaki komutlar listesine bir araç çubuğu düğmesi ekler|
|[CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)|Kaynaklardan menü yükler ve [CMFCToolBarsCustomizeDialog çağırır::AddMenuKomutları](#addmenucommands) **komutları** sayfasında komutlar listesine bu menü eklemek için.|
|[CMFCToolBarsCustomizeDialog::AddMenuKomutları](#addmenucommands)|Kaynaklardan menü yükler ve [CMFCToolBarsCustomizeDialog çağırır::AddMenuKomutları](#addmenucommands) **komutları** sayfasında komutlar listesine bu menü eklemek için.|
|[CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|Kaynaklardan bir araç çubuğu yükler. Daha sonra, menüdeki her komut için [CMFCToolBarsCustomizeDialog çağırır::AddButton](#addbutton) yöntemi belirtilen kategori altında **Komutlar** sayfasında komutlar listesinde bir düğme eklemek için.|
|[CMFCToolBarsCustomizeDialog::Oluştur](#create)|**Özelleştirme** iletişim kutusunu görüntüler.|
|`CMFCToolBarsCustomizeDialog::EnableTools`|Daha sonraki kullanımlar için ayrılmıştır.|
|[CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|**Özelleştir** iletişim kutusunu kullanarak yeni araç çubukları oluşturmayı etkinleştirir veya devre dışı kaldırır.|
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|Sağlanan `CListBox` nesneyi **Tüm Komutlar** kategorisindeki komutlarla doldurur.|
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|Sağlanan `CComboBox` nesneyi **Özelleştir** iletişim kutusunda her komut kategorisinin adıyla doldurur.|
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|Sağlanan `CListBox` nesneyi **Özelleştir** iletişim kutusunda her komut kategorisinin adıyla doldurur.|
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|Verilen komut kimliğiyle ilişkili adı alır.|
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|Sağlanan listedeki belirli bir metin etiketine sahip öğelerin sayısını alır.|
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|İletişim kutusunun davranışını etkileyen bayrak kümesini alır.|
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|Bir kullanıcının araç çubuğu düğmesini veya menü öğesi simgesini özelleştirebilmeleri için görüntü düzenleyicisi başlatır.|
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|Özellik sayfası başlatmayı artırmak için geçersiz kılar. (CPropertySheet geçersiz [kılar::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|Pencere yıkıldıktan sonra çerçeve tarafından çağrılır. (Geçersiz `CPropertySheet::PostNcDestroy`kılar .)|
|[CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|Belirtilen komut kimliğiyle birlikte belirtilen kategoriden veya tüm kategorilerden düğmeyi kaldırır.|
|[CMFCToolBarsCustomizeDialog::RenameKategori](#renamecategory)|**Komutlar** sekmesindeki kategorilerin liste kutusundaki bir kategoriyi yeniden adlandırır.|
|[CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|**Komutlar** sekmesindeki komutlar listesindeki bir düğmeyi yeni bir araç çubuğu düğmesi nesnesiyle değiştirir.|
|[CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|**Komutlar** sekmesinde görüntülenecek kategoriler listesine bir kategori ekler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|Kullanıcı tanımlı araçlar listesinin geçerli olup olmadığını belirlemek için çerçeve tarafından çağrılır.|
|[CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|Kullanıcı tanımlı bir aracın özellikleri değiştiğinde çerçeve tarafından çağrılır.|
|[CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|Belirli bir klavye kısayolu bir eyleme atanıp atanamayacağını belirler.|
|[CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|Kullanıcı tanımlı bir aracın değiştirilip değiştirilemeyeceğini belirler.|
|[CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|Kullanıcı **Araçlar** sekmesini seçtiğinde çerçeve tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

**Özelleştir** iletişim kutusunu görüntülemek için `CMFCToolBarsCustomizeDialog` bir nesne oluşturun ve [CMFCToolBarsCustomizeDialog::Oluşturma](#create) yöntemini arayın.

**Özelleştir** iletişim kutusu etkin olsa da, uygulama kullanıcıyı özelleştirme görevleriyle sınırlayan özel bir modda çalışır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemlerin `CMFCToolBarsCustomizeDialog` nasıl kullanılacağını göstermektedir. Örnek, **Komutlar** sayfasındaki komutlar listesindeki araç çubuğu düğmesinin nasıl değiştirilin, **Özelleştir** iletişim kutusunu kullanarak yeni araç çubukları oluşturmayı etkinleştirmek ve Özelleştirme iletişim kutusunu görüntülemek için nasıl **gösterileceklerini** gösterir. Bu kod parçacığı [IE Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cpropertysheet](../../mfc/reference/cpropertysheet-class.md)

`CMFCToolBarsCustomizeDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxToolBarsCustomizeDialog.h

## <a name="cmfctoolbarscustomizedialogaddbutton"></a><a name="addbutton"></a>CMFCToolBarsCustomizeDialog::AddButton

**Komutlar** sayfasındaki komutlar listesine bir araç çubuğu düğmesi ekler.

```
void AddButton(
    UINT uiCategoryId,
    const CMFCToolBarButton& button,
    int iInsertBefore=-1);

void AddButton(
    LPCTSTR lpszCategory,
    const CMFCToolBarButton& button,
    int iInsertBefore=-1);
```

### <a name="parameters"></a>Parametreler

*uiCategoryId*<br/>
[içinde] Düğmeyi eklediği kategori kimliğini belirtir.

*Düğme*<br/>
[içinde] Eklemek için düğmeyi belirtir.

*iInsertBefore*<br/>
[içinde] Düğmenin takılmadan önce araç çubuğu düğmesinin sıfır tabanlı dizinini belirtir.

*lpszKategori*<br/>
[içinde] Düğmeyi eklemek için kategori dizesini belirtir.

### <a name="remarks"></a>Açıklamalar

Yöntem, `AddButton` standart komut iI'lerine (ID_FILE_MRU_FILE1 gibi) sahip düğmeleri, izin verilmeyecek komutları (bkz. [CMFCToolBar::IsCommandAllowed)](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)ve sahte düğmeleri yok sayar.

Bu yöntem, düğmenin çalışma zamanı `button` sınıfını kullanarak aynı türden (genellikle [CMFCToolBarButton Sınıfı)](../../mfc/reference/cmfctoolbarbutton-class.md)yeni bir nesne oluşturur. Daha sonra [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) düğmesinin veri üyelerini kopyalamak için çağırır ve kopyayı belirtilen kategoriye ekler.

Yeni düğme `OnAddToCustomizePage` takıldığında, bildirimi alır.

-1 ise, `iInsertBefore` düğme kategoriler listesine eklenir; aksi takdirde belirtilen dizin ile öğenin önüne eklenir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın yönteminin `AddButton` nasıl `CMFCToolBarsCustomizeDialog` kullanılacağını göstermektedir. Bu kod parçacığı [Kaydırıcı örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]

## <a name="cmfctoolbarscustomizedialogaddmenu"></a><a name="addmenu"></a>CMFCToolBarsCustomizeDialog::AddMenu

Kaynaklardan menü yükler ve [CMFCToolBarsCustomizeDialog çağırır::AddMenuKomutları](#addmenucommands) **komutları** sayfasında komutlar listesine bu menü eklemek için.

```
BOOL AddMenu(UINT uiMenuResId);
```

### <a name="parameters"></a>Parametreler

*uiMenuResId*<br/>
[içinde] Yüklenmesi gereken bir menünün kaynak kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir menü başarıyla eklendiyse DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Aramada `AddMenuCommands`, *bPopup* FALSE olduğunu. Sonuç olarak, bu yöntem komutlar listesine alt menüler içeren menü öğeleri eklemez. Bu yöntem, alt menülerde menü öğeleri komutları listesine ekler.

## <a name="cmfctoolbarscustomizedialogaddmenucommands"></a><a name="addmenucommands"></a>CMFCToolBarsCustomizeDialog::AddMenuKomutları

Belirtilen menüdeki tüm öğeleri temsil etmek için **Komutlar** sayfasındaki komutlar listesine öğeler ekler.

```
void AddMenuCommands(
    const CMenu* pMenu,
    BOOL bPopup,
    LPCTSTR lpszCategory=NULL,
    LPCTSTR lpszMenuPath=NULL);
```

### <a name="parameters"></a>Parametreler

*pMenü*<br/>
[içinde] CMenu nesnesine eklenecek bir işaretçi.

*bPopup*<br/>
[içinde] Açılır menü öğelerinin komutlar listesine eklenip eklenmeyeceğini belirtir.

*lpszKategori*<br/>
[içinde] Menüyü eklemek için kategorinin adı.

*lpszMenuPath*<br/>
[içinde] **Tüm Kategoriler** listesinde komut gösterildiğinde ada eklenen bir önek.

### <a name="remarks"></a>Açıklamalar

Yöntem `AddMenuCommands` *pMenu*tüm menü öğeleri üzerinde döngüler. Alt menü içermeyen her menü öğesi için, bu yöntem bir [CMFCToolBarButton Sınıf](../../mfc/reference/cmfctoolbarbutton-class.md) nesnesi oluşturur ve [CMFCToolBarsCustomizeDialog çağırır::AddButton](#addbutton) yöntemi **komutlar** sayfasında komutlar listesine bir araç çubuğu düğmesi olarak menü öğesi eklemek için. Ayırıcılar bu işlemde yoksayılır.

*bPopup* TRUE ise, bir alt menü içeren her menü öğesi için bu yöntem bir [CMFCToolBarMenuButton Sınıf](../../mfc/reference/cmfctoolbarmenubutton-class.md) nesnesi oluşturur ve arayarak `AddButton`komutları listesine ekler. Aksi takdirde alt menüiçeren menü öğeleri komutlar listesinde görüntülenmez. Her iki durumda `AddMenuCommands` da, bir alt menü ile bir menü öğesi karşılaştığında kendini özyinelemeli çağırır, *pMenu* parametresi olarak alt menüsüne bir işaretçi geçen ve *lpszMenuPath*için alt menü etiketi ekleme .

## <a name="cmfctoolbarscustomizedialogaddtoolbar"></a><a name="addtoolbar"></a>CMFCToolBarsCustomizeDialog::AddToolBar

Kaynaklardan bir araç çubuğu yükler. Daha sonra, menüdeki her komut için [CMFCToolBarsCustomizeDialog çağırır::AddButton](#addbutton) yöntemi belirtilen kategori altında **Komutlar** sayfasında komutlar listesinde bir düğme eklemek için.

```
BOOL AddToolBar(
    UINT uiCategoryId,
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,
    UINT uiToolbarResId);
```

### <a name="parameters"></a>Parametreler

*uiCategoryId*<br/>
[içinde] Araç çubuğunu eklemek için kategorinin kaynak kimliğini belirtir.

*uiToolbarResId*<br/>
[içinde] Komutları komutlar listesine eklenen bir araç çubuğunun kaynak kimliğini belirtir.

*lpszKategori*<br/>
[içinde] Araç çubuğunu ekleyeceğiniz kategorinin adını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa DOĞRU; aksi takdirde YANLIŞ.

### <a name="example"></a>Örnek

Aşağıdaki örnek, yöntemin sınıfta `AddToolBar` nasıl `CMFCToolBarsCustomizeDialog` kullanılacağını göstermektedir. Bu kod parçacığı Word Pad [örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]

### <a name="remarks"></a>Açıklamalar

Her komutu temsil etmek için kullanılan denetim bir [CMFCToolBarButton Sınıf](../../mfc/reference/cmfctoolbarbutton-class.md) nesnesidir. Araç çubuğunu ekledikten sonra [CMFCToolBarsCustomizeDialog::ReplaceButton'u](#replacebutton)arayarak düğmeyi türetilmiş bir türün denetimiyle değiştirebilirsiniz.

## <a name="cmfctoolbarscustomizedialogchecktoolsvalidity"></a><a name="checktoolsvalidity"></a>CMFCToolBarsCustomizeDialog::CheckToolsValidity

Kullanıcı araçları listesinin geçerliliğini doğrular.

```
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```

### <a name="parameters"></a>Parametreler

*lstTools*<br/>
[içinde] Denetlenen kullanıcı tanımlı araçların listesi.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tanımlı araçların listesi geçerliyse TRUE döndürür; aksi takdirde YANLIŞ. Varsayılan uygulama her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Çerçeve [CMFCToolBarsCustomizeDialog](#checktoolsvalidity)tarafından döndürülen kullanıcı tanımlı araçları temsil eden nesnelerin geçerliliğini doğrulamak için bu yöntemi çağırır::CheckToolsValidity .

Kullanıcı iletişim `CheckToolsValidity` kutusunu kapatmadan `CMFCToolBarsCustomizeDialog` önce kullanıcı araçlarını doğrulamak istiyorsanız, türetilen bir sınıftayöntemi geçersiz kılın. Bu yöntem, kullanıcı iletişim kutusunun sağ üst köşesindeki **Kapat** düğmesini veya iletişim kutusunun sağ alt köşesinde **Kapat** etiketli düğmeye tıkladığında FALSE döndürürse, iletişim kutusu kapatmak yerine **Araçlar** sekmesini görüntüler. Bu yöntem, kullanıcı **Araçlar** sekmesinden uzaklaşmak için bir sekmeyi tıklattığında FALSE döndürürse, gezinti gerçekleşmez. Doğrulamanın başarısız olmasıyla ilgili sorunu kullanıcıya bildirmek için uygun bir ileti kutusu görüntülemeniz gerekir.

## <a name="cmfctoolbarscustomizedialogcmfctoolbarscustomizedialog"></a><a name="cmfctoolbarscustomizedialog"></a>CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog

Bir `CMFCToolBarsCustomizeDialog` nesne inşa eder.

```
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bAutoSetFromMenus = FALSE,
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```

### <a name="parameters"></a>Parametreler

*pWndParentFrame*<br/>
[içinde] Ana çerçeveiçin bir işaretçi. Bu parametre NULL olmamalıdır.

*bAutoSetFromMenüler*<br/>
[içinde] Tüm menülerden menü komutlarının **Komutlar** sayfasındaki komutlar listesine eklenip eklenmeyeceğini belirten bir Boolean değeri. Bu parametre TRUE ise, menü komutları eklenir. Aksi takdirde, menü komutları eklenmez.

*uiFlags*<br/>
[içinde] İletişim kutusunun davranışını etkileyen bayrakların birleşimi. Bu parametre aşağıdaki değerlerden biri veya birkaçı olabilir:

- AFX_CUSTOMIZE_MENU_SHADOWS

- AFX_CUSTOMIZE_TEXT_LABELS

- AFX_CUSTOMIZE_MENU_ANIMATIONS

- AFX_CUSTOMIZE_NOHELP

- AFX_CUSTOMIZE_CONTEXT_HELP

- AFX_CUSTOMIZE_NOTOOLS

- AFX_CUSTOMIZE_MENUAMPERS

- AFX_CUSTOMIZE_NO_LARGE_ICONS

*plistCustomPages*<br/>
[içinde] Ek özel sayfalar `CRuntimeClass` belirten nesneler listesine işaretçi.

### <a name="remarks"></a>Açıklamalar

*plistCustomPages* parametresi, ek `CRuntimeClass` özel sayfalar belirten nesnelerin listesini ifade eder. Oluşturucu CRuntimeClass kullanarak iletişim kutusuna daha fazla sayfa [ekler::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject) yöntemi. **Özelleştir** iletişim kutusuna daha fazla sayfa ekleyen bir örnek için CustomPages örneğine bakın.

*uiFlags* parametresinde geçebileceğiniz değerler hakkında daha fazla bilgi için [CMFCToolBarsCustomizeDialog::GetFlags](#getflags)' a bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCToolBarsCustomizeDialog` nasıl inşa edilebildiğini gösterir. Bu kod parçacığı Özel Sayfalar [örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]

## <a name="cmfctoolbarscustomizedialogcreate"></a><a name="create"></a>CMFCToolBarsCustomizeDialog::Oluştur

**Özelleştirme** iletişim kutusunu görüntüler.

```
virtual BOOL Create();
```

### <a name="return-value"></a>Dönüş Değeri

Özelleştirme özelliği sayfası başarıyla oluşturulursa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Yöntemi `Create` yalnızca sınıfı tamamen başlatmadan sonra arayın.

## <a name="cmfctoolbarscustomizedialogenableuserdefinedtoolbars"></a><a name="enableuserdefinedtoolbars"></a>CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars

**Özelleştir** iletişim kutusunu kullanarak yeni araç çubukları oluşturmayı etkinleştirir veya devre dışı kaldırır.

```
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] Kullanıcı tanımlı araç çubuklarını etkinleştirmek için TRUE; Araç çubuklarını devre dışı kıtır.

### <a name="remarks"></a>Açıklamalar

*bEnable* DOĞRUise, **Araç Çubukları** sayfasında **Yeni**, **Yeniden Adlandır** ve **Sil** düğmeleri görüntülenir.

Varsayılan olarak veya *bEnable* FALSE ise, bu düğmeler görüntülenmez ve kullanıcı yeni araç çubukları tanımlayamaz.

## <a name="cmfctoolbarscustomizedialogfillallcommandslist"></a><a name="fillallcommandslist"></a>CMFCToolBarsCustomizeDialog::FillAllCommandsList

Sağlanan `CListBox` nesneyi **Tüm Komutlar** kategorisindeki komutlarla doldurur.

```
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;
```

### <a name="parameters"></a>Parametreler

*wndListOfKomutlar*<br/>
[çıkış] Doldurulacak nesneye `CListBox` bir başvuru.

### <a name="remarks"></a>Açıklamalar

**Tüm Komutlar** kategorisi tüm kategorilerin komutlarını içerir. [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) yöntemi sizin için **Tüm Komutlar** kategorisine sağlanan düğme ile ilişkili komutu ekler.

Bu yöntem, Tüm `CListBox` **Komutlar** kategorisindeki komutlarla doldurmadan önce sağlanan nesnenin içeriğini temizler.

Sınıf, `CMFCMousePropertyPage` çift tıklatma olay listesi kutusunu doldurmak için bu yöntemi kullanır.

## <a name="cmfctoolbarscustomizedialogfillcategoriescombobox"></a><a name="fillcategoriescombobox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesComboBox

Sağlanan `CComboBox` nesneyi **Özelleştir** iletişim kutusunda her komut kategorisinin adıyla doldurur.

```
void FillCategoriesComboBox(
    CComboBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*wndKategori*<br/>
[çıkış] Doldurulacak nesneye `CComboBox` bir başvuru.

*bAddEmpty*<br/>
[içinde] Komutları olmayan açılan kutuya kategoriler ekleyip eklemeyin ilerler belirten bir Boolean değeri. Bu parametre TRUE ise, açılan kutuya boş kategoriler eklenir. Aksi takdirde, boş kategoriler eklenmez.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CMFCToolBarsCustomizeDialog gibidir::FillCategoriesListBox](#fillcategorieslistbox) yöntemi dışında bu `CComboBox` yöntem bir nesne ile çalışır.

Bu yöntem, doldurmadan önce `CComboBox` nesnenin içeriğini temizlemez. **Tüm Komutlar** kategorisinin açılan kutudaki son öğe olmasını garanti eder.

[CMFCToolBarsCustomizeDialog::AddButton](#addbutton) yöntemini kullanarak yeni komut kategorileri ekleyebilirsiniz. [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) yöntemini kullanarak varolan bir kategorinin adını değiştirebilirsiniz.

Ve `CMFCToolBarsKeyboardPropertyPage` `CMFCKeyMapDialog` sınıflar klavye eşlemelerini kategorilere ayırmak için bu yöntemi kullanır.

## <a name="cmfctoolbarscustomizedialogfillcategorieslistbox"></a><a name="fillcategorieslistbox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesListBox

Sağlanan `CListBox` nesneyi **Özelleştir** iletişim kutusunda her komut kategorisinin adıyla doldurur.

```
void FillCategoriesListBox(
    CListBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*wndKategori*<br/>
[çıkış] Doldurulacak nesneye `CListBox` bir başvuru.

*bAddEmpty*<br/>
[içinde] Komutları olmayan liste kutusuna kategoriler eklenip eklenmeyeceğini belirten bir Boolean değeri. Bu parametre TRUE ise, boş kategoriler liste kutusuna eklenir. Aksi takdirde, boş kategoriler eklenmez.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CMFCToolBarsCustomizeDialog gibidir::FillCategoriesComboBox](#fillcategoriescombobox) yöntemi dışında bu `CListBox` yöntem bir nesne ile çalışır.

Bu yöntem, doldurmadan önce `CListBox` nesnenin içeriğini temizlemez. **Tüm Komutlar** kategorisinin liste kutusundaki son öğe olmasını garanti eder.

[CMFCToolBarsCustomizeDialog::AddButton](#addbutton) yöntemini kullanarak yeni komut kategorileri ekleyebilirsiniz. [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) yöntemini kullanarak varolan bir kategorinin adını değiştirebilirsiniz.

Sınıf, `CMFCToolBarsCommandsPropertyPage` her komut kategorisiyle ilişkili komutların listesini göstermek için bu yöntemi kullanır.

## <a name="cmfctoolbarscustomizedialoggetcommandname"></a><a name="getcommandname"></a>CMFCToolBarsCustomizeDialog::GetCommandName

Verilen komut kimliğiyle ilişkili adı alır.

```
LPCTSTR GetCommandName(UINT uiCmd) const;
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Alınacak komutun kimliği.

### <a name="return-value"></a>Dönüş Değeri

Verilen komut kimliğiyle ilişkili ad veya komut yoksa NULL.

## <a name="cmfctoolbarscustomizedialoggetcountincategory"></a><a name="getcountincategory"></a>CMFCToolBarsCustomizeDialog::GetCountInCategory

Sağlanan listedeki belirli bir metin etiketine sahip öğelerin sayısını alır.

```
int GetCountInCategory(
    LPCTSTR lpszItemName,
    const CObList& lstCommands) const;
```

### <a name="parameters"></a>Parametreler

*lpszItemName*<br/>
[içinde] Eşleşecek metin etiketi.

*lstKomutlar*<br/>
[içinde] Nesneleri içeren `CMFCToolBarButton` bir listeye başvuru.

### <a name="return-value"></a>Dönüş Değeri

Metin etiketi *lpszItemName*eşittir sağlanan listede öğe sayısı .

### <a name="remarks"></a>Açıklamalar

Sağlanan nesne listesindeki her öğe `CMFCToolBarButton`türünde olmalıdır. Bu yöntem [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) ile *lpszItemName* karşılaştırır::m_strText veri üyesi.

## <a name="cmfctoolbarscustomizedialoggetflags"></a><a name="getflags"></a>CMFCToolBarsCustomizeDialog::GetFlags

İletişim kutusunun davranışını etkileyen bayrak kümesini alır.

```
UINT GetFlags() const;
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunun davranışını etkileyen bayraklar kümesi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, oluşturucuya geçirilen *uiFlags* parametresinin değerini alır. İade değeri aşağıdaki değerlerden biri veya birkaçı olabilir:

|||
|-|-|
|AFX_CUSTOMIZE_MENU_SHADOWS|Kullanıcının menünün gölge görünümünü belirtmesine olanak tanır.  |
|AFX_CUSTOMIZE_TEXT_LABELS|Kullanıcının araç çubuğu düğmesi görüntülerinin altında metin etiketleri gösterip gösterilmediğini belirtmesine olanak tanır.  |
|AFX_CUSTOMIZE_MENU_ANIMATIONS|Kullanıcının menü animasyon stilini belirtmesine olanak tanır.  |
|AFX_CUSTOMIZE_NOHELP|Yardım düğmesini özelleştirme iletişim kutusundan kaldırır.  |
|AFX_CUSTOMIZE_CONTEXT_HELP|Görsel stili WS_EX_CONTEXTHELP sağlar.  |
|AFX_CUSTOMIZE_NOTOOLS|Özelleştirme iletişim kutusundan **Araçlar** sayfasını kaldırır. Uygulamanız sınıfı kullanıyorsa `CUserToolsManager` bu bayrak geçerlidir.  |
|AFX_CUSTOMIZE_MENUAMPERS|Düğme altyazılarının ampersand ( **&**) karakterini içermesine izin verir.  |
|AFX_CUSTOMIZE_NO_LARGE_ICONS|**Büyük Simgeler** seçeneğini özelleştirme iletişim kutusundan kaldırır.  |

görsel stil WS_EX_CONTEXTHELP hakkında daha fazla bilgi için [Genişletilmiş Pencere Stilleri'ne](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)bakın.

## <a name="cmfctoolbarscustomizedialogonafterchangetool"></a><a name="onafterchangetool"></a>CMFCToolBarsCustomizeDialog::OnAfterChangeTool

Kullanıcı aracındaki bir değişikliği oluştuktan hemen sonra yanıtlar.

```
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Parametreler

*pSelTool*<br/>
[içinde, dışarı] Değiştirilen kullanıcı aracı nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kullanıcı tanımlı bir aracın özelliklerini değiştirdiğinde çerçeve tarafından çağrılır. Varsayılan uygulama hiçbir şey yapmaz. Bir kullanıcı aracında değişiklik `CMFCToolBarsCustomizeDialog` gerçekleştikten sonra işleme gerçekleştirmek için türetilen bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctoolbarscustomizedialogonassignkey"></a><a name="onassignkey"></a>CMFCToolBarsCustomizeDialog::OnAssignKey

Kullanıcı tanımlı olarak klavye kısayollarını doğrular.

```
virtual BOOL OnAssignKey(ACCEL* pAccel);
```

### <a name="parameters"></a>Parametreler

*pAccel*<br/>
[içinde, dışarı] [ACCEL](/windows/win32/api/winuser/ns-winuser-accel) struct olarak ifade edilen önerilen klavye assigment işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Anahtar atanamıyorsa DOĞRU veya anahtar atanamıyorsa FALSE. Varsayılan uygulama her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanıcı yeni bir klavye kısayolu atadığında ek işleme gerçekleştirmek veya kullanıcı bunları tanımladığı gibi klavye kısayollarını doğrulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın. Bir kısayol atanmasını önlemek için FALSE döndürün. Ayrıca bir ileti kutusu görüntülemeniz veya klavye kısayolu reddedildi neden kullanıcıbilgilendirmek gerekir.

## <a name="cmfctoolbarscustomizedialogonbeforechangetool"></a><a name="onbeforechangetool"></a>CMFCToolBarsCustomizeDialog::OnBeforeChangeTool

Kullanıcı değişiklik uygulamak üzereyken bir kullanıcı aracında değişiklik olduğunda özel işleme gerçekleştirir.

```
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Parametreler

*pSelTool*<br/>
[içinde, dışarı] Değiştirilmek üzere olan kullanıcı aracı nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kullanıcı tanımlı bir aracın özellikleri değişmek üzereyken çerçeve tarafından çağrılır. Varsayılan uygulama hiçbir şey yapmaz. *pSelTool'un* kullandığı kaynakları `CMFCToolBarsCustomizeDialog` serbest bırakmak gibi bir kullanıcı aracında değişiklik gerçekleşmeden önce işleme gerçekleştirmek istiyorsanız, türetilen bir sınıftaki `OnBeforeChangeTool` yöntemi geçersiz kılın.

## <a name="cmfctoolbarscustomizedialogonedittoolbarmenuimage"></a><a name="onedittoolbarmenuimage"></a>CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage

Bir kullanıcının araç çubuğu düğmesini veya menü öğesi simgesini özelleştirebilmeleri için görüntü düzenleyicisi başlatır.

```
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,
    CBitmap& bitmap,
    int nBitsPerPixel);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Üst pencereiçin bir işaretçi.

*Bitmap*<br/>
[içinde] Düzenlenecek bir bitmap nesnesine başvuru.

*nBitsPerPixel*<br/>
[içinde] Bitmap renk çözünürlüğü, piksel başına bit olarak.

### <a name="return-value"></a>Dönüş Değeri

Bir değişiklik gerçekleniyorsa DOĞRU; aksi takdirde YANLIŞ. Varsayılan uygulama bir iletişim kutusu görüntüler ve kullanıcı **Onay'ı**tıklatarsa VEYA kullanıcı **İptal'i** veya **Kapat** düğmesini tıklatarsa TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kullanıcı görüntü düzenleyicisini çalıştırdığında çerçeve tarafından çağrılır. Varsayılan uygulama [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md) iletişim kutusunu görüntüler. Özel `OnEditToolbarMenuImage` bir görüntü düzenleyicisi kullanmak için türetilmiş bir sınıfta geçersiz kılın.

## <a name="cmfctoolbarscustomizedialogoninitdialog"></a><a name="oninitdialog"></a>CMFCToolBarsCustomizeDialog::OnInitDialog

Özellik sayfası başlatmayı artırmak için geçersiz kılar.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

[CPropertySheet arama sonucu::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) yöntemi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iletişim kutusunun geçerli ekran boyutuna uyduğundan emin olmak ve **yardım** düğmesini iletişim kutusunun sol alt köşesine taşıyarak, **Kapat** düğmesini görüntüleyerek taban sınıf uygulaması [CPropertySheet::OnInitDialog'u](../../mfc/reference/cpropertysheet-class.md#oninitdialog)genişletir.

## <a name="cmfctoolbarscustomizedialogoninittoolspage"></a><a name="oninittoolspage"></a>CMFCToolBarsCustomizeDialog::OnInitToolsPage

**Araçlar** sayfasının başolarak başlatılması nı üzere olduğu çerçeveden gelen bildirimi işler.

```
virtual void OnInitToolsPage();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz. Bu bildirimi işlemek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctoolbarscustomizedialogpostncdestroy"></a><a name="postncdestroy"></a>CMFCToolBarsCustomizeDialog::PostNcDestroy

Pencere yıkıldıktan sonra çerçeve tarafından çağrılır.

```
virtual void PostNcDestroy();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CPropertySheet::PostNcDestroy`uygulamayı önceki moda geri vererek taban sınıf uygulamasını genişletir.

[CMFCToolBarsCustomizeDialog::Oluşturma](#create) yöntemi, uygulamayı kullanıcıyı özelleştirme görevleriyle sınırlayan özel bir moda yerleştirir.

## <a name="cmfctoolbarscustomizedialogremovebutton"></a><a name="removebutton"></a>CMFCToolBarsCustomizeDialog::RemoveButton

Belirtilen komut kimliğiyle birlikte belirtilen kategoriden veya tüm kategorilerden düğmeyi kaldırır.

```
int RemoveButton(
    UINT uiCategoryId,
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,
    UINT uiCmdId);
```

### <a name="parameters"></a>Parametreler

*uiCategoryId*<br/>
[içinde] Düğmeyi kaldırmak için kategori kimliğini belirtir.

*uiCmdId*<br/>
[içinde] Düğmenin komut kimliğini belirtir.

*lpszKategori*<br/>
[içinde] Düğmeyi kaldırmak için kategorinin adını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Kaldırılan düğmenin sıfır tabanlı dizinveya belirtilen komut kimliği belirtilen kategoride bulunamazsa -1. *UiCategoryId* -1 ise, iade değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Tüm kategorilerden bir düğmeyi kaldırmak için, bu yöntemin ilk aşırı yüklemesini arayın ve *uiCategoryId'i* -1 olarak ayarlayın.

## <a name="cmfctoolbarscustomizedialogrenamecategory"></a><a name="renamecategory"></a>CMFCToolBarsCustomizeDialog::RenameKategori

**Komutlar** sayfasındaki kategorilerin liste kutusundaki bir kategoriyi yeniden adlandırır.

```
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,
    LPCTSTR lpszCategoryNew);
```

### <a name="parameters"></a>Parametreler

*lpszCategoryEski*<br/>
[içinde] Değiştirilen kategori adı.

*lpszCategoryYeni*<br/>
[içinde] Yeni kategori adı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olsaydı DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Kategori adı benzersiz olmalıdır.

## <a name="cmfctoolbarscustomizedialogreplacebutton"></a><a name="replacebutton"></a>CMFCToolBarsCustomizeDialog::ReplaceButton

**Komutlar** sayfasındaki komutların liste kutusundaki araç çubuğu düğmesini değiştirir.

```
void ReplaceButton(
    UINT uiCmd,
    const CMFCToolBarButton& button);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Değiştirilecek düğmenin komutunu belirtir.

*Düğme*<br/>
[içinde] Eski düğmenin yerini alan araç çubuğu düğmesi nesnesine **const** başvurusu.

### <a name="remarks"></a>Açıklamalar

[CMFCToolBarsCustomizeDialog::AddMenu](#addmenu), [CMFCToolBarsCustomizeDialog::AddMenuKomutları](#addmenucommands), veya [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar) **Komutlar** sayfasına bir komut ekler, bu komut [cmfcToolBarButton Sınıf](../../mfc/reference/cmfctoolbarbutton-class.md) nesnesi (veya [cmfcToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md) `AddMenuCommands`nesnesi) bir alt menü ekleyen bir menü öğesi için ). Çerçeve de otomatik olarak komutları eklemek için bu üç yöntem çağırır. Bunun yerine türetilmiş bir tür tarafından temsil `ReplaceButton` edilecek bir komut istiyorsanız, türetilmiş türün bir düğmesini arayın ve geçirin.

### <a name="example"></a>Örnek

Aşağıdaki örnek, yöntemin sınıfta `ReplaceButton` nasıl `CMFCToolBarsCustomizeDialog` kullanılacağını göstermektedir. Bu kod snippet [Visual Studio Demo örnek](../../overview/visual-cpp-samples.md)parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]

## <a name="cmfctoolbarscustomizedialogsetusercategory"></a><a name="setusercategory"></a>CMFCToolBarsCustomizeDialog::SetUserCategory

**Komutlar** sayfasındaki kategoriler listesinde hangi kategorinin kullanıcı kategorisi olduğunu belirtir. [CMFCToolBarsCustomizeDialog'u](#create)aramadan önce bu işlevi aramanız gerekir::Oluştur .

```
BOOL SetUserCategory(LPCTSTR lpszCategory);
```

### <a name="parameters"></a>Parametreler

*lpszKategori*<br/>
[içinde] Kategorinin adı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Kullanıcı kategorisi ayarı şu anda çerçeve tarafından kullanılmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CPropertySheet Sınıfı](../../mfc/reference/cpropertysheet-class.md)
