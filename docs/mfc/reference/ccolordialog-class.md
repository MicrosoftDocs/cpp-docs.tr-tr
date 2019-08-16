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
ms.openlocfilehash: 3031b1e5870dd7f59af7adf48a6a77aaccdf53fc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507208"
---
# <a name="ccolordialog-class"></a>CColorDialog sınıfı

Uygulamanıza renk seçimi iletişim kutusu eklemenize olanak sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CColorDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CColorDialog:: CColorDialog](#ccolordialog)|Bir `CColorDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CColorDialog::D oModal](#domodal)|Bir renk iletişim kutusu görüntüler ve kullanıcının seçim yapmasına izin verir.|
|[CColorDialog:: GetColor](#getcolor)|Seçilen rengin `COLORREF` değerlerini içeren bir yapı döndürür.|
|[CColorDialog:: GetSavedCustomColors](#getsavedcustomcolors)|Kullanıcı tarafından oluşturulan özel renkleri alır.|
|[CColorDialog:: SetCurrentColor](#setcurrentcolor)|Geçerli renk seçimini belirtilen renge zorlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CColorDialog:: OnColorOK](#oncolorok)|İletişim kutusuna girilen rengi doğrulamak için geçersiz kılın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CColorDialog:: m_cc](#m_cc)|İletişim kutusunun ayarlarını özelleştirmek için kullanılan bir yapı.|

## <a name="remarks"></a>Açıklamalar

Bir `CColorDialog` nesne, görüntüleme sistemi için tanımlanan renklerin listesini içeren bir iletişim kutusudur. Kullanıcı listeden belirli bir rengi seçebilir veya oluşturabilir, ardından iletişim kutusu çıktığında uygulamaya geri bildirilir.

Bir `CColorDialog` nesne oluşturmak için, belirtilen oluşturucuyu kullanın veya yeni bir sınıf türetebilir ve kendi özel oluşturucuyu kullanın.

İletişim kutusu oluşturulduktan sonra, iletişim kutusu denetimlerinin değerlerini başlatmak için [m_cc](#m_cc) yapısındaki herhangi bir değeri ayarlayabilir veya değiştirebilirsiniz. *M_cc* yapısı [choosecolor](/windows/win32/api/commdlg/ns-commdlg-choosecolorw)türündedir.

İletişim kutusunun denetimlerini başlattıktan sonra, iletişim kutusunu göstermek ve `DoModal` kullanıcının bir renk seçmesine izin vermek için üye işlevini çağırın. `DoModal`kullanıcının iletişim kutusunun Tamam (IDOK) veya Cancel (ıDCANCEL) düğmesi seçimini döndürür.

IDOK `CColorDialog`döndürürse,Kullanıcı tarafından bilgi girişi almak için üye işlevlerinden birini kullanabilirsiniz. `DoModal`

İletişim kutusunun başlatılması sırasında oluşan bir hata olup olmadığını ve hata hakkında daha fazla bilgi edinmek için Windows [Commdlextende,](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini kullanabilirsiniz.

`CColorDialog`, COMMDLG 'e dayanır. Windows sürümleri 3,1 ve üzeri ile birlikte gelen DLL dosyası.

İletişim kutusunu özelleştirmek için, öğesinden `CColorDialog`bir sınıf türetebilir, özel bir iletişim kutusu şablonu sağlayın ve genişletilmiş denetimlerden gelen bildirim iletilerini işlemek için bir ileti eşlemesi ekleyin. İşlenmemiş tüm iletiler taban sınıfına geçirilmelidir.

Kanca işlevinin özelleştirilmesi gerekli değildir.

> [!NOTE]
>  Bazı yüklemelerde, `CColorDialog` diğer `CDialog` nesneleri gri hale getirmek için çerçevesini kullandıysanız nesne gri bir arka planla görüntülenmez.

Kullanma `CColorDialog`hakkında daha fazla bilgi için bkz. [ortak iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CColorDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs. h

##  <a name="ccolordialog"></a>CColorDialog:: CColorDialog

Bir `CColorDialog` nesnesi oluşturur.

```
CColorDialog(
    COLORREF clrInit = 0,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*clrInit*<br/>
Varsayılan renk seçimi. Değer belirtilmemişse, varsayılan RGB 'dir (0, 0, 0) (siyah).

*dwFlags*<br/>
İletişim kutusunun işlevini ve görünümünü özelleştiren bir bayrak kümesi. Daha fazla bilgi için Windows SDK [choosecolor](/windows/win32/api/commdlg/ns-commdlg-choosecolorw) yapısına bakın.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresine yönelik bir işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]

##  <a name="domodal"></a>CColorDialog::D oModal

Windows ortak renk iletişim kutusunu göstermek ve kullanıcının bir renk seçmesine izin vermek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

IDOK veya ıDCANCEL. IDCANCEL döndürülürse, bir hatanın oluşup oluşmadığını öğrenmek için Windows [Commıdextendebir](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini çağırın.

IDOK ve ıDCANCEL, kullanıcının Tamam veya Iptal düğmesini seçip seçmediğini belirten sabitlerdir.

### <a name="remarks"></a>Açıklamalar

[M_cc](#m_cc) yapısının üyelerini ayarlayarak çeşitli renk iletişim kutusu seçeneklerini başlatmak istiyorsanız, bunu çağırmadan `DoModal` önce, ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir.

Öğesini çağırdıktan `DoModal`sonra, Kullanıcı tarafından iletişim kutusuna ayarları veya bilgi girişini almak için diğer üye işlevlerini çağırabilirsiniz.

### <a name="example"></a>Örnek

  [CColorDialog:: CColorDialog](#ccolordialog)örneğine bakın.

##  <a name="getcolor"></a>CColorDialog:: GetColor

Kullanıcının seçtiği renkle ilgili bilgileri `DoModal` almak için çağrıldıktan sonra bu işlevi çağırın.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Renk iletişim kutusunda seçilen rengin RGB bilgilerini içeren [colorref](/windows/win32/gdi/colorref) değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]

##  <a name="getsavedcustomcolors"></a>CColorDialog:: GetSavedCustomColors

`CColorDialog`nesneler kullanıcıya izin verir, renkleri seçmeye ek olarak 16 özel renk tanımlar.

```
static COLORREF* PASCAL GetSavedCustomColors();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tarafından oluşturulan özel renkleri depolayan 16 RGB renk değeri dizisine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`GetSavedCustomColors` Üye işlevi bu renklere erişim sağlar. Bu renkler, [DoModal](#domodal) IDOK öğesini döndürdüğünden alınabilir.

Döndürülen dizideki her 16 RGB değeri, RGB (255255255) (beyaz) olarak başlatılır. Kullanıcı tarafından seçilen özel renkler yalnızca uygulamanın içindeki iletişim kutusu etkinleştirmeleri arasında kaydedilir. Bu renkleri uygulamanın etkinleştirmeleri arasında kaydetmek isterseniz, bunları bir başlatma (. gibi) gibi başka bir şekilde kaydetmelisiniz. INI) dosyası.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]

##  <a name="m_cc"></a>CColorDialog:: m_cc

Üyeleri iletişim kutusunun özelliklerini ve değerlerini depolayan [choosecolor](/windows/win32/api/commdlg/ns-commdlg-choosecolorw)türünde bir yapı.

```
CHOOSECOLOR m_cc;
```

### <a name="remarks"></a>Açıklamalar

Bir `CColorDialog` nesne oluşturduktan sonra, [DoModal](#domodal) üye işlevini çağırmadan önce iletişim kutusunun çeşitli yönlerini ayarlamak için *m_cc* kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]

##  <a name="oncolorok"></a>CColorDialog:: OnColorOK

İletişim kutusuna girilen rengi doğrulamak için geçersiz kılın.

```
virtual BOOL OnColorOK();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu kapatılacağını sıfır olmayan şekilde yapın; Aksi takdirde, girilen rengi kabul etmek için 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca kullanıcının renk iletişim kutusunda seçtiği renge özel doğrulama sağlamak istiyorsanız geçersiz kılın.

Kullanıcı aşağıdaki iki yöntemden birini seçerek renk seçebilir:

- Renk paletindeki bir renge tıklanın. Seçilen rengin RGB değerleri, uygun RGB düzenleme kutularına yansıtılır.

- RGB düzenleme kutularına değer girme

Geçersiz `OnColorOK` kılma, kullanıcının uygulamaya özgü nedenlerle ortak bir renk iletişim kutusuna girdiği rengi reddetmesini sağlar.

Normalde, bu işlevi kullanmanız gerekmez, çünkü Framework renklerin varsayılan doğrulamasını sağlar ve geçersiz bir renk girilirse bir ileti kutusu görüntüler.

Renk seçimini zorlamak için içinden `OnColorOK` [SetCurrentColor](#setcurrentcolor) öğesini çağırabilirsiniz. Başlatıldıktan `OnColorOK` sonra (diğer bir deyişle, Kullanıcı renk değişikliğini kabul etmek için **Tamam** ' a tıkladığında), yeni rengin rgb değerini almak için [GetColor](#getcolor) öğesini çağırabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]

##  <a name="setcurrentcolor"></a>CColorDialog:: SetCurrentColor

Geçerli renk seçimini *clr*'de `DoModal` belirtilen renk değerine zorlamak için çağrıldıktan sonra bu işlevi çağırın.

```
void SetCurrentColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*clr*<br/>
Bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev bir ileti işleyicisi veya `OnColorOK`içinden çağrılır. İletişim kutusu, kullanıcının seçimini *clr* parametresinin değerine göre otomatik olarak güncelleştirir.

### <a name="example"></a>Örnek

  [CColorDialog:: OnColorOK](#oncolorok)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek DRAWCLı](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
