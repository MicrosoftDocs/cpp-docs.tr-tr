---
title: CPropertyPage sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 6a6223708c83f7a5b3e6532a2016660d558f8270
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502799"
---
# <a name="cpropertypage-class"></a>CPropertyPage sınıfı

Bir özellik sayfasının tek tek sayfalarını gösterir, aksi halde sekme iletişim kutusu olarak bilinir.

## <a name="syntax"></a>Sözdizimi

```
class CPropertyPage : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPropertyPage:: CPropertyPage](#cpropertypage)|Bir `CPropertyPage` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPropertyPage:: CancelToClose](#canceltoclose)|Tamam düğmesini Oku Kapat olarak değiştirir ve kalıcı özellik sayfası sayfasında kurtarılamaz bir değişiklikten sonra Iptal düğmesini devre dışı bırakır.|
|[CPropertyPage:: yapısı](#construct)|Bir `CPropertyPage` nesnesi oluşturur. Çalışma `Construct` zamanında parametrelerinizi belirtmek istiyorsanız veya diziler kullanıyorsanız kullanın.|
|[CPropertyPage:: GetPSP](#getpsp)|`CPropertyPage` Nesnesiyle ilişkili Windows [propsheetpage](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) yapısını alır.|
|[CPropertyPage:: OnApply](#onapply)|Şimdi Uygula düğmesine tıklandığında Framework tarafından çağırılır.|
|[CPropertyPage:: OnCancel](#oncancel)|Iptal düğmesine tıklandığında Framework tarafından çağırılır.|
|[CPropertyPage:: OnKillActive](#onkillactive)|Geçerli sayfa artık etkin sayfa olmadığında Framework tarafından çağırılır. Veri doğrulamasını burada gerçekleştirin.|
|[CPropertyPage:: OnOK](#onok)|Tamam, şimdi Uygula ya da Kapat düğmesine tıklandığında Framework tarafından çağırılır.|
|[CPropertyPage:: OnQueryCancel](#onquerycancel)|Iptal düğmesine tıklandığında ve iptal gerçekleşmeden önce Framework tarafından çağırılır.|
|[CPropertyPage:: OnReset](#onreset)|Iptal düğmesine tıklandığında Framework tarafından çağırılır.|
|[CPropertyPage:: OnSetActive](#onsetactive)|Sayfa etkin sayfa yapıldığında Framework tarafından çağırılır.|
|[CPropertyPage:: OnWizardBack](#onwizardback)|Sihirbaz türü özellik sayfası kullanılırken geri düğmesine tıklandığında Framework tarafından çağırılır.|
|[CPropertyPage:: onwizardtamamlay](#onwizardfinish)|Sihirbaz türü özellik sayfası kullanılırken son düğmesine tıklandığında Framework tarafından çağırılır.|
|[CPropertyPage:: OnWizardNext](#onwizardnext)|Sihirbaz türü özellik sayfası kullanılırken Ileri düğmesine tıklandığında Framework tarafından çağırılır.|
|[CPropertyPage:: Queryeşdüzey 'lar](#querysiblings)|İletiyi Özellik sayfasının her sayfasına iletir.|
|[CPropertyPage:: SetModified](#setmodified)|Şimdi Uygula düğmesini etkinleştirmek veya devre dışı bırakmak için çağırın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPropertyPage:: m_psp](#m_psp)|Windows [propsheetpage](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) yapısı. Temel özellik sayfası parametrelerine erişim sağlar.|

## <a name="remarks"></a>Açıklamalar

Standart iletişim kutularında olduğu gibi, özellik sayfanızdaki her sayfa `CPropertyPage` için bir sınıf türetirsiniz. Türetilmiş nesneleri `CPropertyPage`kullanmak için, önce bir [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) nesnesi oluşturun ve sonra özellik sayfasında yer alan her sayfa için bir nesne oluşturun. Sayfadaki her sayfa için [CPropertySheet:: AddPage](../../mfc/reference/cpropertysheet-class.md#addpage) ' i çağırın ve ardından [cpropertysheet::D omodal](../../mfc/reference/cpropertysheet-class.md#domodal) ' ı çağırarak özellik sayfasını, kalıcı bir özellik sayfası Için veya [CPropertySheet:: Create](../../mfc/reference/cpropertysheet-class.md#create) için bir kalıcı özellik sayfası ile görüntüleyin.

Bir cihaz ayarlama veya bülten oluşturma gibi bir işlemin adımları boyunca kullanıcıya kılavuzluk eden Özellik sayfaları dizisi olan bir özellik sayfasından oluşan, sihirbaz adlı bir sekme iletişim kutusu türü oluşturabilirsiniz. Sihirbaz-tür sekmesi iletişim kutusunda, özellik sayfalarında sekmeler yoktur ve tek seferde yalnızca bir özellik sayfası görünür. Ayrıca, tamam ve şimdi Uygula düğmelerine sahip olmak yerine, bir sihirbaz türü sekme iletişim kutusu geri düğmesi, Ileri veya son düğmesi ve bir Iptal düğmesi içerir.

Sihirbaz olarak bir özellik sayfası oluşturma hakkında daha fazla bilgi için bkz. [CPropertySheet:: SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode). Nesneleri kullanma `CPropertyPage` hakkında daha fazla bilgi için, özellik sayfaları [ve özellik sayfaları](../../mfc/property-sheets-and-property-pages-in-mfc.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CPropertyPage`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs. h

