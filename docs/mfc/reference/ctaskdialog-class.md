---
title: CTaskDialog Sınıfı
ms.date: 11/19/2018
f1_keywords:
- CTaskDialog
- AFXTASKDIALOG/CTaskDialog
- AFXTASKDIALOG/CTaskDialog::CTaskDialog
- AFXTASKDIALOG/CTaskDialog::AddCommandControl
- AFXTASKDIALOG/CTaskDialog::AddRadioButton
- AFXTASKDIALOG/CTaskDialog::ClickCommandControl
- AFXTASKDIALOG/CTaskDialog::ClickRadioButton
- AFXTASKDIALOG/CTaskDialog::DoModal
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonCount
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonFlag
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonId
- AFXTASKDIALOG/CTaskDialog::GetOptions
- AFXTASKDIALOG/CTaskDialog::GetSelectedCommandControlID
- AFXTASKDIALOG/CTaskDialog::GetSelectedRadioButtonID
- AFXTASKDIALOG/CTaskDialog::GetVerificationCheckboxState
- AFXTASKDIALOG/CTaskDialog::IsCommandControlEnabled
- AFXTASKDIALOG/CTaskDialog::IsRadioButtonEnabled
- AFXTASKDIALOG/CTaskDialog::IsSupported
- AFXTASKDIALOG/CTaskDialog::LoadCommandControls
- AFXTASKDIALOG/CTaskDialog::LoadRadioButtons
- AFXTASKDIALOG/CTaskDialog::NavigateTo
- AFXTASKDIALOG/CTaskDialog::OnCommandControlClick
- AFXTASKDIALOG/CTaskDialog::OnCreate
- AFXTASKDIALOG/CTaskDialog::OnDestroy
- AFXTASKDIALOG/CTaskDialog::OnExpandButtonClick
- AFXTASKDIALOG/CTaskDialog::OnHelp
- AFXTASKDIALOG/CTaskDialog::OnHyperlinkClick
- AFXTASKDIALOG/CTaskDialog::OnInit
- AFXTASKDIALOG/CTaskDialog::OnNavigatePage
- AFXTASKDIALOG/CTaskDialog::OnRadioButtonClick
- AFXTASKDIALOG/CTaskDialog::OnTimer
- AFXTASKDIALOG/CTaskDialog::OnVerificationCheckboxClick
- AFXTASKDIALOG/CTaskDialog::RemoveAllCommandControls
- AFXTASKDIALOG/CTaskDialog::RemoveAllRadioButtons
- AFXTASKDIALOG/CTaskDialog::SetCommandControlOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtons
- AFXTASKDIALOG/CTaskDialog::SetContent
- AFXTASKDIALOG/CTaskDialog::SetDefaultCommandControl
- AFXTASKDIALOG/CTaskDialog::SetDefaultRadioButton
- AFXTASKDIALOG/CTaskDialog::SetDialogWidth
- AFXTASKDIALOG/CTaskDialog::SetExpansionArea
- AFXTASKDIALOG/CTaskDialog::SetFooterIcon
- AFXTASKDIALOG/CTaskDialog::SetFooterText
- AFXTASKDIALOG/CTaskDialog::SetMainIcon
- AFXTASKDIALOG/CTaskDialog::SetMainInstruction
- AFXTASKDIALOG/CTaskDialog::SetOptions
- AFXTASKDIALOG/CTaskDialog::SetProgressBarMarquee
- AFXTASKDIALOG/CTaskDialog::SetProgressBarPosition
- AFXTASKDIALOG/CTaskDialog::SetProgressBarRange
- AFXTASKDIALOG/CTaskDialog::SetProgressBarState
- AFXTASKDIALOG/CTaskDialog::SetRadioButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckbox
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckboxText
- AFXTASKDIALOG/CTaskDialog::SetWindowTitle
- AFXTASKDIALOG/CTaskDialog::ShowDialog
- AFXTASKDIALOG/CTaskDialog::TaskDialogCallback
helpviewer_keywords:
- CTaskDialog [MFC], CTaskDialog
- CTaskDialog [MFC], AddCommandControl
- CTaskDialog [MFC], AddRadioButton
- CTaskDialog [MFC], ClickCommandControl
- CTaskDialog [MFC], ClickRadioButton
- CTaskDialog [MFC], DoModal
- CTaskDialog [MFC], GetCommonButtonCount
- CTaskDialog [MFC], GetCommonButtonFlag
- CTaskDialog [MFC], GetCommonButtonId
- CTaskDialog [MFC], GetOptions
- CTaskDialog [MFC], GetSelectedCommandControlID
- CTaskDialog [MFC], GetSelectedRadioButtonID
- CTaskDialog [MFC], GetVerificationCheckboxState
- CTaskDialog [MFC], IsCommandControlEnabled
- CTaskDialog [MFC], IsRadioButtonEnabled
- CTaskDialog [MFC], IsSupported
- CTaskDialog [MFC], LoadCommandControls
- CTaskDialog [MFC], LoadRadioButtons
- CTaskDialog [MFC], NavigateTo
- CTaskDialog [MFC], OnCommandControlClick
- CTaskDialog [MFC], OnCreate
- CTaskDialog [MFC], OnDestroy
- CTaskDialog [MFC], OnExpandButtonClick
- CTaskDialog [MFC], OnHelp
- CTaskDialog [MFC], OnHyperlinkClick
- CTaskDialog [MFC], OnInit
- CTaskDialog [MFC], OnNavigatePage
- CTaskDialog [MFC], OnRadioButtonClick
- CTaskDialog [MFC], OnTimer
- CTaskDialog [MFC], OnVerificationCheckboxClick
- CTaskDialog [MFC], RemoveAllCommandControls
- CTaskDialog [MFC], RemoveAllRadioButtons
- CTaskDialog [MFC], SetCommandControlOptions
- CTaskDialog [MFC], SetCommonButtonOptions
- CTaskDialog [MFC], SetCommonButtons
- CTaskDialog [MFC], SetContent
- CTaskDialog [MFC], SetDefaultCommandControl
- CTaskDialog [MFC], SetDefaultRadioButton
- CTaskDialog [MFC], SetDialogWidth
- CTaskDialog [MFC], SetExpansionArea
- CTaskDialog [MFC], SetFooterIcon
- CTaskDialog [MFC], SetFooterText
- CTaskDialog [MFC], SetMainIcon
- CTaskDialog [MFC], SetMainInstruction
- CTaskDialog [MFC], SetOptions
- CTaskDialog [MFC], SetProgressBarMarquee
- CTaskDialog [MFC], SetProgressBarPosition
- CTaskDialog [MFC], SetProgressBarRange
- CTaskDialog [MFC], SetProgressBarState
- CTaskDialog [MFC], SetRadioButtonOptions
- CTaskDialog [MFC], SetVerificationCheckbox
- CTaskDialog [MFC], SetVerificationCheckboxText
- CTaskDialog [MFC], SetWindowTitle
- CTaskDialog [MFC], ShowDialog
- CTaskDialog [MFC], TaskDialogCallback
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
ms.openlocfilehash: e9aeee31d2952d5362c983934ce85f0332f553fa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366643"
---
# <a name="ctaskdialog-class"></a>CTaskDialog Sınıfı

İleti kutusu gibi çalışan ancak kullanıcıya ek bilgiler görüntüleyebilen açılır iletişim kutusu. Ayrıca `CTaskDialog` kullanıcıdan bilgi toplamak için işlevsellik içerir.

## <a name="syntax"></a>Sözdizimi

