---
title: CColorDialog Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CColorDialog
- AFXDLGS/CColorDialog
- AFXDLGS/CColorDialog::CColorDialog
- AFXDLGS/CColorDialog::DoModal
- AFXDLGS/CColorDialog::GetColor
- AFXDLGS/CColorDialog::GetSavedCustomColors
- AFXDLGS/CColorDialog::SetCurrentColor
- AFXDLGS/CColorDialog::OnColorOK
- AFXDLGS/CColorDialog::m_cc
helpviewer_keywords:
- CColorDialog [MFC], CColorDialog
- CColorDialog [MFC], DoModal
- CColorDialog [MFC], GetColor
- CColorDialog [MFC], GetSavedCustomColors
- CColorDialog [MFC], SetCurrentColor
- CColorDialog [MFC], OnColorOK
- CColorDialog [MFC], m_cc
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
ms.openlocfilehash: ab8d934ca0c40c7073f2fc6d88549eb8db595b3f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352233"
---
# <a name="ccolordialog-class"></a>CColorDialog Sınıfı

Uygulamanıza renk seçimi iletişim kutusu dahil etmenizi sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CColorDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CColorDialog::CColorDialog](#ccolordialog)|Bir `CColorDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CColorDialog::DoModal](#domodal)|Renk iletişim kutusunu görüntüler ve kullanıcının seçim yapmasına izin verir.|
|[CColorDialog::GetColor](#getcolor)|Seçili `COLORREF` rengin değerlerini içeren bir yapı döndürür.|
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|Kullanıcı tarafından oluşturulan özel renkleri alır.|
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|Geçerli renk seçimini belirtilen renge zorlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CColorDialog::OnColorOK](#oncolorok)|İletişim kutusuna girilen rengi doğrulamak için geçersiz kılın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CColorDialog::m_cc](#m_cc)|İletişim kutusunun ayarlarını özelleştirmek için kullanılan bir yapı.|

## <a name="remarks"></a>Açıklamalar

`CColorDialog` Nesne, görüntü sistemi için tanımlanan renklerin listesini içeren bir iletişim kutusudur. Kullanıcı, iletişim kutusu çıktığında uygulamaya geri bildirilen listeden belirli bir renk seçebilir veya oluşturabilir.

Bir `CColorDialog` nesne oluşturmak için, sağlanan oluşturucuyu kullanın veya yeni bir sınıf türetin ve kendi özel oluşturucunuzu kullanın.

İletişim kutusu oluşturulduktan sonra, iletişim kutusunun denetimlerinin değerlerini açmak için [m_cc](#m_cc) yapısındaki tüm değerleri ayarlayabilir veya değiştirebilirsiniz. *m_cc* yapısı [SELECTCOLOR](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1)türüdür.

İletişim kutusunun denetimlerini aldıktan sonra, `DoModal` iletişim kutusunu görüntülemek ve kullanıcının bir renk seçmesine izin vermek için üye işlevini arayın. `DoModal`Kullanıcının iletişim kutusunun Tamam (IDOK) veya İptal (IDCANCEL) düğmesini seçmesini döndürür.

`DoModal` IDOK'u döndürürse, kullanıcı tarafından bilgi girdisini almak için `CColorDialog`'üye işlevlerden birini kullanabilirsiniz.

İletişim kutusunun başlatılması sırasında bir hata oluşup oluşmadığını belirlemek ve hata hakkında daha fazla bilgi edinmek için Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini kullanabilirsiniz.

`CColorDialog`COMMDLG'ye dayanır. DLL dosyası, Windows sürümleri 3.1 ve sonraki sürümlerle birlikte iletin.

İletişim kutusunu özelleştirmek için, bir sınıf `CColorDialog`türetin, özel bir iletişim şablonu sağlayın ve genişletilmiş denetimlerden gelen bildirim iletilerini işlemek için bir ileti eşlemi ekleyin. İşlenmemiş iletiler taban sınıfa geçirilmelidir.

Kanca işlevini özelleştirmek gerekli değildir.

> [!NOTE]
> Bazı yüklemelerde, `CColorDialog` diğer `CDialog` nesneleri gri yapmak için çerçeveyi kullandıysanız, nesne gri arka planla görüntülemez.

Kullanma `CColorDialog`hakkında daha fazla bilgi için [Ortak İletişim Sınıfları'na](../../mfc/common-dialog-classes.md) bakın

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CColorDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs.h

## <a name="ccolordialogccolordialog"></a><a name="ccolordialog"></a>CColorDialog::CColorDialog

Bir `CColorDialog` nesne inşa eder.

```
CColorDialog(
    COLORREF clrInit = 0,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*clrInit*<br/>
Varsayılan renk seçimi. Değer belirtilmemişse, varsayılan değer RGB(0,0,0) (siyah) olur.

*Dwflags*<br/>
İletişim kutusunun işlevini ve görünümünü özelleştiren bir bayrak kümesi. Daha fazla bilgi için Windows SDK'daki [SELECTCOLOR](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1) yapısına bakın.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresiiçin bir işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]

## <a name="ccolordialogdomodal"></a><a name="domodal"></a>CColorDialog::DoModal

Windows ortak renk iletişim kutusunu görüntülemek ve kullanıcının bir renk seçmesine izin vermek için bu işlevi arayın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İDOK veya IDCANCEL. IDCANCEL döndürülürse, bir hata oluşup oluşmadığını belirlemek için Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini arayın.

IDOK ve IDCANCEL, kullanıcının Ok veya İptal düğmesini seçip seçmediğini gösteren sabitlerdir.

### <a name="remarks"></a>Açıklamalar

[m_cc](#m_cc) yapısının üyelerini ayarlayarak çeşitli renk iletişim kutusu seçeneklerini başlatmayı istiyorsanız, bunu `DoModal` aramadan önce ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmalısınız.

Aradıktan `DoModal`sonra, kullanıcı tarafından iletişim kutusuna ayarları veya bilgi girişini almak için diğer üye işlevleri arayabilirsiniz.

### <a name="example"></a>Örnek

  [CColorDialog örneğine bakın:CColorDialog.](#ccolordialog)

## <a name="ccolordialoggetcolor"></a><a name="getcolor"></a>CColorDialog::GetColor

Kullanıcının seçtiği `DoModal` renk hakkındaki bilgileri almak için aradıktan sonra bu işlevi arayın.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Renk iletişim kutusunda seçilen renk için RGB bilgilerini içeren BIR [COLORREF](/windows/win32/gdi/colorref) değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]

## <a name="ccolordialoggetsavedcustomcolors"></a><a name="getsavedcustomcolors"></a>CColorDialog::GetSavedCustomColors

`CColorDialog`nesneler, renk seçimine ek olarak kullanıcının en fazla 16 özel renk tanımlamasına izin verir.

```
static COLORREF* PASCAL GetSavedCustomColors();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tarafından oluşturulan özel renkleri depolayan 16 RGB renk değeri dizisine işaretçi.

### <a name="remarks"></a>Açıklamalar

`GetSavedCustomColors` Üye işlev bu renklere erişim sağlar. Bu renkler [DoModal](#domodal) IDOK döndükten sonra alınabilir.

Döndürülen dizideki 16 RGB değerlerinin her biri RGB(255.255.255) (beyaz) olarak başolarak aparatedilir. Kullanıcı tarafından seçilen özel renkler yalnızca uygulama içindeki iletişim kutusu çağrıları arasında kaydedilir. Bu renkleri uygulama nın çağrıları arasında kaydetmek istiyorsanız, bunları başlatma (. INI) dosyası.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]

## <a name="ccolordialogm_cc"></a><a name="m_cc"></a>CColorDialog::m_cc

Üyeleri iletişim kutusunun özelliklerini ve değerlerini depolayan [SELECTCOLOR](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1)türündeki bir yapı.

```
CHOOSECOLOR m_cc;
```

### <a name="remarks"></a>Açıklamalar

Bir `CColorDialog` nesne yaptıktan sonra, [DoModal](#domodal) üye işlevini aramadan önce iletişim kutusunun çeşitli yönlerini ayarlamak için *m_cc* kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]

## <a name="ccolordialogoncolorok"></a><a name="oncolorok"></a>CColorDialog::OnColorOK

İletişim kutusuna girilen rengi doğrulamak için geçersiz kılın.

```
virtual BOOL OnColorOK();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu kapatılmazsa sıfıra inmez; aksi takdirde 0 girilen rengi kabul etmek.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca kullanıcının renk iletişim kutusunda seçtiği rengin özel doğrulanmasını sağlamak istiyorsanız geçersiz kılın.

Kullanıcı aşağıdaki iki yöntemden birine göre bir renk seçebilir:

- Renk paletinde bir renk tıklatma. Seçili rengin RGB değerleri daha sonra uygun RGB edit kutularına yansıtılır.

- RGB edit kutularına değerleri girme

Geçersiz `OnColorOK` kılma, kullanıcının uygulamaya özgü herhangi bir nedenle ortak bir renk iletişim kutusuna girdiği rengi reddetmenize olanak tanır.

Normalde, çerçeve renklerin varsayılan doğrulaması sağlar ve geçersiz bir renk girilirse bir ileti kutusu görüntüler, çünkü bu işlevi kullanmanız gerekmez.

Renk seçimini zorlamak için `OnColorOK` [SetCurrentColor'ı](#setcurrentcolor) içeriden arayabilirsiniz. Bir `OnColorOK` kez ateş lendikten sonra (diğer bir şekilde, kullanıcı renk değişikliğini kabul etmek için **Tamam'ı** tıklatıyor), yeni rengin RGB değerini almak için [GetColor'u](#getcolor) arayabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]

## <a name="ccolordialogsetcurrentcolor"></a><a name="setcurrentcolor"></a>CColorDialog::SetCurrentColor

Geçerli renk seçimini `DoModal` *clr'de*belirtilen renk değerine zorlamak için çağrıda bulunduktan sonra bu işlevi arayın.

```
void SetCurrentColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*Clr*<br/>
RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ileti işleyicisi `OnColorOK`veya . İletişim *kutusu, clr* parametresinin değerine bağlı olarak kullanıcının seçimini otomatik olarak günceller.

### <a name="example"></a>Örnek

  [CColorDialog örneğine bakın:OnColorOK](#oncolorok).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek ÇEKMECE](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