##  <a name="canceltoclose"></a>CPropertyPage:: CancelToClose

Kalıcı bir özellik sayfasının sayfasındaki verilerde kurtarılamaz bir değişiklik yapıldıktan sonra bu işlevi çağırın.

```
void CancelToClose();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, Kapat düğmesini kapatmak ve Iptal düğmesini devre dışı bırakmak için Tamam düğmesini değiştirecek. Bu değişiklik, kullanıcıyı bir değişikliğin kalıcı olduğunu ve değişikliklerin iptal edilemez olduğunu uyarır.

Kalıcı olmayan özellik sayfasında varsayılan olarak bir iptal düğmesi bulunmadığından, üyeişlevimodsuzbirözelliksayfasındahiçbirşeyyapmaz.`CancelToClose`

### <a name="example"></a>Örnek

  [CPropertyPage:: Queryeşdüzey](#querysiblings)örnekleri için örneğe bakın.

##  <a name="construct"></a>CPropertyPage:: yapısı

Bir `CPropertyPage` nesne oluşturmak için bu üye işlevini çağırın.

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

*Nıdtemplate*<br/>
Bu sayfa için kullanılan şablonun KIMLIĞI.

*nIDCaption*<br/>
Bu sayfanın sekmesine yerleştirilecek adın KIMLIĞI. 0 ise, Bu sayfa için iletişim şablonundan ad alınır.

*lpszTemplateName*<br/>
Bir şablon kaynağının adı olan null ile sonlandırılmış bir dize içerir.

*Nıdheadertitle*<br/>
Özellik sayfası üstbilgisinin başlık konumuna yerleştirilecek adın KIMLIĞI. Varsayılan olarak 0.

*Nıdheaderalt başlığı*<br/>
Özellik sayfası üstbilgisinin alt başlık konumuna yerleştirilecek adın KIMLIĞI. Varsayılan olarak 0.

### <a name="remarks"></a>Açıklamalar

Nesnesi aşağıdaki koşulların tümü karşılandıktan sonra görüntülenir:

- Sayfa, [CPropertySheet:: AddPage](../../mfc/reference/cpropertysheet-class.md#addpage)kullanılarak bir özellik sayfasına eklenmiştir.

- Özellik sayfasının [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) veya [oluşturma](../../mfc/reference/cpropertysheet-class.md#create) işlevi çağrıldı.

- Kullanıcı (sekmeli) bu sayfayı seçti.

Diğer `Construct` sınıf oluşturucularından biri çağrılmışsa çağırın. Parametre ifadesini boş bırakabileceğiniz ve kodunuzda herhangi bir noktada birden fazla parametre ve oluşturma belirten üyeişleviesnektir.`Construct`

Dizilerle çalışırken `Construct` kullanmanız gerekir ve veri üyelerine uygun değerler atanması için dizinin `Construct` her üyesi için çağrı yapmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]

##  <a name="cpropertypage"></a>CPropertyPage:: CPropertyPage

Bir `CPropertyPage` nesnesi oluşturur.

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

*Nıdtemplate*<br/>
Bu sayfa için kullanılan şablonun KIMLIĞI.

*nIDCaption*<br/>
Bu sayfanın sekmesine yerleştirilecek adın KIMLIĞI. 0 ise, Bu sayfa için iletişim şablonundan ad alınır.

*dwSize*<br/>
*lpszTemplateName* Bu sayfa için şablon adını içeren bir dizeye işaret eder. NULL olamaz.

*Nıdheadertitle*<br/>
Özellik sayfası üstbilgisinin başlık konumuna yerleştirilecek adın KIMLIĞI.

*Nıdheaderalt başlığı*<br/>
Özellik sayfası üstbilgisinin alt başlık konumuna yerleştirilecek adın KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Nesnesi aşağıdaki koşulların tümü karşılandıktan sonra görüntülenir:

- Sayfa, [CPropertySheet:: AddPage](../../mfc/reference/cpropertysheet-class.md#addpage)kullanılarak bir özellik sayfasına eklenmiştir.

- Özellik sayfasının [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) veya [oluşturma](../../mfc/reference/cpropertysheet-class.md#create) işlevi çağrıldı.

- Kullanıcı (sekmeli) bu sayfayı seçti.

Birden çok parametreye sahipseniz (örneğin, bir dizi kullanıyorsanız), yerine `CPropertyPage` [CPropertySheet:: yapısını](../../mfc/reference/cpropertysheet-class.md#construct) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]

##  <a name="getpsp"></a>CPropertyPage:: GetPSP

`CPropertyPage` Nesnesiyle ilişkili Windows [propsheetpage](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) yapısını alır.

```
const PROPSHEETPAGE& GetPSP() const;

