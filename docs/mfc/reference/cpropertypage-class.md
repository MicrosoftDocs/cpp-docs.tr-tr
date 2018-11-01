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
ms.openlocfilehash: 1816e6ee2dc0f358cb2da4c8bab572daa33a29c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561245"
---
# <a name="cpropertypage-class"></a>CPropertyPage sınıfı

Aksi takdirde bir sekme iletişim kutusu bilinen bir özellik sayfası, her bir sayfayı temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CPropertyPage : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPropertyPage::CPropertyPage](#cpropertypage)|Oluşturur bir `CPropertyPage` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPropertyPage::CancelToClose](#canceltoclose)|Kapat okumak için Tamam düğmesine değiştirir ve bir kalıcı özellik sayfasını sayfasında kurtarılamaz bir değişiklikten sonra iptal düğmesi devre dışı bırakır.|
|[CPropertyPage::Construct](#construct)|Oluşturur bir `CPropertyPage` nesne. Kullanım `Construct` parametrelerinizi çalışma zamanında belirtmek istiyorsanız veya diziler kullanıyorsanız.|
|[CPropertyPage::GetPSP](#getpsp)|Windows alır [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-_propsheetpagea_v2) yapısı ile ilişkili `CPropertyPage` nesne.|
|[CPropertyPage::OnApply](#onapply)|Şimdi Uygula düğmesine tıklandığında framework tarafından çağırılır.|
|[CPropertyPage::OnCancel](#oncancel)|İptal düğmesine tıklandığında framework tarafından çağırılır.|
|[CPropertyPage::OnKillActive](#onkillactive)|Geçerli sayfa artık etkin sayfa gerektiğinde framework tarafından çağırılır. Veri doğrulama gerçekleştirin.|
|[CPropertyPage::OnOK](#onok)|Tamam, şimdi Uygula ya da Kapat düğmesine tıklandığında framework tarafından çağırılır.|
|[CPropertyPage::OnQueryCancel](#onquerycancel)|İptal düğmesine tıklandığında ve iptal etme gerçekleşmemişken framework tarafından çağırılır.|
|[CPropertyPage::OnReset](#onreset)|İptal düğmesine tıklandığında framework tarafından çağırılır.|
|[CPropertyPage::OnSetActive](#onsetactive)|Sayfa etkin sayfa yapıldığında framework tarafından çağırılır.|
|[CPropertyPage::OnWizardBack](#onwizardback)|Sihirbaz türü özellik sayfası kullanılırken geri düğmesine tıklandığında framework tarafından çağırılır.|
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|Sihirbaz türü özellik sayfası kullanılırken Son düğmesine tıklandığında framework tarafından çağırılır.|
|[CPropertyPage::OnWizardNext](#onwizardnext)|Sihirbaz türü özellik sayfası kullanılırken İleri düğmesine tıklandığında framework tarafından çağırılır.|
|[CPropertyPage::QuerySiblings](#querysiblings)|İletinin özellik sayfasının her sayfaya iletir.|
|[CPropertyPage::SetModified](#setmodified)|Etkinleştirme veya devre dışı şimdi Uygula düğmesine çağırın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPropertyPage::m_psp](#m_psp)|Windows [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-_propsheetpagea_v2) yapısı. Temel özellik sayfa parametrelerini erişim sağlar.|

## <a name="remarks"></a>Açıklamalar

Standart iletişim kutuları, öğesinden bir sınıf türetin gibi `CPropertyPage` , özellik sayfasında her sayfa için. Kullanılacak `CPropertyPage`-türetilmiş nesneler, ilk oluşturmak bir [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) nesnesi ve ardından özellik sayfasında giden her sayfa için bir nesne oluşturun. Çağrı [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage) her sayfada sayfasında ve özellik sayfası çağırarak görüntülemek [CPropertySheet::DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) bir kalıcı özellik sayfası için veya [CPropertySheet:: Oluşturma](../../mfc/reference/cpropertysheet-class.md#create) modelsiz bir özellik sayfası için.

Sekme iletişim kutusu, kullanıcı cihazı kurarken ya da bir bülten oluşturma gibi bir işlemin adımlarında rehberlik özellik sayfaları dizisi ile bir özellik sayfasından oluşan bir sihirbaz adlı bir türünü oluşturabilirsiniz. Sihirbaz türü sekme iletişim kutusu, özellik sayfaları sekmeleri yoktur ve aynı anda yalnızca bir özellik sayfası görünür. Ayrıca, Tamam ve şimdi Uygula düğmeleri sahip olmak yerine, bir sihirbaz türü sekme iletişim kutusu geri düğmesi, bir sonraki veya Son'a düğmesi ve iptal düğmesi var.

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

Veriler bir kalıcı özellik sayfasının bir sayfa üzerinde kurtarılamaz bir değişiklik yapıldıktan sonra bu işlevi çağırın.

```
void CancelToClose();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, Tamam düğmesine yakın bir değiştirme ve iptal düğmesi devre dışı bırakın. Bu uyarılar kullanıcının kalıcı bir işlemdir ve değişiklikleri bir değişikliktir iptal edilemez değiştirin.

`CancelToClose` Üye işlev hiçbir şey yapmaz kalıcı olmayan özellik sayfası, çünkü kalıcı olmayan özellik sayfası varsayılan olarak bir iptal düğmesi yok.

### <a name="example"></a>Örnek

  Örneğin bakın [CPropertyPage::QuerySiblings](#querysiblings).

##  <a name="construct"></a>  CPropertyPage::Construct

Oluşturmak için bu üye işlevi çağrısı bir `CPropertyPage` nesne.

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
Bu sayfa için sekmesinde yerleştirilecek adı kimliği. 0 ise, bu sayfa için iletişim kutusu şablonundan adı alınır.

*lpszTemplateName*<br/>
Bir şablon kaynağı adı null ile sonlandırılmış bir dize içerir.

*nIDHeaderTitle*<br/>
Özellik sayfa üstbilgisi başlık konumunu yerleştirilecek adı kimliği. Varsayılan olarak, 0.

*nIDHeaderSubTitle*<br/>
Özellik sayfa üstbilgisi alt konu başlığını konumunu yerleştirilecek adı kimliği. Varsayılan olarak, 0.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki koşulların tümü yerine getirildikten sonra nesneyi görüntülenir:

- Kullanarak bir özellik sayfası sayfası eklendi [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).

- Özellik Sayfası'nın [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) veya [Oluştur](../../mfc/reference/cpropertysheet-class.md#create) işlevini çağırdı.

- Kullanıcının seçtiği (sekmeli) bu sayfa.

Çağrı `Construct` bir sınıf oluşturucuları birini çağrılmadıysa durumunda. `Construct` Üye işlevi, parametre ifadesi boş bırakın ve ardından birden çok parametre ve herhangi bir noktada yapım kodunuzda belirtin çünkü esnektir.

Kullanmalısınız `Construct` ne zaman dizilerle çalışır ve çağırmalısınız `Construct` dizinin her üyesi için veri üyeleri, uygun değerler atanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]

##  <a name="cpropertypage"></a>  CPropertyPage::CPropertyPage

Oluşturur bir `CPropertyPage` nesne.

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
Bu sayfa için sekmesinde yerleştirilecek adı kimliği. 0 ise, bu sayfa için iletişim kutusu şablonundan adı alınır.

*dwSize*<br/>
*lpszTemplateName* bu sayfa için şablon adını içeren bir dize işaret eder. NULL olamaz.

*nIDHeaderTitle*<br/>
Özellik sayfa üstbilgisi başlık konumunu yerleştirilecek adı kimliği.

*nIDHeaderSubTitle*<br/>
Özellik sayfa üstbilgisi alt konu başlığını konumunu yerleştirilecek adı kimliği.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki koşulların tümü yerine getirildikten sonra nesneyi görüntülenir:

- Kullanarak bir özellik sayfası sayfası eklendi [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).

- Özellik Sayfası'nın [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) veya [Oluştur](../../mfc/reference/cpropertysheet-class.md#create) işlevini çağırdı.

- Kullanıcının seçtiği (sekmeli) bu sayfa.

Birden çok parametre (örneğin, bir dizi kullanıyorsa) varsa, [CPropertySheet::Construct](../../mfc/reference/cpropertysheet-class.md#construct) yerine `CPropertyPage`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]

##  <a name="getpsp"></a>  CPropertyPage::GetPSP

Windows alır [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-_propsheetpagea_v2) yapısı ile ilişkili `CPropertyPage` nesne.

```
const PROPSHEETPAGE& GetPSP() const;

PROPSHEETPAGE& GetPSP();
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru `PROPSHEETPAGE` yapısı.

##  <a name="m_psp"></a>  CPropertyPage::m_psp

`m_psp` bir yapı üyeleri özelliklerini depolamak [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-_propsheetpagea_v2).

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Açıklamalar

Bu yapı, oluşturduğu sonra bir özellik sayfasının görünümünü başlatmak için kullanın.

Bu grubun üyeleri listesi dahil olmak üzere, bu yapı hakkında daha fazla bilgi için bkz. `PROPSHEETPAGE` Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]

##  <a name="onapply"></a>  CPropertyPage::OnApply

Bu üye işlevi kullanıcı Tamam'ı veya şimdi Uygula düğmesini seçtiğinde framework tarafından çağırılır.

```
virtual BOOL OnApply();
```

### <a name="return-value"></a>Dönüş Değeri

Değişiklikler kabul edilirse sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Framework bu işlevini çağırdığında, özellik sayfasında tüm özellik sayfalarındaki yapılan değişiklikler kabul edilir, özellik sayfası odağını korur ve `OnApply` (değer 1) TRUE döndürür. Önce `OnApply` volat jen tehdy çerçeve tarafından çağrısı yapmanız gerekir [SetModified](#setmodified) ve onun parametresi TRUE olarak ayarlayın. Özellik sayfasında bir değişiklik kullanıcının yaptığı hemen sonra bu şimdi Uygula düğmesi etkinleşir.

Bu üye işlevi, kullanıcı şimdi Uygula düğmesine tıkladığında, programınızın gereken eylemi belirtmek için geçersiz kılın. Geçersiz kılarken, işlev değişiklikleri kabul etmek için TRUE ve FALSE, değişiklikler etkili fotoğrafını çekmenizi engellemek için döndürmelidir.

Varsayılan uygulaması `OnApply` çağrıları `OnOK`.

Kullanıcı bir özellik sayfasında şimdi Uygula veya Tamam düğmesine bastığında gönderilen bildirim iletileri hakkında daha fazla bilgi için bkz: [PSN_APPLY](/windows/desktop/Controls/psn-apply) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CPropertyPage::OnOK](#onok).

##  <a name="oncancel"></a>  CPropertyPage::OnCancel

İptal düğmesi seçildiğinde bu üye işlevi framework tarafından çağırılır.

```
virtual void OnCancel();
```

### <a name="remarks"></a>Açıklamalar

İptal düğmesi eylemleri gerçekleştirmek için bu üye işlevini geçersiz kılar. Varsayılan yapılmış değişiklikleri olumsuz duruma getirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]

##  <a name="onkillactive"></a>  CPropertyPage::OnKillActive

Sayfa artık etkin sayfa olduğunda bu üye işlevi framework tarafından çağırılır.

```
virtual BOOL OnKillActive();
```

### <a name="return-value"></a>Dönüş Değeri

Veriler başarıyla güncelleştirildi olursa sıfır dışı Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, özel veri doğrulama görevleri gerçekleştirmek için geçersiz kılın.

Bu üye işlevinin varsayılan uygulama ayarları özellik sayfasını denetimlerinde özellik sayfası için üye değişkenleri kopyalar. Verileri bir iletişim kutusu veri doğrulama (DDV) hatası nedeniyle başarıyla güncelleştirilmedi, sayfanın odağını korur.

Bu üye işlevi başarıyla döndükten sonra sayfanın framework göndereceği [OnOK](#onok) işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]

##  <a name="onok"></a>  CPropertyPage::OnOK

Kullanıcı framework çağrıları hemen sonra Tamam'ı veya şimdi Uygula düğmesini seçtiğinde framework tarafından bu üye işlevi çağrılan [OnKillActive](#onkillactive).

```
virtual void OnOK();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı, Tamam'ı veya şimdi Uygula düğmesini seçtiğinde framework alır [PSN_APPLY](/windows/desktop/Controls/psn-apply) özellik sayfasından bildirim. Çağrı `OnOK` çağırırsanız yapılan olmaz [CPropertySheet::PressButton](../../mfc/reference/cpropertysheet-class.md#pressbutton) çünkü özellik sayfası bu durumda bildirim göndermez.

Tüm özellik sayfası kullanıcı atar, o anda etkin sayfaya özgü ek davranışı uygulamak için bu üye işlevi geçersiz kılar.

Bu üye işlevinin varsayılan uygulama sayfası, verilerin güncelleştirildiği yansıtmak için "clean" olarak işaretler `OnKillActive` işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]

##  <a name="onquerycancel"></a>  CPropertyPage::OnQueryCancel

Bu üye işlevi kullanıcı iptal düğmesine tıklar ve önce iptal etme eylemi devre dışı yapıldığının framework tarafından çağırılır.

```
virtual BOOL OnQueryCancel();
```

### <a name="return-value"></a>Dönüş Değeri

İzin vermek için TRUE ya da iptal işlemini engellemek için false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanıcı iptal düğmesine tıkladığında programın aldığı eylemi belirtmek için bu üye işlevini geçersiz kılar.

Varsayılan uygulaması `OnQueryCancel` TRUE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]

##  <a name="onreset"></a>  CPropertyPage::OnReset

Bu üye işlevi, kullanıcı İptal düğmesini seçtiğinde framework tarafından çağırılır.

```
virtual void OnReset();
```

### <a name="remarks"></a>Açıklamalar

Framework bu işlevini çağırdığında, daha önce şimdi Uygula düğmesini seçerek kullanıcı tarafından yapılan tüm özellik sayfalarını değişiklikler atılır ve özellik sayfası odağını korur.

Kullanıcı iptal düğmesine tıkladığında programın aldığı eylemi belirtmek için bu üye işlevini geçersiz kılar.

Varsayılan uygulaması `OnReset` hiçbir şey yapmaz.

### <a name="example"></a>Örnek

  Örneğin bakın [CPropertyPage::OnCancel](#oncancel).

##  <a name="onsetactive"></a>  CPropertyPage::OnSetActive

Sayfa kullanıcı tarafından seçilir ve etkin sayfa olur, bu üye işlevi framework tarafından çağırılır.

```
virtual BOOL OnSetActive();
```

### <a name="return-value"></a>Dönüş Değeri

Sayfa başarıyla active ayarlandığını olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi bir sayfa etkinleştirildiğinde görevleri gerçekleştirmek için geçersiz kılın. Bu üye işlevin geçersiz kılma, genellikle veri üyeleri, sayfa denetimleri yeni veriler ile güncelleştirmek için izin vermek için güncelleştirdikten sonra varsayılan sürüm çağırırsınız.

Varsayılan uygulama, sayfa için bir pencere oluşturur yoksa daha önce oluşturduğunuz ve etkin sayfa kolaylaştırır.

### <a name="example"></a>Örnek

  Örneğin bakın [CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext).

##  <a name="onwizardback"></a>  CPropertyPage::OnWizardBack

Bu üye işlevi bir sihirbaz geri düğmesine tıkladığında framework tarafından çağırılır.

```
virtual LRESULT OnWizardBack();
```

### <a name="return-value"></a>Dönüş Değeri

otomatik olarak sonraki sayfaya ilerlemek için 0; sayfayı değiştirmesini engellemek için -1. Dışında bir sonraki sayfasına atlamak için görüntülenecek iletişim kutusunun tanımlayıcısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanıcı geri düğmesine basıldığında almalıdır bazı eylemleri belirtmek için bu üye işlevini geçersiz kılar.

Sihirbaz türü özellik sayfası yapma hakkında daha fazla bilgi için bkz. [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]

##  <a name="onwizardfinish"></a>  CPropertyPage::OnWizardFinish

Bu üye işlevi bir sihirbaz Son düğmesine tıkladığında framework tarafından çağırılır.

```
virtual BOOL OnWizardFinish();
```

### <a name="return-value"></a>Dönüş Değeri

Sihirbaz sona erdiğinde özellik sayfası yok olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Kullanıcı tıkladığında **son** framework bir sihirbaz düğmesi bu işlevi çağırır; `OnWizardFinish` döndürür TRUE (sıfır olmayan bir değer), özellik sayfası yok edilecek bulabildiği (ancak aslında yok). Çağrı `DestroyWindow` özellik sayfası yok edilemiyor. Çağırmayın `DestroyWindow` gelen `OnWizardFinish`; bunu yaptığınızda bu nedenle neden olacak yığın bozulması veya diğer hatalar.

Kullanıcının son düğmesine basıldığında almalıdır bazı eylemleri belirtmek için bu üye işlevini geçersiz kılabilirsiniz. Bu işlev geçersiz kılarken, özellik sayfası yok ediliyor önlemek için FALSE döndürür.

Kullanıcı bir sihirbaz özellik sayfasında son düğmesine bastığında gönderilen bildirim iletileri hakkında daha fazla bilgi için bkz. [PSN_WIZFINISH](/windows/desktop/Controls/psn-wizfinish) Windows SDK.

Sihirbaz türü özellik sayfası yapma hakkında daha fazla bilgi için bkz. [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]

[!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]

[!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]

[!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]

##  <a name="onwizardnext"></a>  CPropertyPage::OnWizardNext

Bu üye işlevi kullanıcı sihirbazdaki İleri düğmesine tıkladığında framework tarafından çağırılır.

```
virtual LRESULT OnWizardNext();
```

### <a name="return-value"></a>Dönüş Değeri

otomatik olarak sonraki sayfaya ilerlemek için 0; sayfayı değiştirmesini engellemek için -1. Dışında bir sonraki sayfasına atlamak için görüntülenecek iletişim kutusunun tanımlayıcısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanıcı, İleri düğmesine basıldığında almalıdır bazı eylemleri belirtmek için bu üye işlevini geçersiz kılar.

Sihirbaz türü özellik sayfası yapma hakkında daha fazla bilgi için bkz. [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]

##  <a name="querysiblings"></a>  CPropertyPage::QuerySiblings

Özellik sayfasında her sayfa için bir ileti iletmek için bu üye işlevini çağırın.

```
LRESULT QuerySiblings(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*wParam*<br/>
Ek ileti bağımlı bilgileri belirtir.

*lParam*<br/>
Ek ileti bağımlı bilgi belirtir

### <a name="return-value"></a>Dönüş Değeri

Sıfır dışında bir değeri özellik sayfası veya 0 ise sayfasından tüm sayfaları 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası bir sayfa sıfır olmayan bir değer döndürürse, iletiyi sonraki sayfalara göndermez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]

[!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]

##  <a name="setmodified"></a>  CPropertyPage::SetModified

Etkinleştirmek veya özellik sayfası ayarları için uygun dış nesne uygulanmalıdır olup göre şimdi Uygula düğmesini devre dışı bırakmak için bu üye işlevini çağırın.

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>Parametreler

*bChanged*<br/>
Özellik sayfası ayarları uygulanmış olan son daraltılmasından değiştirilmiş belirtmek için TRUE; Özellik sayfası ayarları uygulanmış veya yoksayılıp yoksayılmaması gerektiğini belirtmek için FALSE.

### <a name="remarks"></a>Açıklamalar

Framework tutar izleme hangi sayfaların "kirli" diğer bir deyişle, kendisi için aradığınız özellik sayfaları `SetModified( TRUE )`. Şimdi Uygula düğmesine her zaman çağırırsanız etkinleştirilecek `SetModified( TRUE )` birinin sayfaların. Çağırdığınızda şimdi Uygula düğmesine devre dışı bırakılacak `SetModified( FALSE )` yalnızca diğer sayfalardan hiçbiri "." kirli, ancak sayfalardan biri için

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek CMNCTRL1](../../visual-cpp-samples.md)<br/>
[MFC örnek CMNCTRL2](../../visual-cpp-samples.md)<br/>
[MFC örnek PROPDLG](../../visual-cpp-samples.md)<br/>
[MFC örnek SNAPVW](../../visual-cpp-samples.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPropertySheet Sınıfı](../../mfc/reference/cpropertysheet-class.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
