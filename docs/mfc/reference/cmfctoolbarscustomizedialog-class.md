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
ms.openlocfilehash: fc313a5cb6e9ce6ebd06ed0432f99203a0f1ff4d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87182921"
---
# <a name="cmfctoolbarscustomizedialog-class"></a>CMFCToolBarsCustomizeDialog sınıfı

Kullanıcının araç çubuklarını, menüleri, klavye kısayollarını, Kullanıcı tanımlı araçları ve bir uygulamada görsel stilini özelleştirmesini sağlayan, engelleyici olmayan bir sekme iletişim kutusu ( [CPropertySheet sınıfı](../../mfc/reference/cpropertysheet-class.md)). Genellikle, Kullanıcı bu iletişim kutusuna **Araçlar** menüsünden **Özelleştir** ' i seçerek erişir.

**Özelleştir** iletişim kutusunda altı sekme vardır: **Komutlar**, **araç çubukları**, **Araçlar**, **klavye**, **menü**ve **Seçenekler**.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarsCustomizeDialog : public CPropertySheet
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|Bir `CMFCToolBarsCustomizeDialog` nesnesi oluşturur.|
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarsCustomizeDialog:: AddButton](#addbutton)|**Komutlar** sayfasındaki komutlar listesine bir araç çubuğu düğmesi ekler|
|[CMFCToolBarsCustomizeDialog:: MenüEkle](#addmenu)|Kaynaklardan bir menü yükler ve **Komutlar** sayfasındaki komutlar listesine eklemek için [CMFCToolBarsCustomizeDialog:: AddMenuCommands](#addmenucommands) ' i çağırır.|
|[CMFCToolBarsCustomizeDialog:: AddMenuCommands](#addmenucommands)|Kaynaklardan bir menü yükler ve **Komutlar** sayfasındaki komutlar listesine eklemek için [CMFCToolBarsCustomizeDialog:: AddMenuCommands](#addmenucommands) ' i çağırır.|
|[CMFCToolBarsCustomizeDialog:: AddToolBar](#addtoolbar)|Kaynaklardan bir araç çubuğu yükler. Ardından, menüdeki her komut için, belirtilen kategori altındaki **Komutlar** sayfasında komutlar listesine bir düğme eklemek için [CMFCToolBarsCustomizeDialog:: AddButton](#addbutton) yöntemini çağırır.|
|[CMFCToolBarsCustomizeDialog:: Create](#create)|**Özelleştirme** iletişim kutusunu görüntüler.|
|`CMFCToolBarsCustomizeDialog::EnableTools`|Daha sonraki kullanımlar için ayrılmıştır.|
|[CMFCToolBarsCustomizeDialog:: EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|**Özelleştir** iletişim kutusunu kullanarak yeni araç çubuklarını oluşturmayı mümkün veya devre dışı bırakır.|
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|`CListBox` **Tüm komutlar** kategorisindeki komutlarla, belirtilen nesneyi doldurur.|
|[CMFCToolBarsCustomizeDialog:: FillCategoriesComboBox](#fillcategoriescombobox)|Belirtilen `CComboBox` nesneyi **Özelleştir** iletişim kutusundaki her komut kategorisinin adıyla doldurur.|
|[CMFCToolBarsCustomizeDialog:: FillCategoriesListBox](#fillcategorieslistbox)|Belirtilen `CListBox` nesneyi **Özelleştir** iletişim kutusundaki her komut kategorisinin adıyla doldurur.|
|[CMFCToolBarsCustomizeDialog:: GetCommandName](#getcommandname)|Verilen komut KIMLIĞIYLE ilişkili olan adı alır.|
|[CMFCToolBarsCustomizeDialog:: Getcounıncategory](#getcountincategory)|Sağlanan listede verilen metin etiketine sahip öğelerin sayısını alır.|
|[CMFCToolBarsCustomizeDialog:: GetFlags](#getflags)|İletişim kutusunun davranışını etkileyen bayrak kümesini alır.|
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCToolBarsCustomizeDialog:: OnEditToolbarMenuImage](#onedittoolbarmenuimage)|Kullanıcının bir araç çubuğu düğmesini veya menü öğesi simgesini özelleştirebilmesi için bir görüntü Düzenleyicisi başlatır.|
|[CMFCToolBarsCustomizeDialog:: OnInitDialog](#oninitdialog)|Özellik sayfası başlatmasını artırmak için geçersiz kılar. ( [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog)geçersiz kılar.)|
|[CMFCToolBarsCustomizeDialog::P ostNcDestroy](#postncdestroy)|Pencere yok edildikten sonra Framework tarafından çağırılır. (Geçersiz kılmalar `CPropertySheet::PostNcDestroy` .)|
|[CMFCToolBarsCustomizeDialog:: RemoveButton](#removebutton)|Belirtilen kategoriden veya tüm kategorilerden belirtilen komut KIMLIĞIYLE düğmeyi kaldırır.|
|[CMFCToolBarsCustomizeDialog:: RenameCategory](#renamecategory)|**Komutlar** sekmesindeki kategorilerin liste kutusunda bir kategoriyi yeniden adlandırır.|
|[CMFCToolBarsCustomizeDialog:: ReplaceButton](#replacebutton)|**Komutlar** sekmesindeki komutlar listesindeki bir düğmeyi yeni bir araç çubuğu düğmesi nesnesi ile değiştirir.|
|[CMFCToolBarsCustomizeDialog:: SetUserCategory](#setusercategory)|**Komutlar** sekmesinde görüntülenecek kategoriler listesine bir kategori ekler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarsCustomizeDialog:: Checkaraçları geçerliliği](#checktoolsvalidity)|Kullanıcı tanımlı araçların listesinin geçerli olup olmadığını anlamak için Framework tarafından çağırılır.|
|[CMFCToolBarsCustomizeDialog:: OnAfterChangeTool](#onafterchangetool)|Kullanıcı tanımlı bir aracın özellikleri değiştiğinde Framework tarafından çağırılır.|
|[CMFCToolBarsCustomizeDialog:: Onatamaanahtarı](#onassignkey)|Belirli bir klavye kısayolunun bir eyleme atanıp atanamayacağını belirler.|
|[CMFCToolBarsCustomizeDialog:: OnBeforeChangeTool](#onbeforechangetool)|Kullanıcı tanımlı bir aracın değiştirilip değiştirilemeyeceğini belirler.|
|[CMFCToolBarsCustomizeDialog:: Onınitaraçları sayfası](#oninittoolspage)|Kullanıcı **Araçlar** sekmesini seçtiğinde Framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

**Özelleştir** iletişim kutusunu göstermek için bir `CMFCToolBarsCustomizeDialog` nesne oluşturun ve [CMFCToolBarsCustomizeDialog:: Create](#create) metodunu çağırın.

**Özelleştir** iletişim kutusu etkin olsa da, uygulama, kullanıcıyı özelleştirme görevleriyle sınırlayan özel bir modda çalışıyor.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir `CMFCToolBarsCustomizeDialog` . Örnek, **Komutlar** sayfasındaki komutların liste kutusunda bir araç çubuğu düğmesinin nasıl değiştirileceğini gösterir, **Özelleştir** iletişim kutusunu kullanarak yeni araç çubukları oluşturmayı etkinleştirir ve **Özelleştirme** iletişim kutusunu görüntüler. Bu kod parçacığı, [IE demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

`CMFCToolBarsCustomizeDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxToolBarsCustomizeDialog. h

## <a name="cmfctoolbarscustomizedialogaddbutton"></a><a name="addbutton"></a>CMFCToolBarsCustomizeDialog:: AddButton

**Komutlar** sayfasındaki komutlar listesine bir araç çubuğu düğmesi ekler.

```cpp
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
'ndaki Düğmenin ekleneceği kategori KIMLIĞINI belirtir.

*Bu*<br/>
'ndaki Eklenecek düğmeyi belirtir.

*daha önce ıınsert*<br/>
'ndaki Düğmenin eklendiği bir araç çubuğu düğmesinin sıfır tabanlı dizinini belirtir.

*lpszCategory*<br/>
'ndaki Düğmeyi eklemek için kategori dizesini belirtir.

### <a name="remarks"></a>Açıklamalar

`AddButton`Yöntemi, standart komut kimliklerine sahip düğmeleri (ID_FILE_MRU_FILE1 gibi) yok sayar, izin verilmeyen komutlar (bkz. [CMFCToolBar:: ıscommandizin verilir](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) ve kukla düğmeleri.

Bu yöntem `button` , düğmenin Runtime sınıfını kullanarak (genellikle [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)) aynı türde yeni bir nesne oluşturur. Ardından düğmenin veri üyelerini kopyalamak için [CMFCToolBarButton:: CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) komutunu çağırır ve kopyayı belirtilen kategoriye ekler.

Yeni düğme eklendiğinde, `OnAddToCustomizePage` bildirimi alır.

`iInsertBefore`-1 ise, düğme Kategori listesine eklenir; Aksi halde, belirtilen dizine sahip öğeden önce eklenir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının yönteminin nasıl kullanılacağını gösterir `AddButton` `CMFCToolBarsCustomizeDialog` . Bu kod parçacığı, [kaydırıcı örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]

## <a name="cmfctoolbarscustomizedialogaddmenu"></a><a name="addmenu"></a>CMFCToolBarsCustomizeDialog:: MenüEkle

Kaynaklardan bir menü yükler ve **Komutlar** sayfasındaki komutlar listesine eklemek için [CMFCToolBarsCustomizeDialog:: AddMenuCommands](#addmenucommands) ' i çağırır.

```
BOOL AddMenu(UINT uiMenuResId);
```

### <a name="parameters"></a>Parametreler

*Uııd*<br/>
'ndaki Yüklenecek menünün kaynak KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir menü başarıyla eklendiyse doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Çağrısında `AddMenuCommands` *BPOPUP* false şeklindedir. Sonuç olarak, bu yöntem alt menüler içeren menü öğelerini komut listesine eklemez. Bu yöntem, alt menülerde menü öğelerini komut listesine ekler.

## <a name="cmfctoolbarscustomizedialogaddmenucommands"></a><a name="addmenucommands"></a>CMFCToolBarsCustomizeDialog:: AddMenuCommands

Belirtilen menüdeki tüm öğeleri göstermek için **Komutlar** sayfasındaki komutlar listesine öğe ekler.

```cpp
void AddMenuCommands(
    const CMenu* pMenu,
    BOOL bPopup,
    LPCTSTR lpszCategory=NULL,
    LPCTSTR lpszMenuPath=NULL);
```

### <a name="parameters"></a>Parametreler

*pMenu*<br/>
'ndaki Eklenecek CMenu nesnesine yönelik bir işaretçi.

*bPopup*<br/>
'ndaki Açılan menü öğelerinin komut listesine eklenip eklenmeyeceğini belirtir.

*lpszCategory*<br/>
'ndaki Menünün ekleneceği kategorinin adı.

*lpszMenuPath*<br/>
'ndaki Komut **Tüm Kategoriler** listesinde gösterildiğinde ada eklenen bir ön ek.

### <a name="remarks"></a>Açıklamalar

`AddMenuCommands`Yöntemi, *pMenu*'nin tüm menü öğeleri üzerinde döngü başlatır. Alt menü içermeyen her bir menü öğesi için, bu yöntem bir [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md) nesnesi oluşturur ve menü öğesini **Komutlar** sayfasındaki komutlar listesine bir araç çubuğu düğmesi olarak eklemek Için [CMFCToolBarsCustomizeDialog:: AddButton](#addbutton) yöntemini çağırır. Ayırıcılar bu işlemde yok sayılır.

*BPopup* true ise, bir alt menü içeren her bir menü öğesi için, bu yöntem bir [Cmfctoolbarmenubtan Class](../../mfc/reference/cmfctoolbarmenubutton-class.md) nesnesi oluşturur ve çağırarak komutları listesine ekler `AddButton` . Aksi halde alt menüler içeren menü öğeleri komut listesinde gösterilmez. Her iki durumda da, alt menüye `AddMenuCommands` sahip bir menü öğesiyle karşılaştığında, bir Işaretçiyi *pMenu* parametresi olarak alt menüye bir işaretçi geçirerek ve alt menünün etiketini *lpszMenuPath*' ye ekleyerek kendisini yinelemeli olarak çağırır.

## <a name="cmfctoolbarscustomizedialogaddtoolbar"></a><a name="addtoolbar"></a>CMFCToolBarsCustomizeDialog:: AddToolBar

Kaynaklardan bir araç çubuğu yükler. Ardından, menüdeki her komut için, belirtilen kategori altındaki **Komutlar** sayfasında komutlar listesine bir düğme eklemek için [CMFCToolBarsCustomizeDialog:: AddButton](#addbutton) yöntemini çağırır.

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
'ndaki Araç çubuğunun ekleneceği kategorinin kaynak KIMLIĞINI belirtir.

*Uıtoolbarresd*<br/>
'ndaki Komutları komut listesine eklenen bir araç çubuğunun kaynak KIMLIĞINI belirtir.

*lpszCategory*<br/>
'ndaki Araç çubuğunun ekleneceği kategorinin adını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; Aksi halde yanlış.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında yönteminin nasıl kullanılacağını gösterir `AddToolBar` `CMFCToolBarsCustomizeDialog` . Bu kod parçacığı, [sözcük paneli örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]

### <a name="remarks"></a>Açıklamalar

Her bir komutu temsil etmek için kullanılan denetim bir [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md) nesnesidir. Araç çubuğunu ekledikten sonra, [CMFCToolBarsCustomizeDialog:: ReplaceButton](#replacebutton)öğesini çağırarak düğme türetilmiş bir tür denetimiyle değiştirebilirsiniz.

## <a name="cmfctoolbarscustomizedialogchecktoolsvalidity"></a><a name="checktoolsvalidity"></a>CMFCToolBarsCustomizeDialog:: Checkaraçları geçerliliği

Kullanıcı araçları listesinin geçerliliğini doğrular.

```
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```

### <a name="parameters"></a>Parametreler

*lstTools*<br/>
'ndaki Denetlenecek Kullanıcı tanımlı araçların listesi.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tanımlı araçların listesi geçerliyse TRUE değerini döndürür; Aksi halde yanlış. Varsayılan uygulama her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Framework, [CMFCToolBarsCustomizeDialog:: Checkaraçları geçerliliği](#checktoolsvalidity)tarafından döndürülen Kullanıcı tanımlı araçları temsil eden nesnelerin geçerliliğini doğrulamak için bu yöntemi çağırır.

`CheckToolsValidity` `CMFCToolBarsCustomizeDialog` Kullanıcı iletişim kutusunu kapatmadan önce kullanıcı araçlarını doğrulamak istiyorsanız, öğesinden türetilmiş bir sınıftaki yöntemi geçersiz kılın. Kullanıcı iletişim kutusunun sağ üst köşesindeki **Kapat** düğmesine veya iletişim kutusunun sağ alt köşesinde **Kapat** etiketli düğmeye tıkladığında bu yöntem false döndürürse, Iletişim kutusunda kapatma yerine **Araçlar** sekmesi görüntülenir. Bu yöntem, Kullanıcı **Araçlar** sekmesinden uzaklaşmak üzere bir SEKMEYE tıkladığında false döndürürse, gezinti gerçekleşmez. Kullanıcıya doğrulamanın başarısız olmasına neden olan sorunu bilgilendirmek için uygun bir ileti kutusu görüntülenmelidir.

## <a name="cmfctoolbarscustomizedialogcmfctoolbarscustomizedialog"></a><a name="cmfctoolbarscustomizedialog"></a>CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog

Bir `CMFCToolBarsCustomizeDialog` nesnesi oluşturur.

```
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bAutoSetFromMenus = FALSE,
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```

### <a name="parameters"></a>Parametreler

*pWndParentFrame*<br/>
'ndaki Üst çerçeveye yönelik bir işaretçi. Bu parametre NULL olmamalıdır.

*bAutoSetFromMenus*<br/>
'ndaki Tüm menülerden menü komutlarının **Komutlar** sayfasındaki komut listesine eklenip eklenmeyeceğini belirten bir Boole değeri. Bu parametre TRUE ise, menü komutları eklenir. Aksi takdirde, menü komutları eklenmez.

*Uılags*<br/>
'ndaki İletişim kutusunun davranışını etkileyen bayrakların birleşimi. Bu parametre aşağıdaki değerlerden biri veya daha fazlası olabilir:

- AFX_CUSTOMIZE_MENU_SHADOWS

- AFX_CUSTOMIZE_TEXT_LABELS

- AFX_CUSTOMIZE_MENU_ANIMATIONS

- AFX_CUSTOMIZE_NOHELP

- AFX_CUSTOMIZE_CONTEXT_HELP

- AFX_CUSTOMIZE_NOTOOLS

- AFX_CUSTOMIZE_MENUAMPERS

- AFX_CUSTOMIZE_NO_LARGE_ICONS

*plistCustomPages*<br/>
'ndaki `CRuntimeClass`Ek özel sayfalar belirten nesne listesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*PlistCustomPages* parametresi, `CRuntimeClass` ek özel sayfalar belirten nesne listesini ifade eder. Oluşturucu, [CRuntimeClass:: CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject) metodunu kullanarak iletişim kutusuna daha fazla sayfa ekler. **Özelleştirme** iletişim kutusuna daha fazla sayfa ekleyen bir örnek için CustomPages örneğine bakın.

*Uıcılags* parametresinde geçirebilmeniz gereken değerler hakkında daha fazla bilgi için bkz. [CMFCToolBarsCustomizeDialog:: GetFlags](#getflags).

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu gösterir `CMFCToolBarsCustomizeDialog` . Bu kod parçacığı, [özel sayfalar örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]

## <a name="cmfctoolbarscustomizedialogcreate"></a><a name="create"></a>CMFCToolBarsCustomizeDialog:: Create

**Özelleştirme** iletişim kutusunu görüntüler.

```
virtual BOOL Create();
```

### <a name="return-value"></a>Dönüş Değeri

Özelleştirme özellik sayfası başarıyla oluşturulursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

`Create`Yalnızca sınıfı tam olarak başlattıktan sonra yöntemi çağırın.

## <a name="cmfctoolbarscustomizedialogenableuserdefinedtoolbars"></a><a name="enableuserdefinedtoolbars"></a>CMFCToolBarsCustomizeDialog:: EnableUserDefinedToolbars

**Özelleştir** iletişim kutusunu kullanarak yeni araç çubuklarını oluşturmayı mümkün veya devre dışı bırakır.

```cpp
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Kullanıcı tanımlı araç çubuklarını etkinleştirmek için TRUE; Araç çubuklarını devre dışı bırakmak için FALSE.

### <a name="remarks"></a>Açıklamalar

*BEnable* değeri true Ise, **Yeni**, **Yeniden Adlandır** ve **Sil** düğmeleri **araç çubukları** sayfasında görüntülenir.

Varsayılan olarak veya *bEnable* false ise, bu düğmeler görüntülenmez ve Kullanıcı yeni araç çubuklarını tanımlayamazlar.

## <a name="cmfctoolbarscustomizedialogfillallcommandslist"></a><a name="fillallcommandslist"></a>CMFCToolBarsCustomizeDialog::FillAllCommandsList

`CListBox` **Tüm komutlar** kategorisindeki komutlarla, belirtilen nesneyi doldurur.

```
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;
```

### <a name="parameters"></a>Parametreler

*Wndlıfcommands*<br/>
dışı `CListBox`Doldurulması için nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

**Tüm komutlar** kategorisi tüm kategorilerin komutlarını içerir. [CMFCToolBarsCustomizeDialog:: AddButton](#addbutton) yöntemi, belirtilen düğmeyle ilişkili komutu, sizin Için **tüm komutlar** kategorisine ekler.

Bu yöntem, `CListBox` **tüm komutlar** kategorisindeki komutlarla doldurulmadan önce, belirtilen nesnenin içeriğini temizler.

`CMFCMousePropertyPage`Sınıfı, Çift tıklama olay listesi kutusunu doldurmak için bu yöntemi kullanır.

## <a name="cmfctoolbarscustomizedialogfillcategoriescombobox"></a><a name="fillcategoriescombobox"></a>CMFCToolBarsCustomizeDialog:: FillCategoriesComboBox

Belirtilen `CComboBox` nesneyi **Özelleştir** iletişim kutusundaki her komut kategorisinin adıyla doldurur.

```cpp
void FillCategoriesComboBox(
    CComboBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*wndCategory*<br/>
dışı `CComboBox`Doldurulması için nesneye bir başvuru.

*bAddEmpty*<br/>
'ndaki Birleşik giriş kutusuna komutlarına sahip olmayan kategoriler eklenip eklenmeyeceğini belirten bir Boole değeri. Bu parametre TRUE ise, açılan kutuya boş kategoriler eklenir. Aksi takdirde boş kategoriler eklenmez.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bu yöntemin bir nesneyle çalışması dışında [CMFCToolBarsCustomizeDialog:: FillCategoriesListBox](#fillcategorieslistbox) yöntemine benzer `CComboBox` .

Bu yöntem, nesnenin içeriğini doldurmadan önce temizlemez `CComboBox` . **Tüm komutlar** kategorisinin Birleşik giriş kutusundaki son öğe olmasını güvence altına alır.

[CMFCToolBarsCustomizeDialog:: AddButton](#addbutton) metodunu kullanarak yeni komut kategorileri ekleyebilirsiniz. Var olan bir kategorinin adını [CMFCToolBarsCustomizeDialog:: RenameCategory](#renamecategory) metodunu kullanarak değiştirebilirsiniz.

`CMFCToolBarsKeyboardPropertyPage`Ve `CMFCKeyMapDialog` sınıfları, klavye eşlemelerini sınıflandırmak için bu yöntemi kullanır.

## <a name="cmfctoolbarscustomizedialogfillcategorieslistbox"></a><a name="fillcategorieslistbox"></a>CMFCToolBarsCustomizeDialog:: FillCategoriesListBox

Belirtilen `CListBox` nesneyi **Özelleştir** iletişim kutusundaki her komut kategorisinin adıyla doldurur.

```cpp
void FillCategoriesListBox(
    CListBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*wndCategory*<br/>
dışı `CListBox`Doldurulması için nesneye bir başvuru.

*bAddEmpty*<br/>
'ndaki Liste kutusuna komutlarına sahip olmayan kategoriler eklenip eklenmeyeceğini belirten bir Boole değeri. Bu parametre TRUE ise, liste kutusuna boş kategoriler eklenir. Aksi takdirde boş kategoriler eklenmez.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CMFCToolBarsCustomizeDialog:: FillCategoriesComboBox](#fillcategoriescombobox) yöntemine benzer, bu yöntemin bir nesneyle çalışması dışında `CListBox` .

Bu yöntem, nesnenin içeriğini doldurmadan önce temizlemez `CListBox` . **Tüm komutlar** kategorisinin liste kutusunda son öğe olmasını güvence altına alır.

[CMFCToolBarsCustomizeDialog:: AddButton](#addbutton) metodunu kullanarak yeni komut kategorileri ekleyebilirsiniz. Var olan bir kategorinin adını [CMFCToolBarsCustomizeDialog:: RenameCategory](#renamecategory) metodunu kullanarak değiştirebilirsiniz.

`CMFCToolBarsCommandsPropertyPage`Sınıfı, her komut kategorisiyle ilişkili komutların listesini göstermek için bu yöntemi kullanır.

## <a name="cmfctoolbarscustomizedialoggetcommandname"></a><a name="getcommandname"></a>CMFCToolBarsCustomizeDialog:: GetCommandName

Verilen komut KIMLIĞIYLE ilişkili olan adı alır.

```
LPCTSTR GetCommandName(UINT uiCmd) const;
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Alınacak komutun KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Verilen komut KIMLIĞIYLE ilişkili ad veya komut yoksa NULL.

## <a name="cmfctoolbarscustomizedialoggetcountincategory"></a><a name="getcountincategory"></a>CMFCToolBarsCustomizeDialog:: Getcounıncategory

Sağlanan listede verilen metin etiketine sahip öğelerin sayısını alır.

```
int GetCountInCategory(
    LPCTSTR lpszItemName,
    const CObList& lstCommands) const;
```

### <a name="parameters"></a>Parametreler

*lpszItemName*<br/>
'ndaki Eşleştirilecek metin etiketi.

*lstCommands*<br/>
'ndaki Nesneleri içeren bir listeye başvuru `CMFCToolBarButton` .

### <a name="return-value"></a>Dönüş Değeri

Belirtilen listedeki metin etiketini *lpszItemName*eşit olan öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Belirtilen nesne listesindeki her öğe türünde olmalıdır `CMFCToolBarButton` . Bu yöntem, *lpszItemName* Ile [CMFCToolBarButton:: m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) veri üyesiyle karşılaştırılır.

## <a name="cmfctoolbarscustomizedialoggetflags"></a><a name="getflags"></a>CMFCToolBarsCustomizeDialog:: GetFlags

İletişim kutusunun davranışını etkileyen bayrak kümesini alır.

```
UINT GetFlags() const;
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunun davranışını etkileyen bayraklar kümesi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, oluşturucuya geçirilen *Uıiflags* parametresinin değerini alır. Dönüş değeri aşağıdaki değerlerden biri veya daha fazlası olabilir:

|||
|-|-|
|AFX_CUSTOMIZE_MENU_SHADOWS|Kullanıcının menünün gölge görünümünü belirlemesine izin verir.  |
|AFX_CUSTOMIZE_TEXT_LABELS|Kullanıcının araç çubuğu düğmesi görüntülerinin altında metin etiketlerinin gösterilip gösterilmeyeceğini belirlemesine izin verir.  |
|AFX_CUSTOMIZE_MENU_ANIMATIONS|Kullanıcının menü animasyon stilini belirtmesini sağlar.  |
|AFX_CUSTOMIZE_NOHELP|Özelleştirme iletişim kutusundan Yardım düğmesini kaldırır.  |
|AFX_CUSTOMIZE_CONTEXT_HELP|WS_EX_CONTEXTHELP görsel stilini etkinleştirilir.  |
|AFX_CUSTOMIZE_NOTOOLS|Özelleştirme iletişim kutusundan **Araçlar** sayfasını kaldırır. Bu bayrak, uygulamanız sınıfını kullanıyorsa geçerlidir `CUserToolsManager` .  |
|AFX_CUSTOMIZE_MENUAMPERS|Düğme açıklamalı alt yazıların ampersan ( **&** ) karakterini içermesini sağlar.  |
|AFX_CUSTOMIZE_NO_LARGE_ICONS|Özelleştirme iletişim kutusundan **büyük simgeler** seçeneğini kaldırır.  |

WS_EX_CONTEXTHELP görsel stili hakkında daha fazla bilgi için bkz. [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

## <a name="cmfctoolbarscustomizedialogonafterchangetool"></a><a name="onafterchangetool"></a>CMFCToolBarsCustomizeDialog:: OnAfterChangeTool

Bir kullanıcı aracında bir değişikliği oluştuktan hemen sonra yanıtlar.

```
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Parametreler

*pSelTool*<br/>
[in, out] Değiştirilen kullanıcı aracı nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Kullanıcı tanımlı bir aracın özelliklerini değiştirdiğinde Framework tarafından çağrılır. Varsayılan uygulama hiçbir şey yapmaz. Bir `CMFCToolBarsCustomizeDialog` Kullanıcı aracında değişiklik yapıldıktan sonra işlemeyi gerçekleştirmek için öğesinden türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctoolbarscustomizedialogonassignkey"></a><a name="onassignkey"></a>CMFCToolBarsCustomizeDialog:: Onatamaanahtarı

Klavye kısayollarını kullanıcı tarafından tanımladığı şekilde doğrular.

```
virtual BOOL OnAssignKey(ACCEL* pAccel);
```

### <a name="parameters"></a>Parametreler

*pAccel*<br/>
[in, out] Bir [Accel](/windows/win32/api/winuser/ns-winuser-accel) yapısı olarak ifade edilen önerilen klavye ataması işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Anahtar atanabiliyorsa TRUE, anahtar atanacaksa FALSE. Varsayılan uygulama her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bir Kullanıcı yeni bir klavye kısayolu atarken veya Kullanıcı tarafından tanımlandığında klavye kısayollarını doğrulayacağından, daha fazla işlem gerçekleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın. Bir kısayolun atanmasını engellemek için FALSE döndürün. Ayrıca, bir ileti kutusu görüntülemelidir veya kullanıcıya klavye kısayolunun reddedilme nedenini bildirmeniz gerekir.

## <a name="cmfctoolbarscustomizedialogonbeforechangetool"></a><a name="onbeforechangetool"></a>CMFCToolBarsCustomizeDialog:: OnBeforeChangeTool

Kullanıcı bir değişiklik uygulamak üzere olduğunda kullanıcı aracında değişiklik yapıldığında özel işleme gerçekleştirir.

```
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Parametreler

*pSelTool*<br/>
[in, out] Değiştirilmesini gerektiren Kullanıcı aracı nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Kullanıcı tanımlı bir aracın özellikleri değiştirmek üzereyken Framework tarafından çağırılır. Varsayılan uygulama hiçbir şey yapmaz. `OnBeforeChangeTool` `CMFCToolBarsCustomizeDialog` , *PSelTool* 'un kullandığı kaynakları serbest bırakma gibi bir kullanıcı aracında değişiklik yapmadan önce işleme gerçekleştirmek istiyorsanız, öğesinden türetilmiş bir sınıftaki yöntemi geçersiz kılın.

## <a name="cmfctoolbarscustomizedialogonedittoolbarmenuimage"></a><a name="onedittoolbarmenuimage"></a>CMFCToolBarsCustomizeDialog:: OnEditToolbarMenuImage

Kullanıcının bir araç çubuğu düğmesini veya menü öğesi simgesini özelleştirebilmesi için bir görüntü Düzenleyicisi başlatır.

```
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,
    CBitmap& bitmap,
    int nBitsPerPixel);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Ana pencereye yönelik bir işaretçi.

*biteş*<br/>
'ndaki Düzenlenecek bir bit eşlem nesnesine başvuru.

*nBitsPerPixel*<br/>
'ndaki Bit eşlem renk çözünürlüğü, piksel başına bit cinsinden.

### <a name="return-value"></a>Dönüş Değeri

Bir değişiklik yürütüliyorsa TRUE; Aksi halde yanlış. Varsayılan uygulama bir iletişim kutusu görüntüler ve Kullanıcı **Tamam**' a tıkladığında true, Kullanıcı **iptal** ' i veya **Kapat** düğmesine tıkladığında false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Kullanıcı görüntü düzenleyicisini çalıştırdığında Framework tarafından çağırılır. Varsayılan uygulama [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md) iletişim kutusunu görüntüler. `OnEditToolbarMenuImage`Özel bir görüntü Düzenleyicisi kullanmak için türetilmiş bir sınıfta geçersiz kılın.

## <a name="cmfctoolbarscustomizedialogoninitdialog"></a><a name="oninitdialog"></a>CMFCToolBarsCustomizeDialog:: OnInitDialog

Özellik sayfası başlatmasını artırmak için geçersiz kılar.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

[CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) metodunu çağırma sonucu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iletişim kutusunun geçerli ekran boyutuna uygun olduğundan emin olarak ve **Yardım** düğmesini iletişim kutusunun sol alt köşesine **Close** taşıyarak, [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog)temel sınıf uygulamasını genişletir.

## <a name="cmfctoolbarscustomizedialogoninittoolspage"></a><a name="oninittoolspage"></a>CMFCToolBarsCustomizeDialog:: Onınitaraçları sayfası

**Araçlar** sayfasının başlatılması için olduğu çerçeveden gelen bildirimi işler.

```
virtual void OnInitToolsPage();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz. Bu bildirimi işlemek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctoolbarscustomizedialogpostncdestroy"></a><a name="postncdestroy"></a>CMFCToolBarsCustomizeDialog::P ostNcDestroy

Pencere yok edildikten sonra Framework tarafından çağırılır.

```
virtual void PostNcDestroy();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CPropertySheet::PostNcDestroy` uygulamayı önceki moda geri yükleyerek temel sınıf uygulamasını genişletir.

[CMFCToolBarsCustomizeDialog:: Create](#create) yöntemi, uygulamayı özelleştirme görevlerini sınırlayan özel bir moda koyar.

## <a name="cmfctoolbarscustomizedialogremovebutton"></a><a name="removebutton"></a>CMFCToolBarsCustomizeDialog:: RemoveButton

Belirtilen kategoriden veya tüm kategorilerden belirtilen komut KIMLIĞIYLE düğmeyi kaldırır.

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
'ndaki Düğmenin kaldırılacağı kategori KIMLIĞINI belirtir.

*Uıımıdıd*<br/>
'ndaki Düğmenin komut KIMLIĞINI belirtir.

*lpszCategory*<br/>
'ndaki Düğmenin kaldırılacağı kategorinin adını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Kaldırılan düğmenin sıfır tabanlı dizini veya belirtilen komut KIMLIĞI belirtilen kategoride bulunmazsa-1. *UiCategoryId* -1 ise, dönüş değeri 0 ' dır.

### <a name="remarks"></a>Açıklamalar

Tüm kategorilerden bir düğmeyi kaldırmak için, bu yöntemin ilk tekrar yüklemesini çağırın ve *uiCategoryId* öğesini-1 olarak ayarlayın.

## <a name="cmfctoolbarscustomizedialogrenamecategory"></a><a name="renamecategory"></a>CMFCToolBarsCustomizeDialog:: RenameCategory

**Komutlar** sayfasındaki kategorilerin liste kutusunda bir kategoriyi yeniden adlandırır.

```
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,
    LPCTSTR lpszCategoryNew);
```

### <a name="parameters"></a>Parametreler

*lpszCategoryOld*<br/>
'ndaki Değiştirilecek kategori adı.

*lpszCategoryNew*<br/>
'ndaki Yeni kategori adı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Kategori adı benzersiz olmalıdır.

## <a name="cmfctoolbarscustomizedialogreplacebutton"></a><a name="replacebutton"></a>CMFCToolBarsCustomizeDialog:: ReplaceButton

**Komutlar** sayfasındaki komutların liste kutusunda bir araç çubuğu düğmesini değiştirir.

```cpp
void ReplaceButton(
    UINT uiCmd,
    const CMFCToolBarButton& button);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Değiştirilmekte olan düğmenin komutunu belirtir.

*Bu*<br/>
'ndaki **`const`** Eski düğmenin yerini alan araç çubuğu düğme nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

[CMFCToolBarsCustomizeDialog:: MenüEkle](#addmenu), [CMFCToolBarsCustomizeDialog:: AddMenuCommands](#addmenucommands)veya [CMFCToolBarsCustomizeDialog:: AddToolBar](#addtoolbar) **komutları** sayfasına bir komut eklerse, bu komut bir [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md) nesnesi (ya da tarafından eklenen bir alt menü içeren bir [cmfctoolbarmenubtan Class](../../mfc/reference/cmfctoolbarmenubutton-class.md) nesnesi `AddMenuCommands` ) biçimindedir. Framework Ayrıca komutları otomatik olarak eklemek için bu üç yöntemi çağırır. Bir komutun bunun yerine türetilmiş bir türle temsil olmasını istiyorsanız, `ReplaceButton` türetilmiş türün bir düğmesini çağırın ve geçirin.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında yönteminin nasıl kullanılacağını gösterir `ReplaceButton` `CMFCToolBarsCustomizeDialog` . Bu kod parçacığı, [Visual Studio Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]

## <a name="cmfctoolbarscustomizedialogsetusercategory"></a><a name="setusercategory"></a>CMFCToolBarsCustomizeDialog:: SetUserCategory

**Komutlar** sayfasında kategori listesindeki hangi kategorinin Kullanıcı kategorisi olduğunu belirtir. [CMFCToolBarsCustomizeDialog:: Create](#create)çağrısını yapmadan önce bu işlevi çağırmanız gerekir.

```
BOOL SetUserCategory(LPCTSTR lpszCategory);
```

### <a name="parameters"></a>Parametreler

*lpszCategory*<br/>
'ndaki Kategorinin adı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Kullanıcı kategorisi ayarı şu anda Framework tarafından kullanılmıyor.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CPropertySheet sınıfı](../../mfc/reference/cpropertysheet-class.md)