PROPSHEETPAGE& GetPSP();
```

### <a name="return-value"></a>Dönüş Değeri

`PROPSHEETPAGE` Yapıya bir başvuru.

##  <a name="m_psp"></a>CPropertyPage:: m_psp

`m_psp`, üyeleri [propsheetpage](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2)özelliklerini depolayan bir yapıdır.

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Açıklamalar

Bir özellik sayfasının oluşturulduktan sonra görünümünü başlatmak için bu yapıyı kullanın.

Üyelerinin bir listesi de dahil olmak üzere bu yapı hakkında daha fazla bilgi için, `PROPSHEETPAGE` Windows SDK bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]

##  <a name="onapply"></a>CPropertyPage:: OnApply

Bu üye işlevi, Kullanıcı Tamam veya Şimdi Uygula düğmesini seçtiğinde Framework tarafından çağırılır.

```
virtual BOOL OnApply();
```

### <a name="return-value"></a>Dönüş Değeri

Değişiklikler kabul edilirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çerçeve bu işlevi çağırdığında, özellik sayfasındaki tüm özellik sayfalarında yapılan değişiklikler kabul edilir, özellik sayfası odağı korur ve `OnApply` true değerini döndürür (1 değeri). Framework `OnApply` tarafından çağrılmadan önce [SetModified](#setmodified) çağrılmalıdır ve parametresini true olarak ayarlamanız gerekir. Bu işlem, Kullanıcı Özellik sayfasında bir değişiklik yaptığında Şimdi Uygula düğmesini etkinleştirir.

Kullanıcı Şimdi Uygula düğmesine tıkladığında programınızın hangi eyleme uygulanacağını belirtmek için bu üye işlevi geçersiz kılın. Geçersiz kıldığınızda, değişikliklerin etkili olmasını engellemek için, işlevi değişiklikleri kabul etmek için TRUE, FALSE değerini döndürmelidir.

`OnApply` Çağrıların`OnOK`varsayılan uygulama.

Kullanıcı bir özellik sayfasında Şimdi Uygula veya Tamam düğmesine bastığında gönderilen bildirim iletileri hakkında daha fazla bilgi için, Windows SDK [PSN_APPLY](/windows/win32/Controls/psn-apply) bakın.

### <a name="example"></a>Örnek

  [CPropertyPage:: OnOK](#onok)örneğine bakın.

##  <a name="oncancel"></a>CPropertyPage:: OnCancel

Bu üye işlevi, Iptal düğmesi seçildiğinde Framework tarafından çağırılır.

```
virtual void OnCancel();
```

### <a name="remarks"></a>Açıklamalar

Iptal düğmesi eylemlerini gerçekleştirmek için bu üye işlevini geçersiz kılın. Varsayılan değer yapılan tüm değişiklikleri geçersiz kılar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]

##  <a name="onkillactive"></a>CPropertyPage:: OnKillActive

Bu üye işlevi, sayfa artık etkin sayfa olmadığında Framework tarafından çağırılır.

```
virtual BOOL OnKillActive();
```

### <a name="return-value"></a>Dönüş Değeri

Veriler başarıyla güncellendiyse sıfır dışında, 0.

### <a name="remarks"></a>Açıklamalar

Özel veri doğrulama görevlerini gerçekleştirmek için bu üye işlevini geçersiz kılın.

Bu üye işlevinin varsayılan uygulanması, özellik sayfasındaki denetimlerden ayarları özellik sayfasının üye değişkenlerine kopyalar. Bir iletişim kutusu veri doğrulama (DDV) hatası nedeniyle veriler başarıyla güncellenmemişse, sayfa odağı korur.

Bu üye işlevi başarılı bir şekilde döndüğünde, çerçeve sayfanın [OnOK](#onok) işlevini çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]

##  <a name="onok"></a>CPropertyPage:: OnOK

Bu üye işlevi, Kullanıcı, bir daha önce Tamam veya Şimdi Uygula düğmesini seçtiğinde çerçeve tarafından çağrılır. [](#onkillactive)

```
virtual void OnOK();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı Tamam ' ı ya da şimdi Uygula düğmesini seçtiğinde, çerçeve özellik sayfasından [PSN_APPLY](/windows/win32/Controls/psn-apply) bildirimini alır. Özellik sayfası bildirimi `OnOK` bu durumda göndermediğinden [CPropertySheet::P ressbutton](../../mfc/reference/cpropertysheet-class.md#pressbutton) öğesini çağırdığınızda çağrı yapılmaz.

