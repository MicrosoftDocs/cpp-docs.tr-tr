---
title: CTaskDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b8d3f081cc74c6e4288bc2e0e8d3b15af8dba325
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42464684"
---
# <a name="ctaskdialog-class"></a>CTaskDialog sınıfı
İşlevler bir açılır iletişim kutusunda bir ileti kutusu gibi ancak kullanıcıya ek bilgileri görüntüleyebilirsiniz. `CTaskDialog` Ayrıca kullanıcıdan bilgi toplama işlevi içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CTaskDialog : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[CTaskDialog::CTaskDialog](#ctaskdialog)|Oluşturur bir `CTaskDialog` nesne.|  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CTaskDialog::AddCommandControl](#addcommandcontrol)|Komut düğmesi denetimi için ekler `CTaskDialog`.|  
|[CTaskDialog::AddRadioButton](#addradiobutton)|Radyo düğmesini ekler `CTaskDialog`.|  
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|Program aracılığıyla bir komut düğmesi denetimi veya ortak düğmesine tıklar.|  
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|Program aracılığıyla bir radyo düğmesine tıklar.|  
|[CTaskDialog::DoModal](#domodal)|Görüntüler `CTaskDialog`.|  
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|Ortak düğmeler kullanılabilir sayısını alır.|  
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|Windows düğme için ortak bir düğme türü ile ilişkili standart dönüştürür `CTaskDialog` sınıfı.|  
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|İle ilişkili ortak düğmesi türlerinden birini dönüştürür `CTaskDialog` standart bir Windows düğme sınıfı.|  
|[CTaskDialog::GetOptions](#getoptions)|Bu seçenek bayraklarını döndürür `CTaskDialog`.|  
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|Seçili komut düğmesi denetimini döndürür.|  
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|Seçili radyo düğmesinin döndürür.|  
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|Doğrulama onay kutusunun durumunu alır.|  
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|Bir komut düğmesi denetimi veya ortak düğmesi etkin olup olmadığını belirler.|  
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|Bir radyo düğmesi etkin olup olmadığını belirler.|  
|[CTaskDialog::IsSupported](#issupported)|Uygulamasını çalıştıran bilgisayarın destekleyip desteklemediğini belirler `CTaskDialog`.|  
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|Dize tablosu verilerini kullanarak komut düğmesi denetimleri ekler.|  
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|Dize tablosu verilerini kullanarak radyo düğmeleri ekler.|  
|[CTaskDialog::NavigateTo](#navigateto)|Odağı diğerine aktaran `CTaskDialog`.|  
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|Kullanıcı komut düğmesi denetimi tıkladığında framework bu yöntemi çağırır.|  
|[CTaskDialog::OnCreate](#oncreate)|Oluşturur sonra framework bu yöntemi çağırır `CTaskDialog`.|  
|[CTaskDialog::OnDestroy](#ondestroy)|Hemen önce yok eder framework bu yöntemi çağırır `CTaskDialog`.|  
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|Kullanıcı genişletme düğmesine tıkladığında framework bu yöntemi çağırır.|  
|[CTaskDialog::OnHelp](#onhelp)|Kullanıcı Yardım istediğinde framework bu yöntemi çağırır.|  
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|Kullanıcı bir köprüye tıkladığında framework bu yöntemi çağırır.|  
|[CTaskDialog::OnInit](#oninit)|Framework bu yöntemi çağırır olduğunda `CTaskDialog` başlatılır.|  
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|Kullanıcı denetimleri ile ilgili odağı hareket framework bu yöntemi çağırır `CTaskDialog`.|  
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|Kullanıcı bir radyo düğmesi denetimini seçtiğinde framework bu yöntemi çağırır.|  
|[CTaskDialog::OnTimer](#ontimer)|Süreölçerdeki Süre dolduğunda framework bu yöntemi çağırır.|  
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|Kullanıcı doğrulama onay kutusunu tıkladığında framework bu yöntemi çağırır.|  
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|Tüm komut denetimlerden kaldırır `CTaskDialog`.|  
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|Tüm radyo düğmelerinden kaldırır `CTaskDialog`.|  
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|Komut düğmesi denetimi güncelleştirmelerini `CTaskDialog`.|  
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|UAC yükseltme gerektirir ve etkin için ortak düğmeleri kümesini güncelleştirir.|  
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|Ortak düğmeleri ekler `CTaskDialog`.|  
|[CTaskDialog::SetContent](#setcontent)|İçeriği güncelleştirme `CTaskDialog`.|  
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|Varsayılan komut düğmesi denetimi belirtir.|  
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|Varsayılan radyo düğmesini belirtir.|  
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|Genişliğini ayarlar `CTaskDialog`.|  
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|Genişletme alan, güncelleştirir `CTaskDialog`.|  
|[CTaskDialog::SetFooterIcon](#setfootericon)|Alt bilgi simgesi güncelleştirmeleri `CTaskDialog`.|  
|[CTaskDialog::SetFooterText](#setfootertext)|Alt bilgisi metni güncelleştirir `CTaskDialog`.|  
|[CTaskDialog::SetMainIcon](#setmainicon)|Ana simgesini güncelleştirmeleri `CTaskDialog`.|  
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|Ana yönergesinin güncelleştirmeleri `CTaskDialog`.|  
|[CTaskDialog::SetOptions](#setoptions)|Seçeneklerini yapılandırır `CTaskDialog`.|  
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|Bir kayan kenarlık çubuğu için yapılandırır `CTaskDialog` ve iletişim kutusuna ekler.|  
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|İlerleme çubuğu konumunu ayarlar.|  
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|İlerleme çubuğu aralığı ayarlar.|  
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|İlerleme çubuğu durumu ayarlar ve görüntüler `CTaskDialog`.|  
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|Etkinleştirir veya radyo düğmesi devre dışı bırakır.|  
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|Doğrulama onay kutusunun işaretli durumu ayarlar.|  
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|Metin doğrulama onay kutusunun sağ tarafında ayarlar.|  
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|Başlığını ayarlar `CTaskDialog`.|  
|[CTaskDialog::ShowDialog](#showdialog)|Oluşturur ve görüntüler bir `CTaskDialog`.|  
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|Framework, bunun çeşitli Windows iletilere yanıt olarak çağırır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|`m_aButtons`|Komut düğmesi denetimleri için bir dizi `CTaskDialog`.|  
|`m_aRadioButtons`|Dizi için bir radyo düğmesi denetimini `CTaskDialog`.|  
|`m_bVerified`|`TRUE` Doğrulama onay kutusunun seçili olduğunu gösterir. `FALSE` değil gösterir.|  
|`m_footerIcon`|Alt bilgisi simge `CTaskDialog`.|  
|`m_hWnd`|Bir tanıtıcı penceresine `CTaskDialog`.|  
|`m_mainIcon`|Ana simgesini `CTaskDialog`.|  
|`m_nButtonDisabled`|Ortak düğmelerinin gösteren bir maskesi devre dışı bırakılır.|  
|`m_nButtonElevation`|Ortak düğmelerinin gösteren bir maskesi UAC yükseltme gerektirir.|  
|`m_nButtonId`|Seçili komut düğme denetiminin kimliği.|  
|`m_nCommonButton`|Ortak düğmeleri gösteren maske görüntülenir `CTaskDialog`.|  
|`m_nDefaultCommandControl`|Komut düğmesi kimliği Denetim seçildiğinde `CTaskDialog` görüntülenir.|  
|`m_nDefaultRadioButton`|Radyo düğmesinin kimliği Denetim seçildiğinde `CTaskDialog` görüntülenir.|  
|`m_nFlags`|Seçeneklerini belirten bir maske `CTaskDialog`.|  
|`m_nProgressPos`|İlerleme çubuğu için geçerli konumu.  Bu değer arasında olmalıdır `m_nProgressRangeMin` ve `m_nProgressRangeMax`.|  
|`m_nProgressRangeMax`|İlerleme çubuğu için en büyük değer.|  
|`m_nProgressRangeMin`|İlerleme çubuğu için en düşük değer.|  
|`m_nProgressState`|İlerleme çubuğu durumu. Daha fazla bilgi için [CTaskDialog::SetProgressBarState](#setprogressbarstate).|  
|`m_nRadioId`|Seçili radyo düğmesi denetimini kimliği.|  
|`m_nWidth`|Genişliği `CTaskDialog` piksel.|  
|`m_strCollapse`|Dize `CTaskDialog` genişletilmiş bilgileri gizli genişletme kutusunun sağında görüntülenir.|  
|`m_strContent`|İçerik dizesinin `CTaskDialog`.|  
|`m_strExpand`|Dize `CTaskDialog` genişletilmiş bilgileri görüntülendiğinde genişletme kutusunun sağında görüntülenir.|  
|`m_strFooter`|Alt bilgisi `CTaskDialog`.|  
|`m_strInformation`|Genişletilmiş bilgileri `CTaskDialog`.|  
|`m_strMainInstruction`|Ana yönergesinin `CTaskDialog`.|  
|`m_strTitle`|Başlığı `CTaskDialog`.|  
|`m_strVerification`|Dize, `CTaskDialog` doğrulama onay kutusunun sağında görüntülenir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CTaskDialog` Sınıfı standart Windows ileti kutusu değiştirir ve kullanıcıdan bilgi toplamak için yeni denetimler gibi ek işlevlere sahiptir. MFC Kitaplığı'nda Visual Studio 2010 ve sonraki sürümlerinde sınıftır. `CTaskDialog` Windows Vista'dan itibaren kullanılabilir. Önceki Windows sürümlerinde görüntüleyemiyor `CTaskDialog` nesne. Kullanım `CTaskDialog::IsSupported` görev iletişim kutusu geçerli kullanıcının gösterip gösteremeyeceğini çalışma zamanında belirlemek için. Standart Windows ileti kutusu hala desteklenmektedir.  
  
 `CTaskDialog` Yalnızca uygulamanızın Unicode kitaplığını kullanarak oluşturduğunuzda kullanılabilir.  
  
 `CTaskDialog` İki farklı Oluşturucusu vardır. Bir Oluşturucu iki komut düğmeleri ve en fazla altı normal bir düğme denetimleri belirtmenize olanak sağlar. Oluşturduktan sonra daha fazla komut düğmesi ekleyebilirsiniz `CTaskDialog`. İkinci oluşturucu herhangi bir komut düğmeleri desteklemez, ancak normal bir düğme denetimleri sınırsız sayıda ekleyebilirsiniz. Oluşturucular hakkında daha fazla bilgi için bkz. [CTaskDialog::CTaskDialog](#ctaskdialog).  
  
 Aşağıdaki görüntüde bir örnek gösterilmektedir `CTaskDialog` bazı denetimleri konumunu göstermek için.  
  
 ![CTaskDialog örneği](../../mfc/reference/media/ctaskdialogsample.png "ctaskdialogsample")  
CTaskDialog örnek  
  
## <a name="requirements"></a>Gereksinimler  
 **Gereken en düşük işletim sistemi:** Windows Vista  
  
 **Başlık:** afxtaskdialog.h  
  
##  <a name="addcommandcontrol"></a>  CTaskDialog::AddCommandControl  
 Yeni bir komut düğmesi denetimi ekler `CTaskDialog`.  
  
```  
void AddCommandControl(
    int nCommandControlID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nCommandControlID*  
 Komut denetimi kimlik numarası.  
  
 [in] *strCaption*  
 Dize, `CTaskDialog` kullanıcıya görüntüler. Komut amacı açıklamak için şu dizeyi kullanın.  
  
 [in] *bEtkin*  
 Yeni düğmesi etkin veya devre dışı olduğunu gösteren bir Boole parametresi.  
  
 [in] *bRequiresElevation*  
 Bir komut ayrıcalık gerekli olup olmadığını gösteren bir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CTaskDialog Class` Komut düğmesi denetimleri sınırsız sayıda görüntüleyebilirsiniz. Ancak, bir `CTaskDialog` görüntüler herhangi bir komut düğmesi denetimleri, en fazla altı düğmeleri görüntüleyebilirsiniz. Varsa bir `CTaskDialog` hiçbir komut düğme denetimine sahiptir, düğmeler, sınırsız sayıda görüntüleyebilirsiniz.  
  
 Kullanıcı komut düğmesi denetimi seçtiğinde `CTaskDialog` kapatır. Uygulamanızı kullanarak iletişim kutusu görüntülenirse [CTaskDialog::DoModal](#domodal), `DoModal` döndürür *nCommandControlID* seçili komut düğmesi denetimi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="addradiobutton"></a>  CTaskDialog::AddRadioButton  
 Radyo düğmesini ekler `CTaskDialog`.  
  
```  
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRadioButtonID*  
 Radyo düğmesinin kimlik numarası.  
  
 [in] *strCaption*  
 Dize, `CTaskDialog` yanındaki radyo düğmesini gösterir.  
  
 [in] *bEtkin*  
 Radyo düğmesi etkin olup olmadığını gösteren bir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Radyo düğmeleri için [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md) kullanıcıdan bilgi toplamanızı sağlar. İşlevini [CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid) hangi radyo düğmesi seçilir belirlemek için.  
  
 `CTaskDialog` , Gerektirmez *nRadioButtonID* parametreleri her radyo düğmesi için benzersizdir. Ancak, her bir radyo düğmesi için benzersiz bir tanımlayıcı kullanmazsanız beklenmeyen davranışlarla karşılaşabilirsiniz.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="clickcommandcontrol"></a>  CTaskDialog::ClickCommandControl  
 Program aracılığıyla bir komut düğmesi denetimi veya ortak düğmesine tıklar.  
  
```  
protected:  
void ClickCommandControl(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nCommandControlID*  
 Denetimin tıklayın komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem windows iletisi TDM_CLICK_BUTTON oluşturur.  
  
##  <a name="clickradiobutton"></a>  CTaskDialog::ClickRadioButton  
 Program aracılığıyla bir radyo düğmesine tıklar.  
  
```  
protected:  
void ClickRadioButton(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRadioButtonID*  
 Radyo düğmesini tıklatın kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem windows iletisi TDM_CLICK_RADIO_BUTTON oluşturur.  
  
##  <a name="ctaskdialog"></a>  CTaskDialog::CTaskDialog  
 Örneği oluşturur [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md).  
  
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
 [in] *strContent*  
 İçeriği için kullanılacak dize `CTaskDialog`.  
  
 [in] *strMainInstruction*  
 Ana yönergesinin `CTaskDialog`.  
  
 [in] *strTitle*  
 Başlığı `CTaskDialog`.  
  
 [in] *nCommonButtons*  
 Ortak bir düğme eklemek için bir maske `CTaskDialog`.  
  
 [in] *nTaskDialogOptions*  
 Kullanılmak üzere seçenekleri kümesi `CTaskDialog`.  
  
 [in] *strFooter*  
 Alt bilgi olarak kullanılacak dize.  
  
 [in] *nIDCommandControlsFirst*  
 İlk komut dize kimliği.  
  
 [in] *nIDCommandControlsLast*  
 Son komut dize kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Ekleyebileceğiniz iki yolla bir `CTaskDialog` uygulamanıza. İlk yol oluşturucular birini oluşturmak için kullanılacak olan bir `CTaskDialog` ve kullanarak görüntüleme [CTaskDialog::DoModal](#domodal). İkinci yol statik işlev kullanmaktır [CTaskDialog::ShowDialog](#showdialog), görüntülemenizi sağlayan bir `CTaskDialog` açıkça oluşturmadan bir `CTaskDialog` nesne.  
  
 İkinci Oluşturucu, uygulamanızın kaynak dosyadan veri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyadaki dize tablosu birkaç ilişkilendirilmiş dize kimliklerini dizelerle sahiptir. Bu yöntem geçerli her giriş için bir komut düğmesi denetimi dize tablosu arasında ekler *nIDCommandControlsFirst* ve *nCommandControlsLast*(dahil). Bu komut düğmesi denetimleri için dize dize tablosunda denetimin açıklamalı alt yazı ve dize kimliği denetimin kimliği.  
  
 Bkz: [CTaskDialog::SetOptions](#setoptions) için geçerli seçeneklerin bir listesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="domodal"></a>  CTaskDialog::DoModal  
 Gösterir `CTaskDialog` kalıcı hale getirir.  
  
```  
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hParent*  
 Üst pencere için `CTaskDialog`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı tarafından yapılan seçime karşılık gelen bir tamsayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu örneği görüntüler [CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Uygulama kullanıcı iletişim kutusunu kapatmak bekler.  
  
 `CTaskDialog` Kullanıcı ortak bir düğme, bir komut bağlantı denetimi seçer veya kapatır kapatır `CTaskDialog`. Dönüş değeri nasıl kullanıcı iletişim kutusu kapalıyken gösteren tanımlayıcısıdır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="getcommonbuttoncount"></a>  CTaskDialog::GetCommonButtonCount  
 Ortak düğme sayısını alır.  
  
```  
int GetCommonButtonCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ortak düğmeler kullanılabilir sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Ortak düğmeler sağladığınız varsayılan düğmelerdir [CTaskDialog::CTaskDialog](#ctaskdialog). [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md) düğmelerini iletişim kutusunun alt kısmında bulunan görüntüler.  
  
 Düğme numaralandırılmış listesini CommCtrl.h içinde sağlanır.  
  
##  <a name="getcommonbuttonflag"></a>  CTaskDialog::GetCommonButtonFlag  
 Windows düğme için ortak bir düğme türü ile ilişkili standart dönüştürür [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md).  
  
```  
int GetCommonButtonFlag(int nButtonId) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nButtonId*  
 Standart Windows düğme değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Buna karşılık gelen değer `CTaskDialog` ortak düğmesi. Bu yöntem, karşılık gelen ortak düğmesi yoksa 0 döndürür.  
  
##  <a name="getcommonbuttonid"></a>  CTaskDialog::GetCommonButtonId  
 İle ilişkili ortak düğmesi türlerinden birini dönüştürür [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md) standart bir Windows düğme.  
  
```  
int GetCommonButtonId(int nFlag);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nFlag*  
 Ortak düğme türü ile ilişkili `CTaskDialog` sınıfı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karşılık gelen standart bir Windows düğme değeri. Karşılık gelen Windows düğmesi yoksa yöntem 0 döndürür.  
  
##  <a name="getoptions"></a>  CTaskDialog::GetOptions  
 Bu seçenek bayraklarını döndürür `CTaskDialog`.  
  
```  
int GetOptions() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bayrakları `CTaskDialog`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılabilir seçenekler hakkında daha fazla bilgi için [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md), bkz: [CTaskDialog::SetOptions](#setoptions).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="getselectedcommandcontrolid"></a>  CTaskDialog::GetSelectedCommandControlID  
 Seçili komut düğmesi denetimini döndürür.  
  
```  
int GetSelectedCommandControlID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda seçili komut düğme denetiminin kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcının seçtiği komut düğmesi Kimliğini almak için bu yöntemi kullanmak zorunda değil. Bu kimliği tarafından döndürülen [CTaskDialog::DoModal](#domodal) veya [CTaskDialog::ShowDialog](#showdialog).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="getselectedradiobuttonid"></a>  CTaskDialog::GetSelectedRadioButtonID  
 Seçili radyo düğmesinin döndürür.  
  
```  
int GetSelectedRadioButtonID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili radyo düğmesinin kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcının seçili radyo düğmesinin almak için iletişim kutusu kapatıldıktan sonra bu yöntemi kullanabilirsiniz.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="getverificationcheckboxstate"></a>  CTaskDialog::GetVerificationCheckboxState  
 Doğrulama onay kutusunun durumunu alır.  
  
```  
BOOL GetVerificationCheckboxState() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu durumda onay kutusunun yanlış işaretlenirse TRUE.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="iscommandcontrolenabled"></a>  CTaskDialog::IsCommandControlEnabled  
 Komut düğmesi denetimi veya düğmesi etkin olup olmadığını belirler.  
  
```  
BOOL IsCommandControlEnabled(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nCommandControlID*  
 Test kimliği komut düğmesi denetimi veya düğmesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değilse denetimi, yanlış etkinse TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
 Ortak düğmelerinin ve hem komut düğmesi denetimleri kullanılabilirliğini belirlemek için bu yöntemi kullanabilirsiniz `CTaskDialog` sınıfı *.  
  
 Varsa *nCommandControlID* geçerli bir tanımlayıcı için ortak olan `CTaskDialog` düğmeyi veya bir komut düğmesi denetimi, bu yöntem bir özel durum oluşturur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="isradiobuttonenabled"></a>  CTaskDialog::IsRadioButtonEnabled  
 Bir radyo düğmesi etkin olup olmadığını belirler.  
  
```  
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRadioButtonID*  
 Test etmek için radyo düğmesinin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE, değilse radyo düğmesi, yanlış etkin olur.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *nRadioButtonID* geçerli bir tanımlayıcı değil bir radyo düğmesi için bu yöntemi bir özel durum oluşturur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="issupported"></a>  CTaskDialog::IsSupported  
 Uygulamasını çalıştıran bilgisayarın destekleyip desteklemediğini belirler `CTaskDialog`.  
  
```  
static BOOL IsSupported();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bilgisayar destekliyorsa TRUE `CTaskDialog`; FALSE Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanında uygulamanızı çalıştıran bilgisayar destekleyip desteklemediğini belirlemek için bu işlevi kullanın `CTaskDialog` sınıfı. Bilgisayar desteklemiyorsa `CTaskDialog`, iletişim bilgileri kullanıcıya başka bir yöntem sağlamanız. Uygulamanızı kullanmaya çalışırsa kilitlenir bir `CTaskDialog` desteği olmayan bir bilgisayarda `CTaskDialog` sınıfı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="loadcommandcontrols"></a>  CTaskDialog::LoadCommandControls  
 Dize tablosu verilerini kullanarak komut düğmesi denetimleri ekler.  
  
```  
void LoadCommandControls(
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIDCommandControlsFirst*  
 İlk komut dize kimliği.  
  
 [in] *nIDCommandControlsLast*  
 Son komut dize kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, uygulamanızın kaynak dosyadan veri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyadaki dize tablosu birkaç ilişkilendirilmiş dize kimliklerini dizelerle sahiptir. Bu yöntem kullanılarak eklenen yeni komut düğmesi denetimleri dize denetimin açıklamalı alt yazı ve dize kimliği için denetimin kimliği için kullanın Seçili dizeleri aralığı tarafından sağlanan *nIDCommandControlsFirst* ve *nCommandControlsLast*(dahil). Yöntemi, varsa boş bir giriş aralığında bir komut düğmesi denetimi, girişi için eklemez.  
  
 Varsayılan olarak, yeni komut düğmesi denetimleri etkinleştirilir ve yükseltme gerektirmez.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="loadradiobuttons"></a>  CTaskDialog::LoadRadioButtons  
 Dize tablosu verilerini kullanarak radyo düğmesi denetimini ekler.  
  
```  
void LoadRadioButtons(
    int nIDRadioButtonsFirst,  
    int nIDRadioButtonsLast);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIDRadioButtonsFirst*  
 İlk radyo düğmesinin dize kimliği.  
  
 [in] *nIDRadioButtonsLast*  
 Son radyo düğmesinin dize kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, radyo düğmeleri, uygulamanızın kaynak dosyadan veri kullanarak oluşturur. Kaynak dosyadaki dize tablosu birkaç ilişkilendirilmiş dize kimliklerini dizelerle sahiptir. Bu yöntem kullanılarak eklenen yeni radyo düğmeleri dize radyo düğmesinin açıklamalı alt yazı ve dize kimliği için radyo düğmesinin kimliği için kullanma Seçili dizeleri aralığı tarafından sağlanan *nIDRadioButtonsFirst* ve *nRadioButtonsLast*(dahil). Yöntemi, aralıktaki boş bir girdi varsa, bu giriş için bir radyo düğmesi eklemez.  
  
 Varsayılan olarak, yeni radyo düğmesi etkinleştirilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="navigateto"></a>  CTaskDialog::NavigateTo  
 Odağı diğerine aktaran `CTaskDialog`.  
  
```  
protected:  
void NavigateTo(CTaskDialog& oTaskDialog) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *oTaskDialog*  
 `CTaskDialog` , Odağı alır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem geçerli gizler `CTaskDialog` zaman görüntüler *oTaskDialog*. *OTaskDialog* geçerli olarak aynı konumu gösterilen `CTaskDialog`.  
  
##  <a name="oncommandcontrolclick"></a>  CTaskDialog::OnCommandControlClick  
 Kullanıcı komut düğmesi denetimi tıkladığında framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nCommandControlID*  
 Kullanıcının seçtiği komut düğme denetiminin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi yok sayın.  
  
##  <a name="oncreate"></a>  CTaskDialog::OnCreate  
 Oluşturur sonra framework bu yöntemi çağırır `CTaskDialog`.  
  
```  
virtual HRESULT OnCreate();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi yok sayın.  
  
##  <a name="ondestroy"></a>  CTaskDialog::OnDestroy  
 Hemen önce yok eder framework bu yöntemi çağırır `CTaskDialog`.  
  
```  
virtual HRESULT OnDestroy();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi yok sayın.  
  
##  <a name="onexpandbuttonclick"></a>  CTaskDialog::OnExpandButtonClick  
 Kullanıcı genişletme düğmesine tıkladığında framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bExpanded*  
 Sıfır dışında bir değeri, ek bilgilerin görüntülendiğini gösterir; 0, ek bilgiler gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi yok sayın.  
  
##  <a name="onhelp"></a>  CTaskDialog::OnHelp  
 Kullanıcı Yardım istediğinde framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnHelp();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi yok sayın.  
  
##  <a name="onhyperlinkclick"></a>  CTaskDialog::OnHyperlinkClick  
 Kullanıcı bir köprüye tıkladığında framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strHref*  
 Köprüyü temsil eden dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemin çağırdığı [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) önce S_OK döndürür.  
  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi yok sayın.  
  
##  <a name="oninit"></a>  CTaskDialog::OnInit  
 Framework bu yöntemi çağırır olduğunda `CTaskDialog` başlatılır.  
  
```  
virtual HRESULT OnInit();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi yok sayın.  
  
##  <a name="onnavigatepage"></a>  CTaskDialog::OnNavigatePage  
 Framework, yanıt olarak bu yöntemi çağırır. [CTaskDialog::NavigateTo](#navigateto) yöntemi.  
  
```  
virtual HRESULT OnNavigatePage();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi yok sayın.  
  
##  <a name="onradiobuttonclick"></a>  CTaskDialog::OnRadioButtonClick  
 Kullanıcı bir radyo düğmesi denetimini seçtiğinde framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRadioButtonID*  
 Kullanıcı tıklanan radyo düğmesi denetimini kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi yok sayın.  
  
##  <a name="ontimer"></a>  CTaskDialog::OnTimer  
 Süreölçerdeki Süre dolduğunda framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnTimer(long lTime);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lTime*  
 Bu yana milisaniye cinsinden süre `CTaskDialog` oluşturuldu veya Zamanlayıcı sıfırlandı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi yok sayın.  
  
##  <a name="onverificationcheckboxclick"></a>  CTaskDialog::OnVerificationCheckboxClick  
 Kullanıcı doğrulama onay kutusunu tıkladığında framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bChecked*  
 TRUE, doğrulama onay kutusu seçili gösterir; FALSE değildir gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi yok sayın.  
  
##  <a name="removeallcommandcontrols"></a>  CTaskDialog::RemoveAllCommandControls  
 Tüm komut düğmesi denetimlerden kaldırır `CTaskDialog`.  
  
```  
void RemoveAllCommandControls();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="removeallradiobuttons"></a>  CTaskDialog::RemoveAllRadioButtons  
 Tüm radyo düğmelerinden kaldırır `CTaskDialog`.  
  
```  
void RemoveAllRadioButtons();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setcommandcontroloptions"></a>  CTaskDialog::SetCommandControlOptions  
 Komut düğmesi denetimi güncelleştirmelerini `CTaskDialog`.  
  
```  
void SetCommandControlOptions(
    int nCommandControlID,  
    BOOL bEnabled,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nCommandControlID*  
 Güncelleştirme Komut denetiminin kimliği.  
  
 [in] *bEtkin*  
 Belirtilen komut düğmesi denetimi etkin veya devre dışı olduğunu gösteren bir Boole parametresi.  
  
 [in] *bRequiresElevation*  
 Belirtilen komut düğmesi denetimi yükseltme gerektirip gerektirmediğini belirten bir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Komut düğmesi denetimi etkin ya da için eklendikten sonra yükseltme gerektirir. değiştirmek için bu yöntemi kullanmak `CTaskDialog` sınıfı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setcommonbuttonoptions"></a>  CTaskDialog::SetCommonButtonOptions  
 Ortak düğmeleri etkinleştirilmesi ve UAC yükseltme kümesini güncelleştirir.  
  
```  
void SetCommonButtonOptions(
    int nDisabledButtonMask,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nDisabledButtonMask*  
 Ortak düğmeleri devre dışı bırakmak için bir maske.  
  
 [in] *nElevationButtonMask*  
 Yetki yükseltmesi gerektiren yaygın düğmeleri için bir maske.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılabilir ortak düğmeleri örneğine ayarlayabilirsiniz [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md) Oluşturucusu kullanarak [CTaskDialog::CTaskDialog](#ctaskdialog) ve yöntem [CTaskDialog::SetCommonButtons ](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions` yeni ortak düğmeler eklemeyi desteklemez.  
  
 Bunun için kullanılabilir değil bir ortak düğme devre dışı bırakın veya değiştirmesine bu yöntemi kullanırsanız `CTaskDialog`, bu yöntemi kullanarak bir özel durum oluşturur. [olun](diagnostic-services.md#ensure) makrosu.  
  
 Bu yöntem kullanılabilir herhangi bir düğme etkinleştirir `CTaskDialog` ancak kullanımda olmayan *nDisabledButtonMask*bile, daha önce devre dışı bırakıldı. Bu yöntem yükseltme benzer şekilde davranır: ortak düğmesi kullanılabilir, ancak dahil değil ise, yükseltme gerektirmiyor olarak ortak düğmeleri kayıtları *nElevationButtonMask*.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcommonbuttons"></a>  CTaskDialog::SetCommonButtons  
 Ortak düğmeleri ekler `CTaskDialog`.  
  
```  
void SetCommonButtons(
    int nButtonMask,  
    int nDisabledButtonMask = 0,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nButtonMask*  
 Düğme eklemek için bir maske `CTaskDialog`.  
  
 [in] *nDisabledButtonMask*  
 Düğmeleri devre dışı bırakmak için bir maske.  
  
 [in] *nElevationButtonMask*  
 Yetki yükseltmesi gerektiren düğmeleri maskesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonra görünen pencere bu örneği için bu yöntem çağıramazsınız `CTaskDialog` sınıf oluşturulur. Bunu yaparsanız, bu yöntem bir özel durum oluşturur.  
  
 Gösterilen düğmeleri *nButtonMask* daha önce eklenen ortak düğmeleri geçersiz kılma `CTaskDialog`. Düğmeleri yalnızca belirtilen *nButtonMask* kullanılabilir.  
  
 Ya da *nDisabledButtonMask* veya *nElevationButtonMask* kullanımda olmayan bir düğme içeren *nButtonMask*, bu yöntem kullanarakbirözeldurumoluşturur.[Olun](diagnostic-services.md#ensure) makrosu.  
  
 Varsayılan olarak, tüm ortak düğmeleri etkinleştirilir ve yükseltme gerektirmez.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcontent"></a>  CTaskDialog::SetContent  
 İçeriği güncelleştirme `CTaskDialog`.  
  
```  
void SetContent(const CString& strContent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strContent*  
 Kullanıcıya görüntülenecek dize.  
  
### <a name="remarks"></a>Açıklamalar  
 İçeriği `CTaskDialog` sınıfı, iletişim kutusunun ana bölümde kullanıcıya görüntülenen metin.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setdefaultcommandcontrol"></a>  CTaskDialog::SetDefaultCommandControl  
 Varsayılan komut düğmesi denetimi belirtir.  
  
```  
void SetDefaultCommandControl(int nCommandControlID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nCommandControlID*  
 Varsayılan komut düğmesi denetiminin kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan komut düğmesi denetimi denetimi olan seçilen `CTaskDialog` önce kullanıcıya gösterilir.  
  
 Tarafından belirtilen komut düğmesi denetimi bulamazsanız, bu yöntem bir istisna atar *nCommandControlID*.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setdefaultradiobutton"></a>  CTaskDialog::SetDefaultRadioButton  
 Varsayılan radyo düğmesini belirtir.  
  
```  
void SetDefaultRadioButton(int nRadioButtonID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRadioButtonID*  
 Varsayılan olarak kullanılacak radyo düğmesinin kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan radyo düğmesi düğmesidir seçilen `CTaskDialog` önce kullanıcıya gösterilir.  
  
 Tarafından belirtilen radyo düğmesini bulamazsa, bu yöntem bir istisna atar *nRadioButtonID*.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setdialogwidth"></a>  CTaskDialog::SetDialogWidth  
 Genişliğini ayarlar `CTaskDialog`.  
  
```  
void SetDialogWidth(int nWidth = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nWidth*  
 İletişim kutusunda, piksel cinsinden genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre *nWidth* değerinden büyük veya 0'a eşit olmalıdır. Aksi takdirde, bu yöntem, bir özel durum oluşturur.  
  
 Varsa *nWidth* 0'dır, bu yöntem ayarlar iletişim kutusunda varsayılan boyutunu ayarlayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setexpansionarea"></a>  CTaskDialog::SetExpansionArea  
 Genişletme alan, güncelleştirir `CTaskDialog`.  
  
```  
void SetExpansionArea(
    const CString& strExpandedInformation,  
    const CString& strCollapsedLabel = _T(""),  
    const CString& strExpandedLabel = _T(""));
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strExpandedInformation*  
 Dize, `CTaskDialog` iletişim kutusunun ana gövdesinde kullanıcı genişletme düğmesine tıkladığında görüntülenir.  
  
 [in] *strCollapsedLabel*  
 Dize, `CTaskDialog` genişletilmiş alan daraltıldığında yanındaki genişletme düğmesi görüntüler.  
  
 [in] *strExpandedLabel*  
 Dize, `CTaskDialog` genişletilmiş alan görüntülendiğinde yanındaki genişletme düğmesi görüntüler.  
  
### <a name="remarks"></a>Açıklamalar  
 Genişletme alanını `CTaskDialog` sınıfı kullanıcıya ek bilgiler girmenizi sağlar. Ana bölümünde genişletme alandır `CTaskDialog`bulunan hemen altındaki başlığı ve içeriği dize.  
  
 Zaman `CTaskDialog` ilk görüntülendiğinde, genişletilmiş bilgi göstermez ve koyar `strCollapsedLabel` genişletme düğmesinin yanındaki. Kullanıcı genişletme düğmeye tıkladığında `CTaskDialog` görüntüler *strExpandedInformation* ve etiketi değişiklikleri *strExpandedLabel*.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootericon"></a>  CTaskDialog::SetFooterIcon  
 Alt bilgi simgesini güncelleştirmeleri `CTaskDialog`.  
  
```  
void SetFooterIcon(HICON hFooterIcon);  
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hFooterIcon*  
 Yeni simgesi `CTaskDialog`.  
  
 [in] *lpszFooterIcon*  
 Yeni simgesi `CTaskDialog`.  
  
### <a name="remarks"></a>Açıklamalar  
 Alt simge, listenin sonuna görüntülenir [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md). Alt bilgi metni ilişkilendirdiğiniz. Alt bilgi metni ile değiştirebilirsiniz [CTaskDialog::SetFooterText](#setfootertext).  
  
 Bu yöntem ile aykırı [emin olun](diagnostic-services.md#ensure) makrosu, `CTaskDialog` görüntülenir veya giriş parametresi NULL.  
  
 A `CTaskDialog` yalnızca kabul edebilen bir `HICON` veya `LPCWSTR` bir alt simge. Bu oluşturucu içinde ' % s'seçeneği TDF_USE_HICON_FOOTER ayarlayarak yapılandırılır veya [CTaskDialog::SetOptions](#setoptions). Varsayılan olarak, `CTaskDialog` kullanacak şekilde yapılandırılmış `LPCWSTR` alt simge için giriş türü. Uygunsuz türü kullanılarak simgesi ayarlamaya çalışırsanız, bu yöntem bir özel durum oluşturur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootertext"></a>  CTaskDialog::SetFooterText  
 Alt bilgisi metni güncelleştirir `CTaskDialog`.  
  
```  
void SetFooterText(const CString& strFooterText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strFooterText*  
 Yeni alt bilgi metni.  
  
### <a name="remarks"></a>Açıklamalar  
 Alt bilgi metni altındaki alt simge yanında `CTaskDialog`. Altbilgi simgesiyle değiştirebilirsiniz [CTaskDialog::SetFooterIcon](#setfootericon).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmainicon"></a>  CTaskDialog::SetMainIcon  
 Ana simgesini güncelleştirmeleri `CTaskDialog`.  
  
```  
void SetMainIcon(HICON hMainIcon);  
void SetMainIcon(LPCWSTR lpszMainIcon);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hMainIcon*  
 Yeni simge.  
  
 [in] *lpszMainIcon*  
 Yeni simge.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ile aykırı [emin olun](diagnostic-services.md#ensure) makrosu, `CTaskDialog` görüntülenir veya giriş parametresi NULL.  
  
 A `CTaskDialog` yalnızca kabul edebilen bir `HICON` veya `LPCWSTR` ana simge. Bu oluşturucu içinde TDF_USE_HICON_MAIN seçeneği ayarlama veya buna yapılandırabilirsiniz [CTaskDialog::SetOptions](#setoptions) yöntemi. Varsayılan olarak, `CTaskDialog` kullanacak şekilde yapılandırılmış `LPCWSTR` giriş türü için ana simge. Uygunsuz türü kullanılarak simgesi ayarlamaya çalışırsanız, bu yöntem bir özel durum oluşturur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmaininstruction"></a>  CTaskDialog::SetMainInstruction  
 Ana yönergesinin güncelleştirmeleri `CTaskDialog`.  
  
```  
void SetMainInstruction(const CString& strInstructions);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strInstructions*  
 Yeni ana yönerge.  
  
### <a name="remarks"></a>Açıklamalar  
 Ana yönergesinin `CTaskDialog` sınıfı, kullanıcı büyük bir kalın yazı tipiyle gösterilen metin. İletişim kutusunun başlık çubuğunun altında bulunur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setoptions"></a>  CTaskDialog::SetOptions  
 Seçeneklerini yapılandırır `CTaskDialog`.  
  
```  
void SetOptions(int nOptionFlag);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nOptionFlag*  
 Kullanılacak bayrakları kümesini `CTaskDialog`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için geçerli olan tüm seçenekleri temizler `CTaskDialog`. Geçerli seçeneklerini korumak için bunları ilk ile alınması gerekir [CTaskDialog::GetOptions](#getoptions) bunları ayarlamak istediğiniz seçenekleri ile birleştirebilirsiniz.  
  
 Aşağıdaki tablo, geçerli tüm seçenekleri listeler.  
  
 TDF_ENABLE_HYPERLINKS  
 Köprü sağlar `CTaskDialog`.  
  
 TDF_USE_HICON_MAIN  
 Yapılandırır `CTaskDialog` kullanmak için bir `HICON` için ana simge. Alternatif kullanmaktır bir `LPCWSTR`.  
  
 TDF_USE_HICON_FOOTER  
 Yapılandırır `CTaskDialog` kullanmak için bir `HICON` alt bilgi simgesi. Alternatif kullanmaktır bir `LPCWSTR`.  
  
 TDF_ALLOW_DIALOG_CANCELLATION  
 Kullanıcının sağlayan `CTaskDialog` klavyeyi kullanarak veya iletişim kutusunda, sağ üst köşesindeki simgeyi kullanarak bile **iptal** düğmesi etkin değil. Bu bayrak ayarlanmazsa ve **iptal** düğmesi etkin değil, iletişim kutusunun Alt + F4 Escape tuşu kullanarak kullanıcının kapatamayacağı veya başlık çubuğunun Kapat düğmesi.  
  
 TDF_USE_COMMAND_LINKS  
 Yapılandırır `CTaskDialog` komut düğmesi denetimleri kullanmak için.  
  
 TDF_USE_COMMAND_LINKS_NO_ICON  
 Yapılandırır `CTaskDialog` denetimi yanında bir simge görüntülemeden komut düğmesi denetimleri kullanmak için. TDF_USE_COMMAND_LINKS TDF_USE_COMMAND_LINKS_NO_ICON geçersiz kılar.  
  
 TDF_EXPAND_FOOTER_AREA  
 Genişletme alanı şu anda genişletilen gösterir.  
  
 TDF_EXPANDED_BY_DEFAULT  
 Genişletme alanı varsayılan olarak genişletildiğinden olup olmadığını belirler.  
  
 TDF_VERIFICATION_FLAG_CHECKED  
 Doğrulama onay kutusunun seçili gösterir.  
  
 TDF_SHOW_PROGRESS_BAR  
 Yapılandırır `CTaskDialog` bir ilerleme çubuğu görüntülenecek.  
  
 TDF_SHOW_MARQUEE_PROGRESS_BAR  
 İlerleme çubuğu, bir kayan ilerleme çubuğu olacak şekilde yapılandırır. Bu seçeneği etkinleştirirseniz, Beklenen davranış sağlamak için TDF_SHOW_PROGRESS_BAR ayarlamanız gerekir.  
  
 TDF_CALLBACK_TIMER  
 Bildiren `CTaskDialog` geri çağırma aralıksa yaklaşık 200 milisaniye.  
  
 TDF_POSITION_RELATIVE_TO_WINDOW  
 Yapılandırır `CTaskDialog` göre ana pencereyi ortalamak için. Bu bayrak etkin değilse `CTaskDialog` İzleyici göre ortalanır.  
  
 TDF_RTL_LAYOUT  
 Yapılandırır `CTaskDialog` sağdan sola okuma düzeni için.  
  
 TDF_NO_DEFAULT_RADIO_BUTTON  
 Hiçbir radyo düğmesi seçili olduğunu gösterir, `CTaskDialog` görünür.  
  
 TDF_CAN_BE_MINIMIZED  
 En aza indirmek kullanıcının sağlayan `CTaskDialog`. Bu seçeneği desteklemek üzere `CTaskDialog` kalıcı hale getirilemiyor. MFC MFC bir geçici desteklemediği için bu seçeneği desteklemiyor `CTaskDialog`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setprogressbarmarquee"></a>  CTaskDialog::SetProgressBarMarquee  
 Bir kayan kenarlık çubuğu için yapılandırır `CTaskDialog` ve iletişim kutusuna ekler.  
  
```  
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,  
    int nMarqueeSpeed = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bEtkin*  
 Kayan çubuğunu etkinleştirmek için TRUE; Kayan çubuğundaki devre dışı bırakabilir ve oradan kaldırın FALSE `CTaskDialog`.  
  
 [in] *nMarqueeSpeed*  
 Kayan çubuğu hızını gösteren bir tamsayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Ana metnin altında çerçevesi çubuğu görünür `CTaskDialog` sınıfı.  
  
 Kullanım *nMarqueeSpeed* çerçevesi çubuğunun; hızını ayarlamak için daha büyük değerler daha yavaş hızını gösterir. Bir değer için 0 *nMarqueeSpeed* Windows için varsayılan hızda taşımak çerçevesi çubuğunun neden olur.  
  
 Bu yöntem ile aykırı [olun](diagnostic-services.md#ensure) makrosu, *nMarqueeSpeed* 0'dan küçük.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarposition"></a>  CTaskDialog::SetProgressBarPosition  
 İlerleme çubuğu konumunu ayarlar.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nProgressPos*  
 İlerleme çubuğu konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ile aykırı [olun](diagnostic-services.md#ensure) makrosu, *nProgressPos* ilerleme çubuğu aralığında değil. İlerleme çubuğu aralığıyla değiştirebilirsiniz [CTaskDialog::SetProgressBarRange](#setprogressbarrange).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarrange"></a>  CTaskDialog::SetProgressBarRange  
 İlerleme çubuğu aralığı ayarlar.  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRangeMin*  
 İlerleme çubuğu alt sınırı.  
  
 [in] *nRangeMax*  
 İlerleme çubuğu üst sınırı.  
  
### <a name="remarks"></a>Açıklamalar  
 İlerleme çubuğunun konumu göreli olduğu *nRangeMin* ve *nRangeMax*. Örneğin, varsa *nRangeMin* 50'dir ve *nRangeMax* 75 konumunu ilerleme çubuğu arasında ortasında ise, 100'dür. Kullanım [CTaskDialog::SetProgressBarPosition](#setprogressbarposition) ilerleme çubuğunun konumu ayarlamak için.  
  
 İlerleme çubuğu görüntülemek için TDF_SHOW_MARQUEE_PROGRESS_BAR ve TDF_SHOW_PROGRESS_BAR etkinleştirilmelidir seçeneği etkinleştirilmemiş gerekir. Bu yöntem, otomatik olarak TDF_SHOW_PROGRESS_BAR ayarlar ve TDF_SHOW_MARQUEE_PROGRESS_BAR temizler. Kullanım [CTaskDialog::SetOptions](#setoptions) el ile bu örneği için seçeneklerini değiştirmek için [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md).  
  
 Bu yöntem ile aykırı [emin olun](diagnostic-services.md#ensure) makrosu, *nRangeMin* olan değerinden küçük olamaz *nRangeMax*. Bu yöntem Ayrıca, bir özel durum oluşturur `CTaskDialog` zaten görüntülenir ve bir kayan ilerleme çubuğu vardır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarstate"></a>  CTaskDialog::SetProgressBarState  
 İlerleme çubuğu durumu ayarlar ve görüntüler `CTaskDialog`.  
  
```  
void SetProgressBarState(int nState = PBST_NORMAL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nDurum*  
 İlerleme çubuğu durumu. Olası değerler için Açıklamalar bölümüne bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ile bir istisna atar [olun](diagnostic-services.md#ensure) makrosu, `CTaskDialog` zaten görüntülenir ve bir kayan ilerleme çubuğu vardır.  
  
 İçin olası değerler aşağıdaki tabloda *nDurum*. Belirlenen Durma konumu ulaşana kadar bu durumlarda, ilerleme çubuğu normal renk ile doldurun. Bu noktada, renk durumuna göre değişir.  
  
 PBST_NORMAL  
 Sonra ilerleme çubuğu doldurur, `CTaskDialog` renk çubuğu değiştirmez. Varsayılan olarak, normal yeşil renkte.  
  
 PBST_ERROR  
 Sonra ilerleme çubuğu doldurur, `CTaskDialog` renk çubuğu hata rengine değiştirir. Varsayılan olarak, kırmızı budur.  
  
 PBST_PAUSED  
 Sonra ilerleme çubuğu doldurur, `CTaskDialog` renk çubuğu duraklatılmış rengine değiştirir. Varsayılan olarak, sarı budur.  
  
 Burada ile ilerleme çubuğu durdurur ayarlayabilirsiniz [CTaskDialog::SetProgressBarPosition](#setprogressbarposition).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setradiobuttonoptions"></a>  CTaskDialog::SetRadioButtonOptions  
 Etkinleştirir veya radyo düğmesi devre dışı bırakır.  
  
```  
void SetRadioButtonOptions(
    int nRadioButtonID,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRadioButtonID*  
 Radyo düğmesi denetimini kimliği.  
  
 [in] *bEtkin*  
 Radyo düğmesini etkinleştirmek için TRUE; Radyo düğmesi devre dışı bırakmak için FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ile aykırı [olun](diagnostic-services.md#ensure) makrosu, *nRadioButtonID* bir radyo düğmesi için geçerli bir kimlik değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setverificationcheckbox"></a>  CTaskDialog::SetVerificationCheckbox  
 Doğrulama onay kutusunun işaretli durumu ayarlar.  
  
```  
void SetVerificationCheckbox(BOOL bChecked);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bChecked*  
 TRUE doğrulama onay kutusunu ne zaman seçtiğiniz `CTaskDialog` görüntülenir; YANLIŞ doğrulama onay kutusunun seçili `CTaskDialog` görüntülenir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setverificationcheckboxtext"></a>  CTaskDialog::SetVerificationCheckboxText  
 Doğrulama onay kutusunun sağında gösterilen metin ayarlar.  
  
```  
void SetVerificationCheckboxText(CString& strVerificationText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strVerificationText*  
 Bu yöntem yanındaki onay kutusunu doğrulama görüntülenen metin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ile aykırı [emin olun](diagnostic-services.md#ensure) makrosu bu örneğini `CTaskDialog` sınıfı zaten görüntülenir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setwindowtitle"></a>  CTaskDialog::SetWindowTitle  
 Başlığını ayarlar `CTaskDialog`.  
  
```  
void SetWindowTitle(CString& strWindowTitle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strWindowTitle*  
 Yeni başlığını `CTaskDialog`.  
  
### <a name="remarks"></a>Açıklamalar  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="showdialog"></a>  CTaskDialog::ShowDialog  
 Oluşturur ve görüntüler bir `CTaskDialog`.  
  
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
 [in] *strContent*  
 İçeriği için kullanılacak dize `CTaskDialog`.  
  
 [in] *strMainInstruction*  
 Ana yönergesinin `CTaskDialog`.  
  
 [in] *strTitle*  
 Başlığı `CTaskDialog`.  
  
 [in] *nIDCommandControlsFirst*  
 İlk komut dize kimliği.  
  
 [in] *nIDCommandControlsLast*  
 Son komut dize kimliği.  
  
 [in] *nCommonButtons*  
 Düğme eklemek için bir maske `CTaskDialog`.  
  
 [in] *nTaskDialogOptions*  
 Kullanılmak üzere seçenekleri kümesi `CTaskDialog`.  
  
 [in] *strFooter*  
 Alt bilgi olarak kullanılacak dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı tarafından yapılan seçime karşılık gelen bir tamsayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu statik yöntem örneği oluşturmanızı sağlayan `CTaskDialog` sınıfı açıkça oluşturmadan bir `CTaskDialog` kodunuzda nesne. Olmadığından hiçbir `CTaskDialog` nesnesi diğer tüm yöntemleri çağıramaz `CTaskDialog` göstermek için bu yöntemi kullandığınızda bir `CTaskDialog` kullanıcı.  
  
 Bu yöntem, uygulamanızın kaynak dosyadan veri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyadaki dize tablosu birkaç ilişkilendirilmiş dize kimliklerini dizelerle sahiptir. Bu yöntem geçerli her giriş için bir komut düğmesi denetimi dize tablosu arasında ekler *nIDCommandControlsFirst* ve *nCommandControlsLast*(dahil). Bu komut düğmesi denetimleri için dize dize tablosunda denetimin açıklamalı alt yazı ve dize kimliği denetimin kimliği.  
  
 Bkz: [CTaskDialog::SetOptions](#setoptions) için geçerli seçeneklerin bir listesi.  
  
 `CTaskDialog` Kullanıcı ortak bir düğme, bir komut bağlantı denetimi seçer veya kapatır kapatır `CTaskDialog`. Dönüş değeri nasıl kullanıcı iletişim kutusu kapalıyken gösteren tanımlayıcısıdır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="taskdialogcallback"></a>  CTaskDialog::TaskDialogCallback  
 Framework, çeşitli Windows iletilere yanıt olarak bu yöntemi çağırır.  
  
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
 [in] *hwnd*  
 İşleyici `m_hWnd` için yapı `CTaskDialog`.  
  
 [in] *uNotification*  
 Bildirim kodunu oluşturulan iletiyi belirtir.  
  
 [in] *wParam*  
 İleti hakkında daha fazla bilgi.  
  
 [in] *lParam*  
 İleti hakkında daha fazla bilgi.  
  
 [in] *dwRefData*  
 Bir işaretçi `CTaskDialog` nesnesini geri çağırma iletisi için geçerlidir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirli bildirim koduna bağlıdır. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulaması `TaskDialogCallback` belirli ileti işleme ve uygun üzerinde yöntemini ı çağırır [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md). Örneğin, TDN_BUTTON_CLICKED iletisine yanıt olarak `TaskDialogCallback` çağrıları [CTaskDialog::OnCommandControlClick](#oncommandcontrolclick).  
  
 Değerleri *wParam* ve *lParam* belirli oluşturulan iletide bağlıdır. Ya da ya da boş olacak şekilde, bu değerlerin her ikisini de mümkündür. Aşağıdaki tabloda desteklenen varsayılan bildirimler ve hangi listeler değerlerini *wParam* ve *lParam* temsil eder. Türetilen bir sınıfta bu yöntemin, her ileti için geri çağırma kodu aşağıdaki tabloda uygulamanız gerekir.  
  
|Bildirim iletisi|*wParam* değeri|*lParam* değeri|  
|--------------------------|--------------------|--------------------|  
|TDN_CREATED|Kullanılmadı.|Kullanılmadı.|  
|TDN_NAVIGATED|Kullanılmadı.|Kullanılmadı.|  
|TDN_BUTTON_CLICKED|Komut düğmesi denetim kimliği.|Kullanılmadı.|  
|TDN_HYPERLINK_CLICKED|Kullanılmadı.|A [LPCWSTR](http://msdn.microsoft.com/library/windows/desktop/aa383751) bağlantısını içeren yapısı.|  
|TDN_TIMER|Bu yana milisaniye cinsinden süre `CTaskDialog` oluşturuldu veya Zamanlayıcı sıfırlandı.|Kullanılmadı.|  
|TDN_DESTROYED|Kullanılmadı.|Kullanılmadı.|  
|TDN_RADIO_BUTTON_CLICKED|Radyo düğmesi kimliği.|Kullanılmadı.|  
|TDN_DIALOG_CONSTRUCTED|Kullanılmadı.|Kullanılmadı.|  
|TDN_VERIFICATION_CLICKED|onay kutusunu işaretlediyseniz 1, 0, değilse.|Kullanılmadı.|  
|TDN_HELP|Kullanılmadı.|Kullanılmadı.|  
|TDN_EXPANDO_BUTTON_CLICKED|genişletme alan daraltılmışsa 0; genişletme metin görüntüleniyorsa, sıfır dışında.|Kullanılmadı.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [İzlenecek yol: Bir Uygulamaya CTaskDialog Ekleme](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)



