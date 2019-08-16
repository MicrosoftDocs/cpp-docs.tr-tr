---
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
ms.openlocfilehash: e2f77a2eda4397ed368e477165e876f9b8fbf936
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502352"
---
# <a name="ctaskdialog-class"></a>CTaskDialog sınıfı

İleti kutusu gibi işlev gören, ancak kullanıcıya ek bilgiler görüntüleyebilen bir açılır iletişim kutusu. Ayrıca `CTaskDialog` , kullanıcıdan bilgi toplamaya yönelik işlevleri de içerir.

## <a name="syntax"></a>Sözdizimi

```
class CTaskDialog : public CObject
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[CTaskDialog:: CTaskDialog](#ctaskdialog)|Bir `CTaskDialog` nesnesi oluşturur.|

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CTaskDialog:: AddCommandControl](#addcommandcontrol)|Öğesine bir komut düğmesi denetimi ekler `CTaskDialog`.|
|[CTaskDialog:: AddRadioButton](#addradiobutton)|Öğesine radyo düğmesi ekler `CTaskDialog`.|
|[CTaskDialog:: ClickCommandControl](#clickcommandcontrol)|Program aracılığıyla bir komut düğmesi denetimine veya ortak düğmeye tıklar.|
|[CTaskDialog:: Clickbutton](#clickradiobutton)|Programlı olarak bir radyo düğmesini tıklatır.|
|[CTaskDialog::D oModal](#domodal)|`CTaskDialog`Görüntüler.|
|[CTaskDialog:: GetCommonButtonCount](#getcommonbuttoncount)|Kullanılabilen ortak düğmelerin sayısını alır.|
|[CTaskDialog:: GetCommonButtonFlag](#getcommonbuttonflag)|Standart bir Windows düğmesini `CTaskDialog` sınıfla ilişkili ortak düğme türüne dönüştürür.|
|[CTaskDialog:: Getcommonbuttonıd](#getcommonbuttonid)|`CTaskDialog` Sınıfla ilişkili ortak düğme türlerinden birini standart bir Windows düğmesine dönüştürür.|
|[CTaskDialog:: GetOptions](#getoptions)|Bunun `CTaskDialog`için seçenek bayraklarını döndürür.|
|[CTaskDialog:: Getselectedcommandcontrolıd](#getselectedcommandcontrolid)|Seçili komut düğmesi denetimini döndürür.|
|[CTaskDialog:: GetSelectedRadioButtonID](#getselectedradiobuttonid)|Seçili radyo düğmesini döndürür.|
|[CTaskDialog:: Getdoğrulamaları Icationcheckboxstate](#getverificationcheckboxstate)|Doğrulama onay kutusunun durumunu alır.|
|[CTaskDialog:: IsCommandControlEnabled](#iscommandcontrolenabled)|Komut düğmesi denetimi veya ortak düğmenin etkinleştirilip etkinleştirilmediğini belirler.|
|[CTaskDialog:: IsRadioButtonEnabled](#isradiobuttonenabled)|Radyo düğmesinin etkinleştirilip etkinleştirilmediğini belirler.|
|[CTaskDialog:: IsSupported](#issupported)|Uygulamayı çalıştıran bilgisayarın öğesini destekleyip desteklemediğini `CTaskDialog`belirler.|
|[CTaskDialog:: LoadCommandControls](#loadcommandcontrols)|Dize tablosundaki verileri kullanarak komut düğmesi denetimleri ekler.|
|[CTaskDialog:: LoadRadioButtons](#loadradiobuttons)|Dize tablosundaki verileri kullanarak radyo düğmeleri ekler.|
|[CTaskDialog:: NavigateTo](#navigateto)|Odağı diğerine `CTaskDialog`aktarır.|
|[CTaskDialog:: OnCommandControlClick](#oncommandcontrolclick)|Kullanıcı bir komut düğmesi denetimine tıkladığında framework bu yöntemi çağırır.|
|[CTaskDialog:: OnCreate](#oncreate)|Framework, `CTaskDialog`oluşturduktan sonra bu yöntemi çağırır.|
|[CTaskDialog:: OnDestroy](#ondestroy)|Framework, `CTaskDialog`yok etmeden önce bu yöntemi hemen çağırır.|
|[CTaskDialog:: OnExpandButtonClick](#onexpandbuttonclick)|Kullanıcı genişletme düğmesine tıkladığında framework bu yöntemi çağırır.|
|[CTaskDialog:: OnHelp](#onhelp)|Kullanıcı yardım istediğinde framework bu yöntemi çağırır.|
|[CTaskDialog:: OnHyperlinkClick](#onhyperlinkclick)|Kullanıcı bir köprüye tıkladığında framework bu yöntemi çağırır.|
|[CTaskDialog:: OnInit](#oninit)|, Başlatıldığında Framework bu yöntemi `CTaskDialog` çağırır.|
|[CTaskDialog:: OnNavigatePage](#onnavigatepage)|Kullanıcı odağı içindeki denetimlerle `CTaskDialog`ilgili olarak taşırken, çerçeve bu yöntemi çağırır.|
|[CTaskDialog:: OnRadioButtonClick](#onradiobuttonclick)|Kullanıcı radyo düğmesi denetimini seçtiğinde Framework bu yöntemi çağırır.|
|[CTaskDialog:: OnTimer](#ontimer)|Zamanlayıcı süresi dolduğunda Framework bu yöntemi çağırır.|
|[CTaskDialog:: Ondoğrulamaları Icationcheckboxclick](#onverificationcheckboxclick)|Kullanıcı doğrulama onay kutusuna tıkladığında framework bu yöntemi çağırır.|
|[CTaskDialog:: RemoveAllCommandControls](#removeallcommandcontrols)|Tüm komut denetimlerini öğesinden `CTaskDialog`kaldırır.|
|[CTaskDialog:: RemoveAllRadioButtons](#removeallradiobuttons)|Tüm radyo düğmelerini öğesinden `CTaskDialog`kaldırır.|
|[CTaskDialog:: SetCommandControlOptions](#setcommandcontroloptions)|Üzerinde bir komut düğmesi denetimini güncelleştirir `CTaskDialog`.|
|[CTaskDialog:: SetCommonButtonOptions](#setcommonbuttonoptions)|Etkin olacak ortak düğmelerin bir alt kümesini güncelleştirir ve UAC yükseltmesi gerektirir.|
|[CTaskDialog:: SetCommonButtons](#setcommonbuttons)|Ortak düğmeleri öğesine `CTaskDialog`ekler.|
|[CTaskDialog:: SetContent](#setcontent)|İçeriğini `CTaskDialog`güncelleştirir.|
|[CTaskDialog:: SetDefaultCommandControl](#setdefaultcommandcontrol)|Varsayılan komut düğmesi denetimini belirtir.|
|[CTaskDialog:: SetDefaultRadioButton](#setdefaultradiobutton)|Varsayılan radyo düğmesini belirtir.|
|[CTaskDialog:: SetDialogWidth](#setdialogwidth)|Genişliğini `CTaskDialog`ayarlar.|
|[CTaskDialog:: SetExpansionArea](#setexpansionarea)|Öğesinin genişletme alanını güncelleştirir `CTaskDialog`.|
|[CTaskDialog:: SetFooterIcon](#setfootericon)|İçin altbilgi simgesini güncelleştirir `CTaskDialog`.|
|[CTaskDialog:: SetFooterText](#setfootertext)|Alt bilgisindeki `CTaskDialog`metni güncelleştirir.|
|[CTaskDialog:: Setmainıcon](#setmainicon)|Ana simgesini `CTaskDialog`güncelleştirir.|
|[CTaskDialog:: SetMainInstruction](#setmaininstruction)|Öğesinin ana yönergesini güncelleştirir `CTaskDialog`.|
|[CTaskDialog:: SetOptions](#setoptions)|Seçeneklerini `CTaskDialog`yapılandırır.|
|[CTaskDialog:: SetProgressBarMarquee](#setprogressbarmarquee)|İçin bir kayan yazı çubuğu yapılandırır `CTaskDialog` ve iletişim kutusuna ekler.|
|[CTaskDialog:: SetProgressBarPosition](#setprogressbarposition)|İlerleme çubuğunun konumunu ayarlar.|
|[CTaskDialog:: SetProgressBarRange](#setprogressbarrange)|İlerleme çubuğunun aralığını ayarlar.|
|[CTaskDialog:: SetProgressBarState](#setprogressbarstate)|İlerleme çubuğunun durumunu ayarlar ve üzerinde `CTaskDialog`görüntüler.|
|[CTaskDialog:: SetRadioButtonOptions](#setradiobuttonoptions)|Radyo düğmesini etkinleştirilir veya devre dışı bırakır.|
|[CTaskDialog:: Setdoğrulamaları Icationcheckbox](#setverificationcheckbox)|Doğrulama onay kutusunun denetlenen durumunu ayarlar.|
|[CTaskDialog:: Setdoğrulamaları Icationcheckboxtext](#setverificationcheckboxtext)|Doğrulama onay kutusunun sağ tarafındaki metni ayarlar.|
|[CTaskDialog:: SetWindowTitle](#setwindowtitle)|Başlığını `CTaskDialog`ayarlar.|
|[CTaskDialog:: ShowDialog](#showdialog)|Oluşturur ve görüntüler `CTaskDialog`.|
|[CTaskDialog:: TaskDialogCallback](#taskdialogcallback)|Framework çeşitli Windows iletilerine yanıt olarak bunu çağırır.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|`m_aButtons`|İçin komut düğmesi denetimleri dizisi `CTaskDialog`.|
|`m_aRadioButtons`|İçin radyo düğmesi denetimleri dizisi `CTaskDialog`.|
|`m_bVerified`|`TRUE`doğrulama onay kutusunun işaretli olduğunu belirtir; `FALSE` olmadığını gösterir.|
|`m_footerIcon`|Öğesinin alt bilgisindeki simgesi `CTaskDialog`.|
|`m_hWnd`|İçin penceresine yönelik `CTaskDialog`bir tanıtıcı.|
|`m_mainIcon`|Öğesinin ana simgesi `CTaskDialog`.|
|`m_nButtonDisabled`|Ortak düğmelerden hangisinin devre dışı bırakıldığını belirten bir maske.|
|`m_nButtonElevation`|Ortak düğmelerden hangisinin UAC yükseltmesi gerektirdiğini gösteren bir maske.|
|`m_nButtonId`|Seçili komut düğmesi denetiminin KIMLIĞI.|
|`m_nCommonButton`|Üzerinde hangi ortak düğmelerin görüntülendiğini gösteren bir maske `CTaskDialog`.|
|`m_nDefaultCommandControl`|Görüntülendiğinde seçilen `CTaskDialog` komut düğmesi denetiminin kimliği.|
|`m_nDefaultRadioButton`|Görüntülendiğinde seçilen `CTaskDialog` radyo düğmesi denetiminin kimliği.|
|`m_nFlags`|Seçeneklerini gösteren bir maske `CTaskDialog`.|
|`m_nProgressPos`|İlerleme çubuğunun geçerli konumu.  Bu değer ve `m_nProgressRangeMin` `m_nProgressRangeMax`arasında olmalıdır.|
|`m_nProgressRangeMax`|İlerleme çubuğunun en büyük değeri.|
|`m_nProgressRangeMin`|İlerleme çubuğunun minimum değeri.|
|`m_nProgressState`|İlerleme çubuğunun durumu. Daha fazla bilgi için bkz. [CTaskDialog:: SetProgressBarState](#setprogressbarstate).|
|`m_nRadioId`|Seçili radyo düğmesi denetiminin KIMLIĞI.|
|`m_nWidth`|Piksel `CTaskDialog` cinsinden genişlik.|
|`m_strCollapse`|Genişletilmiş bilgiler gizliyse `CTaskDialog` , genişleme kutusunun sağında görüntülenen dize.|
|`m_strContent`|Öğesinin içerik dizesi `CTaskDialog`.|
|`m_strExpand`|Genişletilmiş bilgiler görüntülenirken `CTaskDialog` , genişleme kutusunun sağında görüntülenen dize.|
|`m_strFooter`|Öğesinin `CTaskDialog`altbilgisi.|
|`m_strInformation`|İçin genişletilmiş bilgiler `CTaskDialog`.|
|`m_strMainInstruction`|Öğesinin ana yönergesi `CTaskDialog`.|
|`m_strTitle`|Öğesinin `CTaskDialog`başlığı.|
|`m_strVerification`|Doğrulama onay kutusunun sağında `CTaskDialog` görüntülenen dize.|

## <a name="remarks"></a>Açıklamalar

`CTaskDialog` Sınıfı, standart Windows ileti kutusunun yerini alır ve kullanıcıdan bilgi toplamak için yeni denetimler gibi ek işlevlere sahiptir. Bu sınıf, Visual Studio 2010 ve sonraki sürümlerde MFC kitaplığında bulunur. , `CTaskDialog` Windows Vista ile başlayarak kullanılabilir. Önceki Windows sürümleri `CTaskDialog` nesneyi görüntüleyemiyor. Geçerli `CTaskDialog::IsSupported` kullanıcının görev iletişim kutusunu görüntüleyip görüntülememe çalışma zamanını anlamak için kullanın. Standart Windows ileti kutusu hala desteklenmektedir.

`CTaskDialog` Yalnızca uygulamanızı Unicode kitaplığı kullanarak oluşturduğunuzda kullanılabilir.

İki farklı oluşturucuya sahiptir. `CTaskDialog` Bir Oluşturucu iki komut düğmesi ve en fazla altı normal düğme denetimi belirtmenize olanak sağlar. Öğesini oluşturduktan sonra `CTaskDialog`daha fazla komut düğmesi ekleyebilirsiniz. İkinci Oluşturucu herhangi bir komut düğmesini desteklemez, ancak sınırsız sayıda düzenli düğme denetimi ekleyebilirsiniz. Oluşturucular hakkında daha fazla bilgi için bkz. [CTaskDialog:: CTaskDialog](#ctaskdialog).

Aşağıdaki görüntüde bazı denetimlerin konumunu göstermek `CTaskDialog` için bir örnek gösterilmektedir.

![CTaskDialog örneği](../../mfc/reference/media/ctaskdialogsample.png "CTaskDialog örneği") <br/>
CTaskDialog örneği

## <a name="requirements"></a>Gereksinimler

**Gerekli en düşük işletim sistemi:** Windows Vista

**Üstbilgi:** afxtaskdialog. h

##  <a name="addcommandcontrol"></a>CTaskDialog:: AddCommandControl

Öğesine yeni bir komut düğmesi denetimi ekler `CTaskDialog`.

```
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
'ndaki Kullanıcının `CTaskDialog` gösterdiği dize. Komutun amacını açıklamak için bu dizeyi kullanın.