Kullanıcı tüm özellik sayfasını devre dışı kılıyorsa, şu anda etkin olan sayfaya özgü ek davranışı uygulamak için bu üye işlevi geçersiz kılın.

Bu üye işlevi için varsayılan uygulama, sayfada verinin güncelleştirildiğini `OnKillActive` yansıtmak için sayfayı "Temizle" olarak işaretler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]

##  <a name="onquerycancel"></a>CPropertyPage:: OnQueryCancel

Bu üye işlevi, Kullanıcı Iptal düğmesine tıkladığında ve iptal etme eylemi gerçekleşmeden önce Framework tarafından çağırılır.

```
virtual BOOL OnQueryCancel();
```

### <a name="return-value"></a>Dönüş Değeri

İptal işlemini engellemek için FALSE, izin vermek için TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanıcı Iptal düğmesine tıkladığında programın yapacağı bir eylem belirtmek için bu üye işlevi geçersiz kılın.

Varsayılan uygulama `OnQueryCancel` , true döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]

##  <a name="onreset"></a>CPropertyPage:: OnReset

Bu üye işlevi, Kullanıcı Iptal düğmesini seçtiğinde Framework tarafından çağırılır.

```
virtual void OnReset();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve bu işlevi çağırdığında, Kullanıcı tarafından daha önce Uygula düğmesinin seçilmesiyle yapılmış olan tüm özellik sayfalarındaki değişiklikler atılır ve özellik sayfası odağı korur.

Kullanıcı Iptal düğmesine tıkladığında programın hangi eylemi aldığını belirtmek için bu üye işlevi geçersiz kılın.

Varsayılan uygulamasının `OnReset` hiçbir şey yapmaz.

### <a name="example"></a>Örnek

  [CPropertyPage:: OnCancel](#oncancel)örneğine bakın.

##  <a name="onsetactive"></a>CPropertyPage:: OnSetActive

Bu üye işlevi, sayfa Kullanıcı tarafından seçildiğinde çerçeve tarafından çağrılır ve etkin sayfa olur.

```
virtual BOOL OnSetActive();
```

### <a name="return-value"></a>Dönüş Değeri

Sayfa başarıyla etkin ayarlandıysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir sayfa etkinleştirildiğinde görevleri gerçekleştirmek için bu üye işlevini geçersiz kılın. Bu üye işlevinin geçersiz kılınması, genellikle veri üyelerini güncelleştirdikten sonra varsayılan sürümü çağırır ve bu da sayfa denetimlerini yeni verilerle güncelleştirmesine izin verir.

Varsayılan uygulama, daha önce oluşturulmadıysa sayfanın penceresini oluşturur ve etkin sayfa yapar.

### <a name="example"></a>Örnek

  [CPropertySheet:: Setsonlandırhtext](../../mfc/reference/cpropertysheet-class.md#setfinishtext)örneğine bakın.

##  <a name="onwizardback"></a>CPropertyPage:: OnWizardBack

Bu üye işlevi, Kullanıcı bir sihirbazda geri düğmesine tıkladığında Framework tarafından çağırılır.

```
virtual LRESULT OnWizardBack();
```

### <a name="return-value"></a>Dönüş Değeri

sonraki sayfaya otomatik olarak ilerlemek için 0; -1 sayfanın değiştirilmesini engellemek için. Bir sonraki bir sayfaya geçmek için, görüntülenecek iletişim kutusunun tanımlayıcısını döndürün.

### <a name="remarks"></a>Açıklamalar

Geri düğmesine basıldığında kullanıcının yapması gereken eylemi belirtmek için bu üye işlevi geçersiz kılın.

Sihirbaz türü özellik sayfası oluşturma hakkında daha fazla bilgi için bkz. [CPropertySheet:: SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]

##  <a name="onwizardfinish"></a>CPropertyPage:: onwizardtamamlay

Bu üye işlevi, Kullanıcı sihirbazın son düğmesine tıkladığında Framework tarafından çağırılır.

```
virtual BOOL OnWizardFinish();
```

### <a name="return-value"></a>Dönüş Değeri

Sihirbaz tamamlandığında Özellik sayfası yok edildiğinde sıfır dışında; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bir Kullanıcı bir sihirbazda **son** düğmesine tıkladığında framework bu işlevi çağırır; TRUE `OnWizardFinish` değerini döndürdüğünde (sıfır olmayan bir değer), özellik sayfası yok edilebilir (ancak aslında yok edilmez). Özellik `DestroyWindow` sayfasını yok etmek için çağırın. ' Den `DestroyWindow` `OnWizardFinish`çağırmayın; bunu yapmak yığın bozulmasına veya diğer hatalara neden olur.

Son düğmesine basıldığında kullanıcının yapması gereken eylemi belirtmek için bu üye işlevi geçersiz kılabilirsiniz. Bu işlevi geçersiz kıldığınızda, özellik sayfasının yok edilmesi için FALSE döndürün.

Kullanıcı sihirbaz Özellik sayfasında son düğmesine bastığında gönderilen bildirim iletileri hakkında daha fazla bilgi için, Windows SDK [PSN_WIZFINISH](/windows/win32/Controls/psn-wizfinish) bakın.

Sihirbaz türü özellik sayfası oluşturma hakkında daha fazla bilgi için bkz. [CPropertySheet:: SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]

[!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]

[!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]

[!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]

##  <a name="onwizardnext"></a>CPropertyPage:: OnWizardNext

Bu üye işlevi, Kullanıcı bir sihirbazda Ileri düğmesine tıkladığında Framework tarafından çağırılır.

```
virtual LRESULT OnWizardNext();
```

### <a name="return-value"></a>Dönüş Değeri

sonraki sayfaya otomatik olarak ilerlemek için 0; -1 sayfanın değiştirilmesini engellemek için. Bir sonraki bir sayfaya geçmek için, görüntülenecek iletişim kutusunun tanımlayıcısını döndürün.

### <a name="remarks"></a>Açıklamalar

Ileri düğmesine basıldığında kullanıcının yapması gereken eylemi belirtmek için bu üye işlevi geçersiz kılın.

Sihirbaz türü özellik sayfası oluşturma hakkında daha fazla bilgi için bkz. [CPropertySheet:: SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]

##  <a name="querysiblings"></a>CPropertyPage:: Queryeşdüzey 'lar

Özellik sayfasındaki her sayfaya bir ileti iletmek için bu üye işlevini çağırın.

```
LRESULT QuerySiblings(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*wParam*<br/>
İleti ile bağımlı ek bilgileri belirtir.

*lParam*<br/>
İletiye bağımlı ek bilgileri belirtir

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfasındaki bir sayfadan sıfır dışında bir değer veya tüm sayfalar 0 değerini döndürürse 0.

### <a name="remarks"></a>Açıklamalar

Bir sayfa sıfır dışında bir değer döndürürse, özellik sayfası iletiyi sonraki sayfalara göndermez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]

[!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]

##  <a name="setmodified"></a>CPropertyPage:: SetModified

Özellik sayfasındaki ayarların uygun dış nesneye uygulanıp uygulanamayacağını temel alarak Şimdi Uygula düğmesini etkinleştirmek veya devre dışı bırakmak için bu üye işlevi çağırın.

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>Parametreler

*bChanged*<br/>
Özellik sayfası ayarlarının, son uygulanma zamanından bu yana değiştirildiğini belirtmek için TRUE; Özellik sayfası ayarlarının uygulandığını göstermek için FALSE veya yok sayılacak olmalıdır.

### <a name="remarks"></a>Açıklamalar

Framework hangi sayfaların "kirli,", yani hangi özellik sayfaları `SetModified( TRUE )`olduğunu izler. Sayfadan birini çağırırsanız `SetModified( TRUE )` , şimdi Uygula düğmesi her zaman etkinleştirilecek. Bir sayfadan birini çağırdığınızda `SetModified( FALSE )` , ancak yalnızca diğer sayfalardan hiçbiri "kirli" değilse, şimdi Uygula düğmesi devre dışı bırakılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPropertySheet Sınıfı](../../mfc/reference/cpropertysheet-class.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