```
class CTaskDialog : public CObject
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[CTaskDialog::CTaskDialog](#ctaskdialog)|Bir `CTaskDialog` nesne inşa eder.|

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CTaskDialog::AddCommandControl](#addcommandcontrol)|Komut düğmesi denetimi `CTaskDialog`ekler.|
|[CTaskDialog::AddRadioButton](#addradiobutton)|Bir radyo düğmesi `CTaskDialog`ekler.|
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|Komut düğmesi denetimini veya ortak düğmeyi programlı olarak tıklatıyor.|
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|Radyo düğmesini programlı olarak tıklatıyor.|
|[CTaskDialog::DoModal](#domodal)|Görüntüler `CTaskDialog`.|
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|Kullanılabilir ortak düğme sayısını alır.|
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|Standart bir Windows düğmesini `CTaskDialog` sınıfla ilişkili ortak düğme türüne dönüştürür.|
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|`CTaskDialog` Sınıfla ilişkili ortak düğme türlerinden birini standart bir Windows düğmesine dönüştürür.|
|[CTaskDialog::GetOptions](#getoptions)|Bunun `CTaskDialog`için seçenek bayraklarını döndürür.|
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|Seçili komut düğmesi denetimini döndürür.|
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|Seçili radyo düğmesini döndürür.|
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|Doğrulama onay kutusunun durumunu alır.|
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|Komut düğmesi denetiminin mi yoksa ortak düğmenin mi etkin olduğunu belirler.|
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|Radyo düğmesinin etkin olup olmadığını belirler.|
|[CTaskDialog::Desteklendi](#issupported)|Uygulamayı çalıştıran bilgisayarın `CTaskDialog`.|
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|Dize tablosundaki verileri kullanarak komut düğmesi denetimleri ekler.|
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|String tablosundaki verileri kullanarak radyo düğmeleri ekler.|
|[CTaskDialog::NavigateTo](#navigateto)|Odağı başka bir `CTaskDialog`şeye aktarın.|
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|Kullanıcı bir komut düğmesi denetimini tıklattığında çerçeve bu yöntemi çağırır.|
|[CTaskDialog::OnCreate](#oncreate)|Çerçeve, bu yöntemi oluşturduktan `CTaskDialog`sonra çağırır.|
|[CTaskDialog::OnDestroy](#ondestroy)|Çerçeve, bu yöntemi yok etmeden `CTaskDialog`hemen önce çağırır.|
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|Kullanıcı genişletme düğmesini tıklattığında çerçeve bu yöntemi çağırır.|
|[CTaskDialog::OnHelp](#onhelp)|Kullanıcı yardım istediğinde çerçeve bu yöntemi çağırır.|
|[CTaskDialog::OnHyperlinkTıklayın](#onhyperlinkclick)|Kullanıcı bir köprüye tıkladığında çerçeve bu yöntemi çağırır.|
|[CTaskDialog::OnInit](#oninit)|Çerçeve, baş harfe `CTaskDialog` geldiğinde bu yöntemi çağırır.|
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|Çerçeve, kullanıcı' nın denetimleri ile ilgili odağı `CTaskDialog`hareket ettirdiğinde bu yöntemi çağırır.|
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|Kullanıcı bir radyo düğmesi denetimi seçtiğinde çerçeve bu yöntemi çağırır.|
|[CTaskDialog::OnTimer](#ontimer)|Çerçeve, zamanlayıcının süresi dolduğunda bu yöntemi çağırır.|
|[CTaskDialog::OnVerificationCheckboxTıklayın](#onverificationcheckboxclick)|Kullanıcı doğrulama onay kutusunu tıklattığında çerçeve bu yöntemi çağırır.|
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|Tüm komut denetimlerini `CTaskDialog`.|
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|Tüm radyo düğmelerini `CTaskDialog`kaldırır.|
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|Bir komut düğmesi denetimini `CTaskDialog`güncelleştirir.|
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|Etkinleştirilmiş ve UAC yüksekliği gerektiren ortak düğmelerin bir alt kümesini güncelleştirir.|
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|`CTaskDialog`'ye ortak düğmeler ekler.|
|[CTaskDialog::SetContent](#setcontent)|İçeriği `CTaskDialog`güncelleştirir.|
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|Varsayılan komut düğmesi denetimini belirtir.|
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|Varsayılan radyo düğmesini belirtir.|
|[CTaskDialog::SetDialogGenişliği](#setdialogwidth)|Genişliği `CTaskDialog`ayarlar.|
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|`CTaskDialog`Genişletme alanını güncelleştirir.|
|[CTaskDialog::SetFooterIcon](#setfootericon)|Altbilgi simgesini `CTaskDialog`güncelleştirir.|
|[CTaskDialog::SetFooterText](#setfootertext)|Altbilgideki metni `CTaskDialog`güncelleştirir.|
|[CTaskDialog::SetMainIcon](#setmainicon)|Ana simgeyi `CTaskDialog`güncelleştirir.|
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|Günceller ana talimat `CTaskDialog`.|
|[CTaskDialog::SetOptions](#setoptions)|Için seçenekleri `CTaskDialog`yapılandırır.|
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|Bir seçim çerçevesi çubuğunu `CTaskDialog` yapılandırır ve iletişim kutusuna ekler.|
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|İlerleme çubuğunun konumunu ayarlar.|
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|İlerleme çubuğunun aralığını ayarlar.|
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|İlerleme çubuğunun durumunu ayarlar ve 'de `CTaskDialog`görüntüler.|
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|Radyo düğmesini etkinleştirir veya devre dışı kılabilir.|
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|Doğrulama onay kutusunun işaretli durumunu ayarlar.|
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|Metni doğrulama onay kutusunun sağ tarafında ayarlar.|
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|Başlığı `CTaskDialog`ayarlar.|
|[CTaskDialog::ShowDialog](#showdialog)|Oluşturur ve görüntüler. `CTaskDialog`|
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|Çerçeve, çeşitli Windows iletilerine yanıt olarak bunu çağırır.|

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|`m_aButtons`|Komut düğmesi denetimleri `CTaskDialog`dizisi.|
|`m_aRadioButtons`|Için radyo düğmesi denetimleri `CTaskDialog`dizisi.|
|`m_bVerified`|`TRUE`doğrulama onay kutusunun işaretli olduğunu gösterir; `FALSE` olmadığını gösterir.|
|`m_footerIcon`|Altbilgideki `CTaskDialog`simge.|
|`m_hWnd`|Için pencereye bir `CTaskDialog`tutamaç .|
|`m_mainIcon`|Ana simge `CTaskDialog`.|
|`m_nButtonDisabled`|Ortak düğmelerden hangisinin devre dışı bırakıldığını gösteren bir maske.|
|`m_nButtonElevation`|Ortak düğmelerden hangisinin UAC yüksekliği gerektirdiğini gösteren bir maske.|
|`m_nButtonId`|Seçili komut düğmesi denetiminin kimliği.|
|`m_nCommonButton`|`CTaskDialog`Üzerinde hangi ortak düğmelerin görüntülendiğini gösteren bir maske.|
|`m_nDefaultCommandControl`|Görüntülendiğinde seçilen komut düğmesi denetiminin `CTaskDialog` kimliği.|
|`m_nDefaultRadioButton`|Görüntülendiğinde seçilen radyo düğmesi denetiminin `CTaskDialog` kimliği.|
|`m_nFlags`|Için seçenekleri gösteren bir `CTaskDialog`maske.|
|`m_nProgressPos`|İlerleme çubuğu için geçerli konum.  Bu değer arasında `m_nProgressRangeMin` `m_nProgressRangeMax`ve .|
|`m_nProgressRangeMax`|İlerleme çubuğu için en büyük değer.|
|`m_nProgressRangeMin`|İlerleme çubuğu için minimum değer.|
|`m_nProgressState`|İlerleme çubuğunun durumu. Daha fazla bilgi için [Bkz. CTaskDialog::SetProgressBarState](#setprogressbarstate).|
|`m_nRadioId`|Seçili radyo düğmesi denetiminin kimliği.|
|`m_nWidth`|Piksellerin `CTaskDialog` genişliği.|
|`m_strCollapse`|Genişletilmiş bilgiler `CTaskDialog` gizlendiğinde genişletme kutusunun sağındaki dize görüntülenir.|
|`m_strContent`|İçerik `CTaskDialog`dizesi.|
|`m_strExpand`|Genişletilmiş bilgiler `CTaskDialog` görüntülendiğinde genişletme kutusunun sağındaki dize görüntülenir.|
|`m_strFooter`|`CTaskDialog`Altbilgi.|
|`m_strInformation`|Için genişletilmiş bilgi `CTaskDialog`.|
|`m_strMainInstruction`|Ana talimat `CTaskDialog`.|
|`m_strTitle`|Başlığı `CTaskDialog`.|
|`m_strVerification`|Doğrulama onay `CTaskDialog` kutusunun sağında görüntülenebilen dize.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CTaskDialog` standart Windows ileti kutusunun yerini alır ve kullanıcıdan bilgi toplamak için yeni denetimler gibi ek işlevlere sahiptir. Bu sınıf Visual Studio 2010 ve sonrası MFC kütüphanede. Windows `CTaskDialog` Vista'dan başlayarak kullanılabilir. Windows'un önceki sürümleri `CTaskDialog` nesneyi görüntüleyemez. Geçerli `CTaskDialog::IsSupported` kullanıcının görev iletişim kutusunu görüntüleyip görüntüleyemeyeceğini çalışma zamanında belirlemek için kullanın. Standart Windows ileti kutusu hala desteklenir.

Yalnızca `CTaskDialog` Unicode kitaplığını kullanarak uygulamanızı oluşturduğunuzda kullanılabilir.

