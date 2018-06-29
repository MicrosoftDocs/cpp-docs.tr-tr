---
title: CPropertyPage sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPropertyPage
- AFXDLGS/CPropertyPage
- AFXDLGS/CPropertyPage::CPropertyPage
- AFXDLGS/CPropertyPage::CancelToClose
- AFXDLGS/CPropertyPage::Construct
- AFXDLGS/CPropertyPage::GetPSP
- AFXDLGS/CPropertyPage::OnApply
- AFXDLGS/CPropertyPage::OnCancel
- AFXDLGS/CPropertyPage::OnKillActive
- AFXDLGS/CPropertyPage::OnOK
- AFXDLGS/CPropertyPage::OnQueryCancel
- AFXDLGS/CPropertyPage::OnReset
- AFXDLGS/CPropertyPage::OnSetActive
- AFXDLGS/CPropertyPage::OnWizardBack
- AFXDLGS/CPropertyPage::OnWizardFinish
- AFXDLGS/CPropertyPage::OnWizardNext
- AFXDLGS/CPropertyPage::QuerySiblings
- AFXDLGS/CPropertyPage::SetModified
- AFXDLGS/CPropertyPage::m_psp
dev_langs:
- C++
helpviewer_keywords:
- CPropertyPage [MFC], CPropertyPage
- CPropertyPage [MFC], CancelToClose
- CPropertyPage [MFC], Construct
- CPropertyPage [MFC], GetPSP
- CPropertyPage [MFC], OnApply
- CPropertyPage [MFC], OnCancel
- CPropertyPage [MFC], OnKillActive
- CPropertyPage [MFC], OnOK
- CPropertyPage [MFC], OnQueryCancel
- CPropertyPage [MFC], OnReset
- CPropertyPage [MFC], OnSetActive
- CPropertyPage [MFC], OnWizardBack
- CPropertyPage [MFC], OnWizardFinish
- CPropertyPage [MFC], OnWizardNext
- CPropertyPage [MFC], QuerySiblings
- CPropertyPage [MFC], SetModified
- CPropertyPage [MFC], m_psp
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: beeef0d8ff1a89a003987f9cd79172ad2ff86d75
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079635"
---
# <a name="cpropertypage-class"></a>CPropertyPage sınıfı
Aksi halde bir sekme iletişim kutusu olarak bilinen bir özellik sayfası, her bir sayfayı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPropertyPage : public CDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPropertyPage::CPropertyPage](#cpropertypage)|Oluşturan bir `CPropertyPage` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPropertyPage::CancelToClose](#canceltoclose)|Kapat okumak için Tamam düğmesini değiştirir ve kalıcı özellik sayfası sayfasındaki kurtarılamaz bir değişiklikten sonra iptal düğmesi devre dışı bırakır.|  
|[CPropertyPage::Construct](#construct)|Oluşturan bir `CPropertyPage` nesnesi. Kullanım `Construct` çalışma zamanında parametrelerinizi belirtmek istiyorsanız ya da diziler kullanıyorsanız.|  
|[CPropertyPage::GetPSP](#getpsp)|Windows alır [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) ilişkili yapısı `CPropertyPage` nesnesi.|  
|[CPropertyPage::OnApply](#onapply)|Şimdi Uygula düğmesine tıklandığında çerçevesi tarafından çağrılır.|  
|[CPropertyPage::OnCancel](#oncancel)|İptal düğmesi tıklatıldığında çerçevesi tarafından çağrılır.|  
|[CPropertyPage::OnKillActive](#onkillactive)|Geçerli sayfa artık etkin sayfası olmadığında çerçevesi tarafından çağrılır. Veri doğrulama burada gerçekleştirin.|  
|[CPropertyPage::OnOK](#onok)|Tamam, şimdi Uygula veya Kapat düğmesine tıklandığında çerçevesi tarafından çağrılır.|  
|[CPropertyPage::OnQueryCancel](#onquerycancel)|İptal düğmesi tıklatıldığında ve iptal gerçekleştikten önce çerçevesi tarafından çağrılır.|  
|[CPropertyPage::OnReset](#onreset)|İptal düğmesi tıklatıldığında çerçevesi tarafından çağrılır.|  
|[CPropertyPage::OnSetActive](#onsetactive)|Etkin sayfa sayfa yapıldığında çerçevesi tarafından çağrılır.|  
|[CPropertyPage::OnWizardBack](#onwizardback)|Sihirbaz türü özellik sayfası kullanırken geri düğmesine tıklandığında çerçevesi tarafından çağrılır.|  
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|Sihirbaz türü özellik sayfası kullanırken Son düğmesine tıklandığında çerçevesi tarafından çağrılır.|  
|[CPropertyPage::OnWizardNext](#onwizardnext)|Sihirbaz türü özellik sayfası kullanırken İleri düğmesine tıklandığında çerçevesi tarafından çağrılır.|  
|[CPropertyPage::QuerySiblings](#querysiblings)|İletinin özellik sayfası her sayfaya iletir.|  
|[CPropertyPage::SetModified](#setmodified)|Etkinleştirme veya devre dışı şimdi Uygula düğmesi için çağırın.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPropertyPage::m_psp](#m_psp)|Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) yapısı. Temel özellik sayfası parametreleri erişim sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Standart iletişim kutuları ile öğesinden bir sınıf türetin gibi `CPropertyPage` , özellik sayfasında her bir sayfa için. Kullanılacak `CPropertyPage`-türetilen nesneleri ilk oluşturma bir [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) nesne ve özellik sayfasında gider her bir sayfa için bir nesne oluşturun. Çağrı [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage) her sayfada sayfasında ve ardından çağırarak özellik sayfasını görüntülemek [CPropertySheet::DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) kalıcı özellik sayfası için veya [CPropertySheet:: Oluşturma](../../mfc/reference/cpropertysheet-class.md#create) kalıcı olmayan özellik sayfası için.  
  
 Tab iletişim kutusunda, kullanıcı cihazını ayarlamaya veya bülten oluşturma gibi bir işlem adımları boyunca rehberlik özellik sayfaları dizisi ile bir özellik sayfasından oluşan bir sihirbaz denilen türü oluşturabilirsiniz. Sihirbaz türü sekme iletişim kutusunda, özellik sayfaları sekmeleri gerekmez ve aynı anda yalnızca bir özellik sayfası görünür. Ayrıca, Tamam ve şimdi Uygula düğmeleri sahip olmanın yerine, bir sihirbaz türü sekme iletişim kutusu geri düğmesini, bir sonraki veya bitiş düğmesi ve iptal düğmesi'vardır.  
  
 Sihirbaz özellik sayfası oluşturma ile ilgili daha fazla bilgi için bkz: [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode). Kullanma hakkında daha fazla bilgi için `CPropertyPage` nesneleri başlıklı makaleye bakın [özellik bölümleri ve özellik sayfaları](../../mfc/property-sheets-and-property-pages-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdlgs.h  
  
##  <a name="canceltoclose"></a>  CPropertyPage::CancelToClose  
 Kalıcı özellik sayfasının bir sayfa verilerde kurtarılamaz bir değişiklik yapıldıktan sonra bu işlevini çağırın.  
  
```  
void CancelToClose();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, Kapat'Tamam düğmesine değiştirin ve iptal düğmesi devre dışı bırakın. Bu uyarılar kalıcı ve değişikliklerin bir değişikliktir kullanıcı iptal edilemez değiştirin.  
  
 `CancelToClose` Üye işlevi hiçbir şey yapmaz kalıcı olmayan özellik sayfası, çünkü kalıcı olmayan özellik sayfası iptal düğmesi, varsayılan olarak yok.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertyPage::QuerySiblings](#querysiblings).  
  
##  <a name="construct"></a>  CPropertyPage::Construct  
 Oluşturmak için bu üye işlevini çağırın bir `CPropertyPage` nesnesi.  
  
```  
void Construct(
    UINT nIDTemplate,  
    UINT nIDCaption = 0);

 
void Construct(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption = 0);

 
void Construct(
    UINT nIDTemplate,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0);

 
void Construct(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDTemplate*  
 Bu sayfa için kullanılan şablon kimliği.  
  
 *nIDCaption*  
 Bu sayfa için sekmesindeki yerleştirilecek adı kimliği. 0 ise bu sayfa için iletişim kutusu şablondan adı ulaşabilirsiniz.  
  
 *lpszTemplateName*  
 Bir şablon kaynağı adı null ile sonlandırılmış bir dize içeriyor.  
  
 *nIDHeaderTitle*  
 Özellik sayfa üstbilgisi başlık konumunu yerleştirilecek adı kimliği. Varsayılan olarak, 0.  
  
 *nIDHeaderSubTitle*  
 Özellik sayfa üstbilgisi altyazısı konumunu yerleştirilecek adı kimliği. Varsayılan olarak, 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki koşulların tümü yerine getirildikten sonra nesnesi görüntülenir:  
  
-   Kullanarak bir özellik sayfası sayfası eklendi [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Özellik sayfanın [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) veya [oluşturma](../../mfc/reference/cpropertysheet-class.md#create) işlevini çağırdı.  
  
-   Kullanıcının seçtiği (sekmeli) bu sayfa.  
  
 Çağrı `Construct` diğer sınıf oluşturuculardan birine değil çağrılmış. `Construct` Üye işlevi olduğundan esnek parametre ifadesi boş bırakın ve ardından birden çok parametre ve herhangi bir noktada yapım kodunuzda belirtin.  
  
 Kullanmalısınız `Construct` zaman dizilerle çalışma ve çağırmalısınız `Construct` dizinin her bir üyesi için böylece veri üyeleri uygun değerler atanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]  
  
##  <a name="cpropertypage"></a>  CPropertyPage::CPropertyPage  
 Oluşturan bir `CPropertyPage` nesnesi.  
  
```  
CPropertyPage();

 
explicit CPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
explicit CPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
CPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
CPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDTemplate*  
 Bu sayfa için kullanılan şablon kimliği.  
  
 *nIDCaption*  
 Bu sayfa için sekmesindeki yerleştirilecek adı kimliği. 0 ise bu sayfa için iletişim kutusu şablondan adı ulaşabilirsiniz.  
  
 *dwSize*  
 *lpszTemplateName*  
 Bu sayfa için şablon adını içeren bir dize noktalarına. Olamaz **NULL**.  
  
 *nIDHeaderTitle*  
 Özellik sayfa üstbilgisi başlık konumunu yerleştirilecek adı kimliği.  
  
 *nIDHeaderSubTitle*  
 Özellik sayfa üstbilgisi altyazısı konumunu yerleştirilecek adı kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki koşulların tümü yerine getirildikten sonra nesnesi görüntülenir:  
  
-   Kullanarak bir özellik sayfası sayfası eklendi [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Özellik sayfanın [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) veya [oluşturma](../../mfc/reference/cpropertysheet-class.md#create) işlevini çağırdı.  
  
-   Kullanıcının seçtiği (sekmeli) bu sayfa.  
  
 Birden çok parametre (örneğin, bir dizi kullanıyorsanız) varsa, [CPropertySheet::Construct](../../mfc/reference/cpropertysheet-class.md#construct) yerine `CPropertyPage`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]  
  
##  <a name="getpsp"></a>  CPropertyPage::GetPSP  
 Windows alır [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) ilişkili yapısı `CPropertyPage` nesnesi.  
  
```  
const PROPSHEETPAGE& GetPSP() const;  
  
PROPSHEETPAGE& GetPSP();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru **PROPSHEETPAGE** yapısı.  
  
##  <a name="m_psp"></a>  CPropertyPage::m_psp  
 `m_psp` üyeleri özelliklerini depolamak bir yapıdır [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548).  
  
```  
PROPSHEETPAGE m_psp;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yapı, oluşturulan sonra özellik sayfası görünümünü başlatmak için kullanın.  
  
 Bu grubun üyeleri listesi dahil olmak üzere bu yapı hakkında daha fazla bilgi için bkz: **PROPSHEETPAGE** Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]  
  
##  <a name="onapply"></a>  CPropertyPage::OnApply  
 Kullanıcı Tamam'ı veya şimdi Uygula düğmesini seçtiğinde bu üye işlev çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnApply();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değişiklikleri kabul edilirse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework bu işlev aradığında, özellik sayfasında tüm özellik sayfalarını yapılan değişiklikleri kabul edilir, özellik sayfasını odağını korur ve `OnApply` döndürür **TRUE** (değeri 1). Önce `OnApply` çağrılabilir çerçevesi tarafından çağrıldı gerekir [SetModified](#setmodified) ve kendi parametre kümesine **doğru**. Kullanıcının bir değişiklik özellik sayfasında yaptığı hemen sonra bu şimdi Uygula düğmesi etkinleşir.  
  
 Kullanıcı şimdi Uygula düğmesini tıklattığında programınızı alır hangi eylemini belirtmek üzere bu üye işlevi geçersiz kılar. Geçersiz kılarken işlevi döndürmelidir **TRUE** değişiklikleri kabul etmek için ve **FALSE** etkili değişiklikler engellemek için.  
  
 Varsayılan uygulaması `OnApply` çağrıları `OnOK`.  
  
 Kullanıcı bir özellik sayfasında şimdi Uygula veya Tamam düğmesine bastığında gönderilen bildirim iletileri hakkında daha fazla bilgi için bkz: [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertyPage::OnOK](#onok).  
  
##  <a name="oncancel"></a>  CPropertyPage::OnCancel  
 İptal düğmesi seçildiğinde bu üye işlev çerçevesi tarafından çağrılır.  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İptal düğmesi eylemleri gerçekleştirmek için bu üye işlevi geçersiz kılar. Varsayılan yapılmış değişiklikleri üzerindeki geçersiz kılar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]  
  
##  <a name="onkillactive"></a>  CPropertyPage::OnKillActive  
 Sayfa artık etkin sayfa olduğunda bu üye işlev çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Veri başarıyla güncelleştirildiyse sıfır olmayan Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel veri doğrulama görevleri gerçekleştirmek için bu üye işlevi geçersiz kılar.  
  
 Bu üye işlevi varsayılan uygulaması ayarları özellik sayfası denetimlerinde özellik sayfasının üye değişkenleri kopyalar. Verileri bir iletişim kutusu veri doğrulama (DDV) hatası nedeniyle başarıyla güncelleştirilmedi, sayfa odağını korur.  
  
 Bu üye işlevi başarıyla döndükten sonra framework sayfanın çağıracak [OnOK](#onok) işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]  
  
##  <a name="onok"></a>  CPropertyPage::OnOK  
 Kullanıcı hemen framework çağrıları sonra Tamam'ı veya şimdi Uygula düğmesini seçtiğinde bu üye işlev çerçevesi tarafından çağrılır [OnKillActive](#onkillactive).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı Tamam'ı veya şimdi Uygula düğmesini seçtiğinde framework alır [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) özellik sayfasından bildirim. Çağrı `OnOK` çağırırsanız yapılan olmaz [CPropertySheet::PressButton](../../mfc/reference/cpropertysheet-class.md#pressbutton) özellik sayfası bildirim bu durumda göndermek için.  
  
 Tüm özellik sayfası kullanıcı atar, şu anda etkin sayfaya özgü ek davranış uygulamak için bu üye işlevi geçersiz kılar.  
  
 Bu üye işlevi varsayılan uygulaması sayfası "verileri güncelleştirildi yansıtacak şekilde Temizle" olarak işaretler `OnKillActive` işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]  
  
##  <a name="onquerycancel"></a>  CPropertyPage::OnQueryCancel  
 Bu üye işlevi kullanıcı iptal düğmesine tıklar ve önce iptal eylemi devre dışı gerçekleştikten çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **FALSE** İptal işlemi ya da izin vermek için doğru önlemek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı iptal düğmesine tıkladığında programın aldığı bir eylem belirtmek için bu üye işlevi geçersiz kılar.  
  
 Varsayılan uygulaması `OnQueryCancel` döndürür **doğru**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]  
  
##  <a name="onreset"></a>  CPropertyPage::OnReset  
 Kullanıcı İptal düğmesi seçtiğinde bu üye işlev çerçevesi tarafından çağrılır.  
  
```  
virtual void OnReset();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Framework bu işlev aradığında, daha önce şimdi Uygula düğmesini seçerek kullanıcı tarafından yapılan tüm özellik sayfalarını değişiklikler atılır ve özellik sayfasını odağını korur.  
  
 Kullanıcı iptal düğmesine tıkladığında programın aldığı hangi eylemini belirtmek üzere bu üye işlevi geçersiz kılar.  
  
 Varsayılan uygulaması `OnReset` hiçbir şey yapmaz.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertyPage::OnCancel](#oncancel).  
  
##  <a name="onsetactive"></a>  CPropertyPage::OnSetActive  
 Sayfa kullanıcı tarafından seçilir ve etkin sayfa haline gelir, bu üye işlevi çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sayfa başarıyla etkin olarak ayarlandıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir sayfa etkinleştirildiğinde görevleri gerçekleştirmek için bu üye işlevi geçersiz kılar. Bu üye işlevi geçersiz kılma, sayfa denetimleri yeni verilerle güncelleştirmek için izin vermek için veri üyeleri güncelleştirdikten sonra varsayılan sürüm genellikle çağırırdı.  
  
 Varsayılan uygulama, sayfa için pencere oluşturur yoksa daha önce oluşturduğunuz ve etkin sayfa kolaylaştırır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext).  
  
##  <a name="onwizardback"></a>  CPropertyPage::OnWizardBack  
 Kullanıcı bir Sihirbazı'nda geri düğmesine tıkladığında bu üye işlev çerçevesi tarafından çağrılır.  
  
```  
virtual LRESULT OnWizardBack();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 otomatik olarak sonraki sayfaya ilerleyin 0; sayfa değiştirmesini engellemek için -1. Bir sonraki dışında bir sayfaya gitmek için görüntülenecek iletişim tanımlayıcısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevini geri düğmesine basıldığında kullanıcı gerçekleştirmesi gereken bazı eylemi belirtmek için geçersiz kılar.  
  
 Sihirbaz türü özellik sayfası yapma hakkında daha fazla bilgi için bkz: [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]  
  
##  <a name="onwizardfinish"></a>  CPropertyPage::OnWizardFinish  
 Kullanıcı bir Sihirbazı'nda Son düğmesine tıkladığında bu üye işlev çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sihirbaz sona erdiğinde özellik sayfasını yok, sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı tıkladığında **son** framework bir Sihirbazı'nda düğmesini bu işlev çağrıları; zaman `OnWizardFinish` döndürür **TRUE** (sıfır değeri), özellik sayfasında yok edilmesi yapabiliyor (ancak aslında değil yok). Çağrı `DestroyWindow` özellik sayfası yok etmek için. Çağırmayın `DestroyWindow` gelen `OnWizardFinish`; bunun nedenle neden olacak yığın bozulması veya diğer hatalar.  
  
 Son düğmesine basıldığında kullanıcı gerçekleştirmesi gereken bazı eylemi belirtmek için bu üye işlevi geçersiz kılabilirsiniz. Bu işlev geçersiz kılarken dönmek **FALSE** yok gelen özellik sayfasını önlemek için.  
  
 Kullanıcı bir sihirbaz özellik sayfasında son düğmesine bastığında gönderilen bildirim iletileri hakkında daha fazla bilgi için bkz: [PSN_WIZFINISH](http://msdn.microsoft.com/library/windows/desktop/bb774571) Windows SDK'sındaki.  
  
 Sihirbaz türü özellik sayfası yapma hakkında daha fazla bilgi için bkz: [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]  
  
##  <a name="onwizardnext"></a>  CPropertyPage::OnWizardNext  
 Kullanıcı bir sihirbazında İleri düğmesine tıkladığında bu üye işlev çerçevesi tarafından çağrılır.  
  
```  
virtual LRESULT OnWizardNext();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 otomatik olarak sonraki sayfaya ilerleyin 0; sayfa değiştirmesini engellemek için -1. Bir sonraki dışında bir sayfaya gitmek için görüntülenecek iletişim tanımlayıcısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İleri düğmesine basıldığında kullanıcı gerçekleştirmesi gereken bazı eylemi belirtmek için bu üye işlevi geçersiz kılar.  
  
 Sihirbaz türü özellik sayfası yapma hakkında daha fazla bilgi için bkz: [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]  
  
##  <a name="querysiblings"></a>  CPropertyPage::QuerySiblings  
 Özellik sayfasında her sayfaya bir iletiyi iletmesini bu üye işlevini çağırın.  
  
```  
LRESULT QuerySiblings(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 *wParam*  
 Ek ileti bağımlı bilgileri belirtir.  
  
 *lParam*  
 Ek ileti bağımlı bilgi belirtir  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özellik sayfasını veya 0 ise bir sayfadan sıfır olmayan değer tüm sayfaları 0 değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir sayfa sıfır olmayan bir değer döndürürse, özellik sayfasında sonraki sayfalara ileti göndermez.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]  
  
##  <a name="setmodified"></a>  CPropertyPage::SetModified  
 Etkinleştirmek veya özellik sayfasında ayarlarında uygun dış nesnesine uygulanmalıdır olup göre şimdi Uygula düğmesini devre dışı bırakmak için bu üye işlevini çağırın.  
  
```  
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bChanged*  
 **DOĞRU** özellik sayfası ayarları bunlar uygulanan; en son ne zaman beri değiştirilmiş belirtmek için **FALSE** özellik sayfası ayarları uygulanmış olan veya yok sayılması gerektiğini belirtmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework tutar izleme hangisinin sayfaları "kirli" başka bir deyişle, kendisi için adlı özellik sayfaları **SetModified (TRUE)**. Çağırırsanız, her zaman şimdi Uygula düğmesi etkinleştirilir **SetModified (TRUE)** sayfaları biri için. Çağırdığınızda şimdi Uygula düğmesini devre dışı bırakılacak **SetModified (FALSE)** yalnızca Sihirbazın diğer sayfalarını hiçbiri "kirli" ise ancak sayfaları, biri için  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC örnek CMNCTRL2](../../visual-cpp-samples.md)   
 [MFC örnek PROPDLG](../../visual-cpp-samples.md)   
 [MFC örnek SNAPVW](../../visual-cpp-samples.md)   
 [CDialog sınıfı](../../mfc/reference/cdialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CPropertySheet sınıfı](../../mfc/reference/cpropertysheet-class.md)   
 [CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
