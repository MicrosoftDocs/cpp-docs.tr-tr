---
title: CMFCEditBrowseCtrl sınıfı
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
ms.openlocfilehash: db99c5e72e84bb359184f4c62594fcddff7d8ff6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505347"
---
# <a name="cmfceditbrowsectrl-class"></a>CMFCEditBrowseCtrl sınıfı

`CMFCEditBrowseCtrl` Sınıfı, isteğe bağlı olarak bir tarama düğmesi içeren düzenlenebilir bir metin kutusu olan düzenleme gözden geçirme denetimini destekler. Kullanıcı, gözatma düğmesine tıkladığında, Denetim özel bir eylem gerçekleştirir veya bir dosya tarayıcısı ya da klasör tarayıcısı içeren standart bir iletişim kutusu görüntüler.

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
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|, Gözden geçirme düğmesini etkinleştirilir veya devre dışı bırakır (gizler).|
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|Gözden geçirme düğmesine izin verir ve düzenleme gözden geçirme denetimini *dosya tarama* moduna geçirir.|
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|Gözden geçirme düğmesine izin verir ve düzenleme gözden geçirme denetimini *klasör tarama* moduna geçirir.|
|[CMFCEditBrowseCtrl:: GetMode](#getmode)|Geçerli tarama modunu döndürür.|
|[CMFCEditBrowseCtrl:: OnAfterUpdate](#onafterupdate)|Düzenleme gözden geçirme denetiminden sonra, bir tarama eylemi sonucuyla birlikte bu çerçeve tarafından çağırılır.|
|[CMFCEditBrowseCtrl:: Onzat](#onbrowse)|Kullanıcı, gezinme düğmesine tıkladıktan sonra Framework tarafından çağırılır.|
|[CMFCEditBrowseCtrl:: OnChangeLayout](#onchangelayout)|Geçerli düzenleme tarama denetimini yeniden çizer.|
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|, Gezinme düğmesini çizmek için Framework tarafından çağırılır.|
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|Düzenleme denetimine geçersiz bir dosya adı girildiğinde Framework tarafından çağırılır.|
|`CMFCEditBrowseCtrl::PreTranslateMessage`|[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine dağıtılmadan önce pencere iletilerini çevirir. Sözdizimi ve daha fazla bilgi için bkz. [CWnd::P reTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).|
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|Tarama düğmesi için özel bir görüntü ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir dosya veya klasör adı seçmek için bir düzenleme tarayıcı denetimi kullanın. İsteğe bağlı olarak, bir iletişim kutusu görüntüleme gibi özel bir eylem gerçekleştirmek için denetimi kullanın. Görüntüle düğmesini gösterebilir veya görüntüleyemezsiniz, düğme üzerinde özel bir etiket veya resim uygulayabilirsiniz.

Düzenleme gözden geçirme denetiminin gözatmasına ilişkin tarama *modu* , düğme tıklandığında bir gözatın ve bir eylemin ne olduğunu belirler. Daha fazla bilgi için bkz. [GetMode](#getmode) yöntemi.

`CMFCEditBrowseCtrl` Sınıfı aşağıdaki modları destekler.

- **özel mod**

   Kullanıcı, tarayıcı düğmesine tıkladığında bir özel eylem gerçekleştirilir. Örneğin, uygulamaya özgü bir iletişim kutusu görüntüleyebilirsiniz.

- **dosya modu**

   Kullanıcı, gözden geçirme düğmesine tıkladığında standart bir dosya seçimi iletişim kutusu görüntülenir.

- **klasör modu**

   Kullanıcı, gözden geçirme düğmesine tıkladığında bir standart klasör seçimi iletişim kutusu görüntülenir.

## <a name="how-to-specify-an-edit-browse-control"></a>Nasıl yapılır: Bir düzenleme tarama denetimi belirtin

Uygulamanızda bir düzenleme tarama denetimi eklemek için aşağıdaki adımları gerçekleştirin:

1. Özel bir tarama modu uygulamak istiyorsanız, `CMFCEditBrowseCtrl` sınıfından kendi sınıfınızı türetirsiniz ve ardından [CMFCEditBrowseCtrl:: ongözatıt](#onbrowse) metodunu geçersiz kılın. Geçersiz kılınan yöntemde, özel bir gözden geçirme eylemi yürütün ve sonuçla düzenleme gözden geçirme denetimini güncelleştirin.

1. Üst pencere nesnesine nesne veya türetilmiş düzenleme Gözat denetim nesnesini ekleyin. `CMFCEditBrowseCtrl`

1. Bir iletişim kutusu oluşturmak için **sınıf sihirbazını** kullanırsanız, iletişim kutusu formuna bir düzenleme denetimi ( `CEdit`) ekleyin. Ayrıca, üst bilgi dosyanızdaki denetime erişmek için bir değişken ekleyin. Üst bilgi dosyanızda değişkeninin `CEdit` türünü olarak `CMFCEditBrowseCtrl`değiştirin. Düzenleme gözden geçirme denetimi otomatik olarak oluşturulur. **Sınıf Sihirbazı**'nı kullanmıyorsanız, üst bilgi dosyanıza bir `CMFCEditBrowseCtrl` değişken ekleyin `Create` ve sonra metodunu çağırın.

1. Bir iletişim kutusuna bir düzenleme Gözat denetimi eklerseniz, veri değişimini ayarlamak için **ClassWizard** aracını kullanın.

1. [EnableFolderBrowseButton](#enablefolderbrowsebutton), [EnableFileBrowseButton](#enablefilebrowsebutton)veya [EnableBrowseButton](#enablebrowsebutton) metodunu çağırıp, tarama modunu ayarlayın ve tarayıcı düğmesini görüntüleyin. Geçerli tarama modunu almak için [GetMode](#getmode) metodunu çağırın.

1. Tarayıcı düğmesine özel bir görüntü sağlamak için, [SetBrowseButtonImage](#setbrowsebuttonimage) yöntemini çağırın veya [OnDrawBrowseButton](#ondrawbrowsebutton) metodunu geçersiz kılın.

1. Düzenle gözden geçirme denetiminden Kaldır düğmesini kaldırmak için, [EnableBrowseButton](#enablebrowsebutton) yöntemini *BENABLE* parametresi false olarak ayarlanmış şekilde çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCEditBrowseCtrl` sınıfında iki yöntemin nasıl kullanılacağını gösterir: `EnableFolderBrowseButton` ve `EnableFileBrowseButton`. Bu örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxeditbrowsectrl. h

##  <a name="enablebrowsebutton"></a>CMFCEditBrowseCtrl::EnableBrowseButton

Geçerli düzenleme gözden geçirme denetimindeki gözden geçirme düğmesini görüntüler veya görüntülemez.

```
void EnableBrowseButton(
    BOOL bEnable=TRUE,
    LPCTSTR szLabel=_T("..."));
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
Tarama düğmesini göstermek için TRUE; Tarama düğmesinin görüntülenmesi yanlış. Varsayılan değer TRUE 'dur.

*szLabel*<br/>
Tarayıcı düğmesinde görüntülenen etiket. Varsayılan değer " **...** " değeridir.

### <a name="remarks"></a>Açıklamalar

*BEnable* parametresi true ise, gözden geçirme düğmesine tıklandığında gerçekleştirilecek özel bir eylem uygulayın. Özel bir eylem uygulamak için `CMFCEditBrowseCtrl` sınıfından bir sınıf türetirsiniz ve sonra [ongözatıt](#onbrowse) yöntemini geçersiz kılın.

*BEnable* parametresi true ise, denetimin tarama modu olur `BrowseMode_Default`; Aksi takdirde, tarama modu olur. `BrowseMode_None` Tarama modları hakkında daha fazla bilgi için bkz. [GetMode](#getmode) yöntemi.

##  <a name="enablefilebrowsebutton"></a>CMFCEditBrowseCtrl::EnableFileBrowseButton

Geçerli düzenleme gözden geçirme denetimindeki gözden geçirme düğmesini görüntüler ve denetimi *dosya tarama* moduna geçirir.

```
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,
    LPCTSTR lpszFilter=NULL,
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```

### <a name="parameters"></a>Parametreler

*lpszDefExt*<br/>
Dosya seçimi iletişim kutusunda kullanılan varsayılan dosya adı uzantısını belirtir. Varsayılan değer NULL.

*lpszFilter*<br/>
Dosya seçimi iletişim kutusunda kullanılan varsayılan filtre dizesini belirtir. Varsayılan değer NULL.

*dwFlags*<br/>
İletişim kutusu bayrakları. Varsayılan değer, OFN_HIDEREADONLY ve OFN_OVERWRITEPROMPT bit düzeyinde birleşimidir (veya).

### <a name="remarks"></a>Açıklamalar

Düzenle gözden geçirme denetimi dosya tarama modunda olduğunda ve Kullanıcı, gözden geçirme düğmesine tıkladığında, denetim standart dosya seçimi iletişim kutusunu görüntüler.

Kullanılabilir bayrakların tam listesi için bkz. [OpenFileName yapısı](/windows/win32/api/commdlg/ns-commdlg-openfilenamew).

##  <a name="enablefolderbrowsebutton"></a>CMFCEditBrowseCtrl::EnableFolderBrowseButton

Geçerli düzenleme gözden geçirme denetimindeki gözden geçirme düğmesini görüntüler ve denetimi *klasör tarama* moduna geçirir.

```
void EnableFolderBrowseButton();
```

### <a name="remarks"></a>Açıklamalar

Edit gözatmaya yönelik denetim, klasör tarama modunda olduğunda ve Kullanıcı, gözden geçirme düğmesine tıkladığında, denetim standart klasör seçimi iletişim kutusunu görüntüler.

##  <a name="getmode"></a>CMFCEditBrowseCtrl:: GetMode

Geçerli düzenleme tarama denetiminin tarama modunu alır.

```
CMFCEditBrowseCtrl::BrowseMode GetMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düzenleme tarama denetiminin geçerli modunu belirten sabit listesi değerlerinden biri. Tarama modu, Framework 'ün, bir Kullanıcı bu düğmeye tıkladığında ne olduğunu ve bu düğmeyi tıkladığını gösterir.

Aşağıdaki tabloda olası dönüş değerleri listelenmektedir.

|Değer|Açıklama|
|-----------|-----------------|
|`BrowseMode_Default`|**özel mod**. Programcı tanımlı bir eylem gerçekleştirilir.|
|`BrowseMode_File`|**dosya modu**. Standart dosya tarayıcısı iletişim kutusu görüntülenir.|
|`BrowseMode_Folder`|**klasör modu**. Standart klasör tarayıcısı iletişim kutusu görüntülenir.|
|`BrowseMode_None`|Tarayıcı düğmesi görüntülenmez.|

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir `CMFCEditBrowseCtrl` nesne `BrowseMode_None` moduna başlatılır. [CMFCEditBrowseCtrl:: EnableBrowseButton](#enablebrowsebutton), [CMFCEditBrowseCtrl:: EnableFileBrowseButton](#enablefilebrowsebutton)ve [CMFCEditBrowseCtrl:: EnableFolderBrowseButton](#enablefolderbrowsebutton) yöntemleriyle, tarama modunu değiştirin.

##  <a name="onafterupdate"></a>CMFCEditBrowseCtrl:: OnAfterUpdate

Düzenleme gözden geçirme denetiminden sonra, bir tarama eylemi sonucuyla birlikte bu çerçeve tarafından çağırılır.

```
virtual void OnAfterUpdate();
```

### <a name="remarks"></a>Açıklamalar

Özel bir eylem uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

##  <a name="onbrowse"></a>CMFCEditBrowseCtrl:: Onzat

Kullanıcı düzenleme gözden geçirme denetiminin tarayıcı düğmesine tıkladıktan sonra Framework tarafından çağırılır.

```
virtual void OnBrowse();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı düzenleme gözden geçirme denetiminin tarayıcı düğmesine tıkladığında özel kodu yürütmek için bu yöntemi kullanın. `CMFCEditBrowseCtrl` Sınıfından kendi sınıfınızı türetirsiniz ve `OnBrowse` metodunu geçersiz kılın. Bu yöntemde, özel bir gözden geçirme eylemi uygulayın ve isteğe bağlı olarak düzenleme tarama denetiminin metin kutusunu güncelleştirin. Uygulamanızda, düzenleme gözden geçirme denetimini *özel tarama* modunda yerleştirmek için [EnableBrowseButton](#enablebrowsebutton) yöntemini kullanın.

##  <a name="onchangelayout"></a>CMFCEditBrowseCtrl:: OnChangeLayout

Geçerli düzenleme tarama denetimini yeniden çizer.

```
virtual void OnChangeLayout();
```

### <a name="remarks"></a>Açıklamalar

Düzenleme gözden geçirme denetim denetiminin tarama modu değiştiğinde Framework bu yöntemi çağırır. Daha fazla bilgi için bkz. [CMFCEditBrowseCtrl:: GetMode](#getmode).

##  <a name="ondrawbrowsebutton"></a>CMFCEditBrowseCtrl::OnDrawBrowseButton

Düzenleme gözden geçirme denetimine Gözat düğmesi çizmek için Framework tarafından çağırılır.

```
virtual void OnDrawBrowseButton(
    CDC* pDC,
    CRect rect,
    BOOL bIsButtonPressed,
    BOOL bIsButtonHot);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
Tarama düğmesinin sınırlayıcı dikdörtgeni.

*Bisbuttonbasıldı*<br/>
Düğmeye basıldığında doğru; Aksi takdirde, FALSE.

*bIsButtonHot*<br/>
Düğme vurgulanmışsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işlevi, gezinme düğmesinin görünümünü özelleştirmek için türetilmiş bir sınıfta geçersiz kılın.

##  <a name="setbrowsebuttonimage"></a>CMFCEditBrowseCtrl::SetBrowseButtonImage

Düzenleme tarama denetiminin gözatmasına özel bir görüntü ayarlar.

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

*HICON*<br/>
Bir simgenin tutamacı.

*HBITMAP*<br/>
Bit eşlemin tutamacı.

*Uıımpresd*<br/>
Bit eşlemin kaynak KIMLIĞI.

*bAutoDestroy*<br/>
Bu yöntem çıktığında belirtilen simgeyi veya bit eşlemi silmek için TRUE; Aksi takdirde, FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, gözden geçirme düğmesine özel bir görüntü uygulamak için kullanın. Varsayılan olarak, düzenleme gözden geçirme denetimi *Dosya gözatmayı* veya *klasör tarama* modunda olduğunda çerçeve standart bir görüntü alır.

##  <a name="onillegalfilename"></a>CMFCEditBrowseCtrl::OnIllegalFileName

Düzenleme denetimine geçersiz bir dosya adı girildiğinde Framework tarafından çağırılır.

```
virtual BOOL OnIllegalFileName(CString& strFileName);
```

### <a name="parameters"></a>Parametreler

*strFileName*<br/>
Geçersiz dosya adını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bu dosya adı dosya iletişim kutusuna geçirilmemişse, FALSE döndürmelidir. Bu durumda, odak düzenleme denetimine geri ayarlanır ve Kullanıcı düzenlemeye devam etmelidir. Varsayılan uygulama, kullanıcıya geçersiz dosya adı hakkında söylediğini belirten bir ileti kutusu görüntüler ve FALSE döndürür. Bu yöntemi geçersiz kılabilir, dosya adını düzeltebilir ve daha fazla işleme için TRUE değerini döndürebilirsiniz.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