İki `CTaskDialog` farklı yapıcısı vardır. Bir oluşturucu iki komut düğmesi ve en fazla altı düzenli düğme denetimi belirtmenizi sağlar. 'yi oluşturduktan sonra daha fazla `CTaskDialog`komut düğmesi ekleyebilirsiniz. İkinci oluşturucu herhangi bir komut düğmesini desteklemez, ancak sınırsız sayıda düzenli düğme denetimi ekleyebilirsiniz. Oluşturucular hakkında daha fazla bilgi için [Bkz. CTaskDialog::CTaskDialog.](#ctaskdialog)

Aşağıdaki resimde, bazı `CTaskDialog` denetimlerin konumunu göstermek için bir örnek gösterilmektedir.

![CTaskDialog örneği](../../mfc/reference/media/ctaskdialogsample.png "CTaskDialog örneği") <br/>
CTaskDialog Örneği

## <a name="requirements"></a>Gereksinimler

**Minimum gerekli işletim sistemi:** Windows Vista

**Üstbilgi:** afxtaskdialog.h

## <a name="ctaskdialogaddcommandcontrol"></a><a name="addcommandcontrol"></a>CTaskDialog::AddCommandControl

Yeni bir komut düğmesi `CTaskDialog`denetimi ekler.

```
void AddCommandControl(
    int nCommandControlID,
    const CString& strCaption,
    BOOL bEnabled = TRUE,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>Parametreler

*nCommandControlID*<br/>
[içinde] Komuta kontrol kimlik numarası.

*strCaption*<br/>
[içinde] Kullanıcıya görüntüleyen dize. `CTaskDialog` Komutun amacını açıklamak için bu dizeyi kullanın.

*bEtkin*<br/>
[içinde] Yeni düğmenin etkin veya devre dışı bırakıldığını gösteren bir Boolean parametresi.

*bRequiresElevation*<br/>
[içinde] Bir komutun yükseklik gerektiremesini gösteren bir Boolean parametresi.

### <a name="remarks"></a>Açıklamalar

Sınırsız `CTaskDialog Class` sayıda komut düğmesi denetimi görüntülenebilir. Ancak, bir `CTaskDialog` komut düğmesi denetimleri görüntülerse, en fazla altı düğme görüntüleyebilir. Komut `CTaskDialog` düğmesi denetimi yoksa, sınırsız sayıda düğme görüntüleyebilir.

Kullanıcı bir komut düğmesi denetimi seçtiğinde `CTaskDialog` kapanır. Uygulamanız [CTaskDialog::DoModal](#domodal)kullanarak iletişim kutusunu görüntülerse, `DoModal` seçili komut düğmesi denetiminin *nCommandControlID'sini* döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogaddradiobutton"></a><a name="addradiobutton"></a>CTaskDialog::AddRadioButton

Bir radyo düğmesi `CTaskDialog`ekler.

```
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,
    const CString& strCaption,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
[içinde] Radyo düğmesinin kimlik numarası.

*strCaption*<br/>
[içinde] Radyo düğmesinin `CTaskDialog` yanındaki ekranlı dize.

*bEtkin*<br/>
[içinde] Radyo düğmesinin etkin olup olmadığını gösteren bir Boolean parametresi.

### <a name="remarks"></a>Açıklamalar

[CTaskDialog Sınıfı'nın](../../mfc/reference/ctaskdialog-class.md) radyo düğmeleri kullanıcıdan bilgi toplamanızı sağlar. Hangi radyo düğmesinin seçili olduğunu belirlemek için [CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid) işlevini kullanın.

`CTaskDialog` *NRadioButtonID* parametrelerinin her radyo düğmesi için benzersiz olduğunu gerektirmez. Ancak, her radyo düğmesi için farklı bir tanımlayıcı kullanmazsanız beklenmeyen davranışlarla karşılaşabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogclickcommandcontrol"></a><a name="clickcommandcontrol"></a>CTaskDialog::ClickCommandControl

Komut düğmesi denetimini veya ortak düğmeyi programlı olarak tıklatıyor.

```
protected:
void ClickCommandControl(int nCommandControlID) const;
```

### <a name="parameters"></a>Parametreler

*nCommandControlID*<br/>
[içinde] Tıklatmak için denetimkomut kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, windows iletisi TDM_CLICK_BUTTON oluşturur.

## <a name="ctaskdialogclickradiobutton"></a><a name="clickradiobutton"></a>CTaskDialog::ClickRadioButton

Radyo düğmesini programlı olarak tıklatıyor.

```
protected:
void ClickRadioButton(int nRadioButtonID) const;
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
[içinde] Tıklatmak için radyo düğmesinin kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, windows iletisi TDM_CLICK_RADIO_BUTTON oluşturur.

## <a name="ctaskdialogctaskdialog"></a><a name="ctaskdialog"></a>CTaskDialog::CTaskDialog

[CTaskDialog Sınıfı'nın](../../mfc/reference/ctaskdialog-class.md)bir örneğini oluşturur.

```
CTaskDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nCommonButtons = TDCBF_OK_BUTTON | TDCBF_CANCEL_BUTTON,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));

CTaskDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast,
    int nCommonButtons,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));
```

### <a name="parameters"></a>Parametreler

*strContent*<br/>
[içinde] İçeriği için kullanılacak `CTaskDialog`dize.

*strMainInstruction*<br/>
[içinde] Ana talimat `CTaskDialog`.

*strTitle*<br/>
[içinde] Başlığı `CTaskDialog`.

*nCommonButtons*<br/>
[içinde] Ortak düğmeleri bir maske eklemek `CTaskDialog`için .

*nTaskDialogOptions*<br/>
[içinde] Için kullanılacak seçenekler `CTaskDialog`kümesi.

*strFooter*<br/>
[içinde] Altbilgi olarak kullanılacak dize.

*nIDCommandControlsFirst*<br/>
[içinde] İlk komutun dize kimliği.

*nIDCommandControlsLast*<br/>
[içinde] Son komutun dize kimliği.

### <a name="remarks"></a>Açıklamalar

Uygulamanıza a `CTaskDialog` eklemenin iki yolu vardır. İlk yolu oluşturmak `CTaskDialog` ve CTaskDialog kullanarak görüntülemek için yapıcılardan birini kullanmaktır::DoModal . [CTaskDialog::DoModal](#domodal) İkinci yol, ctaskdialog statik işlevini kullanmaktır::ShowDialog , açıkça [CTaskDialog::ShowDialog](#showdialog) `CTaskDialog` bir `CTaskDialog` nesne oluşturmadan bir görüntülemenizi sağlar.

İkinci oluşturucu, uygulamanızın kaynak dosyasındaki verileri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyasındaki dize tablosunda ilişkili dize iI'leri ile birkaç dize vardır. Bu yöntem, *nIDCommandControlsFirst* ve *nCommandControlsLast*, dahil arasındaki dize tablosunda her geçerli giriş için bir komut düğmesi denetimi ekler. Bu komut düğmesi denetimleri için, string tablosundaki dize denetimin başlığı, string kimliği ise denetimin kimliğidir.

Geçerli seçenekler listesi için [CTaskDialog::SetOptions'a](#setoptions) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogdomodal"></a><a name="domodal"></a>CTaskDialog::DoModal

Gösterir `CTaskDialog` ve modal yapar.

```
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```

### <a name="parameters"></a>Parametreler

*hParent*<br/>
[içinde] Için ana pencere `CTaskDialog`.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tarafından yapılan seçime karşılık gelen bir tamsayı.

### <a name="remarks"></a>Açıklamalar

[CTaskDialog'un](../../mfc/reference/ctaskdialog-class.md)bu örneğini görüntüler. Uygulama daha sonra kullanıcının iletişim kutusunu kapatmasını bekler.

Kullanıcı `CTaskDialog` ortak bir düğme, bir komut bağlantısı denetimi seçtiğinde kapanır `CTaskDialog`veya . İade değeri, kullanıcının iletişim kutusunu nasıl kapadığını gösteren tanımlayıcıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialoggetcommonbuttoncount"></a><a name="getcommonbuttoncount"></a>CTaskDialog::GetCommonButtonCount

Ortak düğmelerin sayısını alır.

```
int GetCommonButtonCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanılabilir ortak düğme sayısı.

### <a name="remarks"></a>Açıklamalar

