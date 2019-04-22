---
title: CColorDialog sınıfı
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
ms.openlocfilehash: bc9bc76b328359d4c8ec7796de7dfaa7d3a9cf2c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772845"
---
# <a name="ccolordialog-class"></a>CColorDialog sınıfı

Bir renk seçimi iletişim kutusunu uygulamanıza eklemenize olanak sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CColorDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CColorDialog::CColorDialog](#ccolordialog)|Oluşturur bir `CColorDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CColorDialog::DoModal](#domodal)|Renk iletişim kutusu görüntüler ve kullanıcının seçim yapmanıza izin verir.|
|[CColorDialog::GetColor](#getcolor)|Döndürür bir `COLORREF` seçili renk değerleri içeren yapısı.|
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|Kullanıcı tarafından oluşturulan özel renkler alır.|
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|Belirtilen renk geçerli renk seçimi zorlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CColorDialog::OnColorOK](#oncolorok)|İletişim kutusuna girilen rengi doğrulamak için geçersiz kılın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CColorDialog::m_cc](#m_cc)|İletişim kutusunun ayarlarını özelleştirmek için kullanılan bir yapının.|

## <a name="remarks"></a>Açıklamalar

A `CColorDialog` nesnedir görüntü sistemi için tanımlanan renk listesini içeren bir iletişim kutusu. Kullanıcı seçin veya belirli bir renk iletişim kutusu çıktığında, ardından uygulamaya geri bildirilir listeden oluşturun.

Oluşturmak için bir `CColorDialog` nesne, sağlanan bir oluşturucu kullanın veya yeni bir sınıf türetin ve kendi özel Oluşturucu kullanın.

İletişim kutusu oluşturulmuş bir kez ayarlayabilir veya herhangi bir değer değiştirme [m_cc](#m_cc) Yapısı iletişim kutusunun denetimleri değerlerini başlatılamadı. *M_cc* yapısıdır türünü [CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora).

İletişim kutusunun denetimleri başlatılıyor sonra çağrı `DoModal` iletişim kutusunu görüntülemek ve bir rengi seçmesini sağlamak için üye işlevi. `DoModal` kullanıcının seçiminin ya da iletişim kutusunun Tamam (IDOK) veya iptal edin (IDCANCEL) düğmesinin döndürür.

Varsa `DoModal` IDOK, döndürür birini kullanabilirsiniz `CColorDialog`ait üye işlevleri tarafından kullanıcı giriş bilgileri alınamıyor.

Windows kullanabileceğiniz [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) işlevi bir hata iletişim kutusunun başlatma sırasında oluşup oluşmadığını belirleyin ve hata hakkında daha fazla bilgi edinin.

`CColorDialog` üzerinde COMMDLG kullanır. Windows 3.1 ve sonraki sürümleri ile birlikte gelen DLL dosyası.

Özelleştir iletişim kutusu için öğesinden bir sınıf türetin `CColorDialog`, bir özel iletişim şablonu sağlar ve genişletilmiş denetimlerden bildirim iletilerini işlemek için ileti eşlemesi ekleyin. İşlenmemiş tüm iletiler için temel sınıf geçirilmelidir.

Kanca işlevini özelleştirme gerekli değildir.

> [!NOTE]
>  Bazı yüklemeler üzerinde `CColorDialog` nesnesi diğer yapmak için framework kullandıysanız, gri renkli bir arka plan ile görüntülemez `CDialog` nesneleri gri.

Kullanma hakkında daha fazla bilgi için `CColorDialog`, bkz: [ortak iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CColorDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdlgs.h

##  <a name="ccolordialog"></a>  CColorDialog::CColorDialog

Oluşturur bir `CColorDialog` nesne.

```
CColorDialog(
    COLORREF clrInit = 0,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*clrInit*<br/>
Varsayılan renk seçimi. Değer belirtilmezse, varsayılan RGB(0,0,0) (siyah) olur.

*CertOpenStore*<br/>
İşlevi ve iletişim kutusunu görünümünü özelleştirme bayrak kümesi. Daha fazla bilgi için [CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora) Windows SDK'sındaki yapısı.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresine bir işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]

##  <a name="domodal"></a>  CColorDialog::DoModal

Windows ortak renk iletişim kutusu görüntülemek ve bir rengi seçmesini sağlamak için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

IDOK veya IDCANCEL. IDCANCEL döndürülürse, Windows Arama [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) hata oluşup oluşmadığını belirlemek için işlevi.

IDOK ve IDCANCEL kullanıcı Tamam'ı veya iptal düğmesi seçili olup olmadığını gösteren sabittir.

### <a name="remarks"></a>Açıklamalar

Üyeleri ayarlayarak çeşitli renk iletişim kutusu seçenekleri başlatmak istiyorsanız [m_cc](#m_cc) yapısını çağırmadan önce yapmalısınız `DoModal` ancak sonra iletişim kutusu nesnesi oluşturulur.

Arama sonra `DoModal`, diğer üye işlevleri, kullanıcı giriş bilgileri ve Ayarları iletişim kutusuna alınacak çağırabilirsiniz.

### <a name="example"></a>Örnek

  Örneğin bakın [CColorDialog::CColorDialog](#ccolordialog).

##  <a name="getcolor"></a>  CColorDialog::GetColor

Çağırdıktan sonra bu işlevi çağırın `DoModal` renk seçili kullanıcı hakkında bilgi almak için.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

A [COLORREF](/windows/desktop/gdi/colorref) renk iletişim kutusunda seçilen renk RGB bilgilerini içeren bir değer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]

##  <a name="getsavedcustomcolors"></a>  CColorDialog::GetSavedCustomColors

`CColorDialog` nesneleri, en fazla 16 özel renkler tanımlamasına olanak renk seçme ek olarak kullanıcı izin verir.

```
static COLORREF* PASCAL GetSavedCustomColors();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tarafından oluşturulan özel renkler depolayan 16 RGB renk değerleri dizisi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`GetSavedCustomColors` Üye işlevi bu renklerin erişim sağlar. Bu renklerin sonra alınabilir [DoModal](#domodal) IDOK döndürür.

Döndürülen dizideki 16 RGB değerleri RGB(255,255,255) (beyaz) başlatılır. Kullanıcı tarafından seçilen özel renkler, yalnızca uygulama içinde iletişim kutusu çağrıları arasında kaydedilir. Bu renkler uygulama çağrıları arasında kaydetmek istiyorsanız, bunları bazı diğer biçimde gibi da başlatmada kaydetmeniz gerekir (. INI) dosyası.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]

##  <a name="m_cc"></a>  CColorDialog::m_cc

Türünden bir yapıyı [CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora), özelliklerini ve değerlerini iletişim kutusunun üyeleri depolayın.

```
CHOOSECOLOR m_cc;
```

### <a name="remarks"></a>Açıklamalar

Oluşturma sonrasında bir `CColorDialog` nesne kullanabileceğiniz *m_cc* çeşitli yönlerini çağırmadan önce iletişim kutusunda ayarlanacak [DoModal](#domodal) üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]

##  <a name="oncolorok"></a>  CColorDialog::OnColorOK

İletişim kutusuna girilen rengi doğrulamak için geçersiz kılın.

```
virtual BOOL OnColorOK();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu değil oluşturmayabilir olursa sıfır dışı; Girilen renk kabul etmek için Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yalnızca renk iletişim kutusunda kullanıcının seçtiği bir renk özel doğrulama sağlamak istiyorsanız, bu işlev geçersiz kılar.

Kullanıcı aşağıdaki iki yöntemden birini kullanarak bir renk seçebilirsiniz:

- Bir renk paletini rengi'yı tıklatın. Seçilen rengin RGB değerleri daha sonra uygun RGB Düzenle kutularında yansıtılır.

- Düzenleme kutularının RGB değerleri girme

Geçersiz kılma `OnColorOK` uygulamaya özgü herhangi bir nedenden dolayı kullanıcının girdiği ortak bir renk iletişim kutusu bir renk Reddet olanak tanır.

Normalde, çünkü framework varsayılan renkleri doğrulanmasını sağlar ve bir ileti kutusu görüntüler, geçersiz bir renk girdiyseniz bu işlevi kullanın gerekmez.

Çağırabilirsiniz [SetCurrentColor](#setcurrentcolor) içinden `OnColorOK` bir renk seçimi zorlamak için. Bir kez `OnColorOK` çalıştırılmış (diğer bir deyişle, kullanıcı tıkladığında **Tamam** renk değişikliği kabul etmek için), çağırabilirsiniz [GetColor](#getcolor) yeni rengin RGB değeri alınamıyor.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]

##  <a name="setcurrentcolor"></a>  CColorDialog::SetCurrentColor

Çağırdıktan sonra bu işlevi çağırın `DoModal` belirtilen renk değeri geçerli renk seçimi zorlamak için *clr*.

```
void SetCurrentColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*CLR*<br/>
Bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev bir ileti işleyicisinin içerisinde çağrılır veya `OnColorOK`. İletişim kutusu, kullanıcının seçimini değerine göre otomatik olarak güncelleştirecektir *clr* parametresi.

### <a name="example"></a>Örnek

  Örneğin bakın [CColorDialog::OnColorOK](#oncolorok).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
