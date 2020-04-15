---
title: CPropertyPage Sınıfı
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
ms.openlocfilehash: 816948ea17f674c3cd693331502df33cce62610c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363994"
---
# <a name="cpropertypage-class"></a>CPropertyPage Sınıfı

Bir özellik sayfasının tek tek sayfalarını temsil eder, aksi takdirde sekme iletişim kutusu olarak bilinir.

## <a name="syntax"></a>Sözdizimi

```
class CPropertyPage : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CpropertyPage::cpropertypage](#cpropertypage)|Bir `CPropertyPage` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CpropertyPage::CanceltoClose](#canceltoclose)|Bir modal özellik sayfasının sayfasında kurtarılamayan bir değişiklikten sonra Tamam düğmesini kapat'ı değiştirir ve İptal düğmesini devre dışı kılabilir.|
|[CPropertyPage::Yapı](#construct)|Bir `CPropertyPage` nesne inşa eder. Parametrelerinizi çalışma zamanında belirtmek istiyorsanız veya dizi kullanıyorsanız kullanın. `Construct`|
|[CPropertyPage::GetPSP](#getpsp)|`CPropertyPage` Nesneyle ilişkili Windows [PROPSHEETPAGE](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) yapısını alır.|
|[CpropertyPage::OnApply](#onapply)|Şimdi Uygula düğmesine tıklandığında çerçeve tarafından çağrılır.|
|[CpropertyPage::OnCancel](#oncancel)|İptal düğmesi tıklatıldığında çerçeve tarafından çağrılır.|
|[CpropertyPage::OnKillActive](#onkillactive)|Geçerli sayfa artık etkin sayfa olmadığında çerçeve tarafından çağrılır. Burada veri doğrulama gerçekleştirin.|
|[CpropertyPage::OnOK](#onok)|Tamam, Şimdi Uygula veya Kapat düğmesi tıklatıldığında çerçeve tarafından çağrılır.|
|[CpropertyPage::OnQueryCancel](#onquerycancel)|İptal düğmesi tıklatıldığında ve iptal gerçekleşmeden önce çerçeve tarafından çağrılır.|
|[CPropertyPage::OnReset](#onreset)|İptal düğmesi tıklatıldığında çerçeve tarafından çağrılır.|
|[Cpropertypage::Onsetactive](#onsetactive)|Sayfa etkin sayfa yapıldığında çerçeve tarafından çağrılır.|
|[CpropertyPage::OnWizardback](#onwizardback)|Sihirbaz türünde bir özellik sayfası kullanırken Geri düğmesine tıklandığında çerçeve tarafından çağrılır.|
|[CpropertyPage::OnwizardFinish](#onwizardfinish)|Sihirbaz türünde bir özellik sayfası kullanırken Bitiş düğmesi tıklatıldığında çerçeve tarafından çağrılır.|
|[CpropertyPage::OnWizardNext](#onwizardnext)|Sihirbaz türünde bir özellik sayfası kullanırken Sonraki düğmesine tıklandığında çerçeve tarafından çağrılır.|
|[CPropertyPage::QuerySiblings](#querysiblings)|İletiyi özellik sayfasının her sayfasına iletir.|
|[CpropertyPage::Setmodi](#setmodified)|Şimdi Uygula düğmesini etkinleştirmek veya devre dışı bırakmak için arayın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPropertyPage::m_psp](#m_psp)|Windows [PROPSHEETPAGE](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) yapısı. Temel özellik sayfası parametrelerine erişim sağlar.|

## <a name="remarks"></a>Açıklamalar

Standart iletişim kutularında olduğu gibi, özellik `CPropertyPage` sayfanızdaki her sayfa için bir sınıf türetin. Türetilmiş nesneleri kullanmak `CPropertyPage`için önce bir [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) nesnesi oluşturun ve ardından özellik sayfasına giren her sayfa için bir nesne oluşturun. [CPropertySheet'i arayın::Sayfadaki](../../mfc/reference/cpropertysheet-class.md#addpage) her sayfa için Sayfa Yı ekleyin ve [ardından CPropertySheet::Dmodal](../../mfc/reference/cpropertysheet-class.md#domodal) özellik sayfası için oModal veya [CPropertySheet::Modeless](../../mfc/reference/cpropertysheet-class.md#create) özellik sayfası için oluşturun'u arayarak özellik sayfasını görüntüleyin.

Sihirbaz adı verilen ve kullanıcıya aygıt ayarlama veya bülten oluşturma gibi işlem adımlarından rehberlik eden özellik sayfaları dizisiiçeren bir özellik sayfası içeren bir sekme iletişim kutusu türü oluşturabilirsiniz. Sihirbaz türü sekmesi iletişim kutusunda, özellik sayfalarında sekmeler yoktur ve aynı anda yalnızca bir özellik sayfası görünür. Ayrıca, Tamam ve Şimdi Uygula düğmelerine sahip olmak yerine, sihirbaz türü sekmesi iletişim kutusunda Geri Düğmesi, İleri veya Bitiş düğmesi ve İptal düğmesi bulunur.

Sihirbaz olarak bir özellik sayfası oluşturma hakkında daha fazla bilgi için [Bkz. CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode). Nesneleri kullanma `CPropertyPage` hakkında daha fazla bilgi [için, makaleözellik sayfaları ve Özellik Sayfaları](../../mfc/property-sheets-and-property-pages-in-mfc.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

`CPropertyPage`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs.h

## <a name="cpropertypagecanceltoclose"></a><a name="canceltoclose"></a>CpropertyPage::CanceltoClose

Modal özellik sayfasının bir sayfasındaki verilerde kurtarılamaz bir değişiklik yapıldıktan sonra bu işlevi arayın.

```
void CancelToClose();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev Tamam düğmesini Kapat düğmesine değiştirir ve İptal düğmesini devre dışı eder. Bu değişiklik, kullanıcıyı bir değişikliğin kalıcı olduğu ve değişikliklerin iptal edilemeyeceği konusunda uyarır.

