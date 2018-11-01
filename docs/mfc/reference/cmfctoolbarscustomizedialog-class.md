---
title: CMFCToolBarsCustomizeDialog sınıfı
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
ms.openlocfilehash: 026c7392c3eb93b37a712059939683e3e0ab852c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629002"
---
# <a name="cmfctoolbarscustomizedialog-class"></a>CMFCToolBarsCustomizeDialog sınıfı

Modsuz sekme iletişim kutusu ( [CPropertySheet sınıfı](../../mfc/reference/cpropertysheet-class.md)) araç çubuklarını, menüleri, klavye kısayolları, kullanıcı tanımlı Araçlar ve uygulamada görsel stil özelleştirmek için kullanıcı sağlar. Genellikle, bu iletişim kutusunu erişen seçerek kullanıcı **Özelleştir** gelen **Araçları** menüsü.

**Özelleştir** iletişim kutusunda altı sekme bulunur: **komutları**, **araç çubukları**, **Araçları**, **klavye**,  **Menü**, ve **seçenekleri**.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarsCustomizeDialog : public CPropertySheet
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|Oluşturur bir `CMFCToolBarsCustomizeDialog` nesne.|
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddButton](#addbutton)|Araç çubuğu düğmesi üzerinde komutlar listesine ekler **komutları** sayfası|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)|Bir menü kaynakları ve çağrıları yükler [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) , menü komutlarını listesine eklemek için **komutları** sayfası.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)|Bir menü kaynakları ve çağrıları yükler [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) , menü komutlarını listesine eklemek için **komutları** sayfası.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|Araç çubuğu kaynakları yükler. Ardından, her komut menüsünde çağrılarda [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) komutların listesini de bir düğme eklemek için yöntemi **komutları** sayfasında belirtilen kategori altında.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::Create](#create)|Görüntüler **özelleştirme** iletişim kutusu.|
|`CMFCToolBarsCustomizeDialog::EnableTools`|Daha sonraki kullanımlar için ayrılmıştır.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|Etkinleştirir ya da kullanarak yeni araç çubukları oluşturma devre dışı bırakır **Özelleştir** iletişim kutusu.|
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|Sağlanan doldurur `CListBox` komutlar nesnesiyle **tüm komutları** kategorisi.|
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|Sağlanan doldurur `CComboBox` her komut kategorinin adını nesnesiyle **Özelleştir** iletişim kutusu.|
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|Sağlanan doldurur `CListBox` her komut kategorinin adını nesnesiyle **Özelleştir** iletişim kutusu.|
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|Belirtilen komut kimliğiyle ilişkili adı alır.|
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|Belirtilen metin etiketi olan verilen listedeki öğe sayısını alır.|
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|İletişim kutusunun davranışını etkileyen bayrakları kümesini alır.|
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|Bir kullanıcı bir araç çubuğu düğmesini veya menü öğesi simgesi özelleştirebilmeniz için görüntü Düzenleyicisi başlatılır.|
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|Özellik sayfası başlatıcısını büyütmek için geçersiz kılar. (Geçersiz kılmaları [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|Pencere yok edildikten sonra framework tarafından çağırılır. (Geçersiz kılmaları `CPropertySheet::PostNcDestroy`.)|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|Belirtilen komut kimliği düğmeyle belirtilen kategori veya tüm kategorilerden kaldırır.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)|Kategorilerin liste kutusunda bir kategori üzerinde yeniden adlandırır **komutları** sekmesi.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|Komutların listesini de bir düğme yerini alır **komutları** yeni araç çubuğu düğmesi nesnesi ile sekmesindeki.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|Görüntülenecek kategori listesi için bir kategori ekler **komutları** sekmesi.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|Kullanıcı tanımlı Araçlar listesi geçerli olup olmadığını belirlemek için framework tarafından çağırılır.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|Kullanıcı tanımlı bir aracının özellikleri değiştiğinde framework tarafından çağırılır.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|Belirtilen klavye kısayolu eyleme atanabilir olup olmadığını belirler.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|Bir kullanıcı tanımlı araç değiştirilebilir olup olmadığını belirler.|
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|Kullanıcı seçtiğinde framework tarafından çağırılır **Araçları** sekmesini istendi.|

## <a name="remarks"></a>Açıklamalar

Görüntülenecek **Özelleştir** iletişim kutusunda, oluşturun bir `CMFCToolBarsCustomizeDialog` nesne ve çağrı [CMFCToolBarsCustomizeDialog::Create](#create) yöntemi.

Sırada **Özelleştir** iletişim kutusu etkin olduğu, uygulama, kullanıcıya özelleştirme görevlerini sınırlandıran bir özel modda çalışır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCToolBarsCustomizeDialog` sınıfı. Örnek üzerinde bir araç çubuğu düğmesi liste kutusunda komutların nasıl değiştirileceğini gösterir **komutları** sayfasında, kullanarak yeni araç çubukları oluşturma etkinleştirme **Özelleştir** iletişim kutusu ve görüntü  **Özelleştirme** iletişim kutusu. Bu kod parçacığı parçasıdır [IE gösterim örneği](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

`CMFCToolBarsCustomizeDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxToolBarsCustomizeDialog.h

##  <a name="addbutton"></a>  CMFCToolBarsCustomizeDialog::AddButton

Araç çubuğu düğmesi üzerinde komutlar listesine ekler **komutları** sayfası.

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
[in] Düğme eklemek hangi kategorisi Kimliğini belirtir.

*Düğme*<br/>
[in] Eklemek için düğmeyi belirtir.

*iInsertBefore*<br/>
[in] Düğme önce eklenen bir araç çubuğu düğmesi sıfır tabanlı dizini belirtir.

*lpszCategory*<br/>
[in] Düğme eklemek için kategori dizeyi belirtir.

### <a name="remarks"></a>Açıklamalar

`AddButton` Yöntemi standart komut kimlikleri (örneğin, ID_FILE_MRU_FILE1) düğmeleri yoksayar, komutları, kullanımına izin verilmez (bkz [CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) ve kukla düğmeleri.

Bu yöntem aynı türde yeni bir nesne oluşturur `button` (genellikle bir [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)) düğmesinin çalışma zamanı sınıf kullanarak. Çağırır [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) düğmesi, veri üyeleri kopyalamak ve kopyayı belirtilen kategorisine ekler.

Yeni düğmesini eklendiğinde aldığı `OnAddToCustomizePage` bildirim.

Varsa `iInsertBefore` -1, düğmeyi kategorileri listesine eklenir; Aksi takdirde belirtilen dizin ile öğeyi çizmeden önce eklenir.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `AddButton` yöntemi `CMFCToolBarsCustomizeDialog` sınıfı. Bu kod parçacığı parçasıdır [kaydırıcı örnek](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]

##  <a name="addmenu"></a>  CMFCToolBarsCustomizeDialog::AddMenu

Bir menü kaynakları ve çağrıları yükler [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) , menü komutlarını listesine eklemek için **komutları** sayfası.

```
BOOL AddMenu(UINT uiMenuResId);
```

### <a name="parameters"></a>Parametreler

*uiMenuResId*<br/>
[in] Yüklemek için bir menü kaynak Kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir menü başarıyla eklenmişse TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Çağrısında `AddMenuCommands`, *bPopup* yanlış. Sonuç olarak, bu yöntem, alt komutları listesi içeren bir menü öğeleri eklemez. Bu yöntem, komutların listesini menülerinde menü öğeleri ekleyin.

##  <a name="addmenucommands"></a>  CMFCToolBarsCustomizeDialog::AddMenuCommands

Komutları listesi öğeleri ekler **komutları** belirtilen menüsündeki tüm öğeleri göstermek için sayfa.

```
void AddMenuCommands(
    const CMenu* pMenu,
    BOOL bPopup,
    LPCTSTR lpszCategory=NULL,
    LPCTSTR lpszMenuPath=NULL);
```

### <a name="parameters"></a>Parametreler

*pMenu*<br/>
[in] Eklenecek CMenu nesne işaretçisi.

*bPopup*<br/>
[in] Komutların açılan menü öğelerinin listesine eklemek etkinleştirilip etkinleştirilmeyeceğini belirtir.

*lpszCategory*<br/>
[in] Menü eklemek için bir kategori adı.

*lpszMenuPath*<br/>
[in] Komut içinde gösterildiğinde adına eklenecek bir ön ek **tüm kategorileri** listesi.

### <a name="remarks"></a>Açıklamalar

`AddMenuCommands` Yöntemi döngüler tüm menü öğelerinin üzerinden *pMenu*. Bu yöntem, bir alt içermeyen her menü öğesi için oluşturur bir [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md) nesne ve çağrıları [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) yöntemi bir araç çubuğu menü öğesi eklemek için Düğme komutları listesine **komutları** sayfası. Ayırıcılar, bu işlemde göz ardı edilir.

Varsa *bPopup* doğru ise, alt menüyü içeren her bir menü öğesi için bu yöntemi oluşturur bir [CMFCToolBarMenuButton sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md) çağırarak komutları listesine ekler ve nesne `AddButton`. Aksi takdirde menülerinde içeren menü öğelerini komutları listesinde görüntülenmez. Her iki durumda da, `AddMenuCommands` karşılaştığında bir menü öğesi içeren bir alt menü kendisi bir işaretçi alt geçirerek yinelemeli olarak çağrı yaptığı *pMenu* parametresi ve menüye etiketi ekleyerek *lpszMenuPath*.

##  <a name="addtoolbar"></a>  CMFCToolBarsCustomizeDialog::AddToolBar

Araç çubuğu kaynakları yükler. Ardından, her komut menüsünde çağrılarda [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) komutların listesini de bir düğme eklemek için yöntemi **komutları** sayfasında belirtilen kategori altında.

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
[in] Araç çubuğuna eklenecek kategori kaynak Kimliğini belirtir.

*uiToolbarResId*<br/>
[in] Bir araç çubuğunun komutlarının komutlar listesine eklenen kaynak Kimliğini belirtir.

*lpszCategory*<br/>
[in] Araç eklenecek kategorisinin adını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; Aksi durumda FALSE.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `AddToolBar` yönteminde `CMFCToolBarsCustomizeDialog` sınıfı. Bu kod parçacığı parçasıdır [Word paneli örnek](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]

### <a name="remarks"></a>Açıklamalar

Her komutu temsil etmek için kullanılan bir denetimi bir [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md) nesne. Araç ekledikten sonra düğmeyi türetilmiş bir türde bir denetimle çağırarak değiştirebilirsiniz [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton).

##  <a name="checktoolsvalidity"></a>  CMFCToolBarsCustomizeDialog::CheckToolsValidity

Kullanıcı araçlarını listesini geçerliliğini doğrular.

```
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```

### <a name="parameters"></a>Parametreler

*lstTools*<br/>
[in] Denetlenecek kullanıcı tanımlı Araçlar listesi.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tanımlı Araçlar listesi geçerli ise TRUE döndürür; Aksi durumda FALSE. Varsayılan uygulama her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Framework tarafından döndürülen kullanıcı tanımlı Araçlar temsil eden nesneleri geçerliliğini doğrulamak için bu yöntemi çağırır [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity).

Geçersiz kılma `CheckToolsValidity` sınıfından türetilen bir sınıfta yöntemi `CMFCToolBarsCustomizeDialog` kullanıcı araçlarını kullanıcı iletişim kutusu kapanır önce doğrulamak istiyorsanız. Bu yöntem FALSE döndürürse kullanıcı ya da tıkladığında **Kapat** iletişim kutusunu veya etiketli düğmeye sağ üst köşesindeki düğmeyi **Kapat** iletişim kutusunda, iletişim kutusunun sağ alt köşesindeki görüntüler **Araçları** kapanış yerine sekmesi. Kullanıcının liste kutusundan gitmek için bir sekmeye tıkladığında bu yöntem FALSE döndürürse **Araçları** sekmesinde, gezinti oluşmaz. Doğrulama başarısız olmasına neden olan sorunu kullanıcıyı bilgilendirmek üzere bir uygun bir ileti kutusu görüntülenmelidir.

##  <a name="cmfctoolbarscustomizedialog"></a>  CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog

Oluşturur bir `CMFCToolBarsCustomizeDialog` nesne.

```
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bAutoSetFromMenus = FALSE,
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```

### <a name="parameters"></a>Parametreler

*pWndParentFrame*<br/>
[in] Ana çerçeve işaretçisi. Bu parametre NULL olmamalıdır.

*bAutoSetFromMenus*<br/>
[in] Menü komutlarını tüm menülerden üzerinde komutların listesini eklenip eklenmeyeceğini belirten bir Boole değeri **komutları** sayfası. Bu parametre TRUE ise, menü komutlarını eklenir. Aksi takdirde, menü komutlarını eklenmez.

*uiFlags*<br/>
[in] İletişim kutusunun davranışını etkileyen bayrakların birleşimi. Bu parametre, bir veya daha fazla aşağıdaki değerlerden biri olabilir:

- AFX_CUSTOMIZE_MENU_SHADOWS

- AFX_CUSTOMIZE_TEXT_LABELS

- AFX_CUSTOMIZE_MENU_ANIMATIONS

- AFX_CUSTOMIZE_NOHELP

- AFX_CUSTOMIZE_CONTEXT_HELP

- AFX_CUSTOMIZE_NOTOOLS

- AFX_CUSTOMIZE_MENUAMPERS

- AFX_CUSTOMIZE_NO_LARGE_ICONS

*plistCustomPages*<br/>
[in] Listesine bir işaretçi `CRuntimeClass` ek özel sayfalar belirttiğiniz nesneleri.

### <a name="remarks"></a>Açıklamalar

*PlistCustomPages* parametre listesine başvuruyor `CRuntimeClass` ek özel sayfalar belirttiğiniz nesneleri. Oluşturucu kullanarak daha fazla sayfa iletişim kutusuna ekler [CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject) yöntemi. CustomPages örnek sayfalar ekleyen bir örnek için bkz. **Özelleştir** iletişim kutusu.

İçinde geçirebileceğiniz değerleri hakkında daha fazla bilgi için *uiFlags* parametresi bkz [CMFCToolBarsCustomizeDialog::GetFlags](#getflags).

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCToolBarsCustomizeDialog` sınıfı. Bu kod parçacığı parçasıdır [özel sayfaları örnek](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]

##  <a name="create"></a>  CMFCToolBarsCustomizeDialog::Create

Görüntüler **özelleştirme** iletişim kutusu.

```
virtual BOOL Create();
```

### <a name="return-value"></a>Dönüş Değeri

Özelleştirme özellik sayfası başarıyla oluşturulursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Çağrı `Create` sonra tam olarak yalnızca sınıf başlatma yöntemi.

##  <a name="enableuserdefinedtoolbars"></a>  CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars

Etkinleştirir ya da kullanarak yeni araç çubukları oluşturma devre dışı bırakır **Özelleştir** iletişim kutusu.

```
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] Kullanıcı tanımlı araç çubukları etkinleştirmek için TRUE; Araç çubuklarını devre dışı bırakmak için FALSE.

### <a name="remarks"></a>Açıklamalar

Varsa *bSistemlerde* TRUE ise **yeni**, **Yeniden Adlandır** ve **Sil** düğmeleri görüntülenir **araç çubukları** Sayfa.

Varsayılan olarak veya *bSistemlerde* FALSE olduğunda, bu düğmeler görüntülenmez ve kullanıcının yeni araç çubukları tanımlanamaz.

##  <a name="fillallcommandslist"></a>  CMFCToolBarsCustomizeDialog::FillAllCommandsList

Sağlanan doldurur `CListBox` komutlar nesnesiyle **tüm komutları** kategorisi.

```
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;
```

### <a name="parameters"></a>Parametreler

*wndListOfCommands*<br/>
[out] Bir başvuru `CListBox` doldurulacak nesne.

### <a name="remarks"></a>Açıklamalar

**Tüm komutları** kategorisi, tüm kategorileri komutlarını içerir. [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) yöntemi için sağlanan düğmesi ile ilişkili olan komut ekler **tüm komutları** , kategori.

Bu yöntem sağlanan içeriğini temizler `CListBox` komutları ile doldurma önce nesne **tüm komutları** kategorisi.

`CMFCMousePropertyPage` Sınıfı, çift tıklama olay liste kutusunu doldurmak için bu yöntemi kullanır.

##  <a name="fillcategoriescombobox"></a>  CMFCToolBarsCustomizeDialog::FillCategoriesComboBox

Sağlanan doldurur `CComboBox` her komut kategorinin adını nesnesiyle **Özelleştir** iletişim kutusu.

```
void FillCategoriesComboBox(
    CComboBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*wndCategory*<br/>
[out] Bir başvuru `CComboBox` doldurulacak nesne.

*bAddEmpty*<br/>
[in] Kategorileri komutları olmayan açılan kutu eklenip eklenmeyeceğini belirten bir Boole değeri. Bu parametre ise TRUE, boş kategorileri birleşik giriş kutusuna eklenir. Aksi takdirde boş kategorileri eklenmez.

### <a name="remarks"></a>Açıklamalar

Bu yöntem benzer [CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox) yöntemi dışında bu yöntem çalışır bir `CComboBox` nesne.

Bu yöntem içeriğini temizlemez `CComboBox` bunu doldurma önce nesne. Garanti **tüm komutları** kategorisi birleşik giriş kutusundaki son öğedir.

Yeni komut kategorileri kullanarak ekleyebilirsiniz [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) yöntemi. Var olan bir kategori adını kullanarak değiştirebileceğiniz [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) yöntemi.

`CMFCToolBarsKeyboardPropertyPage` Ve `CMFCKeyMapDialog` sınıfları klavye eşleme kategorilere ayırmak için bu yöntemi kullanın.

##  <a name="fillcategorieslistbox"></a>  CMFCToolBarsCustomizeDialog::FillCategoriesListBox

Sağlanan doldurur `CListBox` her komut kategorinin adını nesnesiyle **Özelleştir** iletişim kutusu.

```
void FillCategoriesListBox(
    CListBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*wndCategory*<br/>
[out] Bir başvuru `CListBox` doldurulacak nesne.

*bAddEmpty*<br/>
[in] Kategorileri komutları olmayan liste kutusuna eklenip eklenmeyeceğini belirten bir Boole değeri. Bu parametre ise TRUE, boş kategorileri liste kutusuna eklenir. Aksi takdirde boş kategorileri eklenmez.

### <a name="remarks"></a>Açıklamalar

Bu yöntem benzer [CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox) yöntemi dışında bu yöntem çalışır bir `CListBox` nesne.

Bu yöntem içeriğini temizlemez `CListBox` bunu doldurma önce nesne. Garanti **tüm komutları** son öğeyi liste kutusunda kategorisidir.

Yeni komut kategorileri kullanarak ekleyebilirsiniz [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) yöntemi. Var olan bir kategori adını kullanarak değiştirebileceğiniz [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) yöntemi.

`CMFCToolBarsCommandsPropertyPage` Sınıfı, her komut kategorisiyle ilişkili komutların listesini göstermek için bu yöntemi kullanır.

##  <a name="getcommandname"></a>  CMFCToolBarsCustomizeDialog::GetCommandName

Belirtilen komut kimliğiyle ilişkili adı alır.

```
LPCTSTR GetCommandName(UINT uiCmd) const;
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[in] Alınacak komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Komut yoksa, belirtilen komut kimliği ya da NULL ile ilişkili ad.

##  <a name="getcountincategory"></a>  CMFCToolBarsCustomizeDialog::GetCountInCategory

Belirtilen metin etiketi olan verilen listedeki öğe sayısını alır.

```
int GetCountInCategory(
    LPCTSTR lpszItemName,
    const CObList& lstCommands) const;
```

### <a name="parameters"></a>Parametreler

*lpszItemName*<br/>
[in] Eşleştirilecek metin etiketi.

*lstCommands*<br/>
[in] Bir başvuru içeren bir liste `CMFCToolBarButton` nesneleri.

### <a name="return-value"></a>Dönüş Değeri

Sağlanan öğe sayısı, metin etiketi eşittir listesinde *lpszItemName*.

### <a name="remarks"></a>Açıklamalar

Sağlanan nesne listedeki her öğe türünde olmalıdır `CMFCToolBarButton`. Bu yöntem karşılaştırır *lpszItemName* ile [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) veri üyesi.

##  <a name="getflags"></a>  CMFCToolBarsCustomizeDialog::GetFlags

İletişim kutusunun davranışını etkileyen bayrakları kümesini alır.

```
UINT GetFlags() const;
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunun davranışını etkileyen bayrak kümesi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, değerini alır. *uiFlags* oluşturucuya geçirilen parametre. Dönüş değeri, bir veya daha fazla aşağıdaki değerlerden biri olabilir:

|||
|-|-|
|AFX_CUSTOMIZE_MENU_SHADOWS|Menü gölge görünümünü belirtmesini sağlar.  |
|AFX_CUSTOMIZE_TEXT_LABELS|Araç çubuğu düğmesi görüntülerini metin etiketi gösterilip gösterilmeyeceğini belirtmesini sağlar.  |
|AFX_CUSTOMIZE_MENU_ANIMATIONS|Menü animasyon stilini belirtmesini sağlar.  |
|AFX_CUSTOMIZE_NOHELP|Özelleştirme iletişim kutusundaki Yardım düğmesini kaldırır.  |
|AFX_CUSTOMIZE_CONTEXT_HELP|WS_EX_CONTEXTHELP görsel stili sağlar.  |
|AFX_CUSTOMIZE_NOTOOLS|Kaldırır **Araçları** özelleştirme iletişim kutusundan sayfası. Bu bayrak uygulamanızın kullanıyorsa geçerlidir `CUserToolsManager` sınıfı.  |
|AFX_CUSTOMIZE_MENUAMPERS|Açıklamalı alt yazılar ve işareti içerecek şekilde düğmesi sağlar ( **&**) karakter.  |
|AFX_CUSTOMIZE_NO_LARGE_ICONS|Kaldırır **büyük simgeler** özelleştirme iletişim kutusundan seçeneği.  |

WS_EX_CONTEXTHELP görsel stili hakkında daha fazla bilgi için bkz: [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

##  <a name="onafterchangetool"></a>  CMFCToolBarsCustomizeDialog::OnAfterChangeTool

Hemen gerçekleştikten sonra kullanıcı aracında bir değişikliğe yanıt verir.

```
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Parametreler

*pSelTool*<br/>
[out içinde] Değiştirildi kullanıcı aracı nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir kullanıcı bir kullanıcı tanımlı araç özellikleri değiştiğinde framework tarafından çağırılır. Varsayılan uygulama, hiçbir şey yapmaz. Türetilen bir sınıfta bu yöntemin üzerine yazması `CMFCToolBarsCustomizeDialog` kullanıcı aracı için bir değişiklik gerçekleştikten sonra işleme gerçekleştirmek için.

##  <a name="onassignkey"></a>  CMFCToolBarsCustomizeDialog::OnAssignKey

Bir kullanıcı bunları tanımladığı gibi klavye kısayolları doğrular.

```
virtual BOOL OnAssignKey(ACCEL* pAccel);
```

### <a name="parameters"></a>Parametreler

*pAccel*<br/>
[out içinde] İşaretçi olarak ifade edilen önerilen klavye atama bir [HIZLANDIRMA](/windows/desktop/api/winuser/ns-winuser-tagaccel) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Anahtar atanmışsa anahtar atanan veya FALSE olabilir, TRUE. Varsayılan uygulama her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Türetilen bir sınıfta bir kullanıcı yeni bir klavye kısayolu atar ya da kullanıcı olarak klavye kısayolları doğrulamak için bunları tanımladığı ek işleme gerçekleştirmek için bu yöntemi yok sayın. Bir kısayol atanmasını önlemek için false değerini döndürür. Ayrıca bir ileti kutusu görüntülemek veya aksi halde neden klavye kısayolunu reddedilme nedeni, kullanıcıyı bilgilendirmek gerekir.

##  <a name="onbeforechangetool"></a>  CMFCToolBarsCustomizeDialog::OnBeforeChangeTool

Kullanıcı yaklaşık bir değişikliği uygulamak için olduğunda özel bir değişiklik olduğunda kullanıcı aracını işleme gerçekleştirir.

```
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Parametreler

*pSelTool*<br/>
[out içinde] Yaklaşık değiştirilmesi gereken kullanıcı aracı nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir kullanıcı tanımlı araç kümesidir değişmek üzere bu yöntem çerçeve tarafından çağrılır. Varsayılan uygulama, hiçbir şey yapmaz. Geçersiz kılma `OnBeforeChangeTool` sınıfından türetilen bir sınıfta yöntemi `CMFCToolBarsCustomizeDialog` kaynakları serbest bırakmak gibi bir kullanıcı aracı için bir değişiklik gerçekleşmeden önce işlem gerçekleştirmek istiyorsanız, *pSelTool* kullanır.

##  <a name="onedittoolbarmenuimage"></a>  CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage

Bir kullanıcı bir araç çubuğu düğmesini veya menü öğesi simgesi özelleştirebilmeniz için görüntü Düzenleyicisi başlatılır.

```
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,
    CBitmap& bitmap,
    int nBitsPerPixel);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[in] Üst penceresine bir işaretçi.

*Bit eşlem*<br/>
[in] Düzenlenecek bir bit eşlem nesnesine bir başvuru.

*nBitsPerPixel*<br/>
[in] Piksel başına bit renk çözünürlüğü bit eşlem.

### <a name="return-value"></a>Dönüş Değeri

Bir değişiklik kararlıdır TRUE; Aksi durumda FALSE. Varsayılan uygulama, bir iletişim kutusu görüntüler ve kullanıcı varsa TRUE değerini döndürür **Tamam**, kullanıcı tıklarsa false **iptal** veya **Kapat** düğmesi.

### <a name="remarks"></a>Açıklamalar

Resim Düzenleyicisi kullanıcı çalıştırdığında bu yöntem framework tarafından çağırılır. Varsayılan uygulama görüntüler [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md) iletişim kutusu. Geçersiz kılma `OnEditToolbarMenuImage` türetilen bir sınıfta bir özel görüntü düzenleyici kullanılacak.

##  <a name="oninitdialog"></a>  CMFCToolBarsCustomizeDialog::OnInitDialog

Özellik sayfası başlatıcısını büyütmek için geçersiz kılar.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Arama sonucu [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) yöntemi.

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu yöntemin genişlettiği [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog), görüntüleyerek **Kapat** düğmesi, iletişim kutusu geçerli ekran boyutu sığdığından emin yaparak ve taşıma **Yardımcı** iletişim kutusunun sol alt köşesindeki düğmeye.

##  <a name="oninittoolspage"></a>  CMFCToolBarsCustomizeDialog::OnInitToolsPage

Çerçeveden bildirim işleme, **Araçları** sayfasıdır yaklaşık olarak başlatılacak.

```
virtual void OnInitToolsPage();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, hiçbir şey yapmaz. Türetilen bir sınıfta bu bildirim işlemek için bu yöntemi yok sayın.

##  <a name="postncdestroy"></a>  CMFCToolBarsCustomizeDialog::PostNcDestroy

Pencere yok edildikten sonra framework tarafından çağırılır.

```
virtual void PostNcDestroy();
```

### <a name="remarks"></a>Açıklamalar

Temel sınıf uygulamasına bu yöntemin genişlettiği `CPropertySheet::PostNcDestroy`, uygulamanın önceki moda döndürerek.

[CMFCToolBarsCustomizeDialog::Create](#create) yöntemi kullanıcıya özelleştirme görevlerini sınırlandıran bir özel modda uygulamaya koyar.

##  <a name="removebutton"></a>  CMFCToolBarsCustomizeDialog::RemoveButton

Belirtilen komut kimliği düğmeyle belirtilen kategori veya tüm kategorilerden kaldırır.

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
[in] Düğme kaldırılacağı kategorisi Kimliğini belirtir.

*uiCmdId*<br/>
[in] Düğme komut Kimliğini belirtir.

*lpszCategory*<br/>
[in] Kaldır düğmesi kategori adını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Kaldırılan düğmesini ya da belirtilen komut kimliği belirtilen kategoride bulunmadığında -1 sıfır tabanlı dizini. Varsa *uiCategoryId* -1, dönüş değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Tüm kategorilerden bir düğme kaldırmak için bu yöntemi ve kümesi ilk aşırı yükleme çağrı *uiCategoryId* -1.

##  <a name="renamecategory"></a>  CMFCToolBarsCustomizeDialog::RenameCategory

Kategorilerin liste kutusunda bir kategori üzerinde yeniden adlandırır **komutları** sayfası.

```
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,
    LPCTSTR lpszCategoryNew);
```

### <a name="parameters"></a>Parametreler

*lpszCategoryOld*<br/>
[in] Değiştirmek için kategori adı.

*lpszCategoryNew*<br/>
[in] Yeni kategori adı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Kategori adı benzersiz olmalıdır.

##  <a name="replacebutton"></a>  CMFCToolBarsCustomizeDialog::ReplaceButton

Araç çubuğu düğmesi liste kutusunda komutların yerini alır **komutları** sayfası.

```
void ReplaceButton(
    UINT uiCmd,
    const CMFCToolBarButton& button);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[in] Değiştirilecek komut düğmesi belirtir.

*Düğme*<br/>
[in] A **const** eski düğmesi değiştirir araç çubuğu düğmesi nesnesine başvuru alınamıyor.

### <a name="remarks"></a>Açıklamalar

Zaman [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu), [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands), veya [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar) ekler bir komut **komutları** sayfasında komut biçiminde olduğunu bir [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md) nesnesi (veya [CMFCToolBarMenuButton sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md) nesne için bir menü tarafından eklenen bir alt içeren öğe `AddMenuCommands`). Framework de komutları otomatik olarak eklemek için bu üç yöntem çağırır. Bunun yerine türetilmiş bir tür tarafından temsil edilebilir komutu istiyorsanız, çağrı `ReplaceButton` ve türetilmiş bir türde bir düğme geçirin.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `ReplaceButton` yönteminde `CMFCToolBarsCustomizeDialog` sınıfı. Bu kod parçacığı parçasıdır [Visual Studio gösterim örneği](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]

##  <a name="setusercategory"></a>  CMFCToolBarsCustomizeDialog::SetUserCategory

Hangi kategoriyi kategoriler listesinde belirtir **komutları** kullanıcı kategorisi sayfasıdır. Çağırmadan önce bu işlevi çağırmanız gerekir [CMFCToolBarsCustomizeDialog::Create](#create).

```
BOOL SetUserCategory(LPCTSTR lpszCategory);
```

### <a name="parameters"></a>Parametreler

*lpszCategory*<br/>
[in] Kategori adı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Şu anda kullanıcı kategorisi ayarı framework tarafından kullanılmaz.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CPropertySheet Sınıfı](../../mfc/reference/cpropertysheet-class.md)
