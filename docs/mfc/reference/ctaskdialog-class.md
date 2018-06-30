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
ms.openlocfilehash: 2971293a61a662b789506bbc32923089097f962d
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123220"
---
# <a name="ctaskdialog-class"></a>CTaskDialog sınıfı
İşlevleri bir açılır iletişim kutusu bir ileti kutusu gibi ancak kullanıcıya ek bilgileri görüntüleyebilirsiniz. `CTaskDialog` Kullanıcıdan bilgi toplama işlevleri de içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CTaskDialog : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[CTaskDialog::CTaskDialog](#ctaskdialog)|Oluşturan bir `CTaskDialog` nesnesi.|  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CTaskDialog::AddCommandControl](#addcommandcontrol)|Bir komut düğmesi denetimi ekler `CTaskDialog`.|  
|[CTaskDialog::AddRadioButton](#addradiobutton)|Radyo düğmesini ekler `CTaskDialog`.|  
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|Program aracılığıyla bir komut düğmesi denetimi veya ortak düğmesine tıklar.|  
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|Program aracılığıyla bir radyo düğmesine tıklar.|  
|[CTaskDialog::DoModal](#domodal)|Görüntüler `CTaskDialog`.|  
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|Ortak düğmeleri kullanılabilir sayısını alır.|  
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|Windows düğme ortak düğme türü için ilişkili bir standart dönüştürür `CTaskDialog` sınıfı.|  
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|İle ilişkili ortak düğmesi türlerinden birini dönüştürür `CTaskDialog` standart Windows düğme sınıfı.|  
|[CTaskDialog::GetOptions](#getoptions)|Bu seçenek bayraklarını döndürür `CTaskDialog`.|  
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|Seçili komut düğmesi denetimini döndürür.|  
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|Seçili radyo düğmesinin döndürür.|  
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|Doğrulama onay kutusunun durumunu alır.|  
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|Komut düğmesi denetimi veya ortak düğmesi etkin olup olmadığını belirler.|  
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|Radyo düğmesi etkin olup olmadığını belirler.|  
|[CTaskDialog::IsSupported](#issupported)|Uygulamayı çalıştıran bilgisayarın destekleyip desteklemediğini belirler `CTaskDialog`.|  
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|Komut düğmesi denetimleri dize tablodan veri kullanarak ekler.|  
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|Radyo düğmeleri dize tablodan veri kullanarak ekler.|  
|[CTaskDialog::NavigateTo](#navigateto)|Odağı diğerine aktarır `CTaskDialog`.|  
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|Kullanıcı komut düğmesi denetimi tıklattığında framework bu yöntemi çağırır.|  
|[CTaskDialog::OnCreate](#oncreate)|Oluşturur sonra framework bu yöntemi çağırır `CTaskDialog`.|  
|[CTaskDialog::OnDestroy](#ondestroy)|Önce bozar hemen framework bu yöntemi çağırır `CTaskDialog`.|  
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|Kullanıcı genişletme düğmesini tıklattığında framework bu yöntemi çağırır.|  
|[CTaskDialog::OnHelp](#onhelp)|Kullanıcı Yardım istediğinde framework bu yöntemi çağırır.|  
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|Kullanıcı bir köprüyü tıklattığında framework bu yöntemi çağırır.|  
|[CTaskDialog::OnInit](#oninit)|Bu yöntem framework çağırır zaman `CTaskDialog` başlatılır.|  
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|Kullanıcı denetimleri açısından odak hareket ettiğinde framework bu yöntemi çağırır `CTaskDialog`.|  
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|Kullanıcı bir radyo düğmesi denetimini seçtiğinde framework bu yöntemi çağırır.|  
|[CTaskDialog::OnTimer](#ontimer)|Süreölçer süresi dolduğunda framework bu yöntemi çağırır.|  
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|Kullanıcı doğrulama onay kutusunu tıklattığında framework bu yöntemi çağırır.|  
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|Tüm komut denetimlerden kaldırır `CTaskDialog`.|  
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|Gelen tüm radyo düğmeleri kaldırır `CTaskDialog`.|  
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|Komut düğmesi denetimi güncelleştirir `CTaskDialog`.|  
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|UAC yükseltmesi gerektiren ve etkin için ortak düğmelerini kümesini güncelleştirir.|  
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|Ortak düğmeleri ekler `CTaskDialog`.|  
|[CTaskDialog::SetContent](#setcontent)|İçeriği güncelleştirmeleri `CTaskDialog`.|  
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|Varsayılan komut düğmesi denetimi belirtir.|  
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|Varsayılan radyo düğmesi belirtir.|  
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|Genişliğini ayarlar `CTaskDialog`.|  
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|Genişletme alanını güncelleştirir `CTaskDialog`.|  
|[CTaskDialog::SetFooterIcon](#setfootericon)|Altbilgi simgesi güncelleştirmeleri `CTaskDialog`.|  
|[CTaskDialog::SetFooterText](#setfootertext)|Altbilgisine üzerindeki metin güncelleştirmeleri `CTaskDialog`.|  
|[CTaskDialog::SetMainIcon](#setmainicon)|Ana simgesini güncelleştirmeleri `CTaskDialog`.|  
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|Ana yönergesinin güncelleştirmeleri `CTaskDialog`.|  
|[CTaskDialog::SetOptions](#setoptions)|İçin seçenekleri yapılandırır `CTaskDialog`.|  
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|İçin bir kayan çubuğu yapılandırır `CTaskDialog` ve iletişim kutusuna ekler.|  
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|İlerleme çubuğu konumunu ayarlar.|  
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|İlerleme çubuğu aralığını ayarlar.|  
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|İlerleme çubuğu durumu ayarlar ve görüntüler `CTaskDialog`.|  
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|Etkinleştirir veya radyo düğmesi devre dışı bırakır.|  
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|Doğrulama onay kutusunun işaretli durumu ayarlar.|  
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|Metin doğrulama onay kutusunun sağ tarafında ayarlar.|  
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|Başlığı ayarlar `CTaskDialog`.|  
|[CTaskDialog::ShowDialog](#showdialog)|Oluşturur ve görüntüler bir `CTaskDialog`.|  
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|Framework bu çeşitli Windows iletilere yanıt olarak çağırır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|`m_aButtons`|Komut düğmesi denetimleri için bir dizi `CTaskDialog`.|  
|`m_aRadioButtons`|Radyo düğmesi denetimleri için bir dizi `CTaskDialog`.|  
|`m_bVerified`|`TRUE` Doğrulama onay kutusunun işaretli gösterir; `FALSE` olmayan gösterir.|  
|`m_footerIcon`|Simgenin altbilgisinde yer `CTaskDialog`.|  
|`m_hWnd`|Penceresi için bir tanıtıcı `CTaskDialog`.|  
|`m_mainIcon`|Ana simgesini `CTaskDialog`.|  
|`m_nButtonDisabled`|Ortak düğmelerin belirten bir maskesi devre dışı bırakılır.|  
|`m_nButtonElevation`|Ortak düğmelerin belirten bir maskesi UAC yükseltmesi gerektirir.|  
|`m_nButtonId`|Seçili komut düğmesi denetimi kimliği.|  
|`m_nCommonButton`|Hangi ortak düğmeleri belirten maske görüntülenir `CTaskDialog`.|  
|`m_nDefaultCommandControl`|Komut düğmesi Kimliğini Denetim seçildiğinde `CTaskDialog` görüntülenir.|  
|`m_nDefaultRadioButton`|Radyo düğmesi Kimliğini Denetim seçildiğinde `CTaskDialog` görüntülenir.|  
|`m_nFlags`|Seçeneklerini gösteren maske `CTaskDialog`.|  
|`m_nProgressPos`|İlerleme çubuğu geçerli konumu.  Bu değer arasında olmalıdır `m_nProgressRangeMin` ve `m_nProgressRangeMax`.|  
|`m_nProgressRangeMax`|İlerleme çubuğu en büyük değer.|  
|`m_nProgressRangeMin`|İlerleme çubuğu için en düşük değer.|  
|`m_nProgressState`|İlerleme çubuğu durumu. Daha fazla bilgi için bkz: [CTaskDialog::SetProgressBarState](#setprogressbarstate).|  
|`m_nRadioId`|Seçili radyo düğmesi denetimini kimliği.|  
|`m_nWidth`|Genişliğini `CTaskDialog` piksel cinsinden.|  
|`m_strCollapse`|Dize `CTaskDialog` genişletilmiş bilgi gizli genişletme kutusunun sağındaki görüntüler.|  
|`m_strContent`|İçerik dizesi `CTaskDialog`.|  
|`m_strExpand`|Dize `CTaskDialog` genişletilmiş bilgi görüntülendiğinde genişletme kutusunun sağındaki görüntüler.|  
|`m_strFooter`|Altbilgisine `CTaskDialog`.|  
|`m_strInformation`|Genişletilmiş bilgilerini `CTaskDialog`.|  
|`m_strMainInstruction`|Ana yönergesinin `CTaskDialog`.|  
|`m_strTitle`|Başlığı `CTaskDialog`.|  
|`m_strVerification`|Dize, `CTaskDialog` doğrulama onay kutusunun sağında görüntüler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CTaskDialog` Sınıfı standart Windows ileti kutusu değiştirir ve kullanıcıdan bilgi toplamak için yeni denetimleri gibi ek işlevleri içerir. Bu sınıf MFC kitaplığında, [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)]. `CTaskDialog` Windows Vista'dan itibaren kullanılabilir. Windows'un önceki sürümlerinde görüntüleyemiyor `CTaskDialog` nesnesi. Kullanım `CTaskDialog::IsSupported` çalışma zamanında geçerli kullanıcının Görev iletişim kutusu görüntüleyip görüntülemeyeceğini belirlemek için. Standart Windows ileti kutusu yine de desteklenen [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)].  
  
 `CTaskDialog` Yalnızca uygulamanızı Unicode kitaplığını kullanarak oluşturduğunuzda kullanılabilir.  
  
 `CTaskDialog` İki farklı Oluşturucusu vardır. Bir Oluşturucu iki komut düğmeleri ve en fazla altı normal düğmesi denetimleri belirtmenize olanak sağlar. Oluşturduktan sonra daha fazla komut düğmeleri ekleyebilirsiniz `CTaskDialog`. İkinci oluşturucu herhangi komut düğmeleri desteklemez, ancak normal düğmesi denetimleri sınırsız sayıda ekleyebilirsiniz. Oluşturucular hakkında daha fazla bilgi için bkz: [CTaskDialog::CTaskDialog](#ctaskdialog).  
  
 Aşağıdaki resimde bir örnek gösterilmiştir `CTaskDialog` bazı denetimler konumunu göstermek için.  
  
 ![CTaskDialog örneği](../../mfc/reference/media/ctaskdialogsample.png "ctaskdialogsample")  
CTaskDialog örnek  
  
## <a name="requirements"></a>Gereksinimler  
 **Gereken en düşük işletim sistemi:** Windows Vista  
  
 **Başlık:** afxtaskdialog.h  
  
##  <a name="addcommandcontrol"></a>  CTaskDialog::AddCommandControl  
 Yeni bir komut düğmesi denetim ekler `CTaskDialog`.  
  
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
 Dize, `CTaskDialog` kullanıcıya görüntüler. Bu dize komutunun amacı açıklamak için kullanın.  
  
 [in] *bEtkin*  
 Yeni düğmesi etkin veya devre dışı olduğunu gösteren bir Boole parametresi.  
  
 [in] *bRequiresElevation*  
 Bir komut yükseltme gerekli olup olmadığını gösterir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CTaskDialog Class` Komut düğmesi denetimleri sınırsız sayıda görüntüleyebilirsiniz. Ancak, bir `CTaskDialog` görüntüler herhangi komut düğmesi denetimleri, en fazla altı düğmeleri görüntüleyebilirsiniz. Varsa bir `CTaskDialog` hiçbir komut düğmesi denetimleri olan, sınırsız sayıda düğmeleri görüntüleyebilirsiniz.  
  
 Kullanıcı bir komut düğmesi denetimi seçtiğinde `CTaskDialog` kapatır. Uygulamanızı kullanarak iletişim kutusu görüntülerse [CTaskDialog::DoModal](#domodal), `DoModal` döndürür *nCommandControlID* seçili komut düğmesi denetimi.  
  
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
 Radyo düğmesi kimliği sayısı.  
  
 [in] *strCaption*  
 Dize, `CTaskDialog` yanındaki radyo düğmesini görüntüler.  
  
 [in] *bEtkin*  
 Radyo düğmesi etkin olup olmadığını belirten bir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Radyo düğmeleri için [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md) kullanıcıdan bilgi toplamanızı sağlar. İşlevini [CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid) hangi radyo düğmesi seçilir belirlemek için.  
  
 `CTaskDialog` , Gerektirmez *nRadioButtonID* parametreleri her radyo düğmesi için benzersizdir. Bununla birlikte, her radyo düğmesi için ayrı bir tanımlayıcı kullanmıyorsanız beklenmeyen davranışlarla karşılaşabilirsiniz.  
  
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
 Komut Kimliği denetiminin'ı tıklatın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem windows ileti TDM_CLICK_BUTTON oluşturur.  
  
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
 Bu yöntem windows ileti TDM_CLICK_RADIO_BUTTON oluşturur.  
  
##  <a name="ctaskdialog"></a>  CTaskDialog::CTaskDialog  
 Bir örneğini oluşturur [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md).  
  
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
 İçeriği için kullanılacak dizesi `CTaskDialog`.  
  
 [in] *strMainInstruction*  
 Ana yönergesinin `CTaskDialog`.  
  
 [in] *strTitle*  
 Başlığı `CTaskDialog`.  
  
 [in] *nCommonButtons*  
 Maske eklemek için ortak düğmelerin `CTaskDialog`.  
  
 [in] *nTaskDialogOptions*  
 İçin kullanılacak seçenekleri kümesi `CTaskDialog`.  
  
 [in] *strFooter*  
 Altbilgi kullanılacak dize.  
  
 [in] *nIDCommandControlsFirst*  
 İlk komut dizesi kimliği.  
  
 [in] *nIDCommandControlsLast*  
 Son komut dizesi kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Ekleyebileceğiniz iki yolla bir `CTaskDialog` uygulamanıza. İlk yol oluşturuculardan birine oluşturmak için kullanılacak olan bir `CTaskDialog` ve kullanarak görüntüleme [CTaskDialog::DoModal](#domodal). İkinci yol statik işlevi kullanmaktır [CTaskDialog::ShowDialog](#showdialog), görüntülemenize olanak sağlayan bir `CTaskDialog` açıkça oluşturmadan bir `CTaskDialog` nesnesi.  
  
 İkinci Oluşturucu, uygulamanızın kaynak dosyasından veri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyanın dize tablosunda ilişkili dize kimlikleri birkaç dizelerle yok. Bu yöntem arasında dize tablosundaki geçerli her giriş için bir komut düğmesi denetimi ekler *nIDCommandControlsFirst* ve *nCommandControlsLast*(dahil). Bu komut düğmesi denetimleri için dize dize tablosundaki denetimin başlığı ve dize kimliği denetimin kimliğidir.  
  
 Bkz: [CTaskDialog::SetOptions](#setoptions) geçerli seçenekler listesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="domodal"></a>  CTaskDialog::DoModal  
 Gösterir `CTaskDialog` ve kalıcı hale getirir.  
  
```  
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hParent*  
 İçin üst pencere `CTaskDialog`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı tarafından yapılan seçime karşılık gelen bir tam sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu örneği görüntüler [CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Uygulama kullanıcı iletişim kutusunu kapatmak bekler.  
  
 `CTaskDialog` Kullanıcı ortak düğmesi, bir komut bağlantı denetimi seçer veya kapatır kapatır `CTaskDialog`. Dönüş değeri nasıl kullanıcı iletişim kutusu kapalı gösterir tanımlayıcısı değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="getcommonbuttoncount"></a>  CTaskDialog::GetCommonButtonCount  
 Ortak düğmeleri sayısını alır.  
  
```  
int GetCommonButtonCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ortak düğmeleri kullanılabilir sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Ortak düğmelerinin sağladığınız varsayılan düğme vardır [CTaskDialog::CTaskDialog](#ctaskdialog). [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md) düğmelerini iletişim kutusunun altında görüntülenir.  
  
 Düğmelerin numaralandırılmış listesini CommCtrl.h içinde sağlanır.  
  
##  <a name="getcommonbuttonflag"></a>  CTaskDialog::GetCommonButtonFlag  
 Windows düğme ortak düğme türü için ilişkili bir standart dönüştürür [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md).  
  
```  
int GetCommonButtonFlag(int nButtonId) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nButtonId*  
 Standart Windows düğme değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Buna karşılık gelen değer `CTaskDialog` ortak düğmesi. Bu yöntem, karşılık gelen ortak düğmesi yoksa 0 döndürür.  
  
##  <a name="getcommonbuttonid"></a>  CTaskDialog::GetCommonButtonId  
 İle ilişkili ortak düğmesi türlerinden birini dönüştürür [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md) standart Windows düğme.  
  
```  
int GetCommonButtonId(int nFlag);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nFlag*  
 Ortak düğme türü ile ilişkili `CTaskDialog` sınıfı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karşılık gelen standart Windows düğme değeri. Karşılık gelen Windows düğmesi yoksa, yöntem 0 döndürür.  
  
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
 Seçili komut düğmesi denetimi kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Seçilen kullanıcı komut düğmesi Kimliğini almak için bu yöntemi kullanmak zorunda değil. Bu kimliği tarafından döndürülen [CTaskDialog::DoModal](#domodal) veya [CTaskDialog::ShowDialog](#showdialog).  
  
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
 Kullanıcının seçili radyo düğmesinin almak için iletişim kutusunu kapattıktan sonra bu yöntemi kullanabilirsiniz.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="getverificationcheckboxstate"></a>  CTaskDialog::GetVerificationCheckboxState  
 Doğrulama onay kutusunun durumunu alır.  
  
```  
BOOL GetVerificationCheckboxState() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu durumda onay kutusunun, yanlış işaretli değilse TRUE.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="iscommandcontrolenabled"></a>  CTaskDialog::IsCommandControlEnabled  
 Komut düğmesi denetimi veya düğmesi etkin olup olmadığını belirler.  
  
```  
BOOL IsCommandControlEnabled(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nCommandControlID*  
 Test etmek için komut düğmesi denetimi veya Kimliğini düğmesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değilse denetim, yanlış etkinleştirilmişse TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
 Hem komut düğmesi denetimleri kullanılabilirliğini ve ortak düğmelerinin belirlemek için bu yöntemi kullanabilirsiniz `CTaskDialog` sınıfı *.  
  
 Varsa *nCommandControlID* geçerli bir tanımlayıcı için ortak olan `CTaskDialog` düğmesini veya bir komut düğmesi denetimi, bu yöntem bir özel durum oluşturur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="isradiobuttonenabled"></a>  CTaskDialog::IsRadioButtonEnabled  
 Radyo düğmesi etkin olup olmadığını belirler.  
  
```  
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRadioButtonID*  
 Test etmek için radyo düğmesi kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değilse radyo düğmesi, yanlış etkinleştirilmişse TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *nRadioButtonID* geçerli bir tanımlayıcı değil için bir radyo düğmesi, bu yöntem bir özel durum oluşturur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="issupported"></a>  CTaskDialog::IsSupported  
 Uygulamayı çalıştıran bilgisayarın destekleyip desteklemediğini belirler `CTaskDialog`.  
  
```  
static BOOL IsSupported();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bilgisayar destekliyorsa TRUE `CTaskDialog`; FALSE Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanında uygulamanızı çalıştıran bilgisayar destekleyip desteklemediğini belirlemek için bu işlevi kullanın `CTaskDialog` sınıfı. Bilgisayar desteklemiyor, `CTaskDialog`, kullanıcıya bilgi iletişim başka bir yöntem sağlamanız. Kullanmaya çalışırsa, uygulamanızın kilitleniyor bir `CTaskDialog` desteği olmayan bir bilgisayarda `CTaskDialog` sınıfı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="loadcommandcontrols"></a>  CTaskDialog::LoadCommandControls  
 Komut düğmesi denetimleri dize tablodan veri kullanarak ekler.  
  
```  
void LoadCommandControls(
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIDCommandControlsFirst*  
 İlk komut dizesi kimliği.  
  
 [in] *nIDCommandControlsLast*  
 Son komut dizesi kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, uygulamanızın kaynak dosyasından veri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyanın dize tablosunda ilişkili dize kimlikleri birkaç dizelerle yok. Bu yöntem kullanılarak eklenen yeni komut düğmesi denetimleri dize denetimin başlık ve dize kimliği için denetimin kimliği için kullanın Seçili dizeleri aralığını tarafından sağlanan *nIDCommandControlsFirst* ve *nCommandControlsLast*(dahil). Aralıktaki boş bir giriş varsa, yöntemi bir komut düğmesi denetimi, girişi eklemez.  
  
 Varsayılan olarak, yeni komut düğmesi denetimleri etkinleştirilir ve ayrıcalık gerektirmez.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="loadradiobuttons"></a>  CTaskDialog::LoadRadioButtons  
 Radyo düğmesi denetimini dize tablodan veri kullanarak ekler.  
  
```  
void LoadRadioButtons(
    int nIDRadioButtonsFirst,  
    int nIDRadioButtonsLast);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIDRadioButtonsFirst*  
 Birinci radyo düğmesini dize kimliği.  
  
 [in] *nIDRadioButtonsLast*  
 Son radyo düğmesi dize kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, uygulamanızın kaynak dosyasından veri kullanarak radyo düğmeleri oluşturur. Kaynak dosyanın dize tablosunda ilişkili dize kimlikleri birkaç dizelerle yok. Bu yöntem kullanılarak eklenen yeni radyo düğmeleri dize radyo düğmesinin başlık ve dize kimliği için radyo düğmesinin kimliği için kullan Seçili dizeleri aralığını tarafından sağlanan *nIDRadioButtonsFirst* ve *nRadioButtonsLast*(dahil). Yöntemi, aralığı içinde boş bir giriş varsa, bu girişi için bir radyo düğmesi eklemez.  
  
 Varsayılan olarak, yeni radyo düğmesi etkinleştirilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="navigateto"></a>  CTaskDialog::NavigateTo  
 Odağı diğerine aktarır `CTaskDialog`.  
  
```  
protected:  
void NavigateTo(CTaskDialog& oTaskDialog) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *oTaskDialog*  
 `CTaskDialog` Odağı alır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem geçerli gizler `CTaskDialog` zaman görüntüler *oTaskDialog*. *OTaskDialog* geçerli ile aynı konumda görüntülenen `CTaskDialog`.  
  
##  <a name="oncommandcontrolclick"></a>  CTaskDialog::OnCommandControlClick  
 Kullanıcı komut düğmesi denetimi tıklattığında framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nCommandControlID*  
 Seçilen kullanıcı komut düğmesi denetimi kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi geçersiz kılın.  
  
##  <a name="oncreate"></a>  CTaskDialog::OnCreate  
 Oluşturur sonra framework bu yöntemi çağırır `CTaskDialog`.  
  
```  
virtual HRESULT OnCreate();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi geçersiz kılın.  
  
##  <a name="ondestroy"></a>  CTaskDialog::OnDestroy  
 Önce bozar hemen framework bu yöntemi çağırır `CTaskDialog`.  
  
```  
virtual HRESULT OnDestroy();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi geçersiz kılın.  
  
##  <a name="onexpandbuttonclick"></a>  CTaskDialog::OnExpandButtonClick  
 Kullanıcı genişletme düğmesini tıklattığında framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bExpanded*  
 Ek bilgiler görüntülenir sıfır olmayan bir değer gösterir; ek bilgi gizli 0 gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi geçersiz kılın.  
  
##  <a name="onhelp"></a>  CTaskDialog::OnHelp  
 Kullanıcı Yardım istediğinde framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnHelp();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi geçersiz kılın.  
  
##  <a name="onhyperlinkclick"></a>  CTaskDialog::OnHyperlinkClick  
 Kullanıcı bir köprüyü tıklattığında framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strHref*  
 Köprüyü temsil eden dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) S_OK döndürmeden önce.  
  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi geçersiz kılın.  
  
##  <a name="oninit"></a>  CTaskDialog::OnInit  
 Bu yöntem framework çağırır zaman `CTaskDialog` başlatılır.  
  
```  
virtual HRESULT OnInit();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi geçersiz kılın.  
  
##  <a name="onnavigatepage"></a>  CTaskDialog::OnNavigatePage  
 Yanıt olarak framework bu yöntemi çağırır [CTaskDialog::NavigateTo](#navigateto) yöntemi.  
  
```  
virtual HRESULT OnNavigatePage();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi geçersiz kılın.  
  
##  <a name="onradiobuttonclick"></a>  CTaskDialog::OnRadioButtonClick  
 Kullanıcı bir radyo düğmesi denetimini seçtiğinde framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRadioButtonID*  
 Kullanıcı tıklattınız radyo düğmesi denetimini kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi geçersiz kılın.  
  
##  <a name="ontimer"></a>  CTaskDialog::OnTimer  
 Süreölçer süresi dolduğunda framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnTimer(long lTime);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lTime*  
 Bu yana milisaniye cinsinden süre `CTaskDialog` oluşturuldu veya Zamanlayıcı sıfırlandı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi geçersiz kılın.  
  
##  <a name="onverificationcheckboxclick"></a>  CTaskDialog::OnVerificationCheckboxClick  
 Kullanıcı doğrulama onay kutusunu tıklattığında framework bu yöntemi çağırır.  
  
```  
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bChecked*  
 TRUE doğrulama onay kutusunun seçili gösterir; FALSE değil gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel davranışı uygulamak için bu yöntemi geçersiz kılın.  
  
##  <a name="removeallcommandcontrols"></a>  CTaskDialog::RemoveAllCommandControls  
 Tüm komut düğmesi denetimlerden kaldırır `CTaskDialog`.  
  
```  
void RemoveAllCommandControls();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="removeallradiobuttons"></a>  CTaskDialog::RemoveAllRadioButtons  
 Gelen tüm radyo düğmeleri kaldırır `CTaskDialog`.  
  
```  
void RemoveAllRadioButtons();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setcommandcontroloptions"></a>  CTaskDialog::SetCommandControlOptions  
 Komut düğmesi denetimi güncelleştirir `CTaskDialog`.  
  
```  
void SetCommandControlOptions(
    int nCommandControlID,  
    BOOL bEnabled,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nCommandControlID*  
 Güncelleştirmek için komut denetiminin kimliği.  
  
 [in] *bEtkin*  
 Belirtilen komut düğmesi denetimi etkin veya devre dışı olduğunu gösteren bir Boole parametresi.  
  
 [in] *bRequiresElevation*  
 Belirtilen komut düğmesi denetimi ayrıcalık gerektirip gerektirmediğini belirten bir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Komut düğmesi denetimi etkin ya da için eklendikten sonra yükseltme gerektirir değiştirmek için bu yöntemi kullanmak `CTaskDialog` sınıfı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setcommonbuttonoptions"></a>  CTaskDialog::SetCommonButtonOptions  
 Bir alt kümesini ortak düğmeleri etkinleştirilmesi ve UAC yükseltmesi gerektirecek şekilde güncelleştirir.  
  
```  
void SetCommonButtonOptions(
    int nDisabledButtonMask,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nDisabledButtonMask*  
 Devre dışı bırakmak ortak düğmelerinin maske.  
  
 [in] *nElevationButtonMask*  
 Yükseltmesi gerektiren ortak düğmelerinin maske.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılabilir ortak düğmeleri örneğine ayarlayabilirsiniz [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md) Oluşturucusu kullanılarak [CTaskDialog::CTaskDialog](#ctaskdialog) ve yöntemi [CTaskDialog::SetCommonButtons ](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions` yeni ortak düğmeler eklemeyi desteklemez.  
  
 Bunun için kullanılabilir olmayan bir ortak düğmesi devre dışı bırakmak veya değiştirmesine bu yöntemi kullanırsanız `CTaskDialog`, bu yöntemi kullanarak bir özel durum oluşturur [olun](diagnostic-services.md#ensure) makrosu.  
  
 Bu yöntem kullanılabilir herhangi bir düğmesini etkinleştirir `CTaskDialog` ancak bulunmayan *nDisabledButtonMask*bunu önceden devre dışı olsa bile. Bu yöntem ayrıcalık benzer şekilde davranır: ortak düğmesi kullanılabilir, ancak değil dahil değilse yükseltme gerektirmeyen olarak ortak düğmeleri kayıtları *nElevationButtonMask*.  
  
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
 Maske eklemek için düğmelerin `CTaskDialog`.  
  
 [in] *nDisabledButtonMask*  
 Devre dışı bırakmak için düğmelerin maske.  
  
 [in] *nElevationButtonMask*  
 Ayrıcalık gerektiren düğmelerin maske.  
  
### <a name="remarks"></a>Açıklamalar  
 Görüntü penceresini sonra bu örneği için bu yöntemi çağrılamıyor `CTaskDialog` sınıfı oluşturulur. Bunu yaparsanız, bu yöntem bir özel durum oluşturur.  
  
 Düğmeleri belirtilen tarafından *nButtonMask* için daha önce eklediğiniz tüm ortak düğmeleri geçersiz kılma `CTaskDialog`. Yalnızca düğmeler belirtilen *nButtonMask* kullanılabilir.  
  
 Her iki *nDisabledButtonMask* veya *nElevationButtonMask* kullanımda olmayan bir düğmeyi içeren *nButtonMask*, bu yöntem kullanarakbirözeldurumoluşturur[Olun](diagnostic-services.md#ensure) makrosu.  
  
 Varsayılan olarak, tüm ortak düğmeleri etkinleştirilir ve ayrıcalık gerektirmez.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcontent"></a>  CTaskDialog::SetContent  
 İçeriği güncelleştirmeleri `CTaskDialog`.  
  
```  
void SetContent(const CString& strContent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strContent*  
 Kullanıcıya görüntülenecek dize.  
  
### <a name="remarks"></a>Açıklamalar  
 İçeriği `CTaskDialog` iletişim kutusunun ana bölümünde kullanıcı için görüntülenen metin bir sınıftır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setdefaultcommandcontrol"></a>  CTaskDialog::SetDefaultCommandControl  
 Varsayılan komut düğmesi denetimi belirtir.  
  
```  
void SetDefaultCommandControl(int nCommandControlID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nCommandControlID*  
 Varsayılan olarak kullanılacak komut düğmesi denetimi kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan komut düğmesi denetimi denetimi olduğu zaman seçili `CTaskDialog` önce kullanıcıya görüntülenir.  
  
 Belirtilen komut düğmesi denetimi bulamazsanız, bu yöntem bir özel durum oluşturur *nCommandControlID*.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setdefaultradiobutton"></a>  CTaskDialog::SetDefaultRadioButton  
 Varsayılan radyo düğmesi belirtir.  
  
```  
void SetDefaultRadioButton(int nRadioButtonID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRadioButtonID*  
 Varsayılan olarak kullanılacak radyo düğmesi kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan radyo düğmesi düğmesi olduğu zaman seçili `CTaskDialog` önce kullanıcıya görüntülenir.  
  
 Tarafından belirtilen radyo düğmesi bulamazsanız, bu yöntem bir özel durum oluşturur *nRadioButtonID*.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setdialogwidth"></a>  CTaskDialog::SetDialogWidth  
 Genişliğini ayarlar `CTaskDialog`.  
  
```  
void SetDialogWidth(int nWidth = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nWidth*  
 İletişim kutusunun piksel cinsinden genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre *nWidth* değerinden büyük veya 0 değerine eşit olmalıdır. Aksi takdirde, bu yöntem bir özel durum oluşturur.  
  
 Varsa *nWidth* 0'dır, bu yöntemi ayarlar iletişim kutusu varsayılan boyutunu ayarlayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setexpansionarea"></a>  CTaskDialog::SetExpansionArea  
 Genişletme alanını güncelleştirir `CTaskDialog`.  
  
```  
void SetExpansionArea(
    const CString& strExpandedInformation,  
    const CString& strCollapsedLabel = _T(""),  
    const CString& strExpandedLabel = _T(""));
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strExpandedInformation*  
 Dize, `CTaskDialog` kullanıcı genişletme düğmesine tıkladığında iletişim kutusunda ana gövdesinde görüntüler.  
  
 [in] *strCollapsedLabel*  
 Dize, `CTaskDialog` genişletilmiş alanı daraltıldığında yanındaki genişletme düğmesini görüntüler.  
  
 [in] *strExpandedLabel*  
 Dize, `CTaskDialog` genişletilmiş alan görüntülendiğinde yanındaki genişletme düğmesini görüntüler.  
  
### <a name="remarks"></a>Açıklamalar  
 Genişletme alanını `CTaskDialog` sınıfı, kullanıcı için ek bilgileri sağlamanıza olanak tanır. Genişletme alanı ana kısmındadır `CTaskDialog`, başlık ve içerik dizesi hemen altında bulunur.  
  
 Zaman `CTaskDialog` ilk görüntülenen, genişletilmiş bilgi göstermez ve koyar `strCollapsedLabel` yanındaki genişletme düğmesi. Kullanıcı genişletme düğmesini tıklattığında `CTaskDialog` görüntüler *strExpandedInformation* ve etiketi değiştirir *strExpandedLabel*.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootericon"></a>  CTaskDialog::SetFooterIcon  
 Altbilgi simgesini güncelleştirmeleri `CTaskDialog`.  
  
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
 Listenin sonuna altbilgi simgesi görüntülenir [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md). Altbilginin ilişkilendirdiğiniz. Altbilgi metinle değiştirebilirsiniz [CTaskDialog::SetFooterText](#setfootertext).  
  
 Bu yöntem ile aykırı [emin olun](diagnostic-services.md#ensure) makrosu varsa `CTaskDialog` görüntülenir veya giriş parametresi NULL.  
  
 A `CTaskDialog` yalnızca kabul edebilen bir `HICON` veya `LPCWSTR` altbilgi simge olarak. Bu oluşturucuda TDF_USE_HICON_FOOTER seçeneği ayarlayarak yapılandırılmış veya [CTaskDialog::SetOptions](#setoptions). Varsayılan olarak, `CTaskDialog` kullanmak üzere yapılandırılmış `LPCWSTR` altbilgi simgesi için girdi türü olarak. Uygunsuz türü kullanılarak simgesi ayarlamaya çalışırsanız, bu yöntem bir özel durum oluşturur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootertext"></a>  CTaskDialog::SetFooterText  
 Altbilgisine üzerindeki metin güncelleştirmeleri `CTaskDialog`.  
  
```  
void SetFooterText(const CString& strFooterText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strFooterText*  
 Altbilgi yeni metin.  
  
### <a name="remarks"></a>Açıklamalar  
 Pencerenin alt kısmındaki altbilgi metnin yanında altbilgi simgesi görünür `CTaskDialog`. Altbilgi simgesiyle değiştirebileceğiniz [CTaskDialog::SetFooterIcon](#setfootericon).  
  
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
 Yeni simgesi.  
  
 [in] *lpszMainIcon*  
 Yeni simgesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ile aykırı [emin olun](diagnostic-services.md#ensure) makrosu varsa `CTaskDialog` görüntülenir veya giriş parametresi NULL.  
  
 A `CTaskDialog` yalnızca kabul edebilen bir `HICON` veya `LPCWSTR` ana bir simge. Bu ayarı oluşturucuda TDF_USE_HICON_MAIN seçeneğini veya buna yapılandırabilirsiniz [CTaskDialog::SetOptions](#setoptions) yöntemi. Varsayılan olarak, `CTaskDialog` kullanmak üzere yapılandırılmış `LPCWSTR` ana simgesi için girdi türü olarak. Uygunsuz türü kullanılarak simgesi ayarlamaya çalışırsanız, bu yöntem bir özel durum oluşturur.  
  
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
 Ana yönergesinin `CTaskDialog` büyük kalın yazı tipiyle kullanıcıya görüntülenen metin bir sınıftır. Başlık çubuğunun altında iletişim kutusunda bulunur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setoptions"></a>  CTaskDialog::SetOptions  
 İçin seçenekleri yapılandırır `CTaskDialog`.  
  
```  
void SetOptions(int nOptionFlag);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nOptionFlag*  
 Kullanılmak üzere bayrakları kümesi `CTaskDialog`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için tüm geçerli seçeneklerini temizler `CTaskDialog`. Geçerli seçeneklerini korumak için bunları ilk ile almanız gerekir [CTaskDialog::GetOptions](#getoptions) ve bunları ayarlamak istediğiniz seçenekleri ile birleştirebilirsiniz.  
  
 Tüm geçerli seçenekleri aşağıdaki tabloda listelenmektedir.  
  
 TDF_ENABLE_HYPERLINKS  
 Köprüleri etkinleştirir `CTaskDialog`.  
  
 TDF_USE_HICON_MAIN  
 Yapılandırır `CTaskDialog` kullanmak için bir `HICON` ana simgesi. Alternatif kullanmaktır bir `LPCWSTR`.  
  
 TDF_USE_HICON_FOOTER  
 Yapılandırır `CTaskDialog` kullanmak için bir `HICON` altbilgi simgesi. Alternatif kullanmaktır bir `LPCWSTR`.  
  
 TDF_ALLOW_DIALOG_CANCELLATION  
 Kapatmak kullanıcının sağlayan `CTaskDialog` klavyeyi kullanarak veya iletişim kutusunun sağ üst köşesinde simgesini kullanarak olsa bile **iptal** düğmesi etkin değil. Bu bayrak ayarlanmazsa ve **iptal** düğmesi etkin değil, Alt + F4, kaçış anahtarı kullanarak, kullanıcı iletişim kutusunu iptal edilemez veya başlık çubuğu düğme kapatın.  
  
 TDF_USE_COMMAND_LINKS  
 Yapılandırır `CTaskDialog` komut düğmesi denetimleri kullanmak için.  
  
 TDF_USE_COMMAND_LINKS_NO_ICON  
 Yapılandırır `CTaskDialog` denetimi yanındaki simge görüntülemeden komut düğmesi denetimleri kullanmak için. TDF_USE_COMMAND_LINKS TDF_USE_COMMAND_LINKS_NO_ICON geçersiz kılar.  
  
 TDF_EXPAND_FOOTER_AREA  
 Genişletme alan şu anda genişletilmiş gösterir.  
  
 TDF_EXPANDED_BY_DEFAULT  
 Varsayılan olarak genişletme alanı genişletilmiş olup olmadığını belirler.  
  
 TDF_VERIFICATION_FLAG_CHECKED  
 Doğrulama onay kutusunun seçili gösterir.  
  
 TDF_SHOW_PROGRESS_BAR  
 Yapılandırır `CTaskDialog` bir ilerleme çubuğu görüntülemek için.  
  
 TDF_SHOW_MARQUEE_PROGRESS_BAR  
 İlerleme çubuğu çerçevesi ilerleme çubuğu olacak şekilde yapılandırır. Bu seçeneği etkinleştirirseniz, beklenen davranışı sağlamak için TDF_SHOW_PROGRESS_BAR ayarlamanız gerekir.  
  
 TDF_CALLBACK_TIMER  
 Belirten `CTaskDialog` geri çağırma aralığı için yaklaşık 200 milisaniye olarak ayarlanır.  
  
 TDF_POSITION_RELATIVE_TO_WINDOW  
 Yapılandırır `CTaskDialog` göre üst pencere ortalanmış için. Bu bayrak etkin değilse `CTaskDialog` İzleyici göre ortalanır.  
  
 TDF_RTL_LAYOUT  
 Yapılandırır `CTaskDialog` sağdan sola okuma düzeni için.  
  
 TDF_NO_DEFAULT_RADIO_BUTTON  
 Hiçbir radyo düğmesi seçilir gösterir zaman `CTaskDialog` görüntülenir.  
  
 TDF_CAN_BE_MINIMIZED  
 En aza indirmek kullanıcının sağlayan `CTaskDialog`. Bu seçeneği desteklemek üzere `CTaskDialog` kalıcı olamaz. MFC MFC bir geçici desteklemediği için bu seçeneği desteklemiyor `CTaskDialog`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setprogressbarmarquee"></a>  CTaskDialog::SetProgressBarMarquee  
 İçin bir kayan çubuğu yapılandırır `CTaskDialog` ve iletişim kutusuna ekler.  
  
```  
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,  
    int nMarqueeSpeed = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bEtkin*  
 Kayan çubuğunu etkinleştirmek için TRUE; Kayan çubuğu devre dışı bırakın ve ondan kaldırmak için FALSE `CTaskDialog`.  
  
 [in] *nMarqueeSpeed*  
 Kayan çubuğu hızını belirten tamsayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayan çubuğunun altında ana metni görünür `CTaskDialog` sınıfı.  
  
 Kullanım *nMarqueeSpeed* kayan çubuğu; hızına ayarlamak için daha büyük değerler daha yavaş hızı gösterir. İçin 0 değerini *nMarqueeSpeed* Windows için varsayılan hızında hareket çerçevesi çubuğunun neden olur.  
  
 Bu yöntem ile aykırı [olun](diagnostic-services.md#ensure) makrosu varsa *nMarqueeSpeed* 0'dan küçük.  
  
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
 Bu yöntem ile aykırı [emin olun](diagnostic-services.md#ensure) makrosu varsa *nProgressPos* ilerleme çubuğu aralığında değil. İlerleme çubuğu aralığıyla değiştirebileceğiniz [CTaskDialog::SetProgressBarRange](#setprogressbarrange).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarrange"></a>  CTaskDialog::SetProgressBarRange  
 İlerleme çubuğu aralığını ayarlar.  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRangeMin*  
 İlerleme çubuğu alt sınır.  
  
 [in] *nRangeMax*  
 İlerleme çubuğu üst sınırı.  
  
### <a name="remarks"></a>Açıklamalar  
 İlerleme çubuğu göreli konumudur *nRangeMin* ve *nRangeMax*. Örneğin, varsa *nRangeMin* 50'dir ve *nRangeMax* 100, ilerleme çubuğu 75 konumunu ortasında yer alan. Kullanım [CTaskDialog::SetProgressBarPosition](#setprogressbarposition) ilerleme çubuğu konumunu ayarlamak için.  
  
 İlerleme çubuğu görüntülemek için TDF_SHOW_MARQUEE_PROGRESS_BAR ve TDF_SHOW_PROGRESS_BAR etkinleştirilmelidir seçeneği etkinleştirilmelidir değil. Bu yöntem, otomatik olarak TDF_SHOW_PROGRESS_BAR ayarlar ve TDF_SHOW_MARQUEE_PROGRESS_BAR temizler. Kullanım [CTaskDialog::SetOptions](#setoptions) el ile bu örneği için seçeneklerini değiştirmek için [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md).  
  
 Bu yöntem ile aykırı [emin olun](diagnostic-services.md#ensure) makrosu varsa *nRangeMin* olan küçük değildir *nRangeMax*. Bu yöntem aynı zamanda bir özel durum döndürürse `CTaskDialog` zaten görüntülenir ve bir kayan ilerleme çubuğu vardır.  
  
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
 Bu yöntem ile aykırı [emin olun](diagnostic-services.md#ensure) makrosu varsa `CTaskDialog` zaten görüntülenir ve bir kayan ilerleme çubuğu vardır.  
  
 İçin olası değerler aşağıdaki tabloda listelenmektedir *nDurum*. Belirlenen durağı konumu ulaşana kadar bu durumlarda, ilerleme çubuğu normal renkle doldurun. Bu noktada renk durumuna göre değişir.  
  
 PBST_NORMAL  
 Sonra ilerleme çubuğu doldurur, `CTaskDialog` çubuğunun rengini değiştirmez. Varsayılan olarak, normal yeşil renkte.  
  
 PBST_ERROR  
 Sonra ilerleme çubuğu doldurur, `CTaskDialog` hata renk çubuğu rengini değiştirir. Varsayılan olarak, bu kırmızıdır.  
  
 PBST_PAUSED  
 Sonra ilerleme çubuğu doldurur, `CTaskDialog` duraklatılmış renk çubuğu rengini değiştirir. Varsayılan olarak, sarı budur.  
  
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
 Bu yöntem ile aykırı [emin olun](diagnostic-services.md#ensure) makrosu varsa *nRadioButtonID* radyo düğmesi için geçerli bir kimliği değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setverificationcheckbox"></a>  CTaskDialog::SetVerificationCheckbox  
 Doğrulama onay kutusunun işaretli durumu ayarlar.  
  
```  
void SetVerificationCheckbox(BOOL bChecked);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bChecked*  
 Girintili doğrulaması onay kutusu ne zaman seçtiniz `CTaskDialog` görüntülenir; YANLIŞ doğrulama onay kutusu seçili `CTaskDialog` görüntülenir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setverificationcheckboxtext"></a>  CTaskDialog::SetVerificationCheckboxText  
 Doğrulama onay kutusunun sağında görüntülenen metni ayarlar.  
  
```  
void SetVerificationCheckboxText(CString& strVerificationText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strVerificationText*  
 Bu yöntem yanındaki doğrulama onay kutusunu görüntüler metin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ile aykırı [emin olun](diagnostic-services.md#ensure) makrosu Bu örneği `CTaskDialog` sınıf zaten görüntülenir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setwindowtitle"></a>  CTaskDialog::SetWindowTitle  
 Başlığı ayarlar `CTaskDialog`.  
  
```  
void SetWindowTitle(CString& strWindowTitle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strWindowTitle*  
 İçin yeni başlık `CTaskDialog`.  
  
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
 İçeriği için kullanılacak dizesi `CTaskDialog`.  
  
 [in] *strMainInstruction*  
 Ana yönergesinin `CTaskDialog`.  
  
 [in] *strTitle*  
 Başlığı `CTaskDialog`.  
  
 [in] *nIDCommandControlsFirst*  
 İlk komut dizesi kimliği.  
  
 [in] *nIDCommandControlsLast*  
 Son komut dizesi kimliği.  
  
 [in] *nCommonButtons*  
 Maske eklemek için düğmelerin `CTaskDialog`.  
  
 [in] *nTaskDialogOptions*  
 İçin kullanılacak seçenekleri kümesi `CTaskDialog`.  
  
 [in] *strFooter*  
 Altbilgi kullanılacak dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı tarafından yapılan seçime karşılık gelen bir tam sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu statik yöntem örneği oluşturmanızı sağlayan `CTaskDialog` açıkça oluşturmadan sınıfı bir `CTaskDialog` kodunuzu nesnesinde. Olduğundan hiçbir `CTaskDialog` nesnesi, herhangi bir yöntem, çağıramaz `CTaskDialog` göstermek için bu yöntemi kullanırsanız, bir `CTaskDialog` kullanıcı.  
  
 Bu yöntem, uygulamanızın kaynak dosyasından veri kullanarak komut düğmesi denetimleri oluşturur. Kaynak dosyanın dize tablosunda ilişkili dize kimlikleri birkaç dizelerle yok. Bu yöntem arasında dize tablosundaki geçerli her giriş için bir komut düğmesi denetimi ekler *nIDCommandControlsFirst* ve *nCommandControlsLast*(dahil). Bu komut düğmesi denetimleri için dize dize tablosundaki denetimin başlığı ve dize kimliği denetimin kimliğidir.  
  
 Bkz: [CTaskDialog::SetOptions](#setoptions) geçerli seçenekler listesi.  
  
 `CTaskDialog` Kullanıcı ortak düğmesi, bir komut bağlantı denetimi seçer veya kapatır kapatır `CTaskDialog`. Dönüş değeri nasıl kullanıcı iletişim kutusu kapalı gösterir tanımlayıcısı değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="taskdialogcallback"></a>  CTaskDialog::TaskDialogCallback  
 Çerçeve, çeşitli Windows iletilere yanıt olarak bu yöntemi çağırır.  
  
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
 İçin bir tanıtıcı `m_hWnd` için yapı `CTaskDialog`.  
  
 [in] *uNotification*  
 Oluşturulan iletiyi belirtir bildirim kodu.  
  
 [in] *wParam*  
 İleti hakkında daha fazla bilgi.  
  
 [in] *lParam*  
 İleti hakkında daha fazla bilgi.  
  
 [in] *dwRefData*  
 Bir işaretçi `CTaskDialog` geri çağırma iletisi uygulanacağı nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirli bildirim koduna bağlıdır. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulaması `TaskDialogCallback` belirli ileti işleme ve uygun yöntemi üzerinde ı çağırır [CTaskDialog sınıfı](../../mfc/reference/ctaskdialog-class.md). Örneğin, TDN_BUTTON_CLICKED iletisine yanıt olarak `TaskDialogCallback` çağrıları [CTaskDialog::OnCommandControlClick](#oncommandcontrolclick).  
  
 Değerleri *wParam* ve *lParam* belirli oluşturulan iletide bağlıdır. Ya da ya da boş olması için bu değerleri her ikisi de mümkündür. Aşağıdaki tabloda desteklenen varsayılan bildirimleri ve ne listeler değerlerini *wParam* ve *lParam* temsil eder. Bir türetilmiş sınıfta bu yöntemi geçersiz kılarsanız aşağıdaki tabloda her ileti için geri çağırma kodu uygulamanız gerekir.  
  
|Bildirim iletisi|*wParam* değeri|*lParam* değeri|  
|--------------------------|--------------------|--------------------|  
|TDN_CREATED|Kullanılmadı.|Kullanılmadı.|  
|TDN_NAVIGATED|Kullanılmadı.|Kullanılmadı.|  
|TDN_BUTTON_CLICKED|Komut düğmesi denetim kimliği.|Kullanılmadı.|  
|TDN_HYPERLINK_CLICKED|Kullanılmadı.|A [LPCWSTR](http://msdn.microsoft.com/library/windows/desktop/aa383751) bağlantıyı içeren yapısı.|  
|TDN_TIMER|Bu yana milisaniye cinsinden süre `CTaskDialog` oluşturuldu veya Zamanlayıcı sıfırlandı.|Kullanılmadı.|  
|TDN_DESTROYED|Kullanılmadı.|Kullanılmadı.|  
|TDN_RADIO_BUTTON_CLICKED|Radyo düğmesi kimliği|Kullanılmadı.|  
|TDN_DIALOG_CONSTRUCTED|Kullanılmadı.|Kullanılmadı.|  
|TDN_VERIFICATION_CLICKED|onay kutusu işaretli değilse 1, 0 değilse.|Kullanılmadı.|  
|TDN_HELP|Kullanılmadı.|Kullanılmadı.|  
|TDN_EXPANDO_BUTTON_CLICKED|genişletme alanı daraltılmışsa 0; sıfır genişletme metin görüntüleniyorsa.|Kullanılmadı.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [İzlenecek yol: Bir Uygulamaya CTaskDialog Ekleme](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)



