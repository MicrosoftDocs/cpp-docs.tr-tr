---
title: CMFCEditBrowseCtrl Sınıfı
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
ms.openlocfilehash: d542af4a87b6f0a33c0344d1d3da76980f8c1a91
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752373"
---
# <a name="cmfceditbrowsectrl-class"></a>CMFCEditBrowseCtrl Sınıfı

Sınıf, `CMFCEditBrowseCtrl` isteğe bağlı olarak bir gözatma düğmesi içeren editable metin kutusu olan edited gözleme denetimini destekler. Kullanıcı gözatma düğmesini tıklattığında, denetim özel bir eylem gerçekleştirir veya dosya tarayıcısı veya klasör tarayıcısı içeren standart bir iletişim kutusu görüntüler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCEditBrowseCtrl : public CEdit
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|Varsayılan oluşturucu.|
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCEditBrowseCtrl::Etkinleştirme Düğmesi](#enablebrowsebutton)|Gözatma düğmesini etkinleştirer veya devre dışı eder (gizler).|
|[CMFCEditBrowseCtrl::EtkinleştirFileBrowseButton](#enablefilebrowsebutton)|Gözatma düğmesini etkinleştiriyor ve gözatma denetimini *dosyaya göz atma* moduna koyar.|
|[CMFCEditBrowseCtrl::EtkinleştirmeFolderBrowseButton](#enablefolderbrowsebutton)|Gözatma düğmesini etkinleştiriyor ve denetim denetimini *klasöre göz atma* moduna yerlebir ediyor.|
|[CMFCEditBrowseCtrl::GetMode](#getmode)|Geçerli gözatma modunu döndürür.|
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|Düzenleme gözatma denetimi bir gözatma eylemi sonucu ile güncelleştirildikten sonra çerçeve tarafından çağrılır.|
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|Kullanıcı gözatma düğmesini tıklattıktan sonra çerçeve tarafından çağrılır.|
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|Geçerli edit gözatma denetimini yeniden çizer.|
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|Gözatma düğmesini çizmek için çerçeve tarafından çağrılır.|
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|Düzenleme denetimine yasadışı bir dosya adı girildiğinde çerçeve tarafından çağrılır.|
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Pencere iletilerini [Çeviri İletisi](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine gönderilmeden önce çevirir. Sözdizimi ve daha fazla bilgi için [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)' a bakın.|
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|Gözatma düğmesi için özel bir görüntü ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir dosya veya klasör adı seçmek için bir göz atma denetimi kullanın. İsteğe bağlı olarak, iletişim kutusunu görüntülemek gibi özel bir eylem gerçekleştirmek için denetimi kullanın. Gözatma düğmesini görüntüleyebilir veya görüntülemeyin ve düğmeye özel bir etiket veya resim uygulayabilirsiniz.

Gözatma denetiminin *gözatma modu,* gözatma düğmesini gösterip görüntülemediğini ve düğme tıklatıldığında hangi eylemin gerçekleşip gerçekleşmeyeceğini belirler. Daha fazla bilgi için [GetMode](#getmode) yöntemine bakın.

Sınıf `CMFCEditBrowseCtrl` aşağıdaki modları destekler.

- **özel mod**

   Kullanıcı gözatma düğmesini tıklattığında özel bir eylem gerçekleştirilir. Örneğin, uygulamaya özgü bir iletişim kutusu görüntüleyebilirsiniz.

- **dosya modu**

   Kullanıcı gözatma düğmesini tıklattığında standart bir dosya seçimi iletişim kutusu görüntülenir.

- **klasör modu**

   Kullanıcı gözatma düğmesini tıklattığında standart klasör seçimi iletişim kutusu görüntülenir.

## <a name="how-to-specify-an-edit-browse-control"></a>Nasıl Yapılılır: Gözat Denetimi Edin

Uygulamanızda bir edit gözatma denetimi dahil etmek için aşağıdaki adımları gerçekleştirin:

1. Özel bir tarama modu uygulamak istiyorsanız, `CMFCEditBrowseCtrl` sınıftan kendi sınıfınızı türetin ve [cmfcEditBrowseCtrl::OnBrowse](#onbrowse) yöntemini geçersiz kılın. Geçersiz kılınan yöntemde, özel bir gözatma eylemi gerçekleştirin ve sonuçla birlikte gözatma denetimini güncelleştirin.

1. Nesneyi veya `CMFCEditBrowseCtrl` türetilmiş edit denetim nesnesini ana pencere nesnesine gömün.

1. İletişim kutusu oluşturmak için **Sınıf Sihirbazı'nı** kullanıyorsanız, `CEdit`iletişim kutusu formuna bir denetim () ekleyin. Ayrıca, üstbilgi dosyanızdaki denetime erişmek için bir değişken ekleyin. Üstbilgi dosyanızda, değişkenin türünü ' `CEdit` `CMFCEditBrowseCtrl`den ' e değiştirin Gözatma denetimi otomatik olarak oluşturulur. **Sınıf Sihirbazı'nı**kullanmıyorsanız, `CMFCEditBrowseCtrl` üstbilgi dosyanıza bir değişken `Create` ekleyin ve yöntemini arayın.

1. Bir iletişim kutusuna bir düzenleme gözatma denetimi eklerseniz, veri alışverişi ayarlamak için **ClassWizard** aracını kullanın.

1. Gözatma modunu ayarlamak ve gözatma düğmesini görüntülemek için [EnableFolderBrowseButton,](#enablefolderbrowsebutton) [EnableFileBrowseButton](#enablefilebrowsebutton)veya [EnableBrowseButton](#enablebrowsebutton) yöntemini arayın. Geçerli gözatma modunu elde etmek için [GetMode](#getmode) yöntemini arayın.

1. Gözatma düğmesi için özel bir görüntü sağlamak için [SetBrowseButtonImage](#setbrowsebuttonimage) yöntemini arayın veya [OnDrawBrowseButton](#ondrawbrowsebutton) yöntemini geçersiz kılın.

1. Gözatma düğmesini edit denetiminden kaldırmak için, *bEnable* parametre sini FALSE olarak ayarlı olarak [EnableBrowseButton](#enablebrowsebutton) yöntemini arayın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cedit](../../mfc/reference/cedit-class.md)

[Cmfceditbrowsectrl](../../mfc/reference/cmfceditbrowsectrl-class.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta iki yöntemin `CMFCEditBrowseCtrl` nasıl `EnableFolderBrowseButton` kullanılacağını gösterir: ve. `EnableFileBrowseButton` Bu örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxeditbrowsectrl.h

## <a name="cmfceditbrowsectrlenablebrowsebutton"></a><a name="enablebrowsebutton"></a>CMFCEditBrowseCtrl::Etkinleştirme Düğmesi

Geçerli edit gözatma denetiminde gözatma düğmesini görüntüler veya görüntülemez.

```cpp
void EnableBrowseButton(
    BOOL bEnable=TRUE,
    LPCTSTR szLabel=_T("..."));
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
Gözatma düğmesini görüntülemek için TRUE; Gözatma düğmesini görüntülemek için YANLIŞ değil. Varsayılan değer TRUE'dur.

*szEtiket*<br/>
Gözatma düğmesinde görüntülenen etiket. Varsayılan değer " **...**".

### <a name="remarks"></a>Açıklamalar

*bEtkinleştir* parametresi TRUE ise, gözatma düğmesi tıklandığında gerçekleştirmek için özel bir eylem uygulayın. Özel bir eylem uygulamak için sınıftan `CMFCEditBrowseCtrl` bir sınıf türetin ve [ardından OnBrowse](#onbrowse) yöntemini geçersiz kılın.

*bEnable* parametresi TRUE ise, denetimin gözatma `BrowseMode_Default`modu; aksi takdirde, gözatma `BrowseMode_None`modu . Gözatma modları hakkında daha fazla bilgi için [GetMode](#getmode) yöntemine bakın.

## <a name="cmfceditbrowsectrlenablefilebrowsebutton"></a><a name="enablefilebrowsebutton"></a>CMFCEditBrowseCtrl::EtkinleştirFileBrowseButton

Geçerli edit gözatma denetiminde gözatma düğmesini görüntüler ve denetimi *dosyaya göz atma* moduna sokar.

```cpp
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,
    LPCTSTR lpszFilter=NULL,
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```

### <a name="parameters"></a>Parametreler

*lpszDefExt*<br/>
Dosya seçimi iletişim kutusunda kullanılan varsayılan dosya adı uzantısını belirtir. Varsayılan değer NULL'dur.

*lpszFiltre*<br/>
Dosya seçimi iletişim kutusunda kullanılan varsayılan filtre dizesini belirtir. Varsayılan değer NULL'dur.

*Dwflags*<br/>
İletişim kutusu bayrakları. Varsayılan değer, OFN_HIDEREADONLY ve OFN_OVERWRITEPROMPT bitwise birleşimidir.

### <a name="remarks"></a>Açıklamalar

Gözatma denetimi dosya yaslanın modunda olduğunda ve kullanıcı gözatma düğmesini tıklattığında, denetim standart dosya seçimi iletişim kutusunu görüntüler.

Kullanılabilir bayrakların tam listesi için [OPENFILENAME yapısına](/windows/win32/api/commdlg/ns-commdlg-openfilenamew)bakın.

## <a name="cmfceditbrowsectrlenablefolderbrowsebutton"></a><a name="enablefolderbrowsebutton"></a>CMFCEditBrowseCtrl::EtkinleştirmeFolderBrowseButton

Geçerli edit gözatma denetiminde gözatma düğmesini görüntüler ve denetimi *klasöre göz atma* moduna sokar.

```cpp
void EnableFolderBrowseButton();
```

### <a name="remarks"></a>Açıklamalar

Edit gözatma denetimi klasöre göz atma modunda olduğunda ve kullanıcı gözatma düğmesini tıklattığında, denetim standart klasör seçimi iletişim kutusunu görüntüler.

## <a name="cmfceditbrowsectrlgetmode"></a><a name="getmode"></a>CMFCEditBrowseCtrl::GetMode

Geçerli edit gözatma denetiminin gözatma modunu alır.

```
CMFCEditBrowseCtrl::BrowseMode GetMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme, göz atma denetiminin geçerli modunu belirten numaralandırma değerlerinden biridir. Gözatma modu, çerçevenin gözatma düğmesini gösterip görüntülemediğini ve kullanıcı bu düğmeyi tıklattığında hangi eylemin gerçekleşip gerçekleşmeyeceğini belirler.

Aşağıdaki tabloda olası iade değerleri listelenilmektedir.

|Değer|Açıklama|
|-----------|-----------------|
|`BrowseMode_Default`|**özel mod.** Programcı tanımlı bir eylem gerçekleştirilir.|
|`BrowseMode_File`|**dosya modu**. Standart dosya tarayıcı iletişim kutusu görüntülenir.|
|`BrowseMode_Folder`|**klasör modu**. Standart klasör tarayıcı iletişim kutusu görüntülenir.|
|`BrowseMode_None`|Gözatma düğmesi görüntülenmez.|

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CMFCEditBrowseCtrl` bir nesne `BrowseMode_None` moda başharfle çevrilir. [CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton), [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)ve [CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton) yöntemleri ile göz atma modunu değiştirin.

## <a name="cmfceditbrowsectrlonafterupdate"></a><a name="onafterupdate"></a>CMFCEditBrowseCtrl::OnAfterUpdate

Düzenleme gözatma denetimi bir gözatma eylemi sonucu ile güncelleştirildikten sonra çerçeve tarafından çağrılır.

```
virtual void OnAfterUpdate();
```

### <a name="remarks"></a>Açıklamalar

Özel bir eylem uygulamak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfceditbrowsectrlonbrowse"></a><a name="onbrowse"></a>CMFCEditBrowseCtrl::OnBrowse

Kullanıcı düzenleme denetiminin gözat düğmesini tıklattıktan sonra çerçeve tarafından çağrılır.

```
virtual void OnBrowse();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı edit gözatma denetiminin gözatma düğmesini tıklattığında özel kodu çalıştırmak için bu yöntemi kullanın. `CMFCEditBrowseCtrl` Sınıftan kendi sınıfınızı türetin `OnBrowse` ve yöntemini geçersiz kılın. Bu yöntemde, özel bir gözatma eylemi uygulayın ve denetim denetiminin metin kutusunu isteğe bağlı olarak güncelleştirin. Uygulamanızda, edit gözatma denetimini *özel gözatma* moduna koymak için [EtkinleştireGöz Düğmesini](#enablebrowsebutton) yöntemini kullanın.

## <a name="cmfceditbrowsectrlonchangelayout"></a><a name="onchangelayout"></a>CMFCEditBrowseCtrl::OnChangeLayout

Geçerli edit gözatma denetimini yeniden çizer.

```
virtual void OnChangeLayout();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, edit denetiminin gözatma modu değiştiğinde bu yöntemi çağırır. Daha fazla bilgi için [CMFCEditBrowseCtrl::GetMode'](#getmode)a bakın.

## <a name="cmfceditbrowsectrlondrawbrowsebutton"></a><a name="ondrawbrowsebutton"></a>CMFCEditBrowseCtrl::OnDrawBrowseButton

Düzenleme denetimindeki gözat düğmesini çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDrawBrowseButton(
    CDC* pDC,
    CRect rect,
    BOOL bIsButtonPressed,
    BOOL bIsButtonHot);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Aygıt bağlamına işaretçi.

*Rect*<br/>
Gözatma düğmesinin sınırlayıcı dikdörtgeni.

*bIsButtonPressed*<br/>
Düğmeye basıldığında DOĞRU; aksi takdirde, YANLIŞ.

*bIsButtonHot*<br/>
Düğme vurgulanırsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Gözatma düğmesinin görünümünü özelleştirmek için türetilmiş bir sınıfta bu işlevi geçersiz kılın.

## <a name="cmfceditbrowsectrlsetbrowsebuttonimage"></a><a name="setbrowsebuttonimage"></a>CMFCEditBrowseCtrl::SetBrowseButtonImage

Edit gözat denetiminin gözat düğmesine özel bir resim ayarlar.

```cpp
void SetBrowseButtonImage(
    HICON hIcon,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(UINT uiBmpResId);
```

### <a name="parameters"></a>Parametreler

*Hıcon*<br/>
Bir simgenin tutamacı.

*Hbıtmap*<br/>
Bitmap'in sapı.

*uiBmpResId*<br/>
Bitmap'in kaynak kimliği.

*bAutoDestroy*<br/>
Bu yöntem çıktığında belirtilen simgeyi veya bit eşlemi silmek için TRUE; aksi takdirde, YANLIŞ. Varsayılan değer TRUE'dur.

### <a name="remarks"></a>Açıklamalar

Gözatma düğmesine özel bir resim uygulamak için bu yöntemi kullanın. Varsayılan olarak, düzenleme gözatma denetimi dosya ya da klasör *eki* *folder browse* gezinme modunda olduğunda çerçeve standart bir görüntü elde eder.

## <a name="cmfceditbrowsectrlonillegalfilename"></a><a name="onillegalfilename"></a>CMFCEditBrowseCtrl::OnIllegalFileName

Düzenleme denetimine yasadışı bir dosya adı girildiğinde çerçeve tarafından çağrılır.

```
virtual BOOL OnIllegalFileName(CString& strFileName);
```

### <a name="parameters"></a>Parametreler

*strFileName*<br/>
Geçersiz dosya adını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bu dosya adı dosya iletişim kutusuna daha fazla geçirilemez ise FALSE döndürmelidir. Bu durumda, odak düzenleme denetimine geri ayarlanır ve kullanıcı düzenlemeye devam etmelidir. Varsayılan uygulama, kullanıcıya yasa dışı dosya adını bildiren bir ileti kutusu görüntüler ve FALSE döndürür. Bu yöntemi geçersiz kılabilir, dosya adını düzeltebilir ve daha fazla işlem için TRUE döndürebilirsiniz.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