*bEnabled*<br/>
'ndaki Yeni düğmenin etkin veya devre dışı olduğunu gösteren bir Boolean parametresi.

*Brequireselede*<br/>
'ndaki Bir komutun yükseltme gerektirip gerektirmediğini belirten bir Boole parametresi.

### <a name="remarks"></a>Açıklamalar

`CTaskDialog Class` Sınırsız sayıda komut düğmesi denetimini görüntüleyebilir. Ancak, bir `CTaskDialog` komut düğmesi denetimini görüntülerse, en fazla altı düğme görüntülenebilir. Bir `CTaskDialog` komut düğmesi denetimine sahip değilse, sınırsız sayıda düğme gösterebilir.

Kullanıcı bir komut düğmesi denetimi `CTaskDialog` seçtiğinde, kapanır. Uygulamanız [CTaskDialog::D omodal](#domodal)kullanarak iletişim kutusunu görüntülerse, `DoModal` seçili komut düğmesi denetiminin *nCommandControlID* 'sini döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="addradiobutton"></a>CTaskDialog:: AddRadioButton

Öğesine radyo düğmesi ekler `CTaskDialog`.

```
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,
    const CString& strCaption,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
'ndaki Radyo düğmesinin kimlik numarası.

*strCaption*<br/>
'ndaki Radyo düğmesinin yanında `CTaskDialog` görüntülenen dize.

*bEnabled*<br/>
'ndaki Radyo düğmesinin etkinleştirilip etkinleştirilmediğini belirten bir Boolean parametresi.

### <a name="remarks"></a>Açıklamalar

[CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md) için radyo düğmeleri kullanıcıdan bilgi toplamanıza olanak tanır. Hangi radyo düğmesinin seçili olduğunu anlamak için [CTaskDialog:: GetSelectedRadioButtonID](#getselectedradiobuttonid) işlevini kullanın.

, `CTaskDialog` Her radyo düğmesi için *nRadioButtonID* parametrelerinin benzersiz olmasını gerektirmez. Ancak, her radyo düğmesi için ayrı bir tanımlayıcı kullanmıyorsanız beklenmeyen davranışlarla karşılaşabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="clickcommandcontrol"></a>CTaskDialog:: ClickCommandControl

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

##  <a name="clickradiobutton"></a>CTaskDialog:: Clickbutton

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

##  <a name="ctaskdialog"></a>CTaskDialog:: CTaskDialog

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
'ndaki İçeriği için kullanılacak dize `CTaskDialog`.

*strMainInstruction*<br/>
'ndaki Öğesinin ana yönergesi `CTaskDialog`.

*strTitle*<br/>
'ndaki Öğesinin `CTaskDialog`başlığı.

*nCommonButtons*<br/>
'ndaki Öğesine eklenecek ortak düğmelerin maskesi `CTaskDialog`.

*nTaskDialogOptions*<br/>
'ndaki İçin kullanılacak seçenekler kümesi `CTaskDialog`.

*strFooter*<br/>
'ndaki Alt bilgi olarak kullanılacak dize.

*nIDCommandControlsFirst*<br/>
'ndaki İlk komutun dize KIMLIĞI.

*nIDCommandControlsLast*<br/>
'ndaki Son komutun dize KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Uygulamanıza ekleyebileceğiniz `CTaskDialog` iki yol vardır. İlk yöntem, oluşturmak `CTaskDialog` için oluşturuculardan birini kullanmak ve [CTaskDialog::D omodal](#domodal)kullanarak görüntülemektir. İkinci yöntem, açıkça bir `CTaskDialog` nesne oluşturmadan görüntülemenizi `CTaskDialog` sağlayan [CTaskDialog:: ShowDialog](#showdialog)statik işlevini kullanmaktır.

İkinci Oluşturucu, uygulamanızın kaynak dosyasındaki verileri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyasındaki dize tablosunda, ilişkili dize kimliklerine sahip birkaç dize vardır. Bu yöntem, *nIDCommandControlsFirst* ve *nCommandControlsLast*dahil olmak üzere dize tablosundaki her geçerli giriş için bir komut düğmesi denetimi ekler. Bu komut düğmesi denetimlerinde, dize tablosundaki dize denetimin başlığı ve dize KIMLIĞI denetimin KIMLIĞIDIR.

Geçerli seçeneklerin listesi için bkz. [CTaskDialog:: SetOptions](#setoptions) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="domodal"></a>CTaskDialog::D oModal

Öğesini gösterir `CTaskDialog` ve kalıcı hale getirir.

```
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```

### <a name="parameters"></a>Parametreler

*hParent*<br/>
'ndaki İçin üst pencere `CTaskDialog`.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tarafından yapılan seçime karşılık gelen bir tamsayı.

### <a name="remarks"></a>Açıklamalar

[CTaskDialog](../../mfc/reference/ctaskdialog-class.md)'un bu örneğini görüntüler. Uygulama daha sonra kullanıcının iletişim kutusunu kapatmasını bekler.

Kullanıcı ortak bir düğmeyi seçtiğinde `CTaskDialog` kapatır,birkomutbağlantıdenetimiyaparveyakapatır.`CTaskDialog` Dönüş değeri, kullanıcının iletişim kutusunu nasıl kapattığını gösteren tanıtıcıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="getcommonbuttoncount"></a>CTaskDialog:: GetCommonButtonCount

Ortak düğmelerin sayısını alır.

```
int GetCommonButtonCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanılabilen ortak düğmelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Ortak düğmeler [CTaskDialog:: CTaskDialog](#ctaskdialog)öğesine sağladığınız varsayılan düğmelerdir. [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md) , iletişim kutusunun alt kısmındaki düğmeleri görüntüler.

Numaralandırılmış düğme listesi CommCtrl. h içinde verilmiştir.

##  <a name="getcommonbuttonflag"></a>CTaskDialog:: GetCommonButtonFlag

Standart bir Windows düğmesini [CTaskDialog sınıfıyla](../../mfc/reference/ctaskdialog-class.md)ilişkili ortak düğme türüne dönüştürür.

```
int GetCommonButtonFlag(int nButtonId) const;
```

### <a name="parameters"></a>Parametreler

*Nbuttonıd*<br/>
'ndaki Standart Windows düğmesi değeri.

### <a name="return-value"></a>Dönüş Değeri

Karşılık gelen `CTaskDialog` ortak düğmenin değeri. Karşılık gelen ortak düğme yoksa, bu yöntem 0 döndürür.

##  <a name="getcommonbuttonid"></a>CTaskDialog:: Getcommonbuttonıd

[CTaskDialog sınıfıyla](../../mfc/reference/ctaskdialog-class.md) ilişkili ortak düğme türlerinden birini standart bir Windows düğmesine dönüştürür.

```
int GetCommonButtonId(int nFlag);
```

### <a name="parameters"></a>Parametreler

*Nbayrak*<br/>
'ndaki `CTaskDialog` Sınıfıyla ilişkili ortak düğme türü.

### <a name="return-value"></a>Dönüş Değeri

Karşılık gelen standart Windows düğmesinin değeri. Karşılık gelen bir Windows düğmesi yoksa, yöntem 0 döndürür.

##  <a name="getoptions"></a>CTaskDialog:: GetOptions

Bunun `CTaskDialog`için seçenek bayraklarını döndürür.

```
int GetOptions() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçin `CTaskDialog`bayraklar.

### <a name="remarks"></a>Açıklamalar

[CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md)için kullanılabilen seçenekler hakkında daha fazla bilgi için bkz. [CTaskDialog:: SetOptions](#setoptions).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="getselectedcommandcontrolid"></a>CTaskDialog:: Getselectedcommandcontrolıd

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

##  <a name="getselectedradiobuttonid"></a>CTaskDialog:: GetSelectedRadioButtonID

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

##  <a name="getverificationcheckboxstate"></a>CTaskDialog:: Getdoğrulamaları Icationcheckboxstate

Doğrulama onay kutusunun durumunu alır.

```
BOOL GetVerificationCheckboxState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Onay kutusu işaretliyse TRUE, değilse FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

##  <a name="iscommandcontrolenabled"></a>CTaskDialog:: IsCommandControlEnabled

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

Komut düğmesi denetimlerinin ve * `CTaskDialog` sınıfının ortak düğmelerinin kullanılabilirliğini öğrenmek için bu yöntemi kullanabilirsiniz.

Eğer *nCommandControlID* , ortak `CTaskDialog` bir düğme ya da bir komut düğmesi denetimi için geçerli bir tanımlayıcı değilse, bu yöntem bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="isradiobuttonenabled"></a>CTaskDialog:: IsRadioButtonEnabled

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

##  <a name="issupported"></a>CTaskDialog:: IsSupported

Uygulamayı çalıştıran bilgisayarın öğesini destekleyip desteklemediğini `CTaskDialog`belirler.

```
static BOOL IsSupported();
```

### <a name="return-value"></a>Dönüş Değeri

Bilgisayar destekliyorsa `CTaskDialog`doğru; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Uygulamanızı çalıştıran bilgisayar `CTaskDialog` sınıfını destekliyorsa, çalışma zamanını öğrenmek için bu işlevi kullanın. Bilgisayar `CTaskDialog`öğesini desteklemiyorsa, kullanıcıya bilgi iletişim için başka bir yöntem sağlamanız gerekir. Uygulamanızı, `CTaskDialog` `CTaskDialog` sınıfı desteklemeyen bir bilgisayarda kullanmayı denediğinde kilitlenme kilitlenir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

##  <a name="loadcommandcontrols"></a>CTaskDialog:: LoadCommandControls

Dize tablosundaki verileri kullanarak komut düğmesi denetimleri ekler.

```
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

##  <a name="loadradiobuttons"></a>CTaskDialog:: LoadRadioButtons

Dize tablosundaki verileri kullanarak radyo düğmesi denetimleri ekler.

```
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

##  <a name="navigateto"></a>CTaskDialog:: NavigateTo

Odağı diğerine `CTaskDialog`aktarır.

```
protected:
void NavigateTo(CTaskDialog& oTaskDialog) const;
```

### <a name="parameters"></a>Parametreler

*oTaskDialog*<br/>
'ndaki `CTaskDialog` Odağı alan.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CTaskDialog` *oTaskDialog iletişim kutusunu*görüntülediğinde geçerli öğeyi gizler. *OTaskDialog* , geçerli `CTaskDialog`ile aynı konumda görüntülenir.

##  <a name="oncommandcontrolclick"></a>CTaskDialog:: OnCommandControlClick

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

##  <a name="oncreate"></a>CTaskDialog:: OnCreate

Framework, `CTaskDialog`oluşturduktan sonra bu yöntemi çağırır.

```
virtual HRESULT OnCreate();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

##  <a name="ondestroy"></a>CTaskDialog:: OnDestroy

Framework, `CTaskDialog`yok etmeden önce bu yöntemi hemen çağırır.

```
virtual HRESULT OnDestroy();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

##  <a name="onexpandbuttonclick"></a>CTaskDialog:: OnExpandButtonClick

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

##  <a name="onhelp"></a>CTaskDialog:: OnHelp

Kullanıcı yardım istediğinde framework bu yöntemi çağırır.

```
virtual HRESULT OnHelp();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

##  <a name="onhyperlinkclick"></a>CTaskDialog:: OnHyperlinkClick

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

Bu yöntem, S_OK döndürülbaşlamadan önce [ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) 'ı çağırır.

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

##  <a name="oninit"></a>CTaskDialog:: OnInit

, Başlatıldığında Framework bu yöntemi `CTaskDialog` çağırır.

```
virtual HRESULT OnInit();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

##  <a name="onnavigatepage"></a>CTaskDialog:: OnNavigatePage

Framework, [CTaskDialog:: NavigateTo](#navigateto) metoduna yanıt olarak bu yöntemi çağırır.

```
virtual HRESULT OnNavigatePage();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

##  <a name="onradiobuttonclick"></a>CTaskDialog:: OnRadioButtonClick

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

##  <a name="ontimer"></a>CTaskDialog:: OnTimer

Zamanlayıcı süresi dolduğunda Framework bu yöntemi çağırır.

```
virtual HRESULT OnTimer(long lTime);
```

### <a name="parameters"></a>Parametreler

*lTime*<br/>
'ndaki Oluşturulduktan veya zamanlayıcının sıfırlanmasından bu yana `CTaskDialog` geçen süre (milisaniye).

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Özel davranışı uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

##  <a name="onverificationcheckboxclick"></a>CTaskDialog:: Ondoğrulamaları Icationcheckboxclick

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

##  <a name="removeallcommandcontrols"></a>CTaskDialog:: RemoveAllCommandControls

Tüm komut düğmesi denetimlerini öğesinden `CTaskDialog`kaldırır.

```
void RemoveAllCommandControls();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="removeallradiobuttons"></a>CTaskDialog:: RemoveAllRadioButtons

Tüm radyo düğmelerini öğesinden `CTaskDialog`kaldırır.

```
void RemoveAllRadioButtons();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="setcommandcontroloptions"></a>CTaskDialog:: SetCommandControlOptions

Üzerinde bir komut düğmesi denetimini güncelleştirir `CTaskDialog`.

```
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

Bu yöntemi, `CTaskDialog` bir komut düğmesi denetiminin etkin olup olmadığını veya sınıfa eklendikten sonra yükseltme gerektirip gerektirmediğini değiştirmek için kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="setcommonbuttonoptions"></a>CTaskDialog:: SetCommonButtonOptions

Etkin olacak ortak düğmelerin bir alt kümesini güncelleştirir ve UAC yükseltmesi gerektirir.

```
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

CTaskDialog [:: CTaskDialog](#ctaskdialog) yapıcısını ve [CTaskDialog:: setcommonbutton](#setcommonbuttons)metodunu kullanarak [CTaskDialog sınıfının](../../mfc/reference/ctaskdialog-class.md) bir örneğine sunulan ortak düğmeleri ayarlayabilirsiniz. `CTaskDialog::SetCommonButtonOptions`, yeni ortak düğme eklenmesini desteklemez.

Bu yöntemi, bu `CTaskDialog`için kullanılamayan ortak bir düğmeyi devre dışı bırakmak veya yükseltmek için kullanırsanız, bu yöntem, izin makrosunu kullanarak bir özel durum oluşturur [](diagnostic-services.md#ensure) .

Bu yöntem, daha önce devre dışı bırakılmış olsa bile `CTaskDialog` , için kullanılabilir olan ancak *ndisabledbuttonmask*içinde olmayan tüm düğmeleri sağlar. Bu yöntem, yükseltmeyi benzer bir şekilde ele alır: ortak düğme kullanılabilir ancak *Nelivationbuttonmask*içinde yoksa, ortak düğmeleri yükseltme gerektirmeyen şekilde kaydeder.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

##  <a name="setcommonbuttons"></a>CTaskDialog:: SetCommonButtons

Ortak düğmeleri öğesine `CTaskDialog`ekler.

```
void SetCommonButtons(
    int nButtonMask,
    int nDisabledButtonMask = 0,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>Parametreler

*nButtonMask*<br/>
'ndaki Öğesine eklenecek düğmelerin maskesi `CTaskDialog`.

*nDisabledButtonMask*<br/>
'ndaki Devre dışı bırakılacak düğmelerin maskesi.

*Nelivationbuttonmask*<br/>
'ndaki Yükseltme gerektiren düğmelerin maskesi.

### <a name="remarks"></a>Açıklamalar

Bu `CTaskDialog` sınıf örneği için görüntüleme penceresi oluşturulduktan sonra bu yöntemi çağrılamaz. Bunu yaparsanız, bu yöntem bir özel durum oluşturur.

*NButtonMask* tarafından belirtilen düğmeler, `CTaskDialog`daha önce öğesine eklenmiş olan tüm ortak düğmeleri geçersiz kılar. Yalnızca *nButtonMask* içinde gösterilen düğmeler kullanılabilir.

*Ndisabledbuttonmask* veya *Netavationbuttonmask* , *nButtonMask*içinde olmayan bir düğme içeriyorsa, bu yöntem, [emin](diagnostic-services.md#ensure) olan makroyu kullanarak bir özel durum oluşturur.

Varsayılan olarak, tüm ortak düğmeler etkindir ve yükseltme gerektirmez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

##  <a name="setcontent"></a>CTaskDialog:: SetContent

İçeriğini `CTaskDialog`güncelleştirir.

```
void SetContent(const CString& strContent);
```

### <a name="parameters"></a>Parametreler

*strContent*<br/>
'ndaki Kullanıcıya görüntülenecek dize.

### <a name="remarks"></a>Açıklamalar

`CTaskDialog` Sınıfının içeriği, iletişim kutusunun ana bölümünde kullanıcıya görüntülenen metindir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setdefaultcommandcontrol"></a>CTaskDialog:: SetDefaultCommandControl

Varsayılan komut düğmesi denetimini belirtir.

```
void SetDefaultCommandControl(int nCommandControlID);
```

### <a name="parameters"></a>Parametreler

*nCommandControlID*<br/>
'ndaki Varsayılan değer olacak komut düğmesi denetiminin KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Varsayılan komut düğmesi denetimi, `CTaskDialog` Kullanıcı ilk kez görüntülendiğinde seçili olan denetimdir.

Bu yöntem, *nCommandControlID*tarafından belirtilen komut düğmesi denetimini bulamazsa bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="setdefaultradiobutton"></a>CTaskDialog:: SetDefaultRadioButton

Varsayılan radyo düğmesini belirtir.

```
void SetDefaultRadioButton(int nRadioButtonID);
```

### <a name="parameters"></a>Parametreler

*nRadioButtonID*<br/>
'ndaki Varsayılan değer olacak radyo düğmesinin KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Varsayılan radyo düğmesi, Kullanıcı ilk kez görüntülendiğinde seçili `CTaskDialog` olan düğmedir.

Bu yöntem, *nRadioButtonID*tarafından belirtilen radyo düğmesini bulamazsa bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="setdialogwidth"></a>CTaskDialog:: SetDialogWidth

Genişliğini `CTaskDialog`ayarlar.

```
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

##  <a name="setexpansionarea"></a>CTaskDialog:: SetExpansionArea

Öğesinin genişletme alanını güncelleştirir `CTaskDialog`.

```
void SetExpansionArea(
    const CString& strExpandedInformation,
    const CString& strCollapsedLabel = _T(""),
    const CString& strExpandedLabel = _T(""));
```

### <a name="parameters"></a>Parametreler

*strExpandedInformation*<br/>
'ndaki Kullanıcı genişletme düğmesine tıkladığında `CTaskDialog` iletişim kutusunun ana gövdesinde görüntülenen dize.

*strCollapsedLabel*<br/>
'ndaki Genişletilen alan daraltıldığında genişletme `CTaskDialog` düğmesinin yanında görüntülenen dize.

*strExpandedLabel*<br/>
'ndaki Genişletilen alan görüntülenirken genişletme `CTaskDialog` düğmesinin yanında görüntülenen dize.

### <a name="remarks"></a>Açıklamalar

`CTaskDialog` Sınıfının genişletme alanı kullanıcıya ek bilgi sağlamanıza olanak sağlar. Genişletme alanı öğesinin `CTaskDialog`ana kısmıdır ve başlık ve içerik dizesinin hemen altında bulunur.

İlk görüntülendiğinde, genişletilmiş bilgileri göstermez ve genişletme düğmesinin yanına yerleştirir `strCollapsedLabel`. `CTaskDialog` Kullanıcı genişletme düğmesine `CTaskDialog` tıkladığında, *strExpandedInformation* görüntüler ve etiketi *strExpandedLabel*olarak değiştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setfootericon"></a>CTaskDialog:: SetFooterIcon

Uygulamasının altbilgi simgesini güncelleştirir `CTaskDialog`.

```
void SetFooterIcon(HICON hFooterIcon);
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```

### <a name="parameters"></a>Parametreler

*Hfooterıcon simgesi*<br/>
'ndaki İçin yeni simge `CTaskDialog`.

*lpszFooterIcon*<br/>
'ndaki İçin yeni simge `CTaskDialog`.

### <a name="remarks"></a>Açıklamalar

Alt bilgi simgesi [CTaskDialog sınıfının](../../mfc/reference/ctaskdialog-class.md)altında görüntülenir. İlişkili alt bilgi metni olabilir. Alt bilgi metnini [CTaskDialog:: SetFooterText](#setfootertext)ile değiştirebilirsiniz.

Bu yöntem, `CTaskDialog` görüntülenirse veya giriş parametresi null ise, makroyu [güvence altına](diagnostic-services.md#ensure) alarak bir özel durum oluşturur.

Yalnızca bir `HICON` veya Altbilgi`LPCWSTR` simgesini kabul edebilir.`CTaskDialog` Bu, constructor veya [CTaskDialog:: SetOptions](#setoptions)içindeki TDF_USE_HICON_FOOTER seçeneği ayarlanarak yapılandırılır. Varsayılan `CTaskDialog` olarak, alt bilgi simgesi için giriş `LPCWSTR` türü olarak kullanılmak üzere yapılandırılır. Bu yöntem, uygunsuz tür kullanarak simge ayarlamaya çalışırsanız bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setfootertext"></a>CTaskDialog:: SetFooterText

Alt bilgisindeki `CTaskDialog`metni güncelleştirir.

```
void SetFooterText(const CString& strFooterText);
```

### <a name="parameters"></a>Parametreler

*strFooterText*<br/>
'ndaki Alt bilgi için yeni metin.

### <a name="remarks"></a>Açıklamalar

Alt simge simgesi, `CTaskDialog`öğesinin altındaki altbilgi metninin yanında görünür. Altbilgi simgesini [CTaskDialog:: SetFooterIcon](#setfootericon)ile değiştirebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setmainicon"></a>CTaskDialog:: Setmainıcon

Ana simgesini `CTaskDialog`güncelleştirir.

```
void SetMainIcon(HICON hMainIcon);
void SetMainIcon(LPCWSTR lpszMainIcon);
```

### <a name="parameters"></a>Parametreler

*Hmainıcon*<br/>
'ndaki Yeni simge.

*lpszMainIcon*<br/>
'ndaki Yeni simge.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CTaskDialog` görüntülenirse veya giriş parametresi null ise, makroyu [güvence altına](diagnostic-services.md#ensure) alarak bir özel durum oluşturur.

Yalnızca bir`HICON` veya bir`LPCWSTR` ana simge kabul edebilir. `CTaskDialog` Bunu oluşturucuda veya [CTaskDialog:: SetOptions](#setoptions) yönteminde TDF_USE_HICON_MAIN seçeneğini ayarlayarak yapılandırabilirsiniz. Varsayılan `CTaskDialog` olarak, ana simgenin giriş türü olarak `LPCWSTR` kullanılmak üzere yapılandırılır. Bu yöntem, uygunsuz tür kullanarak simge ayarlamaya çalışırsanız bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setmaininstruction"></a>CTaskDialog:: SetMainInstruction

Öğesinin ana yönergesini güncelleştirir `CTaskDialog`.

```
void SetMainInstruction(const CString& strInstructions);
```

### <a name="parameters"></a>Parametreler

*Strınstructions*<br/>
'ndaki Yeni Main yönergesi.

### <a name="remarks"></a>Açıklamalar

`CTaskDialog` Sınıfın ana yönergesi, büyük bir kalın yazı tipiyle kullanıcıya görüntülenecek metindir. Başlık çubuğunun altındaki iletişim kutusunda bulunur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setoptions"></a>CTaskDialog:: SetOptions

Seçeneklerini `CTaskDialog`yapılandırır.

```
void SetOptions(int nOptionFlag);
```

### <a name="parameters"></a>Parametreler

*nOptionFlag*<br/>
'ndaki İçin kullanılacak bayraklar kümesi `CTaskDialog`.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CTaskDialog`için tüm geçerli seçenekleri temizler. Geçerli seçenekleri korumak için bunları önce [CTaskDialog:: GetOptions](#getoptions) ile almanız ve bunları ayarlamak istediğiniz seçeneklerle birleştirmeniz gerekir.

Aşağıdaki tabloda tüm geçerli seçenekler listelenmektedir.

|||
|-|-|
|TDF_ENABLE_HYPERLINKS|İçindeki köprüleri sunar `CTaskDialog`.|
|TDF_USE_HICON_MAIN|Ana simge `HICON` için kullanmak üzereöğesiniyapılandırır.`CTaskDialog` Diğer bir `LPCWSTR`seçenek de kullanmaktır.|
|TDF_USE_HICON_FOOTER|' Nı altbilgi simgesi `HICON` için kullanmak üzereyapılandırır.`CTaskDialog` Diğer bir `LPCWSTR`seçenek de kullanmaktır.|
|TDF_ALLOW_DIALOG_CANCELLATION|Kullanıcının klavyeyi kullanarak veya **iptal** düğmesi `CTaskDialog` etkin olmasa bile iletişim kutusunun sağ üst köşesindeki simgesini kullanarak kapatılmasını sağlar. Bu bayrak ayarlanmamışsa ve **iptal** düğmesi etkinleştirilmemişse, Kullanıcı alt + F4, kaçış tuşu veya başlık çubuğunun Kapat düğmesini kullanarak iletişim kutusunu kapatamazsınız.|
|TDF_USE_COMMAND_LINKS|Komut düğmesi denetimlerini kullanmak içinöğesiniyapılandırır.`CTaskDialog`|
|TDF_USE_COMMAND_LINKS_NO_ICON|Denetimin yanında bir simge görüntülemeden komut düğmesi denetimlerini kullanmak içinöğesiniyapılandırır.`CTaskDialog` TDF_USE_COMMAND_LINKS geçersiz kılar TDF_USE_COMMAND_LINKS_NO_ICON.|
|TDF_EXPAND_FOOTER_AREA|Genişleme alanının genişletilmekte olduğunu gösterir.|
|TDF_EXPANDED_BY_DEFAULT|Genişleme alanının varsayılan olarak genişletilip genişletilmeyeceğini belirler.|
|TDF_VERIFICATION_FLAG_CHECKED|Doğrulama onay kutusunun Şu anda seçili olduğunu gösterir.|
|TDF_SHOW_PROGRESS_BAR|, `CTaskDialog` ' Nı bir ilerleme çubuğu görüntüleyecek şekilde yapılandırır.|
|TDF_SHOW_MARQUEE_PROGRESS_BAR|İlerleme çubuğunu bir kayan yazı ilerleme çubuğu olacak şekilde yapılandırır. Bu seçeneği etkinleştirirseniz, TDF_SHOW_PROGRESS_BAR beklenen davranışa sahip olacak şekilde ayarlamanız gerekir.|
|TDF_CALLBACK_TIMER|`CTaskDialog` Geri çağırma aralığının yaklaşık 200 milisaniyeye ayarlandığını gösterir.|
|TDF_POSITION_RELATIVE_TO_WINDOW|Üst pencereye göre ortalanacak şekildeyapılandırır.`CTaskDialog` Bu bayrak etkinleştirilmemişse `CTaskDialog` , monitöre göre ortalandı.|
|TDF_RTL_LAYOUT|Sağdan sola okuma düzeni içinyapılandırır.`CTaskDialog`|
|TDF_NO_DEFAULT_RADIO_BUTTON|`CTaskDialog` Göründüğünde hiçbir radyo düğmesi seçilmediğini belirtir.|
|TDF_CAN_BE_MINIMIZED|Kullanıcının öğesini en aza indirmesine `CTaskDialog`olanak sağlar. Bu seçeneği `CTaskDialog` desteklemek için kalıcı olamaz. MFC kalıcı `CTaskDialog`olmayan bir şekılde desteklemediğinden, MFC bu seçeneği desteklemez.|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setprogressbarmarquee"></a>CTaskDialog:: SetProgressBarMarquee

İçin bir kayan yazı çubuğu yapılandırır `CTaskDialog` ve iletişim kutusuna ekler.

```
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,
    int nMarqueeSpeed = 0);
```

### <a name="parameters"></a>Parametreler

*bEnabled*<br/>
'ndaki Kayan yazı çubuğunu etkinleştirmek için TRUE; Kayan yazı çubuğunu devre dışı bırakmak ve öğesinden `CTaskDialog`kaldırmak için false.

*nMarqueeSpeed*<br/>
'ndaki Kayan yazı çubuğunun hızını gösteren bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Kayan yazı çubuğu, `CTaskDialog` sınıfının ana metninin altında görünür.

Kayan yazı çubuğunun hızını ayarlamak için *nMarqueeSpeed* kullanın; daha büyük değerler daha yavaş bir hız gösterir. *NMarqueeSpeed* için 0 değeri, kayan yazı çubuğunun Windows için varsayılan hızda taşınmasını sağlar.

Bu yöntem, *nMarqueeSpeed* 0 ' dan küçükse, makroyu [güvence altına](diagnostic-services.md#ensure) alarak bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setprogressbarposition"></a>CTaskDialog:: SetProgressBarPosition

İlerleme çubuğunun konumunu ayarlar.

```
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>Parametreler

*nProgressPos*<br/>
'ndaki İlerleme çubuğunun konumu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *nProgressPos* , ilerleme çubuğu aralığında değilse, makroyu [güvence altına](diagnostic-services.md#ensure) alarak bir özel durum oluşturur. İlerleme çubuğu aralığını [CTaskDialog:: SetProgressBarRange](#setprogressbarrange)ile değiştirebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setprogressbarrange"></a>CTaskDialog:: SetProgressBarRange

İlerleme çubuğunun aralığını ayarlar.

```
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

İlerleme çubuğunun konumu *nRangeMin* ve *nRangeMax*öğesine göre belirlenir. Örneğin, *nRangeMin* 50 ve *nrangemax* 100 ise, bir 75 konum, ilerleme çubuğunun üzerinde üst yarısında bulunur. İlerleme çubuğunun konumunu ayarlamak için [CTaskDialog:: SetProgressBarPosition](#setprogressbarposition) kullanın.

İlerleme çubuğunu göstermek için TDF_SHOW_PROGRESS_BAR seçeneğinin etkinleştirilmesi gerekir ve TDF_SHOW_MARQUEE_PROGRESS_BAR etkinleştirilmemelidir. Bu yöntem TDF_SHOW_PROGRESS_BAR otomatik olarak ayarlar ve TDF_SHOW_MARQUEE_PROGRESS_BAR temizler. [CTaskDialog sınıfının](../../mfc/reference/ctaskdialog-class.md)bu örneğinin seçeneklerini el ile değiştirmek Için [CTaskDialog:: SetOptions](#setoptions) kullanın.

Bu yöntem, *nRangeMin* [](diagnostic-services.md#ensure) *nRangeMax*değerinden küçük olmaması halinde makrosuz bir özel durum oluşturur. Bu yöntem, `CTaskDialog` zaten görüntüleniyorsa ve bir kayan yazı ilerleme çubuğu içeriyorsa bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setprogressbarstate"></a>CTaskDialog:: SetProgressBarState

İlerleme çubuğunun durumunu ayarlar ve üzerinde `CTaskDialog`görüntüler.

```
void SetProgressBarState(int nState = PBST_NORMAL);
```

### <a name="parameters"></a>Parametreler

*nDurum*<br/>
'ndaki İlerleme çubuğunun durumu. Olası değerler için açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, zaten görüntüleniyorsa ve bir kayan yazı ilerleme çubuğu `CTaskDialog` içeriyorsa, makroyu [güvence altına](diagnostic-services.md#ensure) alarak bir özel durum oluşturur.

Aşağıdaki tabloda *nState*için olası değerler listelenmektedir. Bu durumda, ilerleme çubuğu, belirlenen durma konumuna ulaşıncaya kadar normal renkle doldurulur. Bu noktada, duruma göre renk değiştirilir.

|||
|-|-|
|PBST_NORMAL|İlerleme çubuğu doldurulduktan `CTaskDialog` sonra çubuğun rengini değiştirmez. Varsayılan olarak, normal renk yeşil ' dir.|
|PBST_ERROR|İlerleme çubuğu doldurulduktan sonra, `CTaskDialog` çubuk rengini hata rengine dönüştürür. Varsayılan olarak, bu kırmızıdır.|
|PBST_PAUSED|İlerleme çubuğu doldurulduktan sonra, `CTaskDialog` çubuk rengini bekleme rengine dönüştürür. Bu, varsayılan olarak sarı.|

İlerleme çubuğunun [CTaskDialog:: SetProgressBarPosition](#setprogressbarposition)ile nerede durması gerektiğini belirleyebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setradiobuttonoptions"></a>CTaskDialog:: SetRadioButtonOptions

Radyo düğmesini etkinleştirilir veya devre dışı bırakır.

```
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

##  <a name="setverificationcheckbox"></a>CTaskDialog:: Setdoğrulamaları Icationcheckbox

Doğrulama onay kutusunun denetlenen durumunu ayarlar.

```
void SetVerificationCheckbox(BOOL bChecked);
```

### <a name="parameters"></a>Parametreler

*bChecked*<br/>
'ndaki Görüntülendiğinde doğrulama onay kutusunun seçili `CTaskDialog` olması için true; Görüntülendiğinde doğrulama onay kutusunun seçimini `CTaskDialog` yapmak için false.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

##  <a name="setverificationcheckboxtext"></a>CTaskDialog:: Setdoğrulamaları Icationcheckboxtext

Doğrulama onay kutusunun sağında görüntülenen metni ayarlar.

```
void SetVerificationCheckboxText(CString& strVerificationText);
```

### <a name="parameters"></a>Parametreler

*Strdoğrulamaları Icationtext*<br/>
'ndaki Bu yöntemin, doğrulama onay kutusunun yanında gösterdiği metin.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CTaskDialog` sınıfın bu örneği zaten görüntüleniyorsa, makroyu [güvence altına](diagnostic-services.md#ensure) alarak bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

##  <a name="setwindowtitle"></a>CTaskDialog:: SetWindowTitle

Başlığını `CTaskDialog`ayarlar.

```
void SetWindowTitle(CString& strWindowTitle);
```

### <a name="parameters"></a>Parametreler

*strWindowTitle*<br/>
'ndaki İçin yeni başlık `CTaskDialog`.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="showdialog"></a>CTaskDialog:: ShowDialog

Oluşturur ve görüntüler `CTaskDialog`.

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
'ndaki İçeriği için kullanılacak dize `CTaskDialog`.

*strMainInstruction*<br/>
'ndaki Öğesinin ana yönergesi `CTaskDialog`.

*strTitle*<br/>
'ndaki Öğesinin `CTaskDialog`başlığı.

*nIDCommandControlsFirst*<br/>
'ndaki İlk komutun dize KIMLIĞI.

*nIDCommandControlsLast*<br/>
'ndaki Son komutun dize KIMLIĞI.

*nCommonButtons*<br/>
'ndaki Öğesine eklenecek düğmelerin maskesi `CTaskDialog`.

*nTaskDialogOptions*<br/>
'ndaki İçin kullanılacak seçenekler kümesi `CTaskDialog`.

*strFooter*<br/>
'ndaki Alt bilgi olarak kullanılacak dize.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tarafından yapılan seçime karşılık gelen bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Bu statik yöntem, `CTaskDialog` kodunuzda açıkça bir `CTaskDialog` nesne oluşturmadan sınıfın bir örneğini oluşturmanızı sağlar. Bir nesne olmadığından, kullanıcıya göstermek için bu yöntemi kullanırsanız, `CTaskDialog` başka bir `CTaskDialog` yöntemi çağrılamaz. `CTaskDialog`

Bu yöntem, uygulamanızın kaynak dosyasındaki verileri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyasındaki dize tablosunda, ilişkili dize kimliklerine sahip birkaç dize vardır. Bu yöntem, *nIDCommandControlsFirst* ve *nCommandControlsLast*dahil olmak üzere dize tablosundaki her geçerli giriş için bir komut düğmesi denetimi ekler. Bu komut düğmesi denetimlerinde, dize tablosundaki dize denetimin başlığı ve dize KIMLIĞI denetimin KIMLIĞIDIR.

Geçerli seçeneklerin listesi için bkz. [CTaskDialog:: SetOptions](#setoptions) .

Kullanıcı ortak bir düğmeyi seçtiğinde `CTaskDialog` kapatır,birkomutbağlantıdenetimiyaparveyakapatır.`CTaskDialog` Dönüş değeri, kullanıcının iletişim kutusunu nasıl kapattığını gösteren tanıtıcıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

##  <a name="taskdialogcallback"></a>CTaskDialog:: TaskDialogCallback

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
'ndaki İçin yapısına`m_hWnd` yönelik bir tanıtıcı. `CTaskDialog`

*uNotification*<br/>
'ndaki Oluşturulan iletiyi belirten bildirim kodu.

*wParam*<br/>
'ndaki İleti hakkında daha fazla bilgi.

*lParam*<br/>
'ndaki İleti hakkında daha fazla bilgi.

*dwRefData*<br/>
'ndaki Geri çağırma iletisinin geçerli `CTaskDialog` olduğu nesneye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirli bildirim koduna bağlıdır. Daha fazla bilgi için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, belirli `TaskDialogCallback` bir iletiyi işler ve sonra [CTaskDialog sınıfının](../../mfc/reference/ctaskdialog-class.md)uygun on yöntemini çağırır. Örneğin, TDN_BUTTON_CLICKED iletisine `TaskDialogCallback` yanıt olarak [CTaskDialog:: OnCommandControlClick ' i](#oncommandcontrolclick)çağırır.

*WParam* ve *lParam* değerleri, oluşturulan özel iletiye bağlıdır. Bu değerlerin her ikisi de boş olması mümkündür. Aşağıdaki tabloda, desteklenen varsayılan bildirimler ve *wParam* ve *lParam* değerlerinin temsil ettiği değerler listelenmiştir. Türetilmiş bir sınıfta bu yöntemi geçersiz kılarsınız, aşağıdaki tablodaki her ileti için geri çağırma kodunu uygulamalısınız.

|Bildirim Iletisi|*wParam* Deeri|*lParam* Deeri|
|--------------------------|--------------------|--------------------|
|TDN_CREATED|Kullanılmadı.|Kullanılmadı.|
|TDN_NAVIGATED|Kullanılmadı.|Kullanılmadı.|
|TDN_BUTTON_CLICKED|Komut düğmesi denetim KIMLIĞI.|Kullanılmadı.|
|TDN_HYPERLINK_CLICKED|Kullanılmadı.|Bağlantıyı içeren bir [LPCWSTR](/windows/win32/WinProg/windows-data-types) yapısı.|
|TDN_TIMER|Oluşturulduktan veya zamanlayıcının sıfırlanmasından bu yana `CTaskDialog` geçen süre (milisaniye).|Kullanılmadı.|
|TDN_DESTROYED|Kullanılmadı.|Kullanılmadı.|
|TDN_RADIO_BUTTON_CLICKED|Radyo düğmesi KIMLIĞI.|Kullanılmadı.|
|TDN_DIALOG_CONSTRUCTED|Kullanılmadı.|Kullanılmadı.|
|TDN_VERIFICATION_CLICKED|1 onay kutusu işaretliyse, 0 ise 0.|Kullanılmadı.|
|TDN_HELP|Kullanılmadı.|Kullanılmadı.|
|TDN_EXPANDO_BUTTON_CLICKED|genişletme alanı daraltılmışsa 0; genişletme metni görüntüleniyorsa sıfır dışı.|Kullanılmadı.|

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[İzlenecek yol: Uygulamaya CTaskDialog Ekleme](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)
