---
title: "CMFCToolBarsCustomizeDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "28"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 69002f6b0b326b9ad4eb9a5aaa2162558ff368af
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfctoolbarscustomizedialog-class"></a>CMFCToolBarsCustomizeDialog sınıfı
Kalıcı olmayan sekme iletişim kutusu ( [CPropertySheet sınıfı](../../mfc/reference/cpropertysheet-class.md)) araç çubukları, menüler, klavye kısayolları, kullanıcı tanımlı Araçlar ve uygulamada görsel stil özelleştirmek için kullanıcı sağlar. Genellikle, bu iletişim kutusunu erişen seçerek kullanıcı **Özelleştir** gelen **Araçları** menüsü.  
  
 **Özelleştir** iletişim kutusunda altı sekme bulunur: **komutları**, **araç çubukları**, **Araçları**, **klavye**,  **Menü**, ve **seçenekleri**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCToolBarsCustomizeDialog : public CPropertySheet  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|Oluşturan bir `CMFCToolBarsCustomizeDialog` nesnesi.|  
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddButton](#addbutton)|Araç çubuğu düğmesi üzerinde komutlar listesine ekler **komutları** sayfası|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddMenu](#addmenu)|Bir menüyü kaynakları ve çağrıları yükler [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) menüye komutlar listesine eklemek için **komutları** sayfası.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)|Bir menüyü kaynakları ve çağrıları yükler [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) menüye komutlar listesine eklemek için **komutları** sayfası.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar)|Araç çubuğu kaynaklardan yükler. Ardından, her komut menü çağrılarında [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) komutların listesini düğmeyi eklemek için yöntemi **komutları** sayfasında belirtilen kategori altında.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::Create](#create)|Görüntüler **özelleştirme** iletişim kutusu.|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|Daha sonraki kullanımlar için ayrılmıştır.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|Etkinleştirir veya kullanarak yeni araç çubukları oluşturma devre dışı bırakır **Özelleştir** iletişim kutusu.|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|Sağlanan doldurur `CListBox` komutlar nesnesiyle **tüm komutları** kategorisi.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|Sağlanan doldurur `CComboBox` her komut kategorisinin adını nesnesiyle **Özelleştir** iletişim kutusu.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|Sağlanan doldurur `CListBox` her komut kategorisinin adını nesnesiyle **Özelleştir** iletişim kutusu.|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](#getcommandname)|Verilen komut kimliğiyle ilişkili adı alır.|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|Verilen metni etikete sahip sağlanan liste öğelerinin sayısını alır.|  
|[CMFCToolBarsCustomizeDialog::GetFlags](#getflags)|İletişim kutusu davranışını etkileyen bayrakları kümesini alır.|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|Böylece kullanıcı bir araç çubuğu düğmesi veya menü öğesi simgesi özelleştirebilirsiniz bir görüntü Düzenleyicisi'ni başlatır.|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](#oninitdialog)|Özellik sayfası başlatma büyütmek için geçersiz kılar. (Geçersiz kılmaları [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](#postncdestroy)|Pencere yok sonra çerçevesi tarafından çağrılır. (Geçersiz kılmaları `CPropertySheet::PostNcDestroy`.)|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|Belirtilen komut kimliği düğmesiyle belirtilen kategorisinden veya tüm kategorilerden kaldırır.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)|Bir kategori kategorilerini liste kutusunda üzerinde yeniden adlandırır **komutları** sekmesi.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|Düğme komutları listesinde yerini alır **komutları** yeni bir araç çubuğu düğmesi nesnesi sekmesi.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|Görüntülenecek kategori listesi, bir kategori ekler **komutları** sekmesi.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|Kullanıcı tanımlı Araçlar listesini geçerli olup olmadığını belirlemek için çerçevesi tarafından çağrılır.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|Kullanıcı tanımlı bir aracı özelliklerini değiştirdiğiniz zaman çerçevesi tarafından çağrılır.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|Bir eylem için belirtilen klavye kısayolu atanmış olup olmadığını belirler.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|Kullanıcı tanımlı bir aracı değiştirilebilir olup olmadığını belirler.|  
|`CMFCToolBarsCustomizeDialog::`[CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|Kullanıcı seçtiğinde çerçevesi tarafından çağrılır **Araçları** sekmesini istendi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Görüntülenecek **Özelleştir** iletişim kutusunda, oluşturmak bir `CMFCToolBarsCustomizeDialog` nesne ve çağrı [CMFCToolBarsCustomizeDialog::Create](#create) yöntemi.  
  
 Sırada **Özelleştir** iletişim kutusu active, uygulama özelleştirme görevlerini kullanıcıya sınırlar özel bir modda çalışır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCToolBarsCustomizeDialog` sınıfı. Örnek üzerinde bir araç çubuğu düğmesi komutların liste kutusunda değiştirme gösterir **komutları** sayfasında, kullanarak yeni araç çubukları oluşturma etkinleştirmek **Özelleştir** iletişim kutusu ve görüntü  **Özelleştirme** iletişim kutusu. Bu kod parçacığını parçası olan [IE gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 `CMFCToolBarsCustomizeDialog`   
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxToolBarsCustomizeDialog.h  
  
##  <a name="addbutton"></a>CMFCToolBarsCustomizeDialog::AddButton  
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
 [in]`uiCategoryId`  
 Ekle düğmesi için içine kategori Kimliğini belirtir.  
  
 [in]`button`  
 Ekle düğmesini belirtir.  
  
 [in]`iInsertBefore`  
 Düğme önce eklenen bir araç çubuğu düğmesi sıfır tabanlı dizini belirtir.  
  
 [in]`lpszCategory`  
 Ekle düğmesi için kategori dizeyi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 `AddButton` Yöntemi (örneğin, ID_FILE_MRU_FILE1) standart komut kimlikleri düğmeleri yoksayar, verilmez komutları (bkz [CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) ve kukla düğmeler.  
  
 Bu yöntem aynı türde yeni bir nesne oluşturur `button` (genellikle bir [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)) düğmesinin çalışma zamanı sınıfı kullanarak. Sonra çağırır [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) düğmesi, veri üyeleri kopyalamak ve kopyayı belirtilen kategoriye ekler.  
  
 Yeni düğmesini takıldığında, aldığı `OnAddToCustomizePage` bildirim.  
  
 Varsa `iInsertBefore` -1 ' dir düğmesi kategoriler listesine eklenir; Aksi halde belirtilen dizinle öğeyi önce eklenir.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `AddButton` yöntemi `CMFCToolBarsCustomizeDialog` sınıfı. Bu kod parçacığını parçası olan [kaydırıcı örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]  
  
##  <a name="addmenu"></a>CMFCToolBarsCustomizeDialog::AddMenu  
 Bir menüyü kaynakları ve çağrıları yükler [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands) menüye komutlar listesine eklemek için **komutları** sayfası.  
  
```  
BOOL AddMenu(UINT uiMenuResId);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiMenuResId`  
 Yüklemek için menü kaynak Kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Menü başarıyla eklendi Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrısında `AddMenuCommands`, `bPopup` olan `FALSE`. Sonuç olarak, bu yöntem, alt menüler komutlar listesine içeren menü öğelerini eklemez. Bu yöntem, komutların listesini menülerinde menü öğelerini ekleyin.  
  
##  <a name="addmenucommands"></a>CMFCToolBarsCustomizeDialog::AddMenuCommands  
 Öğeleri komutlar listesine ekler **komutları** belirtilen menüde tüm öğeleri göstermek için sayfa.  
  
```  
void AddMenuCommands(
    const CMenu* pMenu,  
    BOOL bPopup,  
    LPCTSTR lpszCategory=NULL,  
    LPCTSTR lpszMenuPath=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pMenu`  
 Eklenecek CMenu nesne için bir işaretçi.  
  
 [in]`bPopup`  
 Komutlar listesine açılan menü öğeleri eklenip eklenmeyeceğini belirler.  
  
 [in]`lpszCategory`  
 Kategori Ekle menüsü adı.  
  
 [in]`lpszMenuPath`  
 Komut içinde gösterildiğinde adına eklenen bir ön ek **tüm kategorileri** listesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `AddMenuCommands` Yöntemi döngüler tüm menü öğelerini üzerinden `pMenu`. Bu yöntem bir alt içermiyor her menü öğesi için oluşturur bir [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md) nesne ve çağrıları [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) bir araç menü öğesi ekleme yöntemi Düğme komutları listesine **komutları** sayfası. Ayırıcılar, bu işlemde göz ardı edilir.  
  
 Varsa `bPopup` olan `TRUE`, bir alt içeren her bir menü öğesi için bu yöntem oluşturur bir [CMFCToolBarMenuButton sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md) nesne ve çağırarak komutlar listesine ekler `AddButton`. Aksi halde alt menüler içeren menü öğelerini komutları listesinde görüntülenmez. Her iki durumda da, `AddMenuCommands` menü öğesi karşılaştığı bir menüyü kendisini bir işaretçi menüye geçirme yinelemeli olarak çağırır `pMenu` parametre ve menüye etiketi ekleyerek `lpszMenuPath`.  
  
##  <a name="addtoolbar"></a>CMFCToolBarsCustomizeDialog::AddToolBar  
 Araç çubuğu kaynaklardan yükler. Ardından, her komut menü çağrılarında [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) komutların listesini düğmeyi eklemek için yöntemi **komutları** sayfasında belirtilen kategori altında.  
  
```  
BOOL AddToolBar(
    UINT uiCategoryId,  
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,  
    UINT uiToolbarResId);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiCategoryId`  
 Araç çubuğuna eklemek için kategori kaynak Kimliğini belirtir.  
  
 [in]`uiToolbarResId`  
 Komutlarının komutlar listesine eklenen bir araç çubuğu kaynak Kimliğini belirtir.  
  
 [in]`lpszCategory`  
 Araç çubuğu eklenecek kategorisinin adını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `AddToolBar` yönteminde `CMFCToolBarsCustomizeDialog` sınıfı. Bu kod parçacığını parçası olan [Word paneli örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]  
  
### <a name="remarks"></a>Açıklamalar  
 Her komut temsil etmek için kullanılan denetim bir [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md) nesnesi. Araç çubuğu ekledikten sonra düğme türetilmiş bir tür denetimiyle çağırarak değiştirebilirsiniz [CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton).  
  
##  <a name="checktoolsvalidity"></a>CMFCToolBarsCustomizeDialog::CheckToolsValidity  
 Kullanıcı araçları listesi geçerliliğini doğrular.  
  
```  
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lstTools`  
 Denetlenecek kullanıcı tanımlı Araçlar listesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` kullanıcı tanımlı Araçlar listesi ise, aksi takdirde `FALSE`. Varsayılan uygulama her zaman döndürür `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework tarafından döndürülen kullanıcı tanımlı Araçlar temsil eden nesneler geçerliliğini doğrulamak için bu yöntemi çağırır [CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity).  
  
 Geçersiz kılma `CheckToolsValidity` bir sınıftaki yöntemi türetilen `CMFCToolBarsCustomizeDialog` kullanıcı iletişim kutusu kapanmadan önce kullanıcı araçlarını doğrulamak istiyorsanız. Bu yöntem döndürürse `FALSE` kullanıcı tıkladığında ya da **Kapat** iletişim kutusunu veya etiketli düğmesine sağ üst köşesindeki düğmesini **Kapat** iletişim kutusunun sağ alt köşedeki iletişim kutusu görüntüler **Araçları** kapanış yerine sekmesi. Bu yöntem döndürürse `FALSE` kullanıcı merkezden gitmek için bir sekme tıkladığında **Araçları** sekmesinde, gezinti oluşmaz. Doğrulama başarısız olmasına neden olan sorunu kullanıcıyı bilgilendirmek için uygun ileti kutusu görüntülemelidir.  
  
##  <a name="cmfctoolbarscustomizedialog"></a>CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog  
 Oluşturan bir `CMFCToolBarsCustomizeDialog` nesnesi.  
  
```  
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,  
    BOOL bAutoSetFromMenus = FALSE,  
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),  
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWndParentFrame`  
 Üst çerçeve işaretçisi. Bu parametre olmamalıdır `NULL`.  
  
 [in]`bAutoSetFromMenus`  
 Menü komutlarını tüm menülerden komutlar listesine eklemek belirten bir Boole değeri **komutları** sayfası. Bu parametre ise `TRUE`, menü komutlarını eklenir. Aksi halde menü komutlarını eklenmedi.  
  
 [in]`uiFlags`  
 İletişim kutusu davranışını etkileyen bayrak birleşimi. Bu parametre, bir veya daha fazla aşağıdaki değerlerden biri olabilir:  
  
- `AFX_CUSTOMIZE_MENU_SHADOWS`  
  
- `AFX_CUSTOMIZE_TEXT_LABELS`  
  
- `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
  
- `AFX_CUSTOMIZE_NOHELP`  
  
- `AFX_CUSTOMIZE_CONTEXT_HELP`  
  
- `AFX_CUSTOMIZE_NOTOOLS`  
  
- `AFX_CUSTOMIZE_MENUAMPERS`  
  
- `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
  
 [in]`plistCustomPages`  
 Bir listesi için bir işaretçi `CRuntimeClass` ek özel sayfalar belirtin nesneleri.  
  
### <a name="remarks"></a>Açıklamalar  
 `plistCustomPages` Parametre listesine başvuran `CRuntimeClass` ek özel sayfalar belirtin nesneleri. Oluşturucu kullanarak daha fazla sayfa iletişim kutusuna ekler [CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject) yöntemi. CustomPages örnek sayfalar ekler bir örnek için bkz: **Özelleştir** iletişim kutusu.  
  
 İçinde geçirebilirsiniz değerleri hakkında daha fazla bilgi için `uiFlags` parametresi bkz [CMFCToolBarsCustomizeDialog::GetFlags](#getflags).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCToolBarsCustomizeDialog` sınıfı. Bu kod parçacığını parçası olan [özel sayfaları örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]  
  
##  <a name="create"></a>CMFCToolBarsCustomizeDialog::Create  
 Görüntüler **özelleştirme** iletişim kutusu.  
  
```  
virtual BOOL Create();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`özelleştirme özellik sayfası başarıyla oluşturulduysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `Create` tam olarak yalnızca sınıfı başlatmanız sonra yöntemi.  
  
##  <a name="enableuserdefinedtoolbars"></a>CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars  
 Etkinleştirir veya kullanarak yeni araç çubukları oluşturma devre dışı bırakır **Özelleştir** iletişim kutusu.  
  
```  
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 `TRUE`Kullanıcı tanımlı araç çubukları etkinleştirmek için; `FALSE` araç çubuklarını devre dışı bırakmak için.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bEnable` olan `TRUE`, **yeni**, **yeniden adlandırma** ve **silmek** düğmeleri görüntülenir **araç çubukları** sayfası.  
  
 Varsayılan olarak, veya `bEnable` olan `FALSE`, bu düğmeleri görüntülenmez ve kullanıcının yeni araç çubukları tanımlayamazsınız.  
  
##  <a name="fillallcommandslist"></a>CMFCToolBarsCustomizeDialog::FillAllCommandsList  
 Sağlanan doldurur `CListBox` komutlar nesnesiyle **tüm komutları** kategorisi.  
  
```  
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`wndListOfCommands`  
 Bir başvuru `CListBox` doldurmak için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 **Tüm komutları** kategorisi tüm kategorileri komutlarını içerir. [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) yöntemi için sağlanan düğmesiyle ilişkili komutu ekler **tüm komutları** sizin için kategori.  
  
 Bu yöntem sağlanan içeriğini temizler `CListBox` komutları ile doldurma önce nesne **tüm komutları** kategorisi.  
  
 `CMFCMousePropertyPage` Sınıfı çift olay liste kutusunu doldurmak için bu yöntemi kullanır.  
  
##  <a name="fillcategoriescombobox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesComboBox  
 Sağlanan doldurur `CComboBox` her komut kategorisinin adını nesnesiyle **Özelleştir** iletişim kutusu.  
  
```  
void FillCategoriesComboBox(
    CComboBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`wndCategory`  
 Bir başvuru `CComboBox` doldurmak için nesne.  
  
 [in]`bAddEmpty`  
 Kategoriler komutları olmayan birleşik giriş kutusu eklenip eklenmeyeceğini belirten bir Boole değeri. Bu parametre ise `TRUE`, boş kategorileri açılan kutu eklenir. Aksi durumda, boş kategorileri eklenmedi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem benzer [CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox) yöntemi ile bu yöntem çalışır ancak bu bir `CComboBox` nesnesi.  
  
 Bu yöntem içeriğini temizlemez `CComboBox` onu doldurma önce nesnesi. Bu sayede **tüm komutları** Kategori açılan kutuya son öğedir.  
  
 Yeni komut kategorilerini kullanarak ekleyebileceğiniz [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) yöntemi. Var olan bir kategori adı kullanarak değiştirebilirsiniz [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) yöntemi.  
  
 `CMFCToolBarsKeyboardPropertyPage` Ve `CMFCKeyMapDialog` sınıfları klavye eşlemeleri kategorilere ayırmak için bu yöntemi kullanın.  
  
##  <a name="fillcategorieslistbox"></a>CMFCToolBarsCustomizeDialog::FillCategoriesListBox  
 Sağlanan doldurur `CListBox` her komut kategorisinin adını nesnesiyle **Özelleştir** iletişim kutusu.  
  
```  
void FillCategoriesListBox(
    CListBox& wndCategory,  
    BOOL bAddEmpty = TRUE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`wndCategory`  
 Bir başvuru `CListBox` doldurmak için nesne.  
  
 [in]`bAddEmpty`  
 Kategoriler komutları olmayan liste kutusu eklenip eklenmeyeceğini belirten bir Boole değeri. Bu parametre ise `TRUE`, boş kategorilerini liste kutusu eklenir. Aksi durumda, boş kategorileri eklenmedi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem benzer [CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox) yöntemi ile bu yöntem çalışır ancak bu bir `CListBox` nesnesi.  
  
 Bu yöntem içeriğini temizlemez `CListBox` onu doldurma önce nesnesi. Bu sayede **tüm komutları** kategori liste kutusunda son öğedir.  
  
 Yeni komut kategorilerini kullanarak ekleyebileceğiniz [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) yöntemi. Var olan bir kategori adı kullanarak değiştirebilirsiniz [CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory) yöntemi.  
  
 `CMFCToolBarsCommandsPropertyPage` Sınıfı, her komut kategoriyle ilişkili komutlarının listesini görüntülemek için bu yöntemi kullanır.  
  
##  <a name="getcommandname"></a>CMFCToolBarsCustomizeDialog::GetCommandName  
 Verilen komut kimliğiyle ilişkili adı alır.  
  
```  
LPCTSTR GetCommandName(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiCmd`  
 Almak üzere komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Verilen komut kimliği ile ilişkili adı veya `NULL` komutu mevcut değilse.  
  
##  <a name="getcountincategory"></a>CMFCToolBarsCustomizeDialog::GetCountInCategory  
 Verilen metni etikete sahip sağlanan liste öğelerinin sayısını alır.  
  
```  
int GetCountInCategory(
    LPCTSTR lpszItemName,  
    const CObList& lstCommands) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszItemName`  
 Eşleştirilecek metin etiketi.  
  
 [in]`lstCommands`  
 Bir başvuru içeren bir liste `CMFCToolBarButton` nesneleri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sağlanan öğelerin sayısı, metin etiketi eşittir listesinde `lpszItemName`.  
  
### <a name="remarks"></a>Açıklamalar  
 Sağlanan nesne listesini her bir öğe türü olmalıdır `CMFCToolBarButton`. Bu yöntem karşılaştırır `lpszItemName` ile [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) veri üyesi.  
  
##  <a name="getflags"></a>CMFCToolBarsCustomizeDialog::GetFlags  
 İletişim kutusu davranışını etkileyen bayrakları kümesini alır.  
  
```  
UINT GetFlags() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim kutusu davranışını etkileyen bayrakları kümesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem değerini alır `uiFlags` oluşturucuya geçirilen parametre. Dönüş değeri, bir veya daha fazla aşağıdaki değerlerden biri olabilir:  
  
 `AFX_CUSTOMIZE_MENU_SHADOWS`  
 Menü gölge görünümünü belirtmesini sağlar.  
  
 `AFX_CUSTOMIZE_TEXT_LABELS`  
 Metin etiketleri araç çubuğu düğmesi görüntüleri altında mı gösterileceğini belirtmesini sağlar.  
  
 `AFX_CUSTOMIZE_MENU_ANIMATIONS`  
 Menü animasyon stili belirtmesini sağlar.  
  
 `AFX_CUSTOMIZE_NOHELP`  
 Yardım düğmesi özelleştirme iletişim kutusundan kaldırır.  
  
 `AFX_CUSTOMIZE_CONTEXT_HELP`  
 Etkinleştirir `WS_EX_CONTEXTHELP` görsel stili.  
  
 `AFX_CUSTOMIZE_NOTOOLS`  
 Kaldırır **Araçları** özelleştirme iletişim kutusundan sayfası. Bu bayrak, uygulamanız kullanıyorsa geçerlidir `CUserToolsManager` sınıfı.  
  
 `AFX_CUSTOMIZE_MENUAMPERS`  
 Ve işareti içerecek şekilde düğme resim yazıları sağlar (  **&** ) karakter.  
  
 `AFX_CUSTOMIZE_NO_LARGE_ICONS`  
 Kaldırır **büyük simgeler** özelleştirme iletişim kutusundan seçeneği.  
  
 Hakkında daha fazla bilgi için `WS_EX_CONTEXTHELP` görsel stil bkz [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).  
  
##  <a name="onafterchangetool"></a>CMFCToolBarsCustomizeDialog::OnAfterChangeTool  
 Hemen gerçekleştikten sonra kullanıcı aracında bir değişikliğe yanıt verir.  
  
```  
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>Parametreler  
 [içinde out]`pSelTool`  
 Değiştirildi kullanıcı aracı nesnesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı bir kullanıcı tarafından tanımlanan aracı özelliklerini değiştirdiğinde bu yöntem çerçevesi tarafından çağrılır. Varsayılan uygulama hiçbir şey yapmaz. Türetilen bir sınıfta bu yöntemin üzerine `CMFCToolBarsCustomizeDialog` kullanıcı aracı değişiklik gerçekleştikten sonra işlem yapmak için.  
  
##  <a name="onassignkey"></a>CMFCToolBarsCustomizeDialog::OnAssignKey  
 Bir kullanıcının onları tanımlar gibi klavye kısayolları doğrular.  
  
```  
virtual BOOL OnAssignKey(ACCEL* pAccel);
```  
  
### <a name="parameters"></a>Parametreler  
 [içinde out]`pAccel`  
 İşaretçi olarak ifade edilen önerilen klavye atama için bir [HIZLANDIRMA](http://msdn.microsoft.com/library/windows/desktop/ms646340) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`anahtar atanabilir, veya `FALSE` anahtar atanmışsa. Varsayılan uygulama her zaman döndürür `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı yeni bir klavye kısayolu atar ya da kullanıcı olarak klavye kısayolları doğrulamak için bunları tanımlar ek işleme gerçekleştirmek için bir türetilmiş sınıfta bu yöntemi geçersiz kılın. Bir kısayol atanmasına engel olmak için iade `FALSE`. Ayrıca bir ileti kutusu görüntüleme veya aksi halde neden klavye kısayolu reddedilme nedeni kullanıcı bildirin.  
  
##  <a name="onbeforechangetool"></a>CMFCToolBarsCustomizeDialog::OnBeforeChangeTool  
 Kullanıcı hakkında bir değişikliği uygulamak için olduğunda özel bir kullanıcı aracı için bir değişiklik olduğunda işleme gerçekleştirir.  
  
```  
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```  
  
### <a name="parameters"></a>Parametreler  
 [içinde out]`pSelTool`  
 Yaklaşık değiştirilmesi gereken kullanıcı aracı nesnesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı tanımlı bir aracı özelliklerini olduğunda hakkında değiştirmek için bu yöntem çerçevesi tarafından çağrılır. Varsayılan uygulama hiçbir şey yapmaz. Geçersiz kılma `OnBeforeChangeTool` bir sınıftaki yöntemi türetilen `CMFCToolBarsCustomizeDialog` kaynakları serbest bırakma gibi bir kullanıcı aracı değişiklik gerçekleşmeden önce işleme gerçekleştirmek istiyorsanız, `pSelTool` kullanır.  
  
##  <a name="onedittoolbarmenuimage"></a>CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage  
 Böylece kullanıcı bir araç çubuğu düğmesi veya menü öğesi simgesi özelleştirebilirsiniz bir görüntü Düzenleyicisi'ni başlatır.  
  
```  
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,  
    CBitmap& bitmap,  
    int nBitsPerPixel);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWndParent`  
 Üst pencere için bir işaretçi.  
  
 [in]`bitmap`  
 Düzenlenecek bir bit eşlem nesneye başvuru.  
  
 [in]`nBitsPerPixel`  
 Bit / piksel çözünürlüğü bitmap.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bir değişiklik kaydedilen; Aksi takdirde `FALSE`. Varsayılan uygulama döndürür ve bir iletişim kutusu görüntüler `TRUE` kullanıcı tıklarsa **Tamam**, veya `FALSE` kullanıcı tıklarsa **iptal** veya **Kapat** düğme.  
  
### <a name="remarks"></a>Açıklamalar  
 Görüntü Düzenleyicisi kullanıcı çalıştırdığında bu yöntem çerçevesi tarafından çağrılır. Varsayılan uygulama görüntüler [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md) iletişim kutusu. Geçersiz kılma `OnEditToolbarMenuImage` özel görüntü Düzenleyicisi kullanmak için bir türetilmiş sınıfta.  
  
##  <a name="oninitdialog"></a>CMFCToolBarsCustomizeDialog::OnInitDialog  
 Özellik sayfası başlatma büyütmek için geçersiz kılar.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arama sonucu [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) yöntemi.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog), görüntüleyerek **Kapat** düğmesi, iletişim kutusu geçerli ekran boyutu uygun emin olma ve taşıma **Yardımcı** iletişim kutusunun sol alt köşesine düğmesi.  
  
##  <a name="oninittoolspage"></a>CMFCToolBarsCustomizeDialog::OnInitToolsPage  
 Bildirim çerçeveden işler, **Araçları** sayfasıdır hakkında başlatılacak.  
  
```  
virtual void OnInitToolsPage();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama hiçbir şey yapmaz. Bu bildirim işlemek için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="postncdestroy"></a>CMFCToolBarsCustomizeDialog::PostNcDestroy  
 Pencere yok sonra çerçevesi tarafından çağrılır.  
  
```  
virtual void PostNcDestroy();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği `CPropertySheet::PostNcDestroy`, uygulamanın önceki moduna geri tarafından.  
  
 [CMFCToolBarsCustomizeDialog::Create](#create) yöntemi bir özel modda özelleştirme görevlerini kullanıcıya sınırlar uygulama koyar.  
  
##  <a name="removebutton"></a>CMFCToolBarsCustomizeDialog::RemoveButton  
 Belirtilen komut kimliği düğmesiyle belirtilen kategorisinden veya tüm kategorilerden kaldırır.  
  
```  
int RemoveButton(
    UINT uiCategoryId,  
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,  
    UINT uiCmdId);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiCategoryId`  
 Düğme kaldırılacağı kategori Kimliğini belirtir.  
  
 [in]`uiCmdId`  
 Düğme komut Kimliğini belirtir.  
  
 [in]`lpszCategory`  
 Düğme kaldırılacağı kategorisinin adını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaldırılan düğmesini ya da belirtilen komut Kimliğini belirtilen kategoride bulunamadı -1 sıfır tabanlı dizini. Varsa `uiCategoryId` -1 ' dir dönüş değeri 0'dır.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm kategorilerden düğme kaldırmak için bu yöntemi ve kümesi ilk aşırı yüklemesini çağırın `uiCategoryId` -1.  
  
##  <a name="renamecategory"></a>CMFCToolBarsCustomizeDialog::RenameCategory  
 Bir kategori kategorilerini liste kutusunda üzerinde yeniden adlandırır **komutları** sayfası.  
  
```  
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,  
    LPCTSTR lpszCategoryNew);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszCategoryOld`  
 Değiştirmek için kategori adı.  
  
 [in]`lpszCategoryNew`  
 Yeni kategori adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kategori adı benzersiz olmalıdır.  
  
##  <a name="replacebutton"></a>CMFCToolBarsCustomizeDialog::ReplaceButton  
 Araç çubuğu düğmesi komutların liste kutusunda yerini alır **komutları** sayfası.  
  
```  
void ReplaceButton(
    UINT uiCmd,  
    const CMFCToolBarButton& button);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiCmd`  
 Değiştirilmesi gereken komut düğmesinin belirtir.  
  
 [in]`button`  
 A `const` eski düğmesi değiştirir araç çubuğu düğmesi nesnesine başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman [CMFCToolBarsCustomizeDialog::AddMenu](#addmenu), [CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands), veya [CMFCToolBarsCustomizeDialog::AddToolBar](#addtoolbar) ekler bir komut **komutları** sayfasında komutu biçiminde olduğunu bir [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md) nesne (veya bir [CMFCToolBarMenuButton sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md) menüsüne nesnesi tarafından eklenen bir alt içeren öğesini `AddMenuCommands`). Framework de komutları otomatik olarak eklemek için bu üç yöntemi çağırır. Bir komut tarafından türetilmiş bir tür yerine temsil etmek istiyorsanız, çağrı `ReplaceButton` ve türetilen türün bir düğmesini geçirin.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `ReplaceButton` yönteminde `CMFCToolBarsCustomizeDialog` sınıfı. Bu kod parçacığını parçası olan [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]  
  
##  <a name="setusercategory"></a>CMFCToolBarsCustomizeDialog::SetUserCategory  
 Kategori listesi, hangi kategorisinde belirtir **komutları** sayfasıdır kullanıcı kategorisi. Arama yapmadan önce bu işlevini çağırmanız gerekir [CMFCToolBarsCustomizeDialog::Create](#create).  
  
```  
BOOL SetUserCategory(LPCTSTR lpszCategory);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszCategory`  
 Kategori adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı kategorisi ayarı çerçevesi tarafından şu anda kullanılmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CPropertySheet sınıfı](../../mfc/reference/cpropertysheet-class.md)
