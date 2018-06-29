---
title: CPropertySheet sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPropertySheet
- AFXDLGS/CPropertySheet
- AFXDLGS/CPropertySheet::CPropertySheet
- AFXDLGS/CPropertySheet::AddPage
- AFXDLGS/CPropertySheet::Construct
- AFXDLGS/CPropertySheet::Create
- AFXDLGS/CPropertySheet::DoModal
- AFXDLGS/CPropertySheet::EnableStackedTabs
- AFXDLGS/CPropertySheet::EndDialog
- AFXDLGS/CPropertySheet::GetActiveIndex
- AFXDLGS/CPropertySheet::GetActivePage
- AFXDLGS/CPropertySheet::GetPage
- AFXDLGS/CPropertySheet::GetPageCount
- AFXDLGS/CPropertySheet::GetPageIndex
- AFXDLGS/CPropertySheet::GetTabControl
- AFXDLGS/CPropertySheet::MapDialogRect
- AFXDLGS/CPropertySheet::OnInitDialog
- AFXDLGS/CPropertySheet::PressButton
- AFXDLGS/CPropertySheet::RemovePage
- AFXDLGS/CPropertySheet::SetActivePage
- AFXDLGS/CPropertySheet::SetFinishText
- AFXDLGS/CPropertySheet::SetTitle
- AFXDLGS/CPropertySheet::SetWizardButtons
- AFXDLGS/CPropertySheet::SetWizardMode
- AFXDLGS/CPropertySheet::m_psh
dev_langs:
- C++
helpviewer_keywords:
- CPropertySheet [MFC], CPropertySheet
- CPropertySheet [MFC], AddPage
- CPropertySheet [MFC], Construct
- CPropertySheet [MFC], Create
- CPropertySheet [MFC], DoModal
- CPropertySheet [MFC], EnableStackedTabs
- CPropertySheet [MFC], EndDialog
- CPropertySheet [MFC], GetActiveIndex
- CPropertySheet [MFC], GetActivePage
- CPropertySheet [MFC], GetPage
- CPropertySheet [MFC], GetPageCount
- CPropertySheet [MFC], GetPageIndex
- CPropertySheet [MFC], GetTabControl
- CPropertySheet [MFC], MapDialogRect
- CPropertySheet [MFC], OnInitDialog
- CPropertySheet [MFC], PressButton
- CPropertySheet [MFC], RemovePage
- CPropertySheet [MFC], SetActivePage
- CPropertySheet [MFC], SetFinishText
- CPropertySheet [MFC], SetTitle
- CPropertySheet [MFC], SetWizardButtons
- CPropertySheet [MFC], SetWizardMode
- CPropertySheet [MFC], m_psh
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f194b8119cb080c9a3b29e63781595ada0027ef
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079779"
---
# <a name="cpropertysheet-class"></a>CPropertySheet sınıfı
Özellik sayfaları, olarak da bilinen sekme iletişim kutuları temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPropertySheet : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPropertySheet::CPropertySheet](#cpropertysheet)|Oluşturan bir `CPropertySheet` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPropertySheet::AddPage](#addpage)|Bir sayfa özellik sayfasına ekler.|  
|[CPropertySheet::Construct](#construct)|Oluşturan bir `CPropertySheet` nesnesi.|  
|[CPropertySheet::Create](#create)|Kalıcı olmayan özellik sayfası görüntülenir.|  
|[CPropertySheet::DoModal](#domodal)|Kalıcı özellik sayfasını görüntüler.|  
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|Özellik sayfasını Yığılmış veya kaydırma sekmeleri kullanıp kullanmadığını belirtir.|  
|[CPropertySheet::EndDialog](#enddialog)|Özellik sayfasını sonlandırır.|  
|[CPropertySheet::GetActiveIndex](#getactiveindex)|Etkin sayfa özellik sayfasının dizinini alır.|  
|[CPropertySheet::GetActivePage](#getactivepage)|Etkin sayfa nesnesini döndürür.|  
|[CPropertySheet::GetPage](#getpage)|Belirtilen sayfa için bir işaretçi alır.|  
|[CPropertySheet::GetPageCount](#getpagecount)|Özellik sayfasında sayfa sayısını alır.|  
|[CPropertySheet::GetPageIndex](#getpageindex)|Belirtilen sayfa özellik sayfasının dizinini alır.|  
|[CPropertySheet::GetTabControl](#gettabcontrol)|Sekme denetimi için bir işaretçi alır.|  
|[CPropertySheet::MapDialogRect](#mapdialogrect)|İletişim kutusu birimleri dikdörtgenin ekran birimlerine dönüştürür.|  
|[CPropertySheet::OnInitDialog](#oninitdialog)|Özellik sayfası başlatma büyütmek için geçersiz kılın.|  
|[CPropertySheet::PressButton](#pressbutton)|Özellik sayfasında belirtilen düğmesi seçimi benzetimini yapar.|  
|[CPropertySheet::RemovePage](#removepage)|Bir sayfa özellik sayfasından kaldırır.|  
|[CPropertySheet::SetActivePage](#setactivepage)|Etkin sayfa nesnesi programlı olarak ayarlar.|  
|[CPropertySheet::SetFinishText](#setfinishtext)|Metin için Son düğmesini ayarlar.|  
|[CPropertySheet::SetTitle](#settitle)|Özellik sayfasını resim yazısını ayarlar.|  
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|Sihirbaz düğmeler sağlar.|  
|[CPropertySheet::SetWizardMode](#setwizardmode)|Sihirbaz modu sağlar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPropertySheet::m_psh](#m_psh)|Windows [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) yapısı. Temel özellik sayfası parametreleri erişim sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir özellik sayfası oluşan bir `CPropertySheet` nesne ve bir veya daha fazla [CPropertyPage](../../mfc/reference/cpropertypage-class.md) nesneleri. Çerçeve bir özellik sayfası bir dizi sekmesini dizinlerini ve şu anda seçili sayfasını içeren bir alan içeren bir pencere olarak görüntüler. Kullanıcı uygun sekmesini kullanarak belirli bir sayfaya gider.  
  
 `CPropertySheet` Genişletilmiş için destek sağlar [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) yapısı içinde sunulan [!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)] ve Windows NT 2000. Yapı ek bayrakları ve "Filigran" arka plan bit eşlemi kullanma desteği üyeler içeriyor.  
  
 Bu yeni görüntüleri otomatik olarak özellik sayfası nesnesinde göstermek için çağrısı bit eşlem ve palet görüntüler için geçerli değerler geçirin. [CPropertySheet::Construct](#construct) veya [CPropertySheet::CPropertySheet](#cpropertysheet).  
  
 Olsa bile `CPropertySheet` türetilmedi [CDialog](../../mfc/reference/cdialog-class.md), yöneten bir `CPropertySheet` nesnesidir yönetme gibi bir `CDialog` nesnesi. Örneğin, iki aşamalı yapımı bir özellik sayfası oluşturulmasını gerektirir: Oluşturucusu arayın ve ardından arama [DoModal](#domodal) kalıcı özellik sayfası için veya [oluşturma](#create) kalıcı olmayan özellik sayfası için. `CPropertySheet` Oluşturucular iki tür vardır: [CPropertySheet::Construct](#construct) ve [CPropertySheet::CPropertySheet](#cpropertysheet).  
  
 Oluşturduğunuzda bir `CPropertySheet` nesnesi, bazı [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) gerçekleşmesi ilk fırsat özel durum neden olabilir. Bu özellik sayfası stil sayfası oluşturulmadan önce değiştirmeye sistemden sonuçlanır. Bu özel durumun önlemek için oluşturduğunuzda aşağıdaki stiller belirlediğinizden emin olun, `CPropertySheet`:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 Aşağıdaki stiller isteğe bağlıdır ve ilk fırsat özel durum neden:  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 Diğer `Window Styles` yasaklanmış olduğuna ve bunların etkinleştirmemelisiniz.  
  
 Arasında veri değişimi bir `CPropertySheet` nesne ve dış nesne ile veri değişimi için benzer bir `CDialog` nesnesi. Önemli bir özellik sayfası ayarları genellikle üye değişkenleri olduğunu farktır `CPropertyPage` nesneleri yerine, `CPropertySheet` nesnesinin kendisi.  
  
 Tab iletişim kutusunda, kullanıcı cihazını ayarlamaya veya bülten oluşturma gibi bir işlem adımları boyunca rehberlik özellik sayfaları dizisi ile bir özellik sayfasından oluşan bir sihirbaz denilen türü oluşturabilirsiniz. Sihirbaz türü sekme iletişim kutusunda, özellik sayfaları sekmeleri gerekmez ve aynı anda yalnızca bir özellik sayfası görünür. Ayrıca, sahip olmak yerine **Tamam** ve **şimdi Uygula** düğmesi, bir sihirbaz türü sekme iletişim kutusu var. bir **geri** düğmesi, bir **sonraki** veya  **Son** düğmesi, bir **iptal** düğmesi ve **yardımcı** düğmesi.  
  
 Sihirbaz türü iletişim kutusu oluşturmak için çağrı ancak bir standart özellik sayfası oluşturmak için izlersiniz adımlarının aynısını izleyin [SetWizardMode](#setwizardmode) çağırmadan önce [DoModal](#domodal). Sihirbaz düğmeleri etkinleştirmek için arama [SetWizardButtons](#setwizardbuttons), kendi işlev ve görünümünü özelleştirmek için bayrakları kullanıyor. Etkinleştirmek için **son** düğmesini tıklatın, çağrı [SetFinishText](#setfinishtext) sonra kullanıcı sihirbazın son sayfasında eylem.  
  
 Nasıl kullanılacağı hakkında daha fazla bilgi için `CPropertySheet` nesneleri başlıklı makaleye bakın [özellik bölümleri ve özellik sayfaları](../../mfc/property-sheets-and-property-pages-in-mfc.md). Ayrıca, Bilgi Bankası makalesi Q146916 bkz: nasıl yapılır: standart düğmeleriyle engelleyici olmayan CPropertySheet oluşturun ve Q300606 makale: nasıl yapılır: yeniden boyutlandırılabilir MFC özellik sayfası tasarlayın.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPropertySheet`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdlgs.h  
  
##  <a name="addpage"></a>  CPropertySheet::AddPage  
 En sağdaki sekme sağlanan sayfasıyla özellik sayfasında ekler.  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parametreler  
 *fsayfa*  
 Özellik sayfasına eklenecek sayfasına noktaları. Olamaz **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik sayfasına görünmesini istediğiniz soldan sağa sırayla sayfa ekleyin.  
  
 `AddPage` ekler [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) nesnesini `CPropertySheet` nesne sayfaların listesini kullanıcının ancak aslında sayfa için pencere oluşturmaz. Bu sayfa kullanıcının seçtiği kadar framework sayfa için pencere oluşturulmasını erteler.  
  
 Özellik sayfası kullanılarak eklediğinizde `AddPage`, `CPropertySheet` üst `CPropertyPage`. Özellik sayfası özellik sayfasına erişmek için çağrı [CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent).  
  
 Çağrılacak özellik sayfası penceresi oluşturma kadar beklenecek gerekli değil `AddPage`. Genellikle, çağıracaksınız `AddPage` çağırmadan önce [DoModal](#domodal) veya [oluşturma](#create).  
  
 Çağırırsanız `AddPage` özellik sayfası görüntüleme sonra sekme satırına yeni eklenen sayfa yansıtır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#129](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]  
  
##  <a name="construct"></a>  CPropertySheet::Construct  
 Oluşturan bir `CPropertySheet` nesnesi.  
  
```  
void Construct(
    UINT nIDCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
void Construct(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
void Construct(
    UINT nIDCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);

 
void Construct(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDCaption*  
 Özellik sayfasını kullanılacak resim yazısını kimliği.  
  
 *pParentWnd*  
 Özellik sayfasının üst pencere işaretçi. Varsa **NULL**, uygulamanın ana penceresi üst pencere olacaktır.  
  
 *iSelectPage*  
 En üstte başlangıçta olacaktır sayfanın dizini. Varsayılan sayfasına eklenen ilk sayfa verilmiştir.  
  
 *pszCaption*  
 Özellik sayfasını kullanılacak resim yazısını içeren bir dize işaretçi. Olamaz **NULL**.  
  
 *hbmWatermark*  
 Özellik sayfası Filigran bit eşlem işleyin.  
  
 *hpalWatermark*  
 Filigran bit eşlem ve/veya üstbilgi bit eşlem paletini işleyin.  
  
 *hbmHeader*  
 Özellik sayfasının başlığı bit eşlem işleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıf oluşturucuları birini değil zaten çağrılmış bu üye işlevini çağırın. Örneğin, arama `Construct` ne zaman bildirme veya dizileri tahsis `CPropertySheet` nesneleri. Diziler söz konusu olduğunda, çağırmalısınız `Construct` dizisindeki her üye için.  
  
 Özellik sayfasını görüntülemek için arama [DoModal](#domodal) veya [oluşturma](#create). İlk parametre içinde yer alan dize özellik sayfası için başlık çubuğunda yerleştirilir.  
  
 Üçüncü veya dördüncü prototipleri kullanırsanız, filigran ve/veya üstbilgi görüntüleri otomatik olarak görüntüleyebilirsiniz `Construct`, yukarıda listelenen ve geçerli değerleri geçirmek *hbmWatermark*, *hpalWatermark* , ve/veya *hbmHeader* parametreleri.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, altında gösterir, koşulda çağırırdı `Construct`.  
  
 [!code-cpp[NVC_MFCDocView#130](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]  
  
##  <a name="cpropertysheet"></a>  CPropertySheet::CPropertySheet  
 Oluşturan bir `CPropertySheet` nesnesi.  
  
```  
CPropertySheet();

 
explicit CPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
explicit CPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
CPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);

 
CPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDCaption*  
 Özellik sayfasını kullanılacak resim yazısını kimliği.  
  
 *pParentWnd*  
 Özellik sayfasının üst pencere noktalarına. Varsa **NULL**, uygulamanın ana penceresi üst pencere olacaktır.  
  
 *iSelectPage*  
 En üstte başlangıçta olacaktır sayfanın dizini. Varsayılan sayfasına eklenen ilk sayfa verilmiştir.  
  
 *pszCaption*  
 Özellik sayfasını kullanılacak resim yazısını içeren bir dize noktalarına. Olamaz **NULL**.  
  
 *hbmWatermark*  
 Arka plan bit eşlemi özellik sayfası için bir tanıtıcı.  
  
 *hpalWatermark*  
 Filigran bit eşlem ve/veya üstbilgi bit eşlem paletini işleyici.  
  
 *hbmHeader*  
 Özellik sayfasının başlığı bit eşlem için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik sayfasını görüntülemek için arama [DoModal](#domodal) veya [oluşturma](#create). İlk parametre içinde yer alan dize özellik sayfası için başlık çubuğunda yerleştirilir.  
  
 Birden çok parametre (örneğin, bir dizi kullanıyorsanız) varsa, [oluşturmak](#construct) yerine `CPropertySheet`.  
  
 Üçüncü veya dördüncü prototipleri kullanırsanız, filigran ve/veya üstbilgi görüntüleri otomatik olarak görüntüleyebilirsiniz `CPropertySheet`, yukarıdaki ve geçerli değerleri geçirmek *hbmWatermark*, *hpalWatermark*, ve / veya *hbmHeader* parametreleri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#131](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]  
  
##  <a name="create"></a>  CPropertySheet::Create  
 Kalıcı olmayan özellik sayfası görüntülenir.  
  
```  
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)-1,
    DWORD dwExStyle = 0);  
```  
  
### <a name="parameters"></a>Parametreler  
 *pParentWnd*  
 Üst pencere noktalarına. Varsa **NULL**, üst Masaüstü öğedir.  
  
 *dwStyle*  
 Pencere stilleri özellik sayfası için. Kullanılabilir stiller tam bir listesi için bkz: [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 *dwExStyle*  
 Genişletilmiş pencere stilleri özellik sayfası için. Kullanılabilir stiller tam bir listesi için bkz: [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özellik sayfasını başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `Create` oluşturucusu içinde olabilir veya oluşturucusu çağrıldıktan sonra çağırabilirsiniz.  
  
 Olarak -1 geçirerek ifade varsayılan stilini *dwStyle*, aslında **WS_SYSMENU&#124;**`WS_POPUP`**&#124;ws_captıon&#124;DS_MODALFRAME&#124;DS_ CONTEXTHELP&#124;ws_vısıble**. Varsayılan pencere stili, 0 olarak geçirerek ifade Genişletilmiş *dwExStyle*, aslında **WS_EX_DLGMODALFRAME**.  
  
 `Create` Hemen özellik sayfasını oluşturduktan sonra üye işlevi döndürür. Özellik sayfasını yok etmek için çağrı [CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow).  
  
 Kalıcı olmayan özellik sayfaları çağrısıyla görüntülenen `Create` kalıcı özellik sayfaları gibi Tamam, iptal, şimdi Uygula ve Yardım düğmeleri sahip değil. İstenen düğmeleri kullanıcı tarafından oluşturulmuş olması gerekir.  
  
 Kalıcı özellik sayfasını görüntülemek için arama [DoModal](#domodal) yerine.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]  
  
##  <a name="domodal"></a>  CPropertySheet::DoModal  
 Kalıcı özellik sayfasını görüntüler.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `IDOK` veya `IDCANCEL` işlevi başarılı; Aksi halde 0 veya -1 olursa. Sihirbaz özellik sayfasını kurulduğunda varsa (bkz [SetWizardMode](#setwizardmode)), `DoModal` döndürür `ID_WIZFINISH` veya `IDCANCEL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri, özellik sayfasında kapalı denetim Kimliğine karşılık gelir. Bu işlev döndükten sonra özellik sayfasını ve tüm sayfalar için karşılık gelen windows yok edildi. Nesnelerinin kendilerini var olmaya devam edecek. Genellikle, verileri alacak [CPropertyPage](../../mfc/reference/cpropertypage-class.md) sonra nesneleri `DoModal` döndürür `IDOK`.  
  
 Kalıcı olmayan özellik sayfasını görüntülemek için arama [oluşturma](#create) yerine.  
  
 Özellik sayfasında karşılık gelen iletişim kaynaktan oluşturulduğunda, ilk fırsat özel durum neden olabilir. Bu sayfa oluşturulmadan önce gerekli Stili iletişim kutusu kaynağı stilini değiştirme özellik sayfasından sonuçlanır. Kaynaklar genellikle salt okunur olduğundan, bu bir özel durum neden olur. Sistem özel durumu işler ve değiştirilen kaynak bir kopyasını oluşturur. Bu nedenle ilk fırsat özel durum yoksayılabilir.  
  
> [!NOTE]
>  Zaman uyumsuz özel durum işleme modeli ile derleme, bu özel durum işletim sistemi tarafından ele alınması gerekir. Özel durum işleme modelleri hakkında daha fazla bilgi için bkz: [/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md). Bu durumda, çağrıları kaydırılacak `CPropertySheet::DoModal` C++ try-catch bloğu ile yakalama işleme tüm özel durumları, örneğin, `catch (...)`. Bu bloğu işletim sistemi ve beklenmeyen davranışlara neden için amaçlanan özel durum işleme. Ancak, erişim ihlali özel durumu ile işletim sistemine geçirildiği işleme belirli özel durum türleri veya yapılandırılmış özel durum işleme ile C++ özel durum güvenli bir şekilde kullanabilirsiniz.  
  
 Bu ilk fırsat özel durum oluşturulmasını önlemek için el ile özellik sayfasını doğru olduğunu garanti edebilir [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles). Bir özellik sayfası için aşağıdaki stiller ayarlamanız gerekir:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 Aşağıdaki isteğe bağlı stilleri ilk fırsat özel durum neden olmadan kullanabilirsiniz:  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 Özellik sayfaları ile uyumlu olmadıkları için diğer tüm Windows stilleri devre dışı bırakın. Bu öneriler genişletilmiş stilleri için geçerli değildir. Bu standart stiller uygun şekilde ayarlama, özellik sayfasını değiştirilecek yok ve ilk fırsat özel durum oluşturmadan kaçının güvence altına.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertySheet::AddPage](#addpage).  
  
##  <a name="enablestackedtabs"></a>  CPropertySheet::EnableStackedTabs  
 Bir özellik sayfası sekmeleri satırlarını yığın gösterir.  
  
```  
void EnableStackedTabs(BOOL bStacked);
```  
  
### <a name="parameters"></a>Parametreler  
 *bStacked*  
 Yığılmış sekmeleri özellik sayfasında etkinleştirilip etkinleştirilmediğini gösterir. Etiketlerin Yığılmış satırları ayarlayarak devre dışı *bStacked* için **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özellik sayfası tek bir satırda özellik sayfasının genişliği sığmayacak kadar çok daha fazla sekme varsa, varsayılan olarak, birden çok satır sekmeleri yığın. Kaydırma sekmeleri yerine yığın sekmeleri kullanmak için arama `EnableStackedTabs` ile *bStacked* kümesine **FALSE** çağırmadan önce [DoModal](#domodal) veya [Oluştur](#create).  
  
 Çağırmalısınız `EnableStackedTabs` oluştururken kalıcı bir veya kalıcı olmayan özellik sayfası. Bu stil birleştirmek için bir `CPropertySheet`-türetilmiş sınıf, WM_CREATE için ileti işleyicisi yazma. Geçersiz kılınan sürümünde [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate), çağrı **EnableStackedTabs (FALSE)** temel sınıf uygulamasını çağırmadan önce.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]  
  
##  <a name="enddialog"></a>  CPropertySheet::EndDialog  
 Özellik sayfasını sonlandırır.  
  
```  
void EndDialog(int nEndID);
```  
  
### <a name="parameters"></a>Parametreler  
 *nEndID*  
 Özellik sayfasını dönüş değeri olarak kullanılacak tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Tamam, İptal'i veya Kapat düğmesine basıldığında bu üye işlev çerçevesi tarafından çağrılır. Çağrı, bir olay oluşursa, bu üye işlevi özellik sayfasını kapatmalısınız.  
  
 Bu üye işlevi yalnızca bir modal iletişim kutusu ile kullanılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertySheet::PressButton](#pressbutton).  
  
##  <a name="getactiveindex"></a>  CPropertySheet::GetActiveIndex  
 Özellik sayfası pencerenin etkin sayfa dizin numarasını alır ve parametre olarak döndürülen dizin numarasını kullanır `GetPage`.  
  
```  
int GetActiveIndex() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Etkin sayfa dizin sayısı.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="getactivepage"></a>  CPropertySheet::GetActivePage  
 Özellik sayfası pencerenin etkin sayfayı alır.  
  
```  
CPropertyPage* GetActivePage() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Etkin sayfa yönelik işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu etkin sayfada bazı eylemleri gerçekleştirmek için kullanın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#135](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]  
  
##  <a name="getpage"></a>  CPropertySheet::GetPage  
 Bu özellik sayfasında belirtilen sayfa için bir işaretçi döndürür.  
  
```  
CPropertyPage* GetPage(int nPage) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nPage*  
 İstenen sayfaya, 0'den başlayan dizini. 0 ve bir özellik sayfasını, kapsayıcı sayfalarında sayısından küçük arasında olmalıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sayfa için karşılık gelen işaretçi *nPage* parametresi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).  
  
##  <a name="getpagecount"></a>  CPropertySheet::GetPageCount  
 Şu anda özellik sayfasında sayfa sayısını belirler.  
  
```  
int GetPageCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özellik sayfasında sayfa sayısı.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).  
  
##  <a name="getpageindex"></a>  CPropertySheet::GetPageIndex  
 Özellik sayfasında belirtilen sayfa dizin sayısını alır.  
  
```  
int GetPageIndex(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parametreler  
 *fsayfa*  
 Bulunacak dizin sayfasıyla noktalarına. Olamaz **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sayfa dizini sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, kullanırsınız `GetPageIndex` kullanmak için sayfa dizini almak için [SetActivePage](#setactivepage) veya [GetPage](#getpage).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="gettabcontrol"></a>  CPropertySheet::GetTabControl  
 Sekme denetimi belirli bir şeyler için sekme denetimi için bir işaretçi alır (yani, API'leri birini kullanmak için [CTabCtrl](../../mfc/reference/ctabctrl-class.md)).  
  
```  
CTabCtrl* GetTabControl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sekme denetimine işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, bit eşlemler sekmelerin her birinde için başlatma sırasında eklemek isterseniz, bu üye işlevini çağırın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]  
  
##  <a name="m_psh"></a>  CPropertySheet::m_psh  
 Üyeleri özelliklerini depolamak yapısı [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturulan sonra ancak ile görüntülemeden önce özellik sayfasını görünümünü başlatmak için bu yapı kullanın [DoModal](#domodal) üye işlevi. Örneğin, *dwSize* üyesi `m_psh` boyutuna sahip özellik sayfası istiyor.  
  
 Bu grubun üyeleri listesi dahil olmak üzere bu yapı hakkında daha fazla bilgi için bkz: **PROPSHEETHEADER** Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]  
  
##  <a name="mapdialogrect"></a>  CPropertySheet::MapDialogRect  
 İletişim kutusu birimleri dikdörtgenin ekran birimlerine dönüştürür.  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *lpRect*  
 İşaret eden bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) iletişim kutusu içeren nesne koordinatları dönüştürülecek.  
  
### <a name="remarks"></a>Açıklamalar  
 İletişim kutusu birimleri ortalama genişlik ve yükseklik yazı tipi iletişim kutusu metni için kullanılan karakter türetilmiş geçerli iletişim kutusu temel birim bakımından belirtilmiştir. Bir yatay bir dördüncü iletişim kutusu base-width biriminin birimidir ve bir dikey bir sekizinci iletişim kutusu temel yükseklik biriminin birimdir.  
  
 [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) Windows işlevi sistem yazı tipi boyutu bilgilerini döndürür, ancak kullanırsanız, her özellik sayfası için farklı bir yazı tipi belirtebilirsiniz **DS_SETFONT** içinde stili Kaynak tanımı dosyası. [MapDialogRect](http://msdn.microsoft.com/library/windows/desktop/ms645502) Windows işlevi, Windows SDK'ın açıklanan bu iletişim kutusu için uygun yazı tipini kullanır.  
  
 `MapDialogRect` Üye işlevi değiştirir iletişim kutusu birimleri *lpRect* ile dikdörtgen Oluştur iletişim kutusu veya bir kutu içinde bir denetim konumlandırmak için kullanılan böylece ekran birimler (piksel cinsinden).  
  
##  <a name="oninitdialog"></a>  CPropertySheet::OnInitDialog  
 Özellik sayfası başlatma büyütmek için geçersiz kılar.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulama giriş odağını özellik sayfasını denetimlerinde birine ayarlanmış olup olmadığını belirtir. Varsa `OnInitDialog` döndürür sıfır olmayan Windows ayarlar giriş odağını ilk denetime özellik sayfasında. Uygulama, yalnızca açıkça giriş odağını özellik sayfasını denetimlerinde birine ayarlarsanız 0 geri dönebilirsiniz.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi WM_INITDIALOG iletisine yanıt olarak adlandırılır. Bu ileti sırasında özellik sayfası gönderilmesini [oluşturma](#create) veya [DoModal](#domodal) hemen özellik sayfasını görüntülemeden önce oluşan çağrılar.  
  
 Özellik sayfasını başlatıldığında özel işlem gerçekleştirmeniz gerekiyorsa, bu üye işlevi geçersiz kılar. Geçersiz kılınan sürümünde ilk çağrı temel sınıfı `OnInitDialog` ancak dönüş değerini göz ardı. Normalde döndürülecek **doğru** geçersiz kılınan üye işlevi.  
  
 Bu üye işlevi için bir ileti eşleme girişi gerekmez.  
  
##  <a name="pressbutton"></a>  CPropertySheet::PressButton  
 Özellik sayfasında belirtilen düğmesi seçimi benzetimini yapar.  
  
```  
void PressButton(int nButton);
```  
  
### <a name="parameters"></a>Parametreler  
 *nButton*  
 nButton: düğmesine basıldığında tanımlar. Bu parametre aşağıdaki değerlerden biri olabilir:  
  
- **PSBTN_BACK** geri düğmesini seçer.  
  
- **PSBTN_NEXT** İleri düğmesini seçer.  
  
- **PSBTN_FINISH** Son düğmesini seçer.  
  
- **PSBTN_OK** Tamam düğmesini seçer.  
  
- **PSBTN_APPLYNOW** şimdi Uygula düğmesini seçer.  
  
- **PSBTN_CANCEL** iptal düğmesi seçer.  
  
- **PSBTN_HELP** Yardım düğmesini seçer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [PSM_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb774597) Windows SDK Pressbutton ileti hakkında daha fazla bilgi için.  
  
 Çağrı `PressButton` değil göndereceğiniz [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) Framework özellik sayfasından bildirim. Bu bildirim göndermek için arama [CPropertyPage::OnOK](../../mfc/reference/cpropertypage-class.md#onok).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]  
  
##  <a name="removepage"></a>  CPropertySheet::RemovePage  
 Bir sayfa özellik sayfasından kaldırır ve ilişkili pencere yok eder.  
  
```  
void RemovePage(CPropertyPage* pPage);  
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>Parametreler  
 *fsayfa*  
 Özellik sayfasından kaldırılacak sayfasına noktaları. Olamaz `NULL`.  
  
 *nPage*  
 Kaldırılacak sayfanın dizini. 0 ve bir özellik sayfasını, kapsayıcı sayfalarında sayısından küçük arasında olmalıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md) nesnesinin kendisi kadar sahibi değil yok `CPropertySheet` penceresi kapatıldığında.  
  
##  <a name="setactivepage"></a>  CPropertySheet::SetActivePage  
 Etkin sayfa değiştirir.  
  
```  
BOOL SetActivePage(int nPage);  
BOOL SetActivePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parametreler  
 *nPage*  
 Ayarlamak için sayfanın dizini. 0 ile bir özellik sayfasını, kapsayıcı sayfalarında sayısından küçük arasında olmalıdır.  
  
 *fsayfa*  
 Özellik sayfasında ayarlamak için sayfasına noktaları. Olamaz **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özellik sayfasını başarıyla etkinleştirilmişse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, `SetActivePage` bir sayfada bir kullanıcının eylemi etkin sayfa olacak başka bir sayfaya neden.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="setfinishtext"></a>  CPropertySheet::SetFinishText  
 Metnin son komut düğmesini ayarlar.  
  
```  
void SetFinishText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszText*  
 Son komut düğmesini görüntülenecek metni noktalarına.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `SetFinishText` son komut düğmesini metni görüntülemek ve kullanıcı sihirbazın son sayfasında eylem tamamlandıktan sonra İleri ve geri düğmelerini gizlemek için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="settitle"></a>  CPropertySheet::SetTitle  
 Özellik sayfanın resim yazısını (bir çerçeve penceresinin başlık çubuğunda görüntülenen metin) belirtir.  
  
```  
void SetTitle(
    LPCTSTR lpszText,  
    UINT nStyle = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *nStyle*  
 Özellik sayfası başlık stilini belirtir. Stil 0 veya olarak belirtilmelidir **PSH_PROPTITLE**. Stil olarak ayarlanırsa **PSH_PROPTITLE**, resim yazısı olarak belirtilen metin sonra "Özellikler" sözcüğü görünür. Örneğin, arama `SetTitle`("Basit" **PSH_PROPTITLE**) "Basit özellikler." içinde bir özellik sayfası başlığını neden olur  
  
 *lpszText*  
 Özellik sayfası başlık çubuğunda açıklamalı alt yazı olarak kullanılacak metin noktalarına.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bir özellik sayfası özellik sayfası oluşturucuda resim yazısı parametresini kullanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]  
  
##  <a name="setwizardbuttons"></a>  CPropertySheet::SetWizardButtons  
 Etkinleştirir veya Sihirbazı özellik sayfası geri, İleri ya da Son'u düğmesini devre dışı bırakır.  
  
```  
void SetWizardButtons(DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwFlags*  
 Sihirbaz düğmelerin görünümünü ve işlevini Özelleştir bayrakları kümesi. Bu parametre bir birleşimi aşağıdaki değerlerden biri olabilir:  
  
- **PSWIZB_BACK** geri düğmesi  
  
- **PSWIZB_NEXT** İleri düğmesi  
  
- **PSWIZB_FINISH** Son'u  
  
- **PSWIZB_DISABLEDFINISH** devre dışı son düğmesi  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `SetWizardButtons` yalnızca iletişim; açıldıktan sonra BinaryRead çağrılamıyor `SetWizardButtons` çağırmadan önce [DoModal](#domodal). Genellikle, çağırmalıdır `SetWizardButtons` gelen [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).  
  
 Son'u üzerindeki metin değiştirmek veya sonraki gizlemek istiyorsanız ve geri düğmeleri kez kullanıcı çağrısı Sihirbazı Tamamlandı [SetFinishText](#setfinishtext). Aynı düğmeye bitiş ve sonraki için paylaşılan unutmayın. Bitiş veya aynı anda İleri düğmesi, ancak ikisini görüntüleyebilirsiniz.  
  
### <a name="example"></a>Örnek  
 A `CPropertySheet` üç Sihirbazı özellik sayfaları: `CStylePage`, `CColorPage`, ve `CShapePage`.  Aşağıdaki kod parçası etkinleştirme ve devre dışı gösterilmektedir **geri** ve **sonraki** Sihirbazı özellik sayfasında düğmeler.  
  
 [!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="setwizardmode"></a>  CPropertySheet::SetWizardMode  
 Sihirbaz özellik sayfası oluşturur.  
  
```  
void SetWizardMode();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir anahtar Sihirbazı özellik sayfası kullanıcı sonraki kullanarak gider veya son, yedekleyebilir ve İptal düğmeleri sekmeleri yerine, özelliğidir.  
  
 Çağrı `SetWizardMode` çağırmadan önce [DoModal](#domodal). Çağırdıktan sonra `SetWizardMode`, `DoModal` ya da döndürülecek **ID_WIZFINISH** (kullanıcı Son'u ile kapatırsa) veya **IDCANCEL**.  
  
 `SetWizardMode` PSH_WIZARD bayrağını ayarlar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC örnek CMNCTRL2](../../visual-cpp-samples.md)   
 [MFC örnek PROPDLG](../../visual-cpp-samples.md)   
 [MFC örnek SNAPVW](../../visual-cpp-samples.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



