---
title: "CMFCEditBrowseCtrl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFileBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFolderBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::GetMode
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnAfterUpdate
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnBrowse
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnChangeLayout
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnDrawBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnIllegalFileName
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::SetBrowseButtonImage
dev_langs: C++
helpviewer_keywords:
- CMFCEditBrowseCtrl [MFC], EnableBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFileBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFolderBrowseButton
- CMFCEditBrowseCtrl [MFC], GetMode
- CMFCEditBrowseCtrl [MFC], OnAfterUpdate
- CMFCEditBrowseCtrl [MFC], OnBrowse
- CMFCEditBrowseCtrl [MFC], OnChangeLayout
- CMFCEditBrowseCtrl [MFC], OnDrawBrowseButton
- CMFCEditBrowseCtrl [MFC], OnIllegalFileName
- CMFCEditBrowseCtrl [MFC], SetBrowseButtonImage
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
caps.latest.revision: "33"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: de1e30e6ca9f404199c6db43837f35d612a02b69
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfceditbrowsectrl-class"></a>CMFCEditBrowseCtrl sınıfı
`CMFCEditBrowseCtrl` Sınıfı, isteğe bağlı olarak bir Gözat düğmesi içeren bir düzenlenebilir metin kutusu düzenleme Gözat denetimi destekler. Kullanıcı Gözat düğmesine tıkladığında, Denetim özel bir eylem gerçekleştiren veya bir dosya tarayıcısı veya bir klasörü tarayıcı içeren bir standart iletişim kutusu görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCEditBrowseCtrl : public CEdit  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|Varsayılan Oluşturucu.|  
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|Etkinleştirir veya devre dışı bırakır (gizler) Gözat düğmesine.|  
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|Gözat düğmesini etkinleştirir ve düzenleme Gözat denetimi koyar *dosya Gözat* modu.|  
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|Gözat düğmesini etkinleştirir ve düzenleme Gözat denetimi koyar *klasöre Gözat* modu.|  
|[CMFCEditBrowseCtrl::GetMode](#getmode)|Geçerli gözatma modu döndürür.|  
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|Düzenleme Gözat denetimi bir gözatma eylem sonucu ile güncelleştirildikten sonra çerçevesi tarafından çağrılır.|  
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|Kullanıcı Gözat düğmesini tıklattıktan sonra çerçevesi tarafından çağrılır.|  
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|Geçerli düzenleme Gözat denetimi yeniden çizer.|  
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|Gözat düğmesini çizmek için çerçevesi tarafından çağrılır.|  
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|Geçersiz dosya adı düzenleme denetimine girildiğinde çerçevesi tarafından çağrılır.|  
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Pencere iletileri için gönderilen önce çevirir [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows çalışır. Sözdizimi ve daha fazla bilgi için bkz: [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).|  
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|Gözat düğmesi için özel bir görüntü ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir dosya veya klasör adı seçmek için bir düzen Gözat denetimini kullanın. İsteğe bağlı olarak, bir iletişim kutusu görüntülemek için olduğu gibi özel bir eylem gerçekleştirmek için denetimi kullanın. Görüntülemek veya görüntülememek Gözat düğmesini ve bir özel etiket veya görüntü düğmeyi uygulayabilir.  
  
 *Modu Gözat* olup bir Gözat düğmesi görüntüler ve hangi eylemini düğmesine tıklandığında oluşur düzenleme Gözat denetimi belirler. Daha fazla bilgi için bkz: [GetMode](#getmode) yöntemi.  
  
 `CMFCEditBrowseCtrl` Sınıfı, aşağıdaki modlarını destekler.  
  
 `custom mode`  
 Kullanıcı Gözat düğmesine tıkladığında özel bir eylem gerçekleştirilir. Örneğin, bir uygulamaya özgü iletişim kutusu görüntüleyebilir.  
  
 `file mode`  
 Kullanıcı Gözat düğmesine tıkladığında standart dosya seçimi iletişim kutusu görüntülenir.  
  
 `folder mode`  
 Kullanıcı Gözat düğmesine tıkladığında standart klasör seçimi iletişim kutusu görüntülenir.  
  
## <a name="how-to-specify-an-edit-browse-control"></a>Nasıl yapılır: bir düzenleme Gözat denetimi belirtin  
 Bir düzen Gözat denetimini uygulamanızda eklemek için aşağıdaki adımları gerçekleştirin:  
  
1.  Özel gözatma modu uygulamak istiyorsanız, kendi sınıfından türetilen `CMFCEditBrowseCtrl` sınıfı ve daha sonra geçersiz [CMFCEditBrowseCtrl::OnBrowse](#onbrowse) yöntemi. Geçersiz kılınan yöntemi bir özel Gözat eylem yürütme ve düzenleme Gözat denetimi sonucu ile güncelleştirin.  
  
2.  Ya da katıştırmak `CMFCEditBrowseCtrl` nesne veya türetilmiş düzenleme Gözat denetim nesnesine üst pencere nesnesi.  
  
3.  Kullanırsanız **sınıf Sihirbazı** Oluştur iletişim kutusu için bir düzen denetimi ekleyin ( `CEdit`) için iletişim kutusu formu. Ayrıca, erişim denetimi üstbilgi dosyası için bir değişken ekleyin. Üst bilgi dosyanızda değişkeninden türünü değiştirme `CEdit` için `CMFCEditBrowseCtrl`. Düzenleme Gözat denetimi otomatik olarak oluşturulur. Kullanmıyorsanız, **sınıf Sihirbazı**, ekleme bir `CMFCEditBrowseCtrl` üstbilgi dosyası ve ardından arama değişken kendi `Create` yöntemi.  
  
4.  Bir iletişim kutusu için bir düzen Gözat denetimi eklerseniz, kullanmak **ClassWizard** veri değişimi ayarlamak için aracı.  
  
5.  Çağrı [EnableFolderBrowseButton](#enablefolderbrowsebutton), [EnableFileBrowseButton](#enablefilebrowsebutton), veya [EnableBrowseButton](#enablebrowsebutton) gözatma modu ayarlamak ve Gözat düğmesini görüntülemek için yöntem. Çağrı [GetMode](#getmode) geçerli gözatma modu elde etmek için yöntemi.  
  
6.  Gözat düğmesi için özel bir görüntü sağlamak için arama [SetBrowseButtonImage](#setbrowsebuttonimage) yöntemi veya geçersiz kılma [OnDrawBrowseButton](#ondrawbrowsebutton) yöntemi.  
  
7.  Gözat düğmesini Düzenle Gözat denetiminden kaldırmak için arama [EnableBrowseButton](#enablebrowsebutton) yöntemiyle `bEnable` parametre kümesine `FALSE`.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte iki yöntem de kullanımı gösterilmiştir `CMFCEditBrowseCtrl` sınıfı: `EnableFolderBrowseButton` ve `EnableFileBrowseButton`. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxeditbrowsectrl.h  
  
##  <a name="enablebrowsebutton"></a>CMFCEditBrowseCtrl::EnableBrowseButton  
 Görüntüler veya Gözat düğmesine geçerli düzenleme Gözat denetiminde görüntülemez.  
  
```  
void EnableBrowseButton(
    BOOL bEnable=TRUE,  
    LPCTSTR szLabel=_T("..."));
```  
  
### <a name="parameters"></a>Parametreler  
 `bEnable`  
 `TRUE`Gözat düğmesini görüntülemek için; `FALSE` Gözat düğmesini görüntülememek üzere. Varsayılan değer `TRUE` şeklindedir.  
  
 `szLabel`  
 Gözat düğmesi görüntülenen etiketi. Varsayılan değer " **...** ".  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bEnable` parametresi `TRUE`, Gözat düğmesine tıklandığında gerçekleştirmek için özel bir eylemi uygulamak. Özel bir eylemi uygulamak için öğesinden bir sınıf türetin `CMFCEditBrowseCtrl` sınıfı ve daha sonra geçersiz kendi [OnBrowse](#onbrowse) yöntemi.  
  
 Varsa `bEnable` parametresi `TRUE`, denetimin gözatma modu `BrowseMode_Default`; Aksi halde, gözatma modu `BrowseMode_None`. Gözat modları hakkında daha fazla bilgi için bkz: [GetMode](#getmode) yöntemi.  
  
##  <a name="enablefilebrowsebutton"></a>CMFCEditBrowseCtrl::EnableFileBrowseButton  
 Geçerli düzenleme Gözat denetiminde Gözat düğmesini görüntüler ve denetim koyar *dosya Gözat* modu.  
  
```  
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,  
    LPCTSTR lpszFilter=NULL,  
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszDefExt`  
 Dosya Seçimi iletişim kutusunda kullanılan varsayılan dosya adı uzantısını belirtir. Varsayılan değer `NULL` şeklindedir.  
  
 `lpszFilter`  
 Dosya Seçimi iletişim kutusunda kullanılan varsayılan filtre dizesini belirtir. Varsayılan değer `NULL` şeklindedir.  
  
 `dwFlags`  
 İletişim kutusu bayraklar. Bit düzeyinde bileşimini (veya) OFN_HIDEREADONLY ve OFN_OVERWRITEPROMPT varsayılan değerdir.  
  
### <a name="remarks"></a>Açıklamalar  
 Dosya gözatma modunda düzenleme Gözat denetimdir ve kullanıcı Gözat düğmesine tıkladığında denetimi standart dosya seçimi iletişim kutusunu görüntüler.  
  
 Kullanılabilir bayrakları tam bir listesi için bkz: [AÇIKDOSYAADI yapısı](https://msdn.microsoft.com/library/ms646839.aspx).  
  
##  <a name="enablefolderbrowsebutton"></a>CMFCEditBrowseCtrl::EnableFolderBrowseButton  
 Geçerli düzenleme Gözat denetiminde Gözat düğmesini görüntüler ve denetim koyar *klasöre Gözat* modu.  
  
```  
void EnableFolderBrowseButton();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Klasör gözatma modunda düzenleme Gözat denetimdir ve kullanıcı Gözat düğmesine tıkladığında denetimi standart klasör seçimi iletişim kutusunu görüntüler.  
  
##  <a name="getmode"></a>CMFCEditBrowseCtrl::GetMode  
 Gözatma modu geçerli düzenleme Gözat denetiminin alır.  
  
```  
CMFCEditBrowseCtrl::BrowseMode GetMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli mod düzenleme belirten numaralandırma değerlerinden biri denetim göz atın. Gözatma modu olup framework Gözat düğmesini görüntüler ve hangi eylemini bir kullanıcı o düğmesini tıklattığında oluşur belirler.  
  
 Aşağıdaki tabloda olası dönüş değerleri listelenmektedir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`BrowseMode_Default`|`custom mode`. Programcı tanımlı bir eylem gerçekleştirilir.|  
|`BrowseMode_File`|`file mode`. Standart dosya tarayıcısı iletişim kutusu görüntülenir.|  
|`BrowseMode_Folder`|`folder mode`. Standart klasör Tarayıcı iletişim kutusu görüntülenir.|  
|`BrowseMode_None`|Gözat düğmesini görüntülenmez.|  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bir `CMFCEditBrowseCtrl` nesne başlatılır `BrowseMode_None` modu. Gözatma modu ile değiştirmek [CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton), [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton), ve [CMFCEditBrowseCtrl::EnableFolderBrowseButton ](#enablefolderbrowsebutton) yöntemleri.  
  
##  <a name="onafterupdate"></a>CMFCEditBrowseCtrl::OnAfterUpdate  
 Düzenleme Gözat denetimi bir gözatma eylem sonucu ile güncelleştirildikten sonra çerçevesi tarafından çağrılır.  
  
```  
virtual void OnAfterUpdate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bir eylemi uygulamak için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="onbrowse"></a>CMFCEditBrowseCtrl::OnBrowse  
 Kullanıcı düzenleme Gözat denetimi Gözat düğmesini tıklattıktan sonra çerçevesi tarafından çağrılır.  
  
```  
virtual void OnBrowse();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı düzenleme Gözat denetimi Gözat düğmesini tıklattığında özel kod yürütmek için bu yöntemi kullanın. Kendi sınıfından türetilen `CMFCEditBrowseCtrl` sınıfı ve geçersiz kılma kendi `OnBrowse` yöntemi. Bu yöntem bir özel Gözat eylemi uygulamak ve düzenleme Gözat denetimi metin kutusuna isteğe bağlı olarak güncelleştir. Uygulamanızda kullanmak [EnableBrowseButton](#enablebrowsebutton) düzenleme Gözat denetimi yerleştirmek için yöntemi *özel Gözat* modu.  
  
##  <a name="onchangelayout"></a>CMFCEditBrowseCtrl::OnChangeLayout  
 Geçerli düzenleme Gözat denetimi yeniden çizer.  
  
```  
virtual void OnChangeLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Düzen Gözat Gözat modunu kontrol değiştiğinde framework bu yöntemi çağırır. Daha fazla bilgi için bkz: [CMFCEditBrowseCtrl::GetMode](#getmode).  
  
##  <a name="ondrawbrowsebutton"></a>CMFCEditBrowseCtrl::OnDrawBrowseButton  
 Gözat düğmesini Düzenle Gözat denetiminde çizmek için framework tarafından çağrılır.  
  
```  
virtual void OnDrawBrowseButton(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsButtonPressed,  
    BOOL bIsButtonHot);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 `Rect`  
 Gözat düğmesini sınırlayıcı dikdörtgenini.  
  
 `bIsButtonPressed`  
 `TRUE`düğmeye basıldığında Aksi takdirde `FALSE`.  
  
 `bIsButtonHot`  
 `TRUE`düğmesi vurgulanmış; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev Gözat düğmesini görünümünü özelleştirmek için bir türetilmiş sınıfta geçersiz kılar.  
  
##  <a name="setbrowsebuttonimage"></a>CMFCEditBrowseCtrl::SetBrowseButtonImage  
 Özel görüntü düzenleme Gözat denetimi Gözat düğmesini ayarlar.  
  
```  
void SetBrowseButtonImage(
    HICON hIcon,  
    BOOL bAutoDestroy= TRUE);

 
void SetBrowseButtonImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy= TRUE);  
  
void SetBrowseButtonImage(UINT uiBmpResId);
```  
  
### <a name="parameters"></a>Parametreler  
 `hIcon`  
 Simge işleci.  
  
 `hBitmap`  
 Bir bit eşlem işleci.  
  
 `uiBmpResId`  
 Bir bit eşlem kaynak kimliği.  
  
 `bAutoDestroy`  
 `TRUE`Bu yöntem çıktığında belirtilen simgeyi veya bit eşlem silmek için; Aksi takdirde `FALSE`. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel görüntü Gözat düğmesine uygulamak için bu yöntemi kullanın. Varsayılan olarak, düzenleme Gözat denetimi olduğunda framework standart bir görüntü alır. *dosya Gözat* veya *klasöre Gözat* modu.  
  
##  <a name="onillegalfilename"></a>CMFCEditBrowseCtrl::OnIllegalFileName  
 Geçersiz dosya adı düzenleme denetimine girildiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnIllegalFileName(CString& strFileName);
```  
  
### <a name="parameters"></a>Parametreler  
 `strFileName`  
 Geçersiz dosya adını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürmelidir `FALSE` varsa bu dosya adı dosya iletişim kutusu daha fazla sınırlandıramazsınız geçirilemez. Bu durumda, odak geri düzenleme denetimi ayarlanır ve kullanıcı düzenleme devam etmelidir. Varsayılan uygulama döndürür ve kullanıcı geçersiz dosya adı hakkında bildiren bir ileti kutusu görüntüler `FALSE`. Bu yöntemi yok sayın, dosya adını düzeltin ve dönüş `TRUE` başka bir işleme için.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