Ortak düğmeler, [CTaskDialog::CTaskDialog'a](#ctaskdialog)sağladığınız varsayılan düğmelerdir. [CTaskDialog Class](../../mfc/reference/ctaskdialog-class.md) iletişim kutusunun altındaki düğmeleri görüntüler.

Numaralandırılmış düğme listesi CommCtrl.h'de verilmiştir.

## <a name="ctaskdialoggetcommonbuttonflag"></a><a name="getcommonbuttonflag"></a>CTaskDialog::GetCommonButtonFlag

Standart bir Windows düğmesini [CTaskDialog Sınıfı](../../mfc/reference/ctaskdialog-class.md)ile ilişkili ortak düğme türüne dönüştürür.

```
int GetCommonButtonFlag(int nButtonId) const;
```

### <a name="parameters"></a>Parametreler

*nButtonId*<br/>
[içinde] Standart Windows düğmesi değeri.

### <a name="return-value"></a>Dönüş Değeri

Karşılık gelen `CTaskDialog` ortak düğmenin değeri. Karşılık gelen ortak bir düğme yoksa, bu yöntem 0 döndürür.

## <a name="ctaskdialoggetcommonbuttonid"></a><a name="getcommonbuttonid"></a>CTaskDialog::GetCommonButtonId

[CTaskDialog Class](../../mfc/reference/ctaskdialog-class.md) ile ilişkili ortak düğme türlerinden birini standart bir Windows düğmesine dönüştürür.

```
int GetCommonButtonId(int nFlag);
```

### <a name="parameters"></a>Parametreler

*nBayrak*<br/>
[içinde] `CTaskDialog` Sınıfla ilişkili ortak düğme türü.

### <a name="return-value"></a>Dönüş Değeri

İlgili standart Windows düğmesinin değeri. Karşılık gelen Windows düğmesi yoksa, yöntem 0 döndürür.

## <a name="ctaskdialoggetoptions"></a><a name="getoptions"></a>CTaskDialog::GetOptions

Bunun `CTaskDialog`için seçenek bayraklarını döndürür.

```
int GetOptions() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CTaskDialog`Bayraklar.

### <a name="remarks"></a>Açıklamalar

[CTaskDialog Sınıfı'nın](../../mfc/reference/ctaskdialog-class.md)kullanabileceği seçenekler hakkında daha fazla bilgi için [Bkz. CTaskDialog::SetOptions](#setoptions).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialoggetselectedcommandcontrolid"></a><a name="getselectedcommandcontrolid"></a>CTaskDialog::GetSelectedCommandControlID

Seçili komut düğmesi denetimini döndürür.

```
int GetSelectedCommandControlID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili komut düğmesi denetiminin kimliği.

### <a name="remarks"></a>Açıklamalar

Kullanıcının seçtiği komut düğmesinin kimliğini almak için bu yöntemi kullanmanız gerekmez. Bu kimlik [CTaskDialog tarafından döndürülür::DoModal](#domodal) veya [CTaskDialog::ShowDialog](#showdialog).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialoggetselectedradiobuttonid"></a><a name="getselectedradiobuttonid"></a>CTaskDialog::GetSelectedRadioButtonID

Seçili radyo düğmesini döndürür.

```
int GetSelectedRadioButtonID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili radyo düğmesinin kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, kullanıcı seçili radyo düğmesini almak için iletişim kutusunu kapattıktan sonra kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialoggetverificationcheckboxstate"></a><a name="getverificationcheckboxstate"></a>CTaskDialog::GetVerificationCheckboxState

Doğrulama onay kutusunun durumunu alır.

```
BOOL GetVerificationCheckboxState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Onay kutusu işaretlenirse DOĞRU, doğru değilse FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogiscommandcontrolenabled"></a><a name="iscommandcontrolenabled"></a>CTaskDialog::IsCommandControlEnabled

Komut düğmesi denetiminin veya düğmenin etkin olup olmadığını belirler.

```
BOOL IsCommandControlEnabled(int nCommandControlID) const;
```

### <a name="parameters"></a>Parametreler

*nCommandControlID*<br/>
[içinde] Komut düğmesi denetiminin kimliği veya test etmek için düğme.

### <a name="return-value"></a>Dönüş Değeri

Denetim etkinse DOĞRU, değilse FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, hem komut düğmesi denetimlerinin hem de `CTaskDialog` Sınıfın ortak düğmelerinin kullanılabilirliğini belirlemek için kullanabilirsiniz*.

*nCommandControlID* ortak `CTaskDialog` bir düğme veya komut düğmesi denetimi için geçerli bir tanımlayıcı değilse, bu yöntem bir özel durum atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogisradiobuttonenabled"></a><a name="isradiobuttonenabled"></a>CTaskDialog::IsRadioButtonEnabled

Radyo düğmesinin etkin olup olmadığını belirler.

```
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
[içinde] Test etmek için radyo düğmesinin kimliği.

### <a name="return-value"></a>Dönüş Değeri

Radyo düğmesi etkinse DOĞRU, değilse FALSE.

### <a name="remarks"></a>Açıklamalar

*nRadioButtonID* bir radyo düğmesi için geçerli bir tanımlayıcı değilse, bu yöntem bir özel durum atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogissupported"></a><a name="issupported"></a>CTaskDialog::Desteklendi

Uygulamayı çalıştıran bilgisayarın `CTaskDialog`.

```
static BOOL IsSupported();
```

### <a name="return-value"></a>Dönüş Değeri

Bilgisayar destekliyorsa `CTaskDialog`DOĞRU ; YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Uygulamanızı çalıştıran bilgisayarın `CTaskDialog` sınıfı destekleyip desteklemediğini çalışma zamanında belirlemek için bu işlevi kullanın. Bilgisayar `CTaskDialog`, kullanıcıya bilgi iletmek için başka bir yöntem sağlamalıdır desteklemiyorsa. Uygulamanız, sınıfı desteklemeyen bir `CTaskDialog` bilgisayarda kullanmaya çalışırsa kilitlenir. `CTaskDialog`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

## <a name="ctaskdialogloadcommandcontrols"></a><a name="loadcommandcontrols"></a>CTaskDialog::LoadCommandControls

Dize tablosundaki verileri kullanarak komut düğmesi denetimleri ekler.

```
void LoadCommandControls(
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast);
```

### <a name="parameters"></a>Parametreler

*nIDCommandControlsFirst*<br/>
[içinde] İlk komutun dize kimliği.

*nIDCommandControlsLast*<br/>
[içinde] Son komutun dize kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, uygulamanızın kaynak dosyasındaki verileri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyasındaki dize tablosunda ilişkili dize iI'leri ile birkaç dize vardır. Bu yöntemi kullanarak eklenen yeni komut düğmesi denetimleri, denetimin başlığı için dize ve denetimin kimliği için string kimliği kullanır. Seçilen dizeleri aralığı *nIDCommandControlsFirst* ve *nCommandControlsLast*, dahil tarafından sağlanır. Aralıkta boş bir giriş varsa, yöntem bu giriş için bir komut düğmesi denetimi eklemez.

Varsayılan olarak, yeni komut düğmesi denetimleri etkinleştirilir ve yükseklik gerektirmez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogloadradiobuttons"></a><a name="loadradiobuttons"></a>CTaskDialog::LoadRadioButtons

String tablosundaki verileri kullanarak radyo düğmesi denetimleri ekler.

```
void LoadRadioButtons(
    int nIDRadioButtonsFirst,
    int nIDRadioButtonsLast);
```

### <a name="parameters"></a>Parametreler

*nIDRadioButtonsİlk*<br/>
[içinde] İlk radyo düğmesinin dize kimliği.

*nIDRadioButtonsSon*<br/>
[içinde] Son radyo düğmesinin dize kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, uygulamanızın kaynak dosyasındaki verileri kullanarak radyo düğmeleri oluşturur. Kaynak dosyasındaki dize tablosunda ilişkili dize iI'leri ile birkaç dize vardır. Bu yöntemi kullanarak eklenen yeni radyo düğmeleri, radyo düğmesinin başlığı için dize ve radyo düğmesinin kimliği için string id'yi kullanır. Seçilen dizeleri aralığı *nIDRadioButtonsFirst* ve *nRadioButtonsLast*, dahil tarafından sağlanır. Aralıkta boş bir giriş varsa, yöntem bu giriş için bir radyo düğmesi eklemez.

Varsayılan olarak, yeni radyo düğmeleri etkinleştirilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialognavigateto"></a><a name="navigateto"></a>CTaskDialog::NavigateTo

Odağı başka bir `CTaskDialog`şeye aktarın.

```
protected:
void NavigateTo(CTaskDialog& oTaskDialog) const;
```

### <a name="parameters"></a>Parametreler

*oTaskDialog*<br/>
[içinde] Odak `CTaskDialog` noktası.

### <a name="remarks"></a>Açıklamalar

Bu `CTaskDialog` *yöntem, oTaskDialog'u*görüntülediğinde akımı gizler. *oTaskDialog* geçerli `CTaskDialog`ile aynı konumda görüntülenir.

## <a name="ctaskdialogoncommandcontrolclick"></a><a name="oncommandcontrolclick"></a>CTaskDialog::OnCommandControlClick

Kullanıcı bir komut düğmesi denetimini tıklattığında çerçeve bu yöntemi çağırır.

```
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```

### <a name="parameters"></a>Parametreler

*nCommandControlID*<br/>
[içinde] Kullanıcının seçtiği komut düğmesi denetiminin kimliği.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranış uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogoncreate"></a><a name="oncreate"></a>CTaskDialog::OnCreate

Çerçeve, bu yöntemi oluşturduktan `CTaskDialog`sonra çağırır.

```
virtual HRESULT OnCreate();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranış uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogondestroy"></a><a name="ondestroy"></a>CTaskDialog::OnDestroy

Çerçeve, bu yöntemi yok etmeden `CTaskDialog`hemen önce çağırır.

```
virtual HRESULT OnDestroy();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranış uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogonexpandbuttonclick"></a><a name="onexpandbuttonclick"></a>CTaskDialog::OnExpandButtonClick

Kullanıcı genişletme düğmesini tıklattığında çerçeve bu yöntemi çağırır.

```
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```

### <a name="parameters"></a>Parametreler

*bGenişletilmiş*<br/>
[içinde] Sıfır olmayan bir değer, ek bilgilerin görüntülendiğini gösterir; 0, ek bilgilerin gizli olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranış uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogonhelp"></a><a name="onhelp"></a>CTaskDialog::OnHelp

Kullanıcı yardım istediğinde çerçeve bu yöntemi çağırır.

```
virtual HRESULT OnHelp();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranış uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogonhyperlinkclick"></a><a name="onhyperlinkclick"></a>CTaskDialog::OnHyperlinkTıklayın

Kullanıcı bir köprüye tıkladığında çerçeve bu yöntemi çağırır.

```
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```

### <a name="parameters"></a>Parametreler

*strHref*<br/>
[içinde] Köprüciyi temsil eden dize.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu [yöntem, S_OK](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) dönmeden önce ShellExecute çağırır.

Özel davranış uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogoninit"></a><a name="oninit"></a>CTaskDialog::OnInit

Çerçeve, baş harfe `CTaskDialog` geldiğinde bu yöntemi çağırır.

```
virtual HRESULT OnInit();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranış uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogonnavigatepage"></a><a name="onnavigatepage"></a>CTaskDialog::OnNavigatePage

Çerçeve, CTaskDialog yanıt olarak bu yöntemi [çağırır::NavigateTo](#navigateto) yöntemi.

```
virtual HRESULT OnNavigatePage();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranış uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogonradiobuttonclick"></a><a name="onradiobuttonclick"></a>CTaskDialog::OnRadioButtonClick

Kullanıcı bir radyo düğmesi denetimi seçtiğinde çerçeve bu yöntemi çağırır.

```
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
[içinde] Kullanıcının tıklatdığı radyo düğmesinin kimliği denetimi.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranış uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogontimer"></a><a name="ontimer"></a>CTaskDialog::OnTimer

Çerçeve, zamanlayıcının süresi dolduğunda bu yöntemi çağırır.

```
virtual HRESULT OnTimer(long lTime);
```

### <a name="parameters"></a>Parametreler

*lZaman*<br/>
[içinde] `CTaskDialog` Oluşturulduğu veya zamanlayıcının sıfırlandığından bu yana milisaniye cinsinden zaman.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranış uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogonverificationcheckboxclick"></a><a name="onverificationcheckboxclick"></a>CTaskDialog::OnVerificationCheckboxTıklayın

Kullanıcı doğrulama onay kutusunu tıklattığında çerçeve bu yöntemi çağırır.

```
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```

### <a name="parameters"></a>Parametreler

*bKontrol edildi*<br/>
[içinde] TRUE doğrulama onay kutusunun seçildiğini gösterir; YANLIŞ olmadığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranış uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogremoveallcommandcontrols"></a><a name="removeallcommandcontrols"></a>CTaskDialog::RemoveAllCommandControls

Tüm komut düğmesi denetimlerini `CTaskDialog`.

```
void RemoveAllCommandControls();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogremoveallradiobuttons"></a><a name="removeallradiobuttons"></a>CTaskDialog::RemoveAllRadioButtons

Tüm radyo düğmelerini `CTaskDialog`kaldırır.

```
void RemoveAllRadioButtons();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetcommandcontroloptions"></a><a name="setcommandcontroloptions"></a>CTaskDialog::SetCommandControlOptions

Bir komut düğmesi denetimini `CTaskDialog`güncelleştirir.

```
void SetCommandControlOptions(
    int nCommandControlID,
    BOOL bEnabled,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>Parametreler

*nCommandControlID*<br/>
[içinde] Güncelleştirmek için komut denetiminin kimliği.

*bEtkin*<br/>
[içinde] Belirtilen komut düğmesi denetiminin etkin veya devre dışı bırakıldığını gösteren boolean parametresi.

*bRequiresElevation*<br/>
[içinde] Belirtilen komut düğmesi denetiminin yükseklik gerekip gerekmediğini gösteren bir Boolean parametresi.

### <a name="remarks"></a>Açıklamalar

Komut düğmesi denetiminin etkin olup olmadığını veya `CTaskDialog` sınıfa eklendikten sonra yükseklik gerekip gerekmediğini değiştirmek için bu yöntemi kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogsetcommonbuttonoptions"></a><a name="setcommonbuttonoptions"></a>CTaskDialog::SetCommonButtonOptions

Etkinleştirilmesi ve UAC yüksekliği gerektirmesi için ortak düğmelerin bir alt kümesini güncelleştirir.

```
void SetCommonButtonOptions(
    int nDisabledButtonMask,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>Parametreler

*nDisabledButtonMask*<br/>
[içinde] Ortak düğmelerin devre dışı kalım için bir maske.

*nElevationButtonMask*<br/>
[içinde] Yükseklik gerektiren ortak düğmeler için bir maske.

### <a name="remarks"></a>Açıklamalar

Oluşturucu [CTaskDialog::CTaskDialog](#ctaskdialog) ve [CTaskDialog::SetCommonButtons](#setcommonbuttons)yöntemini kullanarak [CTaskDialog Sınıfı'nın](../../mfc/reference/ctaskdialog-class.md) bir örneğinde bulunan ortak düğmeleri ayarlayabilirsiniz. `CTaskDialog::SetCommonButtonOptions`yeni ortak düğmeler eklemeyi desteklemez.

Bu yöntemi devre dışı atmak veya bunun `CTaskDialog`için kullanılamayan ortak bir düğmeyi yükseltmek için kullanırsanız, bu yöntem [ENSURE](diagnostic-services.md#ensure) makrosunu kullanarak bir özel durum oluşturur.

Bu yöntem, daha önce devre `CTaskDialog` dışı bırakılmış olsa bile, *nDisabledButtonMask'da*bulunmayan ancak kullanılabilen herhangi bir düğmeyi etkinleştirilir. Bu yöntem, yükseklik benzer bir şekilde davranır: ortak düğme kullanılabilir ancak *nElevationButtonMask*dahil değilse yükseklik gerektirmeyen olarak ortak düğmeleri kaydeder.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

## <a name="ctaskdialogsetcommonbuttons"></a><a name="setcommonbuttons"></a>CTaskDialog::SetCommonButtons

`CTaskDialog`'ye ortak düğmeler ekler.

```
void SetCommonButtons(
    int nButtonMask,
    int nDisabledButtonMask = 0,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>Parametreler

*nButtonMask*<br/>
[içinde] Düğmeleri bir maske eklemek için `CTaskDialog`.

*nDisabledButtonMask*<br/>
[içinde] Devre dışı kalmak için düğmelerin maskesi.

*nElevationButtonMask*<br/>
[içinde] Yükseklik gerektiren düğmelerin maskesi.

### <a name="remarks"></a>Açıklamalar

`CTaskDialog` Sınıfın bu örneği için görüntü penceresi oluşturulduktan sonra bu yöntemi arayamazsınız. Bunu yaparsanız, bu yöntem bir özel durum atar.

*nButtonMask* tarafından belirtilen düğmeler daha önce eklenen ortak `CTaskDialog`düğmeleri geçersiz kılar. Yalnızca *nButtonMask'de* belirtilen düğmeler kullanılabilir.

*nDisabledButtonMask* veya *nElevationButtonMask* *nButtonMask'de*olmayan bir düğme içeriyorsa, bu yöntem [ENSURE](diagnostic-services.md#ensure) makrosu kullanarak bir özel durum oluşturur.

Varsayılan olarak, tüm ortak düğmeler etkindir ve yükseklik gerektirmez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

## <a name="ctaskdialogsetcontent"></a><a name="setcontent"></a>CTaskDialog::SetContent

İçeriği `CTaskDialog`güncelleştirir.

```
void SetContent(const CString& strContent);
```

### <a name="parameters"></a>Parametreler

*strContent*<br/>
[içinde] Kullanıcıya görüntülenecek dize.

### <a name="remarks"></a>Açıklamalar

`CTaskDialog` Sınıfın içeriği, iletişim kutusunun ana bölümünde kullanıcıya görüntülenen metindir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetdefaultcommandcontrol"></a><a name="setdefaultcommandcontrol"></a>CTaskDialog::SetDefaultCommandControl

Varsayılan komut düğmesi denetimini belirtir.

```
void SetDefaultCommandControl(int nCommandControlID);
```

### <a name="parameters"></a>Parametreler

*nCommandControlID*<br/>
[içinde] Komut düğmesi denetiminin kimliği varsayılan olarak.

### <a name="remarks"></a>Açıklamalar

Varsayılan komut düğmesi denetimi, kullanıcıya ilk `CTaskDialog` görüntülendiğinde seçilen denetimdir.

Bu yöntem, *nCommandControlID*tarafından belirtilen komut düğmesi denetimini bulamıyorsa bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogsetdefaultradiobutton"></a><a name="setdefaultradiobutton"></a>CTaskDialog::SetDefaultRadioButton

Varsayılan radyo düğmesini belirtir.

```
void SetDefaultRadioButton(int nRadioButtonID);
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
[içinde] Varsayılan olarak radyo düğmesinin kimliği.

### <a name="remarks"></a>Açıklamalar

Varsayılan radyo düğmesi, kullanıcıya ilk `CTaskDialog` görüntülendiğinde seçilen düğmedir.

Bu *yöntem, nRadioButtonID*tarafından belirtilen radyo düğmesini bulamıyorsa bir özel durum atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetdialogwidth"></a><a name="setdialogwidth"></a>CTaskDialog::SetDialogGenişliği

Genişliği `CTaskDialog`ayarlar.

```
void SetDialogWidth(int nWidth = 0);
```

### <a name="parameters"></a>Parametreler

*Nwidth*<br/>
[içinde] İletişim kutusunun genişliği, pikseller halinde.

### <a name="remarks"></a>Açıklamalar

Parametre *nWidth* 0'dan büyük veya eşit olmalıdır. Aksi takdirde, bu yöntem bir özel durum atar.

*nWidth* 0 olarak ayarlanmışsa, bu yöntem iletişim kutusunu varsayılan boyuta ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetexpansionarea"></a><a name="setexpansionarea"></a>CTaskDialog::SetExpansionArea

`CTaskDialog`Genişletme alanını güncelleştirir.

```
void SetExpansionArea(
    const CString& strExpandedInformation,
    const CString& strCollapsedLabel = _T(""),
    const CString& strExpandedLabel = _T(""));
```

### <a name="parameters"></a>Parametreler

*strExpandedBilgi*<br/>
[içinde] Kullanıcı genişletme `CTaskDialog` düğmesini tıklattığında iletişim kutusunun ana gövdesinde görüntüleyen dize.

*strCollapsedLabel*<br/>
[içinde] Genişletilmiş alan `CTaskDialog` daraltıldığında genişletme düğmesinin yanındaki dize.

*strExpandedEtiket*<br/>
[içinde] Genişletilmiş alan `CTaskDialog` görüntülendiğinde genişletme düğmesinin yanındaki ekrandaki dize.

### <a name="remarks"></a>Açıklamalar

`CTaskDialog` Sınıfın genişletme alanı, kullanıcıya ek bilgi sağlamanızı sağlar. Genişletme `CTaskDialog`alanı, başlık ve içerik dizesinin hemen altında yer alan ana bölümünde dir.

`CTaskDialog` İlk görüntülendiğinde, genişletilmiş bilgileri göstermez ve genişletme `strCollapsedLabel` düğmesinin yanına koyar. Kullanıcı genişletme düğmesini tıklattığında, `CTaskDialog` görüntüler *strExpandedInformation* ve *strExpandedLabel*etiketi ni değiştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetfootericon"></a><a name="setfootericon"></a>CTaskDialog::SetFooterIcon

Altbilgi simgesini `CTaskDialog`güncelleştirir.

```
void SetFooterIcon(HICON hFooterIcon);
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```

### <a name="parameters"></a>Parametreler

*hFooterIcon*<br/>
[içinde] Için yeni simge `CTaskDialog`.

*lpszFooterIcon*<br/>
[içinde] Için yeni simge `CTaskDialog`.

### <a name="remarks"></a>Açıklamalar

Altbilgi simgesi [CTaskDialog Sınıfının](../../mfc/reference/ctaskdialog-class.md)alt kısmında görüntülenir. İlişkili altbilgi metni olabilir. CTaskDialog ile altbilgi metnini [değiştirebilirsiniz::SetFooterText](#setfootertext).

Bu yöntem, `CTaskDialog` görüntüleniyorsa veya giriş parametresi NULL ise [ENSURE](diagnostic-services.md#ensure) makrosu yla bir özel durum oluşturur.

A `CTaskDialog` yalnızca bir `HICON` `LPCWSTR` altbilgi simgesi olarak kabul edebilir. Bu, oluşturucu veya CTaskDialog seçeneği TDF_USE_HICON_FOOTER ayarlayarak [yapılandırılır::SetOptions](#setoptions). Varsayılan olarak, `CTaskDialog` altbilgi simgesi `LPCWSTR` için giriş türü olarak kullanmak üzere yapılandırılır. Simgeyi uygunsuz türü kullanarak ayarlamaya çalışırsanız, bu yöntem bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetfootertext"></a><a name="setfootertext"></a>CTaskDialog::SetFooterText

Altbilgideki metni `CTaskDialog`güncelleştirir.

```
void SetFooterText(const CString& strFooterText);
```

### <a name="parameters"></a>Parametreler

*strFooterMetin*<br/>
[içinde] Altbilgi için yeni metin.

### <a name="remarks"></a>Açıklamalar

Altbilgi simgesi alt kısmında altbilgi metninin yanında `CTaskDialog`görünür. CTaskDialog ile altbilgi simgesini [değiştirebilirsiniz::SetFooterIcon](#setfootericon).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetmainicon"></a><a name="setmainicon"></a>CTaskDialog::SetMainIcon

Ana simgeyi `CTaskDialog`güncelleştirir.

```
void SetMainIcon(HICON hMainIcon);
void SetMainIcon(LPCWSTR lpszMainIcon);
```

### <a name="parameters"></a>Parametreler

*hMainIcon*<br/>
[içinde] Yeni simge.

*lpszMainIcon*<br/>
[içinde] Yeni simge.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CTaskDialog` görüntüleniyorsa veya giriş parametresi NULL ise [ENSURE](diagnostic-services.md#ensure) makrosu yla bir özel durum oluşturur.

A `CTaskDialog` yalnızca bir `HICON` `LPCWSTR` veya ana simge olarak kabul edilebilir. Bunu, oluşturucuda veya [CTaskDialog'da](#setoptions) TDF_USE_HICON_MAIN seçeneğini ayarlayarak yapılandırabilirsiniz::SetOptions yöntemi. Varsayılan olarak, `CTaskDialog` ana simge `LPCWSTR` için giriş türü olarak kullanmak üzere yapılandırılır. Simgeyi uygunsuz türü kullanarak ayarlamaya çalışırsanız, bu yöntem bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetmaininstruction"></a><a name="setmaininstruction"></a>CTaskDialog::SetMainInstruction

Günceller ana talimat `CTaskDialog`.

```
void SetMainInstruction(const CString& strInstructions);
```

### <a name="parameters"></a>Parametreler

*strInstructions*<br/>
[içinde] Yeni ana talimat.

### <a name="remarks"></a>Açıklamalar

`CTaskDialog` Sınıfın ana yönergesi, kullanıcıya büyük kalın bir yazı tipinde görüntülenen metindir. Başlık çubuğunun altındaki iletişim kutusunda yer alır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetoptions"></a><a name="setoptions"></a>CTaskDialog::SetOptions

Için seçenekleri `CTaskDialog`yapılandırır.

```
void SetOptions(int nOptionFlag);
```

### <a name="parameters"></a>Parametreler

*nOptionFlag*<br/>
[içinde] Için kullanılacak bayraklar `CTaskDialog`kümesi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem için tüm geçerli `CTaskDialog`seçenekleri temizler. Geçerli seçenekleri korumak için, önce [CTaskDialog::GetOptions](#getoptions) ile bunları almanız ve ayarlamak istediğiniz seçeneklerle birleştirmeniz gerekir.

Aşağıdaki tablotüm geçerli seçenekleri listeler.

|||
|-|-|
|TDF_ENABLE_HYPERLINKS|'deki köprüleri `CTaskDialog`etkinleştirir.|
|TDF_USE_HICON_MAIN|Ana simge `CTaskDialog` için `HICON` kullanılacak şekilde yapılandırır. Alternatif bir `LPCWSTR`.|
|TDF_USE_HICON_FOOTER|`CTaskDialog` Altbilgi simgesi için `HICON` kullanılacak şekilde yapılandırır. Alternatif bir `LPCWSTR`.|
|TDF_ALLOW_DIALOG_CANCELLATION|**İptal** düğmesi etkin olmasa `CTaskDialog` bile, kullanıcının klavyeyi kullanarak veya iletişim kutusunun sağ üst köşesindeki simgeyi kullanarak kapatmasını sağlar. Bu bayrak ayarlanmazsa ve **İptal** düğmesi etkin değilse, kullanıcı Alt+F4, Kaçış tuşu veya başlık çubuğunun kapatma düğmesini kullanarak iletişim kutusunu kapatamaz.|
|TDF_USE_COMMAND_LINKS|Kullanılacak komut `CTaskDialog` düğmesi denetimlerini yapılandırır.|
|TDF_USE_COMMAND_LINKS_NO_ICON|Denetimin `CTaskDialog` yanında bir simge görüntülemeden kullanılacak komut düğmesi denetimlerini yapılandırır. TDF_USE_COMMAND_LINKS TDF_USE_COMMAND_LINKS_NO_ICON geçersiz kılıyor.|
|TDF_EXPAND_FOOTER_AREA|Genişletme alanının şu anda genişletildiğini gösterir.|
|TDF_EXPANDED_BY_DEFAULT|Genişletme alanının varsayılan olarak genişletilip genişletilmeyeceğini belirler.|
|TDF_VERIFICATION_FLAG_CHECKED|Doğrulama onay kutusunun şu anda seçili olduğunu gösterir.|
|TDF_SHOW_PROGRESS_BAR|İlerleme çubuğunu `CTaskDialog` görüntülemek üzere yapılandırır.|
|TDF_SHOW_MARQUEE_PROGRESS_BAR|İlerleme çubuğunu bir seçim çerçevesi ilerleme çubuğu olarak yapılandırır. Bu seçeneği etkinleştiriseniz, beklenen davranışa sahip TDF_SHOW_PROGRESS_BAR ayarlamanız gerekir.|
|TDF_CALLBACK_TIMER|Geri arama `CTaskDialog` aralığının yaklaşık 200 milisaniye olarak ayarlanır olduğunu gösterir.|
|TDF_POSITION_RELATIVE_TO_WINDOW|Üst pencereye göre ortalanacak yapılandırır. `CTaskDialog` Bu bayrak etkinleştirilemezse, `CTaskDialog` monitöre göre ortalanır.|
|TDF_RTL_LAYOUT|Sağdan `CTaskDialog` sola okuma düzenini yapılandırır.|
|TDF_NO_DEFAULT_RADIO_BUTTON|Göründüğünde radyo düğmesinin `CTaskDialog` seçilmediğini gösterir.|
|TDF_CAN_BE_MINIMIZED|Kullanıcının `CTaskDialog`en aza indirilmesini sağlar. Bu seçeneği desteklemek `CTaskDialog` için, modal olamaz. MFC modeless'ı `CTaskDialog`desteklemediği için MFC bu seçeneği desteklemez.|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetprogressbarmarquee"></a><a name="setprogressbarmarquee"></a>CTaskDialog::SetProgressBarMarquee

Bir seçim çerçevesi çubuğunu `CTaskDialog` yapılandırır ve iletişim kutusuna ekler.

```
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,
    int nMarqueeSpeed = 0);
```

### <a name="parameters"></a>Parametreler

*bEtkin*<br/>
[içinde] Seçim çerçevesi çubuğunu etkinleştirmek için TRUE; Yanlış seçim çerçevesi çubuğudevre dışı ve kaldırmak `CTaskDialog`için .

*nMarqueeSpeed*<br/>
[içinde] Seçim çerçevesi çubuğunun hızını gösteren bir sonsayı.

### <a name="remarks"></a>Açıklamalar

Seçim çerçevesi çubuğu `CTaskDialog` sınıfın ana metninin altında görünür.

Seçim çerçevesi çubuğunun hızını ayarlamak için *nMarqueeSpeed'i* kullanın; daha büyük değerler daha yavaş bir hızı gösterir. *nMarqueeSpeed* için 0 değeri, çerçeve çubuğunun Windows için varsayılan hızda hareket ettirir.

Bu yöntem, *nMarqueeSpeed* 0'dan küçükse [ENSURE](diagnostic-services.md#ensure) makrosu ile bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarposition"></a><a name="setprogressbarposition"></a>CTaskDialog::SetProgressBarPosition

İlerleme çubuğunun konumunu ayarlar.

```
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>Parametreler

*nProgressPos*<br/>
[içinde] İlerleme çubuğunun konumu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *progressPos* ilerleme çubuğu aralığında değilse [ENSURE](diagnostic-services.md#ensure) makrosu ile bir özel durum oluşturur. CTaskDialog ile ilerleme çubuğu aralığını [değiştirebilirsiniz::SetProgressBarRange](#setprogressbarrange).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarrange"></a><a name="setprogressbarrange"></a>CTaskDialog::SetProgressBarRange

İlerleme çubuğunun aralığını ayarlar.

```
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>Parametreler

*nRangeMin*<br/>
[içinde] İlerleme çubuğunun alt sınırı.

*nRangeMax*<br/>
[içinde] İlerleme çubuğunun üst sınırı.

### <a name="remarks"></a>Açıklamalar

İlerleme çubuğunun konumu *nRangeMin* ve *nRangeMax*göreli. Örneğin, *nRangeMin* 50 ve *nRangeMax* 100 ise, 75 konumu ilerleme çubuğunun yarısındadır. İlerleme çubuğunun konumunu ayarlamak için [CTaskDialog::SetProgressBarPosition'ı](#setprogressbarposition) kullanın.

İlerleme çubuğunu görüntülemek için TDF_SHOW_PROGRESS_BAR seçeneğinin etkinleştirilmesi ve TDF_SHOW_MARQUEE_PROGRESS_BAR etkin olmaması gerekir. Bu yöntem otomatik olarak TDF_SHOW_PROGRESS_BAR ayarlar ve TDF_SHOW_MARQUEE_PROGRESS_BAR temizler. [CTaskDialog'u kullanın::CTaskDialog](#setoptions) [Sınıfı'nın](../../mfc/reference/ctaskdialog-class.md)bu örneğinin seçeneklerini el ile değiştirmek için Options'ı ayarlayın.

bu *yöntem, nRangeMin* *nRangeMax'ten*az değilse [ENSURE](diagnostic-services.md#ensure) makrosu ile bir özel durum oluşturur. Bu yöntem, zaten görüntülenen `CTaskDialog` ve bir seçim çerçevesi ilerleme çubuğu varsa da bir özel durum atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarstate"></a><a name="setprogressbarstate"></a>CTaskDialog::SetProgressBarState

İlerleme çubuğunun durumunu ayarlar ve 'de `CTaskDialog`görüntüler.

```
void SetProgressBarState(int nState = PBST_NORMAL);
```

### <a name="parameters"></a>Parametreler

*Nstate*<br/>
[içinde] İlerleme çubuğunun durumu. Olası değerler için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, zaten görüntülenen [ENSURE](diagnostic-services.md#ensure) ve bir `CTaskDialog` seçim çerçevesi ilerleme çubuğu varsa ENSURE makrosu ile bir özel durum atar.

Aşağıdaki tabloda *nState*için olası değerleri listeler. Tüm bu durumlarda, ilerleme çubuğu belirlenen durdurma konumuna ulaşana kadar normal renkle doldurulur. Bu noktada duruma göre renk değişecektir.

|||
|-|-|
|PBST_NORMAL|İlerleme çubuğu dolduktan sonra, `CTaskDialog` çubuğun rengi değişmez. Varsayılan olarak, normal renk yeşildir.|
|PBST_ERROR|İlerleme çubuğu dolduktan sonra, çubuğun rengini hata rengiyle `CTaskDialog` değiştirir. Varsayılan olarak, bu kırmızıdır.|
|PBST_PAUSED|İlerleme çubuğu dolduktan sonra, çubuğun rengi duraklatılmış renge `CTaskDialog` dönüşür. Varsayılan olarak, bu sarıdır.|

CTaskDialog ile ilerleme çubuğunun nerede durduğunu [ayarlayabilirsiniz::SetProgressBarPosition](#setprogressbarposition).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetradiobuttonoptions"></a><a name="setradiobuttonoptions"></a>CTaskDialog::SetRadioButtonOptions

Radyo düğmesini etkinleştirir veya devre dışı kılabilir.

```
void SetRadioButtonOptions(
    int nRadioButtonID,
    BOOL bEnabled);
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
[içinde] Radyo düğmesi kontrolünün kimliği.

*bEtkin*<br/>
[içinde] Radyo düğmesini etkinleştirmek için TRUE; Radyo düğmesini devre dışı kıtır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *nRadioButtonID* bir radyo düğmesi için geçerli bir kimlik [değilse, ENSURE](diagnostic-services.md#ensure) makrosu ile bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetverificationcheckbox"></a><a name="setverificationcheckbox"></a>CTaskDialog::SetVerificationCheckbox

Doğrulama onay kutusunun işaretli durumunu ayarlar.

```
void SetVerificationCheckbox(BOOL bChecked);
```

### <a name="parameters"></a>Parametreler

*bKontrol edildi*<br/>
[içinde] Doğru, doğrulama onay kutusunun `CTaskDialog` görüntülendiğinde seçilmesini sağlar; `CTaskDialog` Görüntülendiğinde doğrulama onay kutusunun seçilmemiş olması için FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogsetverificationcheckboxtext"></a><a name="setverificationcheckboxtext"></a>CTaskDialog::SetVerificationCheckboxText

Doğrulama onay kutusunun sağında görüntülenen metni ayarlar.

```
void SetVerificationCheckboxText(CString& strVerificationText);
```

### <a name="parameters"></a>Parametreler

*strVerificationText*<br/>
[içinde] Bu yöntemin doğrulama onay kutusunun yanında görüntülenebilen metin.

### <a name="remarks"></a>Açıklamalar

Sınıfın bu örneği zaten [ENSURE](diagnostic-services.md#ensure) görüntüleniyorsa, `CTaskDialog` bu yöntem ENSURE makrosuyla bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogsetwindowtitle"></a><a name="setwindowtitle"></a>CTaskDialog::SetWindowTitle

Başlığı `CTaskDialog`ayarlar.

```
void SetWindowTitle(CString& strWindowTitle);
```

### <a name="parameters"></a>Parametreler

*strWindowTitle*<br/>
[içinde] Yeni başlık `CTaskDialog`için .

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogshowdialog"></a><a name="showdialog"></a>CTaskDialog::ShowDialog

Oluşturur ve görüntüler. `CTaskDialog`

```
static INT_PTR ShowDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast,
    int nCommonButtons = TDCBF_YES_BUTTON | TDCBF_NO_BUTTON,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));
```

### <a name="parameters"></a>Parametreler

*strContent*<br/>
[içinde] İçeriği için kullanılacak `CTaskDialog`dize.

*strMainInstruction*<br/>
[içinde] Ana talimat `CTaskDialog`.

*strTitle*<br/>
[içinde] Başlığı `CTaskDialog`.

*nIDCommandControlsFirst*<br/>
[içinde] İlk komutun dize kimliği.

*nIDCommandControlsLast*<br/>
[içinde] Son komutun dize kimliği.

*nCommonButtons*<br/>
[içinde] Düğmeleri bir maske eklemek için `CTaskDialog`.

*nTaskDialogOptions*<br/>
[içinde] Için kullanılacak seçenekler `CTaskDialog`kümesi.

*strFooter*<br/>
[içinde] Altbilgi olarak kullanılacak dize.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tarafından yapılan seçime karşılık gelen bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Bu statik yöntem, kodunuzda açıkça `CTaskDialog` bir `CTaskDialog` nesne oluşturmadan sınıfın bir örneğini oluşturmanıza olanak tanır. Nesne olmadığından, `CTaskDialog` kullanıcıya bir `CTaskDialog` `CTaskDialog` nesne göstermek için bu yöntemi kullanırsanız başka bir yöntem çağıramazsınız.

Bu yöntem, uygulamanızın kaynak dosyasındaki verileri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyasındaki dize tablosunda ilişkili dize iI'leri ile birkaç dize vardır. Bu yöntem, *nIDCommandControlsFirst* ve *nCommandControlsLast*, dahil arasındaki dize tablosunda her geçerli giriş için bir komut düğmesi denetimi ekler. Bu komut düğmesi denetimleri için, string tablosundaki dize denetimin başlığı, string kimliği ise denetimin kimliğidir.

Geçerli seçenekler listesi için [CTaskDialog::SetOptions'a](#setoptions) bakın.

Kullanıcı `CTaskDialog` ortak bir düğme, bir komut bağlantısı denetimi seçtiğinde kapanır `CTaskDialog`veya . İade değeri, kullanıcının iletişim kutusunu nasıl kapadığını gösteren tanımlayıcıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

## <a name="ctaskdialogtaskdialogcallback"></a><a name="taskdialogcallback"></a>CTaskDialog::TaskDialogCallback

Çerçeve, çeşitli Windows iletilerine yanıt olarak bu yöntemi çağırır.

```
friend:
HRESULT TaskDialogCallback(
    HWND hWnd,
    UINT uNotification,
    WPARAM wParam,
    LPARAM lParam,
    LONG_PTR dwRefData);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
[içinde] Yapıya bir `m_hWnd` `CTaskDialog`tutamak için .

*uBildirim*<br/>
[içinde] Oluşturulan iletiyi belirten bildirim kodu.

*Wparam*<br/>
[içinde] İleti hakkında daha fazla bilgi.

*Lparam*<br/>
[içinde] İleti hakkında daha fazla bilgi.

*dwRefData*<br/>
[içinde] Geri arama `CTaskDialog` iletisinin uygulandığı nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirli bildirim koduna bağlıdır. Daha fazla bilgi için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama `TaskDialogCallback` belirli bir iletiyi işler ve ardından [CTaskDialog Class'ın](../../mfc/reference/ctaskdialog-class.md)uygun On yöntemini çağırır. Örneğin, TDN_BUTTON_CLICKED iletisine yanıt `TaskDialogCallback` olarak [CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)çağırır.

*wParam* ve *lParam* değerleri belirli oluşturulan iletiye bağlıdır. Bu değerlerin her ikisinin de boş olması mümkündür. Aşağıdaki tabloda desteklenen varsayılan bildirimler ve *wParam* ve *lParam* değerlerinin temsil ettiği listelenir. Türemiş bir sınıfta bu yöntemi geçersiz kılarsanız, aşağıdaki tablodaki her ileti için geri arama kodunu uygulamanız gerekir.

|Bildirim İletisi|*wParam* Değer|*lParam* Değer|
|--------------------------|--------------------|--------------------|
|TDN_CREATED|Kullanılmadı.|Kullanılmadı.|
|TDN_NAVIGATED|Kullanılmadı.|Kullanılmadı.|
|TDN_BUTTON_CLICKED|Komut düğmesi kontrol kimliği.|Kullanılmadı.|
|TDN_HYPERLINK_CLICKED|Kullanılmadı.|Bağlantıyı içeren bir [LPCWSTR](/windows/win32/WinProg/windows-data-types) yapısı.|
|TDN_TIMER|`CTaskDialog` Oluşturulduğu veya zamanlayıcının sıfırlandığından bu yana milisaniye cinsinden zaman.|Kullanılmadı.|
|TDN_DESTROYED|Kullanılmadı.|Kullanılmadı.|
|TDN_RADIO_BUTTON_CLICKED|Radyo düğmesi kimliği.|Kullanılmadı.|
|TDN_DIALOG_CONSTRUCTED|Kullanılmadı.|Kullanılmadı.|
|TDN_VERIFICATION_CLICKED|Onay kutusu işaretlenirse 1, işaret değilse 0.|Kullanılmadı.|
|TDN_HELP|Kullanılmadı.|Kullanılmadı.|
|TDN_EXPANDO_BUTTON_CLICKED|Genişleme alanı daraltılırsa 0; genişletme metni görüntülenirse sıfıra değil.|Kullanılmadı.|

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[İzlenecek yol: Bir Uygulamaya CTaskDialog Ekleme](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)
