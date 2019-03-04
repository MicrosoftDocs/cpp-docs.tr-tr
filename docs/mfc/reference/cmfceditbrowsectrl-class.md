---
title: CMFCEditBrowseCtrl Class
ms.date: 11/04/2016
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
ms.openlocfilehash: 8d1f603f8439815c92360af40ccb807446d0e84a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273289"
---
# <a name="cmfceditbrowsectrl-class"></a>CMFCEditBrowseCtrl Class

`CMFCEditBrowseCtrl` Sınıfı, isteğe bağlı olarak bir Gözat düğmesi içeren düzenlenebilir metin kutusu olan düzenleme Gözat denetimini destekler. Kullanıcı gözatma düğmesini tıkladığında denetim özel bir eylem gerçekleştirir veya dosya Gezgini veya klasör Gezgini içeren standart iletişim kutusunu görüntüler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCEditBrowseCtrl : public CEdit
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|Varsayılan Oluşturucu.|
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|Etkinleştirir ya da (gizler) devre dışı bırakır Gözat düğmesini.|
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|Gözat düğmesini etkinleştirir ve düzenleme Gözat denetimini koyar *dosya tarayıcısı* modu.|
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|Gözat düğmesini etkinleştirir ve düzenleme Gözat denetimini koyar *klasör tarayıcısı* modu.|
|[CMFCEditBrowseCtrl::GetMode](#getmode)|Geçerli gözatma modunu döndürür.|
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|Düzenleme Gözat denetimini bir Gözat eylemi sonuçları ile güncelleştirildikten sonra framework tarafından çağırılır.|
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|Kullanıcı Gözat düğmesine tıkladıktan sonra framework tarafından çağırılır.|
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|Geçerli düzenleme Gözat denetimini yeniden çizer.|
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|Göz at düğmesine çizmek için framework tarafından çağırılır.|
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|Geçersiz dosya adı düzenleme denetimine girilen framework tarafından çağırılır.|
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Pencere iletileri için dağıtılmadan önce çevirir [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows işlevleri. Söz dizimi ve daha fazla bilgi için bkz: [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).|
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|Özel bir görüntü için göz at düğmesine ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir dosya veya klasör adı seçmek için bir düzenleme Gözat denetimini kullanın. İsteğe bağlı olarak, bir iletişim kutusu gibi özel bir eylem gerçekleştirmek için denetimi kullanın. Görüntülemek veya görüntülememek Gözat düğmesini ve düğme üzerinde bir özel etiket veya görüntü uygulanabilir.

*Modu Gözat* olup bir Gözat düğmesi görüntüler ve hangi eylemin düğmesine tıklandığında gerçekleşir düzenleme Gözat denetimi belirler. Daha fazla bilgi için [GetMode](#getmode) yöntemi.

`CMFCEditBrowseCtrl` Sınıfı aşağıdaki modlarını destekler.

- **özel mod**

   Kullanıcı Gözat düğmesine tıkladığında, özel bir eylem gerçekleştirilir. Örneğin, bir uygulamaya özgü iletişim kutusunu görüntüleyebilirsiniz.

- **dosya modu**

   Kullanıcı Gözat düğmesine tıkladığında, standart dosya seçimi iletişim kutusu görüntülenir.

- **Klasör modunda**

   Kullanıcı gözatma düğmesini tıkladığında bir standart klasör seçimi iletişim kutusu görüntülenir.

## <a name="how-to-specify-an-edit-browse-control"></a>Nasıl yapılır: Bir düzenleme Gözat denetimi belirtin

Uygulamanızdaki bir düzenleme Gözat denetimini eklemek için aşağıdaki adımları gerçekleştirin:

1. Özel gözatma modu uygulamak istiyorsanız, kendi sınıfından türetilir `CMFCEditBrowseCtrl` sınıf ve geçersiz kılın [CMFCEditBrowseCtrl::OnBrowse](#onbrowse) yöntemi. Geçersiz kılınan yönteminde özel Gözat eylemi yürütmek ve düzenleme Gözat denetimini sonucu ile güncelleştirin.

1. Ya da ekleme `CMFCEditBrowseCtrl` veya üst pencere nesnesi içine türetilmiş düzenleme Gözat denetimi nesne.

1. Kullanırsanız **sınıf Sihirbazı** Oluştur iletişim kutusu için bir düzenleme denetimi ekleyin ( `CEdit`) iletişim kutusu form. Ayrıca, erişim denetimi, üstbilgi dosyasında için bir değişken ekleyin. Üst bilgi dosyanızda değişkenin türünü değiştirme `CEdit` için `CMFCEditBrowseCtrl`. Düzenleme Gözat denetimini otomatik olarak oluşturulur. Kullanmıyorsanız, **sınıf Sihirbazı**, ekleme bir `CMFCEditBrowseCtrl` üstbilgi dosyasını ve ardından bir çağrı değişkenini kendi `Create` yöntemi.

1. Bir iletişim kutusu için bir düzenleme Gözat denetimi eklerseniz, kullanın **ClassWizard** ayarlamak veri Exchange'i yedeklemek için aracı.

1. Çağrı [EnableFolderBrowseButton](#enablefolderbrowsebutton), [EnableFileBrowseButton](#enablefilebrowsebutton), veya [EnableBrowseButton](#enablebrowsebutton) gözatma modu ayarlamak ve Gözat düğmesini görüntülemek için yöntemi. Çağrı [GetMode](#getmode) geçerli gözatma modu elde etmek için yöntemi.

1. Özel bir görüntü için Gözat düğmesini sağlamak için çağrı [SetBrowseButtonImage](#setbrowsebuttonimage) yöntemi veya geçersiz kılma [OnDrawBrowseButton](#ondrawbrowsebutton) yöntemi.

1. Düzenleme Gözat denetimi Gözat düğmesini kaldırmak için çağrı [EnableBrowseButton](#enablebrowsebutton) yöntemiyle *bSistemlerde* parametresini FALSE olarak ayarlayın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek iki yöntemi kullanarak gösterilmektedir `CMFCEditBrowseCtrl` sınıfı: `EnableFolderBrowseButton` ve `EnableFileBrowseButton`. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxeditbrowsectrl.h

##  <a name="enablebrowsebutton"></a>  CMFCEditBrowseCtrl::EnableBrowseButton

Görüntüler veya göz at düğmesine geçerli düzenleme Gözat denetimini görüntülemez.

```
void EnableBrowseButton(
    BOOL bEnable=TRUE,
    LPCTSTR szLabel=_T("..."));
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
Gözat düğmesini görüntülemek için TRUE; Göz at düğmesine görüntülememek için FALSE. Varsayılan değer True'dur.

*szLabel*<br/>
Gözat düğmesini görüntülenen etiketi. Varsayılan değer " **...** ".

### <a name="remarks"></a>Açıklamalar

Varsa *bSistemlerde* parametresi TRUE, göz at düğmesine tıklandığında gerçekleştirilecek özel bir eylem uygulayın. Özel bir eylem gerçekleştirmek için öğesinden bir sınıf türetin `CMFCEditBrowseCtrl` sınıfı ve daha sonra geçersiz alt [OnBrowse](#onbrowse) yöntemi.

Varsa *bSistemlerde* parametresi TRUE, denetimin gözatma modu `BrowseMode_Default`; Aksi takdirde, gözatma modu `BrowseMode_None`. Göz atma modları hakkında daha fazla bilgi için bkz. [GetMode](#getmode) yöntemi.

##  <a name="enablefilebrowsebutton"></a>  CMFCEditBrowseCtrl::EnableFileBrowseButton

Geçerli düzenleme Gözat denetimini Gözat düğmesini görüntüler ve denetim koyar *dosya tarayıcısı* modu.

```
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,
    LPCTSTR lpszFilter=NULL,
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```

### <a name="parameters"></a>Parametreler

*lpszDefExt*<br/>
Dosya Seçimi iletişim kutusunda kullanılan varsayılan dosya adı uzantısını belirtir. Varsayılan değer NULL olur.

*lpszFilter*<br/>
Dosya Seçimi iletişim kutusunda kullanılan varsayılan filtre dizesi belirtir. Varsayılan değer NULL olur.

*CertOpenStore*<br/>
İletişim kutusu bayraklar. Bitsel bir birleşimi (veya) OFN_HIDEREADONLY ve OFN_OVERWRITEPROMPT varsayılan değerdir.

### <a name="remarks"></a>Açıklamalar

Düzenleme Gözat denetimini dosya gözatma modunda olduğunda ve kullanıcı gözatma düğmesini tıkladığında denetim standart dosya seçimi iletişim kutusunu görüntüler.

Kullanılabilir bayrakları tam bir listesi için bkz. [LPSTRFİLE yapısı](/windows/desktop/api/commdlg/ns-commdlg-tagofna).

##  <a name="enablefolderbrowsebutton"></a>  CMFCEditBrowseCtrl::EnableFolderBrowseButton

Geçerli düzenleme Gözat denetimini Gözat düğmesini görüntüler ve denetim koyar *klasör tarayıcısı* modu.

```
void EnableFolderBrowseButton();
```

### <a name="remarks"></a>Açıklamalar

Düzenleme Gözat denetimini klasör gözatma modunda olduğunda ve kullanıcı gözatma düğmesini tıkladığında denetim standart klasör seçimi iletişim kutusunu görüntüler.

##  <a name="getmode"></a>  CMFCEditBrowseCtrl::GetMode

Gözatma modu geçerli düzenleme Gözat denetimi alır.

```
CMFCEditBrowseCtrl::BrowseMode GetMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli düzenleme modu belirten numaralandırma değerlerinden biri denetim göz atın. Gözatma modu olup framework Gözat düğmesini görüntüler ve hangi eylemin bir kullanıcı bu düğmeyi tıkladığında gerçekleşir belirler.

Aşağıdaki tabloda olası dönüş değerleri listelenmektedir.

|Değer|Açıklama|
|-----------|-----------------|
|`BrowseMode_Default`|**özel mod**. Programcı tanımlı bir eylem gerçekleştirilir.|
|`BrowseMode_File`|**dosya modu**. Standart dosya tarayıcısı iletişim kutusu görüntülenir.|
|`BrowseMode_Folder`|**Klasör modunda**. Standart klasör Tarayıcı iletişim kutusu görüntülenir.|
|`BrowseMode_None`|Göz at düğmesine görüntülenmez.|

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir `CMFCEditBrowseCtrl` nesne için başlatılan `BrowseMode_None` modu. Gözatma modu ile değiştirmek [CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton), [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton), ve [CMFCEditBrowseCtrl::EnableFolderBrowseButton ](#enablefolderbrowsebutton) yöntemleri.

##  <a name="onafterupdate"></a>  CMFCEditBrowseCtrl::OnAfterUpdate

Düzenleme Gözat denetimini bir Gözat eylemi sonuçları ile güncelleştirildikten sonra framework tarafından çağırılır.

```
virtual void OnAfterUpdate();
```

### <a name="remarks"></a>Açıklamalar

Türetilen bir sınıfta bir özel eylem uygulamak için bu yöntemi yok sayın.

##  <a name="onbrowse"></a>  CMFCEditBrowseCtrl::OnBrowse

Kullanıcı düzenleme Gözat denetimini öğesinin gözatma düğmesine tıkladıktan sonra framework tarafından çağırılır.

```
virtual void OnBrowse();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı düzenleme Gözat denetimini öğesinin gözatma düğmesine tıkladığında, özel kod yürütmek için bu yöntemi kullanın. Kendi sınıfından türetilir `CMFCEditBrowseCtrl` sınıf ve geçersiz kılma kendi `OnBrowse` yöntemi. Bu yöntemde özel Gözat eylemi uygulayan ve isteğe bağlı olarak düzenleme Gözat denetimini metin kutusuna güncelleştirin. Uygulamanızda kullanmak [EnableBrowseButton](#enablebrowsebutton) düzenleme Gözat denetimini yerleştirmek için gereken yöntemini *özel tarayıcı* modu.

##  <a name="onchangelayout"></a>  CMFCEditBrowseCtrl::OnChangeLayout

Geçerli düzenleme Gözat denetimini yeniden çizer.

```
virtual void OnChangeLayout();
```

### <a name="remarks"></a>Açıklamalar

Gözatma modunu düzenleme Gözat denetimi değiştiğinde framework bu yöntemi çağırır. Daha fazla bilgi için [CMFCEditBrowseCtrl::GetMode](#getmode).

##  <a name="ondrawbrowsebutton"></a>  CMFCEditBrowseCtrl::OnDrawBrowseButton

Gözat düğmesi üzerinde düzenleme Gözat denetimi çizmek için framework tarafından çağırılır.

```
virtual void OnDrawBrowseButton(
    CDC* pDC,
    CRect rect,
    BOOL bIsButtonPressed,
    BOOL bIsButtonHot);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Bir cihaz bağlamı için bir işaretçi.

*Rect*<br/>
Göz at düğmesine sınırlayıcı dikdörtgenini.

*bIsButtonPressed*<br/>
Düğme denetimine basıldıysa TRUE; Aksi takdirde FALSE.

*bIsButtonHot*<br/>
Düğmesi vurgulanmış TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işlev Gözat düğmesini görünümünü özelleştirmek için türetilen bir sınıfta geçersiz kılar.

##  <a name="setbrowsebuttonimage"></a>  CMFCEditBrowseCtrl::SetBrowseButtonImage

Özel bir görüntü düzenleme Gözat denetimi Gözat düğmesini ayarlar.

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

*hIcon*<br/>
Simge tanıtıcı.

*Hbıtmap*<br/>
Bir bit eşlem tanıtıcısı.

*uiBmpResId*<br/>
Bir bit eşlemi kaynak kimliği.

*bAutoDestroy*<br/>
Bu yöntem çıktığında belirtilen simge ya da bit eşlem silmek için TRUE; Aksi takdirde FALSE. Varsayılan değer True'dur.

### <a name="remarks"></a>Açıklamalar

Özel bir görüntü için Gözat düğmesini uygulamak için bu yöntemi kullanın. Düzenleme Gözat denetimini olduğunda varsayılan olarak, framework standart bir görüntü alır. *dosya tarayıcısı* veya *klasör tarayıcısı* modu.

##  <a name="onillegalfilename"></a>  CMFCEditBrowseCtrl::OnIllegalFileName

Geçersiz dosya adı düzenleme denetimine girilen framework tarafından çağırılır.

```
virtual BOOL OnIllegalFileName(CString& strFileName);
```

### <a name="parameters"></a>Parametreler

*strFileName*<br/>
Geçersiz dosya adını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bu dosya adı, dosya iletişim kutusu daha fazla sınırlandıramazsınız geçirilemez değilse FALSE döndürmelidir. Bu durumda, odak yeniden düzenleme denetimine ise ve kullanıcı düzenlemeye devam etmek. Varsayılan uygulama, kullanıcı hakkında geçersiz dosya adı bildiren bir ileti kutusu görüntüler ve false değerini döndürür. Bu yöntemi yok sayın, dosya adını düzeltin ve daha ayrıntılı işleme için TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
