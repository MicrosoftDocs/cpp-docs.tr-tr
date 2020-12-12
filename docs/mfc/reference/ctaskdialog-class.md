---
description: 'Daha fazla bilgi edinin: CTaskDialog sınıfı'
title: CTaskDialog sınıfı
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
ms.openlocfilehash: 91cd3caec703f8e81116fccd75c0457abb69a3e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318591"
---
# <a name="ctaskdialog-class"></a>CTaskDialog sınıfı

İleti kutusu gibi işlev gören, ancak kullanıcıya ek bilgiler görüntüleyebilen bir açılır iletişim kutusu. `CTaskDialog`Ayrıca, kullanıcıdan bilgi toplamaya yönelik işlevleri de içerir.

## <a name="syntax"></a>Syntax

```
class CTaskDialog : public CObject
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[CTaskDialog:: CTaskDialog](#ctaskdialog)|Bir `CTaskDialog` nesnesi oluşturur.|

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|-|-|
|[CTaskDialog:: AddCommandControl](#addcommandcontrol)|Öğesine bir komut düğmesi denetimi ekler `CTaskDialog` .|
|[CTaskDialog:: AddRadioButton](#addradiobutton)|Öğesine radyo düğmesi ekler `CTaskDialog` .|
|[CTaskDialog:: ClickCommandControl](#clickcommandcontrol)|Program aracılığıyla bir komut düğmesi denetimine veya ortak düğmeye tıklar.|
|[CTaskDialog:: Clickbutton](#clickradiobutton)|Programlı olarak bir radyo düğmesini tıklatır.|
|[CTaskDialog::D oModal](#domodal)|Görüntüler `CTaskDialog` .|
|[CTaskDialog:: GetCommonButtonCount](#getcommonbuttoncount)|Kullanılabilen ortak düğmelerin sayısını alır.|
|[CTaskDialog:: GetCommonButtonFlag](#getcommonbuttonflag)|Standart bir Windows düğmesini sınıfla ilişkili ortak düğme türüne dönüştürür `CTaskDialog` .|
|[CTaskDialog:: Getcommonbuttonıd](#getcommonbuttonid)|Sınıfla ilişkili ortak düğme türlerinden birini `CTaskDialog` Standart bir Windows düğmesine dönüştürür.|
|[CTaskDialog:: GetOptions](#getoptions)|Bunun için seçenek bayraklarını döndürür `CTaskDialog` .|
|[CTaskDialog:: Getselectedcommandcontrolıd](#getselectedcommandcontrolid)|Seçili komut düğmesi denetimini döndürür.|
|[CTaskDialog:: GetSelectedRadioButtonID](#getselectedradiobuttonid)|Seçili radyo düğmesini döndürür.|
|[CTaskDialog:: Getdoğrulamaları Icationcheckboxstate](#getverificationcheckboxstate)|Doğrulama onay kutusunun durumunu alır.|
|[CTaskDialog:: IsCommandControlEnabled](#iscommandcontrolenabled)|Komut düğmesi denetimi veya ortak düğmenin etkinleştirilip etkinleştirilmediğini belirler.|
|[CTaskDialog:: IsRadioButtonEnabled](#isradiobuttonenabled)|Radyo düğmesinin etkinleştirilip etkinleştirilmediğini belirler.|
|[CTaskDialog:: IsSupported](#issupported)|Uygulamayı çalıştıran bilgisayarın öğesini destekleyip desteklemediğini belirler `CTaskDialog` .|
|[CTaskDialog:: LoadCommandControls](#loadcommandcontrols)|Dize tablosundaki verileri kullanarak komut düğmesi denetimleri ekler.|
|[CTaskDialog:: LoadRadioButtons](#loadradiobuttons)|Dize tablosundaki verileri kullanarak radyo düğmeleri ekler.|
|[CTaskDialog:: NavigateTo](#navigateto)|Odağı diğerine aktarır `CTaskDialog` .|
|[CTaskDialog:: OnCommandControlClick](#oncommandcontrolclick)|Kullanıcı bir komut düğmesi denetimine tıkladığında framework bu yöntemi çağırır.|
|[CTaskDialog:: OnCreate](#oncreate)|Framework, oluşturduktan sonra bu yöntemi çağırır `CTaskDialog` .|
|[CTaskDialog:: OnDestroy](#ondestroy)|Framework, yok etmeden önce bu yöntemi hemen çağırır `CTaskDialog` .|
|[CTaskDialog:: OnExpandButtonClick](#onexpandbuttonclick)|Kullanıcı genişletme düğmesine tıkladığında framework bu yöntemi çağırır.|
|[CTaskDialog:: OnHelp](#onhelp)|Kullanıcı yardım istediğinde framework bu yöntemi çağırır.|
|[CTaskDialog:: OnHyperlinkClick](#onhyperlinkclick)|Kullanıcı bir köprüye tıkladığında framework bu yöntemi çağırır.|
|[CTaskDialog:: OnInit](#oninit)|, Başlatıldığında Framework bu yöntemi çağırır `CTaskDialog` .|
|[CTaskDialog:: OnNavigatePage](#onnavigatepage)|Kullanıcı odağı içindeki denetimlerle ilgili olarak taşırken, çerçeve bu yöntemi çağırır `CTaskDialog` .|
|[CTaskDialog:: OnRadioButtonClick](#onradiobuttonclick)|Kullanıcı radyo düğmesi denetimini seçtiğinde Framework bu yöntemi çağırır.|
|[CTaskDialog:: OnTimer](#ontimer)|Zamanlayıcı süresi dolduğunda Framework bu yöntemi çağırır.|
|[CTaskDialog:: Ondoğrulamaları Icationcheckboxclick](#onverificationcheckboxclick)|Kullanıcı doğrulama onay kutusuna tıkladığında framework bu yöntemi çağırır.|
|[CTaskDialog:: RemoveAllCommandControls](#removeallcommandcontrols)|Tüm komut denetimlerini öğesinden kaldırır `CTaskDialog` .|
|[CTaskDialog:: RemoveAllRadioButtons](#removeallradiobuttons)|Tüm radyo düğmelerini öğesinden kaldırır `CTaskDialog` .|
|[CTaskDialog:: SetCommandControlOptions](#setcommandcontroloptions)|Üzerinde bir komut düğmesi denetimini güncelleştirir `CTaskDialog` .|
|[CTaskDialog:: SetCommonButtonOptions](#setcommonbuttonoptions)|Etkin olacak ortak düğmelerin bir alt kümesini güncelleştirir ve UAC yükseltmesi gerektirir.|
|[CTaskDialog:: SetCommonButtons](#setcommonbuttons)|Ortak düğmeleri öğesine ekler `CTaskDialog` .|
|[CTaskDialog:: SetContent](#setcontent)|İçeriğini güncelleştirir `CTaskDialog` .|
|[CTaskDialog:: SetDefaultCommandControl](#setdefaultcommandcontrol)|Varsayılan komut düğmesi denetimini belirtir.|
|[CTaskDialog:: SetDefaultRadioButton](#setdefaultradiobutton)|Varsayılan radyo düğmesini belirtir.|
|[CTaskDialog:: SetDialogWidth](#setdialogwidth)|Genişliğini ayarlar `CTaskDialog` .|
|[CTaskDialog:: SetExpansionArea](#setexpansionarea)|Öğesinin genişletme alanını güncelleştirir `CTaskDialog` .|
|[CTaskDialog:: SetFooterIcon](#setfootericon)|İçin altbilgi simgesini güncelleştirir `CTaskDialog` .|
|[CTaskDialog:: SetFooterText](#setfootertext)|Alt bilgisindeki metni güncelleştirir `CTaskDialog` .|
|[CTaskDialog:: Setmainıcon](#setmainicon)|Ana simgesini güncelleştirir `CTaskDialog` .|
|[CTaskDialog:: SetMainInstruction](#setmaininstruction)|Öğesinin ana yönergesini güncelleştirir `CTaskDialog` .|
|[CTaskDialog:: SetOptions](#setoptions)|Seçeneklerini yapılandırır `CTaskDialog` .|
|[CTaskDialog:: SetProgressBarMarquee](#setprogressbarmarquee)|İçin bir kayan yazı çubuğu yapılandırır `CTaskDialog` ve iletişim kutusuna ekler.|
|[CTaskDialog:: SetProgressBarPosition](#setprogressbarposition)|İlerleme çubuğunun konumunu ayarlar.|
|[CTaskDialog:: SetProgressBarRange](#setprogressbarrange)|İlerleme çubuğunun aralığını ayarlar.|
|[CTaskDialog:: SetProgressBarState](#setprogressbarstate)|İlerleme çubuğunun durumunu ayarlar ve üzerinde görüntüler `CTaskDialog` .|
|[CTaskDialog:: SetRadioButtonOptions](#setradiobuttonoptions)|Radyo düğmesini etkinleştirilir veya devre dışı bırakır.|
|[CTaskDialog:: Setdoğrulamaları Icationcheckbox](#setverificationcheckbox)|Doğrulama onay kutusunun denetlenen durumunu ayarlar.|
|[CTaskDialog:: Setdoğrulamaları Icationcheckboxtext](#setverificationcheckboxtext)|Doğrulama onay kutusunun sağ tarafındaki metni ayarlar.|
|[CTaskDialog:: SetWindowTitle](#setwindowtitle)|Başlığını ayarlar `CTaskDialog` .|
|[CTaskDialog:: ShowDialog](#showdialog)|Oluşturur ve görüntüler `CTaskDialog` .|
|[CTaskDialog:: TaskDialogCallback](#taskdialogcallback)|Framework çeşitli Windows iletilerine yanıt olarak bunu çağırır.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|-|-|
|`m_aButtons`|İçin komut düğmesi denetimleri dizisi `CTaskDialog` .|
|`m_aRadioButtons`|İçin radyo düğmesi denetimleri dizisi `CTaskDialog` .|
|`m_bVerified`|`TRUE` doğrulama onay kutusunun işaretli olduğunu belirtir; olmadığını `FALSE` gösterir.|
|`m_footerIcon`|Öğesinin alt bilgisindeki simgesi `CTaskDialog` .|
|`m_hWnd`|İçin penceresine yönelik bir tanıtıcı `CTaskDialog` .|
|`m_mainIcon`|Öğesinin ana simgesi `CTaskDialog` .|
|`m_nButtonDisabled`|Ortak düğmelerden hangisinin devre dışı bırakıldığını belirten bir maske.|
|`m_nButtonElevation`|Ortak düğmelerden hangisinin UAC yükseltmesi gerektirdiğini gösteren bir maske.|
|`m_nButtonId`|Seçili komut düğmesi denetiminin KIMLIĞI.|
|`m_nCommonButton`|Üzerinde hangi ortak düğmelerin görüntülendiğini gösteren bir maske `CTaskDialog` .|
|`m_nDefaultCommandControl`|Görüntülendiğinde seçilen komut düğmesi denetiminin KIMLIĞI `CTaskDialog` .|
|`m_nDefaultRadioButton`|Görüntülendiğinde seçilen radyo düğmesi denetiminin KIMLIĞI `CTaskDialog` .|
|`m_nFlags`|Seçeneklerini gösteren bir maske `CTaskDialog` .|
|`m_nProgressPos`|İlerleme çubuğunun geçerli konumu.  Bu değer ve arasında olmalıdır `m_nProgressRangeMin` `m_nProgressRangeMax` .|
|`m_nProgressRangeMax`|İlerleme çubuğunun en büyük değeri.|
|`m_nProgressRangeMin`|İlerleme çubuğunun minimum değeri.|
|`m_nProgressState`|İlerleme çubuğunun durumu. Daha fazla bilgi için bkz. [CTaskDialog:: SetProgressBarState](#setprogressbarstate).|
|`m_nRadioId`|Seçili radyo düğmesi denetiminin KIMLIĞI.|
|`m_nWidth`|`CTaskDialog`Piksel cinsinden genişlik.|
|`m_strCollapse`|`CTaskDialog`Genişletilmiş bilgiler gizliyse, genişleme kutusunun sağında görüntülenen dize.|
|`m_strContent`|Öğesinin içerik dizesi `CTaskDialog` .|
|`m_strExpand`|`CTaskDialog`Genişletilmiş bilgiler görüntülenirken, genişleme kutusunun sağında görüntülenen dize.|
|`m_strFooter`|Öğesinin altbilgisi `CTaskDialog` .|
|`m_strInformation`|İçin genişletilmiş bilgiler `CTaskDialog` .|
|`m_strMainInstruction`|Öğesinin ana yönergesi `CTaskDialog` .|
|`m_strTitle`|Öğesinin başlığı `CTaskDialog` .|
|`m_strVerification`|`CTaskDialog`Doğrulama onay kutusunun sağında görüntülenen dize.|

## <a name="remarks"></a>Açıklamalar

`CTaskDialog`Sınıfı, standart Windows ileti kutusunun yerini alır ve kullanıcıdan bilgi toplamak için yeni denetimler gibi ek işlevlere sahiptir. Bu sınıf, Visual Studio 2010 ve sonraki sürümlerde MFC kitaplığında bulunur. , `CTaskDialog` Windows Vista ile başlayarak kullanılabilir. Önceki Windows sürümleri `CTaskDialog` nesneyi görüntüleyemiyor. `CTaskDialog::IsSupported`Geçerli kullanıcının görev iletişim kutusunu görüntüleyip görüntülememe çalışma zamanını anlamak için kullanın. Standart Windows ileti kutusu hala desteklenmektedir.

`CTaskDialog`Yalnızca uygulamanızı Unicode kitaplığı kullanarak oluşturduğunuzda kullanılabilir.

`CTaskDialog`İki farklı oluşturucuya sahiptir. Bir Oluşturucu iki komut düğmesi ve en fazla altı normal düğme denetimi belirtmenize olanak sağlar. Öğesini oluşturduktan sonra daha fazla komut düğmesi ekleyebilirsiniz `CTaskDialog` . İkinci Oluşturucu herhangi bir komut düğmesini desteklemez, ancak sınırsız sayıda düzenli düğme denetimi ekleyebilirsiniz. Oluşturucular hakkında daha fazla bilgi için bkz. [CTaskDialog:: CTaskDialog](#ctaskdialog).

Aşağıdaki görüntüde `CTaskDialog` bazı denetimlerin konumunu göstermek için bir örnek gösterilmektedir.

![CTaskDialog örneği](../../mfc/reference/media/ctaskdialogsample.png "CTaskDialog örneği") <br/>
CTaskDialog örneği

## <a name="requirements"></a>Gereksinimler

**Gerekli en düşük işletim sistemi:** Windows Vista

**Üstbilgi:** afxtaskdialog. h

## <a name="ctaskdialogaddcommandcontrol"></a><a name="addcommandcontrol"></a> CTaskDialog:: AddCommandControl

Öğesine yeni bir komut düğmesi denetimi ekler `CTaskDialog` .

```cpp
void AddCommandControl(
    int nCommandControlID,
    const CString& strCaption,
    BOOL bEnabled = TRUE,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>Parametreler

*nCommandControlID*<br/>
'ndaki Komut denetimi kimlik numarası.

*strCaption*<br/>
'ndaki `CTaskDialog` Kullanıcının gösterdiği dize. Komutun amacını açıklamak için bu dizeyi kullanın.

*bEnabled*<br/>
'ndaki Yeni düğmenin etkin veya devre dışı olduğunu gösteren bir Boolean parametresi.

*Brequireselede*<br/>
'ndaki Bir komutun yükseltme gerektirip gerektirmediğini belirten bir Boole parametresi.

### <a name="remarks"></a>Açıklamalar

`CTaskDialog Class`Sınırsız sayıda komut düğmesi denetimini görüntüleyebilir. Ancak, bir `CTaskDialog` komut düğmesi denetimini görüntülerse, en fazla altı düğme görüntülenebilir. Bir `CTaskDialog` komut düğmesi denetimine sahip değilse, sınırsız sayıda düğme gösterebilir.

Kullanıcı bir komut düğmesi denetimi seçtiğinde, `CTaskDialog` kapanır. Uygulamanız [CTaskDialog::D oModal](#domodal)kullanarak iletişim kutusunu görüntülerse, `DoModal` Seçili komut düğmesi denetiminin *nCommandControlID* 'sini döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogaddradiobutton"></a><a name="addradiobutton"></a> CTaskDialog:: AddRadioButton

Öğesine radyo düğmesi ekler `CTaskDialog` .

```cpp
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,
    const CString& strCaption,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
'ndaki Radyo düğmesinin kimlik numarası.

*strCaption*<br/>
'ndaki `CTaskDialog` Radyo düğmesinin yanında görüntülenen dize.

*bEnabled*<br/>
'ndaki Radyo düğmesinin etkinleştirilip etkinleştirilmediğini belirten bir Boolean parametresi.

### <a name="remarks"></a>Açıklamalar

[CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md) için radyo düğmeleri kullanıcıdan bilgi toplamanıza olanak tanır. Hangi radyo düğmesinin seçili olduğunu anlamak için [CTaskDialog:: GetSelectedRadioButtonID](#getselectedradiobuttonid) işlevini kullanın.

, `CTaskDialog` Her radyo düğmesi Için *nRadioButtonID* parametrelerinin benzersiz olmasını gerektirmez. Ancak, her radyo düğmesi için ayrı bir tanımlayıcı kullanmıyorsanız beklenmeyen davranışlarla karşılaşabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogclickcommandcontrol"></a><a name="clickcommandcontrol"></a> CTaskDialog:: ClickCommandControl

Program aracılığıyla bir komut düğmesi denetimine veya ortak düğmeye tıklar.

```
protected:
void ClickCommandControl(int nCommandControlID) const;
```

### <a name="parameters"></a>Parametreler

*nCommandControlID*<br/>
'ndaki Tıklama denetiminin komut KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu yöntem Windows ileti TDM_CLICK_BUTTON oluşturur.

## <a name="ctaskdialogclickradiobutton"></a><a name="clickradiobutton"></a> CTaskDialog:: Clickbutton

Programlı olarak bir radyo düğmesini tıklatır.

```
protected:
void ClickRadioButton(int nRadioButtonID) const;
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
'ndaki Tıklama radyo düğmesinin KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu yöntem Windows ileti TDM_CLICK_RADIO_BUTTON oluşturur.

## <a name="ctaskdialogctaskdialog"></a><a name="ctaskdialog"></a> CTaskDialog:: CTaskDialog

[CTaskDialog sınıfının](../../mfc/reference/ctaskdialog-class.md)bir örneğini oluşturur.

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
'ndaki İçeriği için kullanılacak dize `CTaskDialog` .

*strMainInstruction*<br/>
'ndaki Öğesinin ana yönergesi `CTaskDialog` .

*strTitle*<br/>
'ndaki Öğesinin başlığı `CTaskDialog` .

*nCommonButtons*<br/>
'ndaki Öğesine eklenecek ortak düğmelerin maskesi `CTaskDialog` .

*nTaskDialogOptions*<br/>
'ndaki İçin kullanılacak seçenekler kümesi `CTaskDialog` .

*strFooter*<br/>
'ndaki Alt bilgi olarak kullanılacak dize.

*nIDCommandControlsFirst*<br/>
'ndaki İlk komutun dize KIMLIĞI.

*nIDCommandControlsLast*<br/>
'ndaki Son komutun dize KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Uygulamanıza ekleyebileceğiniz iki yol vardır `CTaskDialog` . İlk yöntem, oluşturmak için oluşturuculardan birini kullanmak `CTaskDialog` ve [CTaskDialog::D omodal](#domodal)kullanarak görüntülemektir. İkinci yöntem, açıkça bir nesne oluşturmadan görüntülemenizi sağlayan [CTaskDialog:: ShowDialog](#showdialog)statik işlevini kullanmaktır `CTaskDialog` `CTaskDialog` .

İkinci Oluşturucu, uygulamanızın kaynak dosyasındaki verileri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyasındaki dize tablosunda, ilişkili dize kimliklerine sahip birkaç dize vardır. Bu yöntem, *nIDCommandControlsFirst* ve *nCommandControlsLast* dahil olmak üzere dize tablosundaki her geçerli giriş için bir komut düğmesi denetimi ekler. Bu komut düğmesi denetimlerinde, dize tablosundaki dize denetimin başlığı ve dize KIMLIĞI denetimin KIMLIĞIDIR.

Geçerli seçeneklerin listesi için bkz. [CTaskDialog:: SetOptions](#setoptions) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogdomodal"></a><a name="domodal"></a> CTaskDialog::D oModal

Öğesini gösterir `CTaskDialog` ve kalıcı hale getirir.

```
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```

### <a name="parameters"></a>Parametreler

*hParent*<br/>
'ndaki İçin üst pencere `CTaskDialog` .

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tarafından yapılan seçime karşılık gelen bir tamsayı.

### <a name="remarks"></a>Açıklamalar

[CTaskDialog](../../mfc/reference/ctaskdialog-class.md)'un bu örneğini görüntüler. Uygulama daha sonra kullanıcının iletişim kutusunu kapatmasını bekler.

`CTaskDialog`Kullanıcı ortak bir düğmeyi seçtiğinde kapatır, bir komut bağlantı denetimi yapar veya kapatır `CTaskDialog` . Dönüş değeri, kullanıcının iletişim kutusunu nasıl kapattığını gösteren tanıtıcıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialoggetcommonbuttoncount"></a><a name="getcommonbuttoncount"></a> CTaskDialog:: GetCommonButtonCount

Ortak düğmelerin sayısını alır.

```
int GetCommonButtonCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanılabilen ortak düğmelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Ortak düğmeler [CTaskDialog:: CTaskDialog](#ctaskdialog)öğesine sağladığınız varsayılan düğmelerdir. [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md) , iletişim kutusunun alt kısmındaki düğmeleri görüntüler.

Numaralandırılmış düğme listesi CommCtrl. h içinde verilmiştir.

## <a name="ctaskdialoggetcommonbuttonflag"></a><a name="getcommonbuttonflag"></a> CTaskDialog:: GetCommonButtonFlag

Standart bir Windows düğmesini [CTaskDialog sınıfıyla](../../mfc/reference/ctaskdialog-class.md)ilişkili ortak düğme türüne dönüştürür.

```
int GetCommonButtonFlag(int nButtonId) const;
```

### <a name="parameters"></a>Parametreler

*Nbuttonıd*<br/>
'ndaki Standart Windows düğmesi değeri.

### <a name="return-value"></a>Dönüş Değeri

Karşılık gelen `CTaskDialog` ortak düğmenin değeri. Karşılık gelen ortak düğme yoksa, bu yöntem 0 döndürür.

## <a name="ctaskdialoggetcommonbuttonid"></a><a name="getcommonbuttonid"></a> CTaskDialog:: Getcommonbuttonıd

[CTaskDialog sınıfıyla](../../mfc/reference/ctaskdialog-class.md) ilişkili ortak düğme türlerinden birini standart bir Windows düğmesine dönüştürür.

```
int GetCommonButtonId(int nFlag);
```

### <a name="parameters"></a>Parametreler

*Nbayrak*<br/>
'ndaki Sınıfıyla ilişkili ortak düğme türü `CTaskDialog` .

### <a name="return-value"></a>Dönüş Değeri

Karşılık gelen standart Windows düğmesinin değeri. Karşılık gelen bir Windows düğmesi yoksa, yöntem 0 döndürür.

## <a name="ctaskdialoggetoptions"></a><a name="getoptions"></a> CTaskDialog:: GetOptions

Bunun için seçenek bayraklarını döndürür `CTaskDialog` .

```
int GetOptions() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçin bayraklar `CTaskDialog` .

### <a name="remarks"></a>Açıklamalar

[CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md)için kullanılabilen seçenekler hakkında daha fazla bilgi için bkz. [CTaskDialog:: SetOptions](#setoptions).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialoggetselectedcommandcontrolid"></a><a name="getselectedcommandcontrolid"></a> CTaskDialog:: Getselectedcommandcontrolıd

Seçili komut düğmesi denetimini döndürür.

```
int GetSelectedCommandControlID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili olan komut düğmesi denetiminin KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Kullanıcının seçtiği komut düğmesinin KIMLIĞINI almak için bu yöntemi kullanmanız gerekmez. Bu KIMLIK, [CTaskDialog::D oModal](#domodal) ya da [CTaskDialog:: ShowDialog](#showdialog)tarafından döndürülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialoggetselectedradiobuttonid"></a><a name="getselectedradiobuttonid"></a> CTaskDialog:: GetSelectedRadioButtonID

Seçili radyo düğmesini döndürür.

```
int GetSelectedRadioButtonID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçilen radyo düğmesinin KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Kullanıcı iletişim kutusunu kapattıktan sonra seçili radyo düğmesini almak için bu yöntemi kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialoggetverificationcheckboxstate"></a><a name="getverificationcheckboxstate"></a> CTaskDialog:: Getdoğrulamaları Icationcheckboxstate

Doğrulama onay kutusunun durumunu alır.

```
BOOL GetVerificationCheckboxState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Onay kutusu işaretliyse TRUE, değilse FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogiscommandcontrolenabled"></a><a name="iscommandcontrolenabled"></a> CTaskDialog:: IsCommandControlEnabled

Komut düğmesi denetimi veya düğmesinin etkinleştirilip etkinleştirilmediğini belirler.

```
BOOL IsCommandControlEnabled(int nCommandControlID) const;
```

### <a name="parameters"></a>Parametreler

*nCommandControlID*<br/>
'ndaki Sınanacak komut düğmesi denetimi veya düğmesinin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Denetim etkinse TRUE, değilse FALSE.

### <a name="remarks"></a>Açıklamalar

Komut düğmesi denetimlerinin ve * sınıfının ortak düğmelerinin kullanılabilirliğini öğrenmek için bu yöntemi kullanabilirsiniz `CTaskDialog` .

Eğer *nCommandControlID* , ortak bir `CTaskDialog` düğme ya da bir komut düğmesi denetimi için geçerli bir tanımlayıcı değilse, bu yöntem bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogisradiobuttonenabled"></a><a name="isradiobuttonenabled"></a> CTaskDialog:: IsRadioButtonEnabled

Radyo düğmesinin etkinleştirilip etkinleştirilmediğini belirler.

```
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
'ndaki Sınanacak radyo düğmesinin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Radyo düğmesi etkinse TRUE, değilse FALSE.

### <a name="remarks"></a>Açıklamalar

*NRadioButtonID* radyo düğmesi için geçerli bir tanımlayıcı değilse, bu yöntem bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogissupported"></a><a name="issupported"></a> CTaskDialog:: IsSupported

Uygulamayı çalıştıran bilgisayarın öğesini destekleyip desteklemediğini belirler `CTaskDialog` .

```
static BOOL IsSupported();
```

### <a name="return-value"></a>Dönüş Değeri

Bilgisayar destekliyorsa doğru `CTaskDialog` ; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Uygulamanızı çalıştıran bilgisayar sınıfını destekliyorsa, çalışma zamanını öğrenmek için bu işlevi kullanın `CTaskDialog` . Bilgisayar `CTaskDialog` öğesini desteklemiyorsa, kullanıcıya bilgi iletişim için başka bir yöntem sağlamanız gerekir. Uygulamanızı, sınıfı desteklemeyen bir bilgisayarda kullanmayı denediğinde kilitlenme kilitlenir `CTaskDialog` `CTaskDialog` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

## <a name="ctaskdialogloadcommandcontrols"></a><a name="loadcommandcontrols"></a> CTaskDialog:: LoadCommandControls

Dize tablosundaki verileri kullanarak komut düğmesi denetimleri ekler.

```cpp
void LoadCommandControls(
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast);
```

### <a name="parameters"></a>Parametreler

*nIDCommandControlsFirst*<br/>
'ndaki İlk komutun dize KIMLIĞI.

*nIDCommandControlsLast*<br/>
'ndaki Son komutun dize KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, uygulamanızın kaynak dosyasındaki verileri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyasındaki dize tablosunda, ilişkili dize kimliklerine sahip birkaç dize vardır. Bu yöntem kullanılarak eklenen yeni komut düğmesi denetimleri, denetimin alt yazısının dizesini ve denetimin KIMLIĞI için dize KIMLIĞINI kullanır. Seçilen dize aralığı, *nIDCommandControlsFirst* ve *nCommandControlsLast*, dahil olarak sağlanır. Aralıkta boş bir giriş varsa, yöntem bu giriş için bir komut düğmesi denetimi eklemez.

Varsayılan olarak, yeni komut düğmesi denetimleri etkindir ve yükseltme gerektirmez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogloadradiobuttons"></a><a name="loadradiobuttons"></a> CTaskDialog:: LoadRadioButtons

Dize tablosundaki verileri kullanarak radyo düğmesi denetimleri ekler.

```cpp
void LoadRadioButtons(
    int nIDRadioButtonsFirst,
    int nIDRadioButtonsLast);
```

### <a name="parameters"></a>Parametreler

*nIDRadioButtonsFirst*<br/>
'ndaki İlk radyo düğmesinin dize KIMLIĞI.

*nIDRadioButtonsLast*<br/>
'ndaki Son radyo düğmesinin dize KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, uygulamanızın kaynak dosyasındaki verileri kullanarak radyo düğmeleri oluşturur. Kaynak dosyasındaki dize tablosunda, ilişkili dize kimliklerine sahip birkaç dize vardır. Bu yöntem kullanılarak eklenen yeni radyo düğmeleri radyo düğmesinin başlığını ve radyo düğmesinin KIMLIĞI için dize KIMLIĞINI kullanır. Seçili dizeler aralığı *Nidradiobuttonsfirst* ve *nRadioButtonsLast*(dahil) tarafından sağlanır. Aralıkta boş bir giriş varsa, yöntem bu giriş için radyo düğmesi eklemez.

Varsayılan olarak, yeni radyo düğmeleri etkindir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialognavigateto"></a><a name="navigateto"></a> CTaskDialog:: NavigateTo

Odağı diğerine aktarır `CTaskDialog` .

```
protected:
void NavigateTo(CTaskDialog& oTaskDialog) const;
```

### <a name="parameters"></a>Parametreler

*oTaskDialog*<br/>
'ndaki `CTaskDialog` Odağı alan.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CTaskDialog` *oTaskDialog iletişim kutusunu* görüntülediğinde geçerli öğeyi gizler. *OTaskDialog* , geçerli ile aynı konumda görüntülenir `CTaskDialog` .

## <a name="ctaskdialogoncommandcontrolclick"></a><a name="oncommandcontrolclick"></a> CTaskDialog:: OnCommandControlClick

Kullanıcı bir komut düğmesi denetimine tıkladığında framework bu yöntemi çağırır.

```
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```

### <a name="parameters"></a>Parametreler

*nCommandControlID*<br/>
'ndaki Kullanıcının seçtiği komut düğmesi denetiminin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogoncreate"></a><a name="oncreate"></a> CTaskDialog:: OnCreate

Framework, oluşturduktan sonra bu yöntemi çağırır `CTaskDialog` .

```
virtual HRESULT OnCreate();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogondestroy"></a><a name="ondestroy"></a> CTaskDialog:: OnDestroy

Framework, yok etmeden önce bu yöntemi hemen çağırır `CTaskDialog` .

```
virtual HRESULT OnDestroy();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogonexpandbuttonclick"></a><a name="onexpandbuttonclick"></a> CTaskDialog:: OnExpandButtonClick

Kullanıcı genişletme düğmesine tıkladığında framework bu yöntemi çağırır.

```
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```

### <a name="parameters"></a>Parametreler

*bGenişletilmiş*<br/>
'ndaki Sıfır dışında bir değer, ek bilgilerin görüntülendiğini gösterir; 0, ek bilgilerin gizli olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogonhelp"></a><a name="onhelp"></a> CTaskDialog:: OnHelp

Kullanıcı yardım istediğinde framework bu yöntemi çağırır.

```
virtual HRESULT OnHelp();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogonhyperlinkclick"></a><a name="onhyperlinkclick"></a> CTaskDialog:: OnHyperlinkClick

Kullanıcı bir köprüye tıkladığında framework bu yöntemi çağırır.

```
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```

### <a name="parameters"></a>Parametreler

*strHref*<br/>
'ndaki Köprüyü temsil eden dize.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, S_OK döndürülmadan önce [ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) öğesini çağırır.

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogoninit"></a><a name="oninit"></a> CTaskDialog:: OnInit

, Başlatıldığında Framework bu yöntemi çağırır `CTaskDialog` .

```
virtual HRESULT OnInit();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogonnavigatepage"></a><a name="onnavigatepage"></a> CTaskDialog:: OnNavigatePage

Framework, [CTaskDialog:: NavigateTo](#navigateto) metoduna yanıt olarak bu yöntemi çağırır.

```
virtual HRESULT OnNavigatePage();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogonradiobuttonclick"></a><a name="onradiobuttonclick"></a> CTaskDialog:: OnRadioButtonClick

Kullanıcı radyo düğmesi denetimini seçtiğinde Framework bu yöntemi çağırır.

```
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
'ndaki Kullanıcının tıklamadığı radyo düğmesi denetiminin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogontimer"></a><a name="ontimer"></a> CTaskDialog:: OnTimer

Zamanlayıcı süresi dolduğunda Framework bu yöntemi çağırır.

```
virtual HRESULT OnTimer(long lTime);
```

### <a name="parameters"></a>Parametreler

*lTime*<br/>
'ndaki Oluşturulduktan veya zamanlayıcının sıfırlanmasından bu yana geçen süre (milisaniye) `CTaskDialog` .

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogonverificationcheckboxclick"></a><a name="onverificationcheckboxclick"></a> CTaskDialog:: Ondoğrulamaları Icationcheckboxclick

Kullanıcı doğrulama onay kutusuna tıkladığında framework bu yöntemi çağırır.

```
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```

### <a name="parameters"></a>Parametreler

*bChecked*<br/>
'ndaki DOĞRU, doğrulama onay kutusunun seçili olduğunu gösterir. FALSE, olmadığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctaskdialogremoveallcommandcontrols"></a><a name="removeallcommandcontrols"></a> CTaskDialog:: RemoveAllCommandControls

Tüm komut düğmesi denetimlerini öğesinden kaldırır `CTaskDialog` .

```cpp
void RemoveAllCommandControls();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogremoveallradiobuttons"></a><a name="removeallradiobuttons"></a> CTaskDialog:: RemoveAllRadioButtons

Tüm radyo düğmelerini öğesinden kaldırır `CTaskDialog` .

```cpp
void RemoveAllRadioButtons();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetcommandcontroloptions"></a><a name="setcommandcontroloptions"></a> CTaskDialog:: SetCommandControlOptions

Üzerinde bir komut düğmesi denetimini güncelleştirir `CTaskDialog` .

```cpp
void SetCommandControlOptions(
    int nCommandControlID,
    BOOL bEnabled,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>Parametreler

*nCommandControlID*<br/>
'ndaki Güncelleştirilecek komut denetiminin KIMLIĞI.

*bEnabled*<br/>
'ndaki Belirtilen komut düğmesi denetiminin etkin veya devre dışı olduğunu gösteren bir Boolean parametresi.

*Brequireselede*<br/>
'ndaki Belirtilen komut düğmesi denetiminin yükseltme gerektirip gerektirmediğini gösteren bir Boolean parametresi.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, bir komut düğmesi denetiminin etkin olup olmadığını veya sınıfa eklendikten sonra yükseltme gerektirip gerektirmediğini değiştirmek için kullanın `CTaskDialog` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogsetcommonbuttonoptions"></a><a name="setcommonbuttonoptions"></a> CTaskDialog:: SetCommonButtonOptions

Etkin olacak ortak düğmelerin bir alt kümesini güncelleştirir ve UAC yükseltmesi gerektirir.

```cpp
void SetCommonButtonOptions(
    int nDisabledButtonMask,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>Parametreler

*nDisabledButtonMask*<br/>
'ndaki Devre dışı bırakılacak ortak düğmeler için bir maske.

*Nelivationbuttonmask*<br/>
'ndaki Yükseltme gerektiren ortak düğmeler için bir maske.

### <a name="remarks"></a>Açıklamalar

CTaskDialog [:: CTaskDialog](#ctaskdialog) yapıcısını ve [CTaskDialog:: setcommonbutton](#setcommonbuttons)metodunu kullanarak [CTaskDialog sınıfının](../../mfc/reference/ctaskdialog-class.md) bir örneğine sunulan ortak düğmeleri ayarlayabilirsiniz. `CTaskDialog::SetCommonButtonOptions` , yeni ortak düğme eklenmesini desteklemez.

Bu yöntemi, bu için kullanılamayan ortak bir düğmeyi devre dışı bırakmak veya yükseltmek için kullanırsanız `CTaskDialog` , bu yöntem, izin makrosunu kullanarak bir özel durum oluşturur [](diagnostic-services.md#ensure) .

Bu yöntem, `CTaskDialog` daha önce devre dışı bırakılmış olsa bile, için kullanılabilir olan ancak *Ndisabledbuttonmask* içinde olmayan tüm düğmeleri sağlar. Bu yöntem, yükseltmeyi benzer bir şekilde ele alır: ortak düğme kullanılabilir ancak *Nelivationbuttonmask* içinde yoksa, ortak düğmeleri yükseltme gerektirmeyen şekilde kaydeder.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

## <a name="ctaskdialogsetcommonbuttons"></a><a name="setcommonbuttons"></a> CTaskDialog:: SetCommonButtons

Ortak düğmeleri öğesine ekler `CTaskDialog` .

```cpp
void SetCommonButtons(
    int nButtonMask,
    int nDisabledButtonMask = 0,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>Parametreler

*nButtonMask*<br/>
'ndaki Öğesine eklenecek düğmelerin maskesi `CTaskDialog` .

*nDisabledButtonMask*<br/>
'ndaki Devre dışı bırakılacak düğmelerin maskesi.

*Nelivationbuttonmask*<br/>
'ndaki Yükseltme gerektiren düğmelerin maskesi.

### <a name="remarks"></a>Açıklamalar

Bu sınıf örneği için görüntüleme penceresi oluşturulduktan sonra bu yöntemi çağrılamaz `CTaskDialog` . Bunu yaparsanız, bu yöntem bir özel durum oluşturur.

*NButtonMask* tarafından belirtilen düğmeler, daha önce öğesine eklenmiş olan tüm ortak düğmeleri geçersiz kılar `CTaskDialog` . Yalnızca *nButtonMask* içinde gösterilen düğmeler kullanılabilir.

*Ndisabledbuttonmask* veya *Netavationbuttonmask* , *nButtonMask* içinde olmayan bir düğme içeriyorsa, bu yöntem, [emin](diagnostic-services.md#ensure) olan makroyu kullanarak bir özel durum oluşturur.

Varsayılan olarak, tüm ortak düğmeler etkindir ve yükseltme gerektirmez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

## <a name="ctaskdialogsetcontent"></a><a name="setcontent"></a> CTaskDialog:: SetContent

İçeriğini güncelleştirir `CTaskDialog` .

```cpp
void SetContent(const CString& strContent);
```

### <a name="parameters"></a>Parametreler

*strContent*<br/>
'ndaki Kullanıcıya görüntülenecek dize.

### <a name="remarks"></a>Açıklamalar

Sınıfının içeriği, `CTaskDialog` iletişim kutusunun ana bölümünde kullanıcıya görüntülenen metindir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetdefaultcommandcontrol"></a><a name="setdefaultcommandcontrol"></a> CTaskDialog:: SetDefaultCommandControl

Varsayılan komut düğmesi denetimini belirtir.

```cpp
void SetDefaultCommandControl(int nCommandControlID);
```

### <a name="parameters"></a>Parametreler

*nCommandControlID*<br/>
'ndaki Varsayılan değer olacak komut düğmesi denetiminin KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Varsayılan komut düğmesi denetimi, `CTaskDialog` Kullanıcı ilk kez görüntülendiğinde seçili olan denetimdir.

Bu yöntem, *nCommandControlID* tarafından belirtilen komut düğmesi denetimini bulamazsa bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogsetdefaultradiobutton"></a><a name="setdefaultradiobutton"></a> CTaskDialog:: SetDefaultRadioButton

Varsayılan radyo düğmesini belirtir.

```cpp
void SetDefaultRadioButton(int nRadioButtonID);
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
'ndaki Varsayılan değer olacak radyo düğmesinin KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Varsayılan radyo düğmesi, `CTaskDialog` Kullanıcı ilk kez görüntülendiğinde seçili olan düğmedir.

Bu yöntem, *nRadioButtonID* tarafından belirtilen radyo düğmesini bulamazsa bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetdialogwidth"></a><a name="setdialogwidth"></a> CTaskDialog:: SetDialogWidth

Genişliğini ayarlar `CTaskDialog` .

```cpp
void SetDialogWidth(int nWidth = 0);
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
'ndaki İletişim kutusunun piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

*NWidth* parametresi 0 ' dan büyük veya buna eşit olmalıdır. Aksi takdirde, bu yöntem bir özel durum oluşturur.

*NWidth* değeri 0 olarak ayarlandıysa, bu yöntem iletişim kutusunu varsayılan boyuta ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetexpansionarea"></a><a name="setexpansionarea"></a> CTaskDialog:: SetExpansionArea

Öğesinin genişletme alanını güncelleştirir `CTaskDialog` .

```cpp
void SetExpansionArea(
    const CString& strExpandedInformation,
    const CString& strCollapsedLabel = _T(""),
    const CString& strExpandedLabel = _T(""));
```

### <a name="parameters"></a>Parametreler

*strExpandedInformation*<br/>
'ndaki `CTaskDialog` Kullanıcı genişletme düğmesine tıkladığında iletişim kutusunun ana gövdesinde görüntülenen dize.

*strCollapsedLabel*<br/>
'ndaki `CTaskDialog` Genişletilen alan daraltıldığında genişletme düğmesinin yanında görüntülenen dize.

*strExpandedLabel*<br/>
'ndaki `CTaskDialog` Genişletilen alan görüntülenirken genişletme düğmesinin yanında görüntülenen dize.

### <a name="remarks"></a>Açıklamalar

Sınıfının genişletme alanı `CTaskDialog` kullanıcıya ek bilgi sağlamanıza olanak sağlar. Genişletme alanı öğesinin ana kısmıdır `CTaskDialog` ve başlık ve içerik dizesinin hemen altında bulunur.

`CTaskDialog`İlk görüntülendiğinde, genişletilmiş bilgileri göstermez ve `strCollapsedLabel` genişletme düğmesinin yanına yerleştirir. Kullanıcı genişletme düğmesine tıkladığında, `CTaskDialog` *strExpandedInformation* görüntüler ve etiketi *strExpandedLabel* olarak değiştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetfootericon"></a><a name="setfootericon"></a> CTaskDialog:: SetFooterIcon

Uygulamasının altbilgi simgesini güncelleştirir `CTaskDialog` .

```cpp
void SetFooterIcon(HICON hFooterIcon);
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```

### <a name="parameters"></a>Parametreler

*Hfooterıcon simgesi*<br/>
'ndaki İçin yeni simge `CTaskDialog` .

*lpszFooterIcon*<br/>
'ndaki İçin yeni simge `CTaskDialog` .

### <a name="remarks"></a>Açıklamalar

Alt bilgi simgesi [CTaskDialog sınıfının](../../mfc/reference/ctaskdialog-class.md)altında görüntülenir. İlişkili alt bilgi metni olabilir. Alt bilgi metnini [CTaskDialog:: SetFooterText](#setfootertext)ile değiştirebilirsiniz.

Bu yöntem, görüntülenirse veya giriş parametresi NULL ise, makroyu [güvence altına](diagnostic-services.md#ensure) alarak bir özel durum oluşturur `CTaskDialog` .

`CTaskDialog`Yalnızca bir `HICON` veya `LPCWSTR` Altbilgi simgesini kabul edebilir. Bu, constructor veya [CTaskDialog:: SetOptions](#setoptions)içindeki TDF_USE_HICON_FOOTER seçenek ayarlanarak yapılandırılır. Varsayılan olarak, `CTaskDialog` `LPCWSTR` alt bilgi simgesi için giriş türü olarak kullanılmak üzere yapılandırılır. Bu yöntem, uygunsuz tür kullanarak simge ayarlamaya çalışırsanız bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetfootertext"></a><a name="setfootertext"></a> CTaskDialog:: SetFooterText

Alt bilgisindeki metni güncelleştirir `CTaskDialog` .

```cpp
void SetFooterText(const CString& strFooterText);
```

### <a name="parameters"></a>Parametreler

*strFooterText*<br/>
'ndaki Alt bilgi için yeni metin.

### <a name="remarks"></a>Açıklamalar

Alt simge simgesi, öğesinin altındaki altbilgi metninin yanında görünür `CTaskDialog` . Altbilgi simgesini [CTaskDialog:: SetFooterIcon](#setfootericon)ile değiştirebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetmainicon"></a><a name="setmainicon"></a> CTaskDialog:: Setmainıcon

Ana simgesini güncelleştirir `CTaskDialog` .

```cpp
void SetMainIcon(HICON hMainIcon);
void SetMainIcon(LPCWSTR lpszMainIcon);
```

### <a name="parameters"></a>Parametreler

*Hmainıcon*<br/>
'ndaki Yeni simge.

*lpszMainIcon*<br/>
'ndaki Yeni simge.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, görüntülenirse veya giriş parametresi NULL ise, makroyu [güvence altına](diagnostic-services.md#ensure) alarak bir özel durum oluşturur `CTaskDialog` .

`CTaskDialog`Yalnızca bir `HICON` veya bir `LPCWSTR` ana simge kabul edebilir. Bunu, oluşturucuda veya [CTaskDialog:: SetOptions](#setoptions) yönteminde TDF_USE_HICON_MAIN seçeneğini ayarlayarak yapılandırabilirsiniz. Varsayılan olarak, `CTaskDialog` `LPCWSTR` ana simgenin giriş türü olarak kullanılmak üzere yapılandırılır. Bu yöntem, uygunsuz tür kullanarak simge ayarlamaya çalışırsanız bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetmaininstruction"></a><a name="setmaininstruction"></a> CTaskDialog:: SetMainInstruction

Öğesinin ana yönergesini güncelleştirir `CTaskDialog` .

```cpp
void SetMainInstruction(const CString& strInstructions);
```

### <a name="parameters"></a>Parametreler

*Strınstructions*<br/>
'ndaki Yeni Main yönergesi.

### <a name="remarks"></a>Açıklamalar

Sınıfın ana yönergesi, `CTaskDialog` büyük bir kalın yazı tipiyle kullanıcıya görüntülenecek metindir. Başlık çubuğunun altındaki iletişim kutusunda bulunur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetoptions"></a><a name="setoptions"></a> CTaskDialog:: SetOptions

Seçeneklerini yapılandırır `CTaskDialog` .

```cpp
void SetOptions(int nOptionFlag);
```

### <a name="parameters"></a>Parametreler

*nOptionFlag*<br/>
'ndaki İçin kullanılacak bayraklar kümesi `CTaskDialog` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, için tüm geçerli seçenekleri temizler `CTaskDialog` . Geçerli seçenekleri korumak için bunları önce [CTaskDialog:: GetOptions](#getoptions) ile almanız ve bunları ayarlamak istediğiniz seçeneklerle birleştirmeniz gerekir.

Aşağıdaki tabloda tüm geçerli seçenekler listelenmektedir.

|Ad|Açıklama|
|-|-|
|TDF_ENABLE_HYPERLINKS|İçindeki köprüleri sunar `CTaskDialog` .|
|TDF_USE_HICON_MAIN|`CTaskDialog`Ana simge için kullanmak üzere öğesini yapılandırır `HICON` . Diğer bir seçenek de kullanmaktır `LPCWSTR` .|
|TDF_USE_HICON_FOOTER|' Nı `CTaskDialog` `HICON` Altbilgi simgesi için kullanmak üzere yapılandırır. Diğer bir seçenek de kullanmaktır `LPCWSTR` .|
|TDF_ALLOW_DIALOG_CANCELLATION|Kullanıcının `CTaskDialog` klavyeyi kullanarak veya **iptal** düğmesi etkin olmasa bile iletişim kutusunun sağ üst köşesindeki simgesini kullanarak kapatılmasını sağlar. Bu bayrak ayarlanmamışsa ve **iptal** düğmesi etkinleştirilmemişse, Kullanıcı alt + F4, kaçış tuşu veya başlık çubuğunun Kapat düğmesini kullanarak iletişim kutusunu kapatamazsınız.|
|TDF_USE_COMMAND_LINKS|`CTaskDialog`Komut düğmesi denetimlerini kullanmak için öğesini yapılandırır.|
|TDF_USE_COMMAND_LINKS_NO_ICON|`CTaskDialog`Denetimin yanında bir simge görüntülemeden komut düğmesi denetimlerini kullanmak için öğesini yapılandırır. TDF_USE_COMMAND_LINKS geçersiz kılmaları TDF_USE_COMMAND_LINKS_NO_ICON.|
|TDF_EXPAND_FOOTER_AREA|Genişleme alanının genişletilmekte olduğunu gösterir.|
|TDF_EXPANDED_BY_DEFAULT|Genişleme alanının varsayılan olarak genişletilip genişletilmeyeceğini belirler.|
|TDF_VERIFICATION_FLAG_CHECKED|Doğrulama onay kutusunun Şu anda seçili olduğunu gösterir.|
|TDF_SHOW_PROGRESS_BAR|, ' Nı `CTaskDialog` bir ilerleme çubuğu görüntüleyecek şekilde yapılandırır.|
|TDF_SHOW_MARQUEE_PROGRESS_BAR|İlerleme çubuğunu bir kayan yazı ilerleme çubuğu olacak şekilde yapılandırır. Bu seçeneği etkinleştirirseniz, TDF_SHOW_PROGRESS_BAR beklenen davranışa sahip olacak şekilde ayarlamanız gerekir.|
|TDF_CALLBACK_TIMER|`CTaskDialog`Geri çağırma aralığının yaklaşık 200 milisaniyeye ayarlandığını gösterir.|
|TDF_POSITION_RELATIVE_TO_WINDOW|`CTaskDialog`Üst pencereye göre ortalanacak şekilde yapılandırır. Bu bayrak etkinleştirilmemişse, `CTaskDialog` monitöre göre ortalandı.|
|TDF_RTL_LAYOUT|`CTaskDialog`Sağdan sola okuma düzeni için yapılandırır.|
|TDF_NO_DEFAULT_RADIO_BUTTON|Göründüğünde hiçbir radyo düğmesi seçilmediğini belirtir `CTaskDialog` .|
|TDF_CAN_BE_MINIMIZED|Kullanıcının öğesini en aza indirmesine olanak sağlar `CTaskDialog` . Bu seçeneği desteklemek için `CTaskDialog` kalıcı olamaz. MFC kalıcı olmayan bir şekilde desteklemediğinden, MFC bu seçeneği desteklemez `CTaskDialog` .|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetprogressbarmarquee"></a><a name="setprogressbarmarquee"></a> CTaskDialog:: SetProgressBarMarquee

İçin bir kayan yazı çubuğu yapılandırır `CTaskDialog` ve iletişim kutusuna ekler.

```cpp
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,
    int nMarqueeSpeed = 0);
```

### <a name="parameters"></a>Parametreler

*bEnabled*<br/>
'ndaki Kayan yazı çubuğunu etkinleştirmek için TRUE; Kayan yazı çubuğunu devre dışı bırakmak ve öğesinden kaldırmak için FALSE `CTaskDialog` .

*nMarqueeSpeed*<br/>
'ndaki Kayan yazı çubuğunun hızını gösteren bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Kayan yazı çubuğu, sınıfının ana metninin altında görünür `CTaskDialog` .

Kayan yazı çubuğunun hızını ayarlamak için *nMarqueeSpeed* kullanın; daha büyük değerler daha yavaş bir hız gösterir. *NMarqueeSpeed* için 0 değeri, kayan yazı çubuğunun Windows için varsayılan hızda taşınmasını sağlar.

Bu yöntem, *nMarqueeSpeed* 0 ' dan küçükse, makroyu [güvence altına](diagnostic-services.md#ensure) alarak bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarposition"></a><a name="setprogressbarposition"></a> CTaskDialog:: SetProgressBarPosition

İlerleme çubuğunun konumunu ayarlar.

```cpp
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>Parametreler

*nProgressPos*<br/>
'ndaki İlerleme çubuğunun konumu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *nProgressPos* , ilerleme çubuğu aralığında değilse, makroyu [güvence altına](diagnostic-services.md#ensure) alarak bir özel durum oluşturur. İlerleme çubuğu aralığını [CTaskDialog:: SetProgressBarRange](#setprogressbarrange)ile değiştirebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarrange"></a><a name="setprogressbarrange"></a> CTaskDialog:: SetProgressBarRange

İlerleme çubuğunun aralığını ayarlar.

```cpp
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>Parametreler

*nRangeMin*<br/>
'ndaki İlerleme çubuğunun alt sınırı.

*nRangeMax*<br/>
'ndaki İlerleme çubuğunun üst sınırı.

### <a name="remarks"></a>Açıklamalar

İlerleme çubuğunun konumu *nRangeMin* ve *nRangeMax* öğesine göre belirlenir. Örneğin, *nRangeMin* 50 ve *nrangemax* 100 ise, bir 75 konum, ilerleme çubuğunun üzerinde üst yarısında bulunur. İlerleme çubuğunun konumunu ayarlamak için [CTaskDialog:: SetProgressBarPosition](#setprogressbarposition) kullanın.

İlerleme çubuğunu göstermek için TDF_SHOW_PROGRESS_BAR seçeneğinin etkinleştirilmesi ve TDF_SHOW_MARQUEE_PROGRESS_BAR etkinleştirilmemelidir. Bu yöntem TDF_SHOW_PROGRESS_BAR otomatik olarak ayarlar ve TDF_SHOW_MARQUEE_PROGRESS_BAR temizler. [CTaskDialog sınıfının](../../mfc/reference/ctaskdialog-class.md)bu örneğinin seçeneklerini el ile değiştirmek Için [CTaskDialog:: SetOptions](#setoptions) kullanın.

Bu yöntem, *nRangeMin* *nRangeMax* değerinden küçük olmaması [halinde makrosuz](diagnostic-services.md#ensure) bir özel durum oluşturur. Bu yöntem, `CTaskDialog` zaten görüntüleniyorsa ve bir kayan yazı ilerleme çubuğu içeriyorsa bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarstate"></a><a name="setprogressbarstate"></a> CTaskDialog:: SetProgressBarState

İlerleme çubuğunun durumunu ayarlar ve üzerinde görüntüler `CTaskDialog` .

```cpp
void SetProgressBarState(int nState = PBST_NORMAL);
```

### <a name="parameters"></a>Parametreler

*nDurum*<br/>
'ndaki İlerleme çubuğunun durumu. Olası değerler için açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, zaten görüntüleniyorsa ve bir kayan yazı ilerleme çubuğu içeriyorsa, makroyu [güvence altına](diagnostic-services.md#ensure) alarak bir özel durum oluşturur `CTaskDialog` .

Aşağıdaki tabloda *nState* için olası değerler listelenmektedir. Bu durumda, ilerleme çubuğu, belirlenen durma konumuna ulaşıncaya kadar normal renkle doldurulur. Bu noktada, duruma göre renk değiştirilir.

|Ad|Açıklama|
|-|-|
|PBST_NORMAL|İlerleme çubuğu doldurulduktan sonra `CTaskDialog` çubuğun rengini değiştirmez. Varsayılan olarak, normal renk yeşil ' dir.|
|PBST_ERROR|İlerleme çubuğu doldurulduktan sonra, `CTaskDialog` çubuk rengini hata rengine dönüştürür. Varsayılan olarak, bu kırmızıdır.|
|PBST_PAUSED|İlerleme çubuğu doldurulduktan sonra, `CTaskDialog` çubuk rengini bekleme rengine dönüştürür. Bu, varsayılan olarak sarı.|

İlerleme çubuğunun [CTaskDialog:: SetProgressBarPosition](#setprogressbarposition)ile nerede durması gerektiğini belirleyebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetradiobuttonoptions"></a><a name="setradiobuttonoptions"></a> CTaskDialog:: SetRadioButtonOptions

Radyo düğmesini etkinleştirilir veya devre dışı bırakır.

```cpp
void SetRadioButtonOptions(
    int nRadioButtonID,
    BOOL bEnabled);
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
'ndaki Radyo düğmesi denetiminin KIMLIĞI.

*bEnabled*<br/>
'ndaki Radyo düğmesini etkinleştirmek için TRUE; Radyo düğmesini devre dışı bırakmak için FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, radyo düğmesi için *nRadioButtonID* GEÇERLI bir kimlik değilse, makroyu [güvence altına](diagnostic-services.md#ensure) alarak bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetverificationcheckbox"></a><a name="setverificationcheckbox"></a> CTaskDialog:: Setdoğrulamaları Icationcheckbox

Doğrulama onay kutusunun denetlenen durumunu ayarlar.

```cpp
void SetVerificationCheckbox(BOOL bChecked);
```

### <a name="parameters"></a>Parametreler

*bChecked*<br/>
'ndaki Görüntülendiğinde doğrulama onay kutusunun seçili olması için TRUE `CTaskDialog` ; Görüntülendiğinde doğrulama onay kutusunun seçimini yapmak için FALSE `CTaskDialog` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogsetverificationcheckboxtext"></a><a name="setverificationcheckboxtext"></a> CTaskDialog:: Setdoğrulamaları Icationcheckboxtext

Doğrulama onay kutusunun sağında görüntülenen metni ayarlar.

```cpp
void SetVerificationCheckboxText(CString& strVerificationText);
```

### <a name="parameters"></a>Parametreler

*Strdoğrulamaları Icationtext*<br/>
'ndaki Bu yöntemin, doğrulama onay kutusunun yanında gösterdiği metin.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, sınıfın bu örneği zaten görüntüleniyorsa, makroyu [güvence altına](diagnostic-services.md#ensure) alarak bir özel durum oluşturur `CTaskDialog` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogsetwindowtitle"></a><a name="setwindowtitle"></a> CTaskDialog:: SetWindowTitle

Başlığını ayarlar `CTaskDialog` .

```cpp
void SetWindowTitle(CString& strWindowTitle);
```

### <a name="parameters"></a>Parametreler

*strWindowTitle*<br/>
'ndaki İçin yeni başlık `CTaskDialog` .

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogshowdialog"></a><a name="showdialog"></a> CTaskDialog:: ShowDialog

Oluşturur ve görüntüler `CTaskDialog` .

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
'ndaki İçeriği için kullanılacak dize `CTaskDialog` .

*strMainInstruction*<br/>
'ndaki Öğesinin ana yönergesi `CTaskDialog` .

*strTitle*<br/>
'ndaki Öğesinin başlığı `CTaskDialog` .

*nIDCommandControlsFirst*<br/>
'ndaki İlk komutun dize KIMLIĞI.

*nIDCommandControlsLast*<br/>
'ndaki Son komutun dize KIMLIĞI.

*nCommonButtons*<br/>
'ndaki Öğesine eklenecek düğmelerin maskesi `CTaskDialog` .

*nTaskDialogOptions*<br/>
'ndaki İçin kullanılacak seçenekler kümesi `CTaskDialog` .

*strFooter*<br/>
'ndaki Alt bilgi olarak kullanılacak dize.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tarafından yapılan seçime karşılık gelen bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Bu statik yöntem, `CTaskDialog` kodunuzda açıkça bir nesne oluşturmadan sınıfın bir örneğini oluşturmanızı sağlar `CTaskDialog` . Bir nesne olmadığından, `CTaskDialog` `CTaskDialog` kullanıcıya göstermek için bu yöntemi kullanırsanız, başka bir yöntemi çağrılamaz `CTaskDialog` .

Bu yöntem, uygulamanızın kaynak dosyasındaki verileri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyasındaki dize tablosunda, ilişkili dize kimliklerine sahip birkaç dize vardır. Bu yöntem, *nIDCommandControlsFirst* ve *nCommandControlsLast* dahil olmak üzere dize tablosundaki her geçerli giriş için bir komut düğmesi denetimi ekler. Bu komut düğmesi denetimlerinde, dize tablosundaki dize denetimin başlığı ve dize KIMLIĞI denetimin KIMLIĞIDIR.

Geçerli seçeneklerin listesi için bkz. [CTaskDialog:: SetOptions](#setoptions) .

`CTaskDialog`Kullanıcı ortak bir düğmeyi seçtiğinde kapatır, bir komut bağlantı denetimi yapar veya kapatır `CTaskDialog` . Dönüş değeri, kullanıcının iletişim kutusunu nasıl kapattığını gösteren tanıtıcıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

## <a name="ctaskdialogtaskdialogcallback"></a><a name="taskdialogcallback"></a> CTaskDialog:: TaskDialogCallback

Framework çeşitli Windows iletilerine yanıt olarak bu yöntemi çağırır.

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

*lendiği*<br/>
'ndaki İçin yapısına yönelik bir tanıtıcı `m_hWnd` `CTaskDialog` .

*uNotification*<br/>
'ndaki Oluşturulan iletiyi belirten bildirim kodu.

*wParam*<br/>
'ndaki İleti hakkında daha fazla bilgi.

*lParam*<br/>
'ndaki İleti hakkında daha fazla bilgi.

*dwRefData*<br/>
'ndaki `CTaskDialog` Geri çağırma iletisinin geçerli olduğu nesneye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirli bildirim koduna bağlıdır. Daha fazla bilgi için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, `TaskDialogCallback` belirli bir iletiyi işler ve sonra [CTaskDialog sınıfının](../../mfc/reference/ctaskdialog-class.md)uygun on yöntemini çağırır. Örneğin, TDN_BUTTON_CLICKED iletisine yanıt olarak `TaskDialogCallback` [CTaskDialog:: OnCommandControlClick ' i](#oncommandcontrolclick)çağırır.

*WParam* ve *lParam* değerleri, oluşturulan özel iletiye bağlıdır. Bu değerlerin her ikisi de boş olması mümkündür. Aşağıdaki tabloda, desteklenen varsayılan bildirimler ve *wParam* ve *lParam* değerlerinin temsil ettiği değerler listelenmiştir. Türetilmiş bir sınıfta bu yöntemi geçersiz kılarsınız, aşağıdaki tablodaki her ileti için geri çağırma kodunu uygulamalısınız.

|Bildirim Iletisi|*wParam* Deeri|*lParam* Deeri|
|--------------------------|--------------------|--------------------|
|TDN_CREATED|Kullanılmadı.|Kullanılmadı.|
|TDN_NAVIGATED|Kullanılmadı.|Kullanılmadı.|
|TDN_BUTTON_CLICKED|Komut düğmesi denetim KIMLIĞI.|Kullanılmadı.|
|TDN_HYPERLINK_CLICKED|Kullanılmadı.|Bağlantıyı içeren bir [LPCWSTR](/windows/win32/WinProg/windows-data-types) yapısı.|
|TDN_TIMER|Oluşturulduktan veya zamanlayıcının sıfırlanmasından bu yana geçen süre (milisaniye) `CTaskDialog` .|Kullanılmadı.|
|TDN_DESTROYED|Kullanılmadı.|Kullanılmadı.|
|TDN_RADIO_BUTTON_CLICKED|Radyo düğmesi KIMLIĞI.|Kullanılmadı.|
|TDN_DIALOG_CONSTRUCTED|Kullanılmadı.|Kullanılmadı.|
|TDN_VERIFICATION_CLICKED|1 onay kutusu işaretliyse, 0 ise 0.|Kullanılmadı.|
|TDN_HELP|Kullanılmadı.|Kullanılmadı.|
|TDN_EXPANDO_BUTTON_CLICKED|genişletme alanı daraltılmışsa 0; genişletme metni görüntüleniyorsa sıfır dışı.|Kullanılmadı.|

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[İzlenecek yol: bir uygulamaya CTaskDialog ekleme](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)