Modeless özellik sayfasında varsayılan olarak İptal düğmesi `CancelToClose` olmadığından, üye işlev modeless özellik sayfasında hiçbir şey yapmaz.

### <a name="example"></a>Örnek

  CPropertyPage örneğine [bakın:QuerySiblings](#querysiblings).

## <a name="cpropertypageconstruct"></a><a name="construct"></a>CPropertyPage::Yapı

Bir `CPropertyPage` nesne oluşturmak için bu üye işlevi çağırın.

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

*nIDTemplate*<br/>
Bu sayfa için kullanılan şablonun kimliği.

*nIDCaption*<br/>
Bu sayfanın sekmesine yerleştirilecek adın kimliği. 0 ise, ad bu sayfanın iletişim şablonundan alınır.

*lpszTemplateName*<br/>
Şablon kaynağının adı olan null-sonlandırılan bir dize içerir.

*nIDHeaderBaşlık*<br/>
Özellik sayfası üstbilgisinin başlık yerine yerleştirilecek adın kimliği. Varsayılan olarak, 0.

*nIDHeaderSubTitle*<br/>
Özellik sayfası üstbilgisinin altyazı konumuna yerleştirilecek adın kimliği. Varsayılan olarak, 0.

### <a name="remarks"></a>Açıklamalar

Nesne, aşağıdaki koşulların tümü karşılandıktan sonra görüntülenir:

- Sayfa CPropertySheet kullanılarak bir özellik sayfasına [eklendi::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).

- Özellik sayfasının [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) veya [Create](../../mfc/reference/cpropertysheet-class.md#create) işlevi çağrıldı.

- Kullanıcı bu sayfayı seçmiştir (sekmeli beslenmiştir).

Diğer `Construct` sınıf oluşturucularından biri çağrılmediyse arayın. `Construct` Parametre deyimini boş bırakıp ardından kodunuzun herhangi bir noktasında birden çok parametre ve yapı belirtebildiğiniz için üye işlev esnektir.

Dizilerle `Construct` çalışırken kullanmanız gerekir ve veri üyelerine uygun değerler atanması için dizinin her üyesini aramanız `Construct` gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]

## <a name="cpropertypagecpropertypage"></a><a name="cpropertypage"></a>CpropertyPage::cpropertypage

Bir `CPropertyPage` nesne inşa eder.

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

*nIDTemplate*<br/>
Bu sayfa için kullanılan şablonun kimliği.

*nIDCaption*<br/>
Bu sayfanın sekmesine yerleştirilecek adın kimliği. 0 ise, ad bu sayfanın iletişim şablonundan alınır.

*dwSize*<br/>
*lpszTemplateName* Bu sayfanın şablonunun adını içeren bir dizeyi işaret eder. NULL olamaz.

*nIDHeaderBaşlık*<br/>
Özellik sayfası üstbilgisinin başlık yerine yerleştirilecek adın kimliği.

*nIDHeaderSubTitle*<br/>
Özellik sayfası üstbilgisinin altyazı konumuna yerleştirilecek adın kimliği.

### <a name="remarks"></a>Açıklamalar

Nesne, aşağıdaki koşulların tümü karşılandıktan sonra görüntülenir:

- Sayfa CPropertySheet kullanılarak bir özellik sayfasına [eklendi::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).

- Özellik sayfasının [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) veya [Create](../../mfc/reference/cpropertysheet-class.md#create) işlevi çağrıldı.

- Kullanıcı bu sayfayı seçmiştir (sekmeli beslenmiştir).

Birden çok parametreniz varsa (örneğin, bir dizi kullanıyorsanız), [CPropertySheet kullanın::Yapı](../../mfc/reference/cpropertysheet-class.md#construct) yerine. `CPropertyPage`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]

## <a name="cpropertypagegetpsp"></a><a name="getpsp"></a>CPropertyPage::GetPSP

`CPropertyPage` Nesneyle ilişkili Windows [PROPSHEETPAGE](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) yapısını alır.

```
const PROPSHEETPAGE& GetPSP() const;

PROPSHEETPAGE& GetPSP();
```

### <a name="return-value"></a>Dönüş Değeri

Yapıya `PROPSHEETPAGE` bir gönderme.

## <a name="cpropertypagem_psp"></a><a name="m_psp"></a>CPropertyPage::m_psp

`m_psp`üyeleri [PROPSHEETPAGE](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2)özelliklerini depolayan bir yapıdır.

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Açıklamalar

Bir özellik sayfasının oluşturulduktan sonra görünümünü başlatmayı sağlamak için bu yapıyı kullanın.

Üyelerinin listesi de dahil olmak üzere bu yapı `PROPSHEETPAGE` hakkında daha fazla bilgi için Windows SDK'ya bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]

## <a name="cpropertypageonapply"></a><a name="onapply"></a>CpropertyPage::OnApply

Kullanıcı Tamam veya Şimdi Uygula düğmesini seçtiğinde bu üye işlev çerçeve tarafından çağrılır.

```
virtual BOOL OnApply();
```

### <a name="return-value"></a>Dönüş Değeri

Değişiklikler kabul edilirse sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çerçeve bu işlevi aradığında, özellik sayfasındaki tüm özellik sayfalarında yapılan değişiklikler kabul edilir, `OnApply` özellik sayfası odağı korur ve TRUE (değer 1) döndürür. Çerçeve `OnApply` tarafından çağrılmadan [önce, SetModified'i](#setmodified) aramış ve parametresini TRUE olarak ayarlamış olmalısınız. Bu, kullanıcı özellik sayfasında değişiklik yapar etmez Şimdi Uygula düğmesini etkinleştirecektir.

Kullanıcı Şimdi Uygula düğmesini tıklattığında programınızın hangi eylemi yaptığını belirtmek için bu üye işlevini geçersiz kılın. Geçersiz kılınırken, işlev değişiklikleri kabul etmek için TRUE ve değişikliklerin etkili olmasını önlemek için FALSE döndürmelidir.

Çağrıların `OnApply` `OnOK`varsayılan uygulaması.

Kullanıcı bir özellik sayfasında Ki Şimdi Uygula veya Tamam düğmesine bastığında gönderilen bildirim iletileri hakkında daha fazla bilgi için Windows SDK'daki [PSN_APPLY](/windows/win32/Controls/psn-apply) bakın.

### <a name="example"></a>Örnek

  CPropertyPage örneğine [bakın::OnOK](#onok).

## <a name="cpropertypageoncancel"></a><a name="oncancel"></a>CpropertyPage::OnCancel

Bu üye işlev, İptal düğmesi seçildiğinde çerçeve tarafından çağrılır.

```
virtual void OnCancel();
```

### <a name="remarks"></a>Açıklamalar

İptal düğmesi eylemlerini gerçekleştirmek için bu üye işlevi geçersiz kılın. Varsayılan, yapılan değişiklikleri geçersiz kıldığı için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]

## <a name="cpropertypageonkillactive"></a><a name="onkillactive"></a>CpropertyPage::OnKillActive

Bu üye işlev, sayfa artık etkin sayfa olmadığında çerçeve tarafından çağrılır.

```
virtual BOOL OnKillActive();
```

### <a name="return-value"></a>Dönüş Değeri

Veri başarıyla güncelleştirildiyse sıfır olmayan, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Özel veri doğrulama görevleri gerçekleştirmek için bu üye işlevi geçersiz kılın.

Bu üye işlevin varsayılan uygulaması, özellik sayfasındaki denetimlerden özellik sayfasının üye değişkenlerine kadar ayarları kopyalar. Bir iletişim veri doğrulama (DDV) hatası nedeniyle veriler başarıyla güncelleştirilmediyse, sayfa odağı korur.

Bu üye işlev başarıyla döndükten sonra, çerçeve sayfanın [OnOK](#onok) işlevini çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]

## <a name="cpropertypageonok"></a><a name="onok"></a>CpropertyPage::OnOK

Bu üye işlev, kullanıcı Ok veya Şimdi Uygula düğmesini seçtiğinde, çerçeve [OnKillActive'i](#onkillactive)çağırdıktan hemen sonra çerçeve tarafından çağrılır.

```
virtual void OnOK();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı Tamam veya Şimdi Uygula düğmesini seçtiğinde, çerçeve özellik sayfasından [PSN_APPLY](/windows/win32/Controls/psn-apply) bildirimi alır. Özellik sayfası `OnOK` bu durumda bildirimi göndermediği için [CPropertySheet::PressButton'ı](../../mfc/reference/cpropertysheet-class.md#pressbutton) ararsanız çağrı yapılmaz.

Kullanıcı tüm özellik sayfasını reddettiğinde, şu anda etkin olan sayfaya özgü ek davranış uygulamak için bu üye işlevini geçersiz kılın.

Bu üye işlevin varsayılan uygulaması, verilerin `OnKillActive` işlevde güncelleştirileni yansıtacak şekilde sayfayı "temiz" olarak işaretler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]

## <a name="cpropertypageonquerycancel"></a><a name="onquerycancel"></a>CpropertyPage::OnQueryCancel

Bu üye işlevi, kullanıcı İptal düğmesini tıklattığında ve iptal eylemi gerçekleşmeden önce çerçeve tarafından çağrılır.

```
virtual BOOL OnQueryCancel();
```

### <a name="return-value"></a>Dönüş Değeri

İptal işlemini önlemek için FALSE veya izin vermek için TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanıcı İptal düğmesini tıklattığında programın aldığı bir eylemi belirtmek için bu üye işlevini geçersiz kılın.

True döndürür `OnQueryCancel` varsayılan uygulaması.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]

## <a name="cpropertypageonreset"></a><a name="onreset"></a>CPropertyPage::OnReset

Kullanıcı İptal düğmesini seçtiğinde bu üye işlev çerçeve tarafından çağrılır.

```
virtual void OnReset();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve bu işlevi aradığında, daha önce Şimdi Uygula düğmesini seçen kullanıcı tarafından yapılan tüm özellik sayfalarındayapılan değişiklikler atılır ve özellik sayfası odağı korur.

Kullanıcı İptal düğmesini tıklattığında programın hangi eylemi yaptığını belirtmek için bu üye işlevini geçersiz kılın.

Varsayılan uygulama `OnReset` hiçbir şey yapmaz.

### <a name="example"></a>Örnek

  CPropertyPage örneğine [bakın::OnCancel](#oncancel).

## <a name="cpropertypageonsetactive"></a><a name="onsetactive"></a>Cpropertypage::Onsetactive

Bu üye işlev, sayfa kullanıcı tarafından seçildiğinde ve etkin sayfa olduğunda çerçeve tarafından çağrılır.

```
virtual BOOL OnSetActive();
```

### <a name="return-value"></a>Dönüş Değeri

Sayfa başarıyla etkin olarak ayarlanmışsa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir sayfa etkinleştirildiğinde görevleri gerçekleştirmek için bu üye işlevi geçersiz kılın. Bu üye işlevin geçersiz kılınması, sayfa denetimlerini yeni verilerle güncelleştirmesine izin vermek için genellikle veri üyelerini güncelleştirmeden sonra varsayılan sürümü çağırır.

Varsayılan uygulama, daha önce oluşturulmamadıysa sayfa için pencere oluşturur ve onu etkin sayfa yapar.

### <a name="example"></a>Örnek

  CPropertySheet örneğine [bakın:SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext).

## <a name="cpropertypageonwizardback"></a><a name="onwizardback"></a>CpropertyPage::OnWizardback

Bu üye işlev, kullanıcı bir sihirbazda Geri Düğmesini tıklattığında çerçeve tarafından çağrılır.

```
virtual LRESULT OnWizardBack();
```

### <a name="return-value"></a>Dönüş Değeri

0 otomatik olarak bir sonraki sayfaya ilerlemek için; -1 sayfanın değişmesini önlemek için. Bir sonrakisayfadan başka bir sayfaya atlamak için, görüntülenecek iletişim kutusunun tanımlayıcısını döndürün.

### <a name="remarks"></a>Açıklamalar

Geri düğmesine basıldığında kullanıcının yapması gereken bazı eylemlerbelirtmek için bu üye işlevini geçersiz kılın.

Sihirbaz türünde bir özellik sayfasının nasıl yapılacağını hakkında daha fazla bilgi için [Bkz. CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]

## <a name="cpropertypageonwizardfinish"></a><a name="onwizardfinish"></a>CpropertyPage::OnwizardFinish

Bu üye işlev, kullanıcı bir sihirbazda Finish düğmesini tıklattığında çerçeve tarafından çağrılır.

```
virtual BOOL OnWizardFinish();
```

### <a name="return-value"></a>Dönüş Değeri

Sihirbaz bittiğinde özellik sayfası yok edilirse sıfırolmayan; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Bir kullanıcı sihirbazda **Bitiş** düğmesini tıklattığında, çerçeve bu işlevi çağırır; TRUE `OnWizardFinish` (sıfır olmayan bir değer) döndürdüğünde, özellik sayfası yok edilebilir (ancak gerçekte yok edilmez). Mülkiyet `DestroyWindow` sayfasını yok etmek için arayın. `DestroyWindow` Aramayın; `OnWizardFinish` bunu yapmak yığın bozulmasına veya diğer hatalara neden olur.

Bitiş düğmesine basıldığında kullanıcının yapması gereken bazı eylemlerbelirtmek için bu üye işlevini geçersiz kılabilirsiniz. Bu işlevi geçersiz kılarak, özellik sayfasının yok olmasını önlemek için FALSE döndürün.

Kullanıcı sihirbaz özellik sayfasında Kiİşleme düğmesine bastığında gönderilen bildirim iletileri hakkında daha fazla bilgi için Windows SDK'daki [PSN_WIZFINISH](/windows/win32/Controls/psn-wizfinish) bakın.

Sihirbaz türünde bir özellik sayfasının nasıl yapılacağını hakkında daha fazla bilgi için [Bkz. CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]

[!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]

[!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]

[!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]

## <a name="cpropertypageonwizardnext"></a><a name="onwizardnext"></a>CpropertyPage::OnWizardNext

Bu üye işlev, kullanıcı bir sihirbazda İleri düğmesini tıklattığında çerçeve tarafından çağrılır.

```
virtual LRESULT OnWizardNext();
```

### <a name="return-value"></a>Dönüş Değeri

0 otomatik olarak bir sonraki sayfaya ilerlemek için; -1 sayfanın değişmesini önlemek için. Bir sonrakisayfadan başka bir sayfaya atlamak için, görüntülenecek iletişim kutusunun tanımlayıcısını döndürün.

### <a name="remarks"></a>Açıklamalar

İleri düğmesine basıldığında kullanıcının yapması gereken bazı eylemlerbelirtmek için bu üye işlevini geçersiz kılın.

Sihirbaz türünde bir özellik sayfasının nasıl yapılacağını hakkında daha fazla bilgi için [Bkz. CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]

## <a name="cpropertypagequerysiblings"></a><a name="querysiblings"></a>CPropertyPage::QuerySiblings

Özellik sayfasındaki her sayfaya bir ileti iletmek için bu üye işlevini arayın.

```
LRESULT QuerySiblings(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*Wparam*<br/>
İletiye bağımlı ek bilgileri belirtir.

*Lparam*<br/>
İletiye bağımlı ek bilgileri belirtir

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfasındaki bir sayfadan sıfır olmayan değer veya tüm sayfalar 0 değeri döndürüyorsa 0.

### <a name="remarks"></a>Açıklamalar

Bir sayfa sıfır olmayan bir değer döndürürse, özellik sayfası iletiyi sonraki sayfalara göndermez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]

[!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]

## <a name="cpropertypagesetmodified"></a><a name="setmodified"></a>CpropertyPage::Setmodi

Özellik sayfasındaki ayarların uygun dış nesneye uygulanıp uygulanmayacağına bağlı olarak Şimdi Uygula düğmesini etkinleştirmek veya devre dışı etmek için bu üye işlevini arayın.

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>Parametreler

*b Değiştirildi*<br/>
Özellik sayfası ayarlarının son uygulandığından beri değiştirildiğini belirtmek için TRUE; Özellik sayfası ayarlarının uygulandığını veya yoksayılması gerektiğini belirtmek için FALSE.

### <a name="remarks"></a>Açıklamalar

Çerçeve, hangi sayfaların "kirli" olduğunu, yani sizin için `SetModified( TRUE )`çağırdığınız özellik sayfalarını izler. Sayfalardan birini ararsanız `SetModified( TRUE )` Şimdi Uygula düğmesi her zaman etkinleştirilir. Şimdi Uygula düğmesi, sayfalardan `SetModified( FALSE )` birini aradiğinizde, ancak diğer sayfaların hiçbiri "kirli" değilse devre dışı bırakılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Numune CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[MFC Numune CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPropertySheet Sınıfı](../../mfc/reference/cpropertysheet-class.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
