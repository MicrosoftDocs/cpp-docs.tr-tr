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
ms.openlocfilehash: 54fd987d683a9236531baee3afbb9ee61be623e2
ms.sourcegitcommit: 13f42c339fb7af935e3a93ac80e350d5e784c9f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2020
ms.locfileid: "87470764"
---
# <a name="ccolordialog-class"></a>CColorDialog sınıfı

Uygulamanıza renk seçimi iletişim kutusu eklemenize olanak sağlar.

## <a name="syntax"></a>Syntax

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
|[CColorDialog:: GetColor](#getcolor)|`COLORREF`Seçilen rengin değerlerini içeren bir yapı döndürür.|
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

Bir nesne oluşturmak için `CColorDialog` , belirtilen oluşturucuyu kullanın veya yeni bir sınıf türetebilir ve kendi özel oluşturucuyu kullanın.

İletişim kutusu oluşturulduktan sonra, iletişim kutusu denetimlerinin değerlerini başlatmak için [m_cc](#m_cc) yapısındaki herhangi bir değeri ayarlayabilir veya değiştirebilirsiniz. *M_cc* yapısı [choosecolor](/windows/win32/api/commdlg/ns-commdlg-choosecolora-r1)türündedir.

İletişim kutusunun denetimlerini başlattıktan sonra, `DoModal` iletişim kutusunu göstermek ve kullanıcının bir renk seçmesine izin vermek için üye işlevini çağırın. `DoModal`kullanıcının iletişim kutusunun Tamam (IDOK) veya Cancel (ıDCANCEL) düğmesi seçimini döndürür.

`DoModal`IDOK döndürürse, `CColorDialog` Kullanıcı tarafından bilgi girişi almak için üye işlevlerinden birini kullanabilirsiniz.

İletişim kutusunun başlatılması sırasında oluşan bir hata olup olmadığını ve hata hakkında daha fazla bilgi edinmek için Windows [Commdlextende,](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini kullanabilirsiniz.

`CColorDialog`, 3,1 ve üzeri Windows sürümleriyle birlikte gelen COMMDLG.DLL dosyasını kullanır.

İletişim kutusunu özelleştirmek için, öğesinden bir sınıf türetebilir `CColorDialog` , özel bir iletişim kutusu şablonu sağlayın ve genişletilmiş denetimlerden gelen bildirim iletilerini işlemek için bir ileti eşlemesi ekleyin. İşlenmemiş tüm iletiler taban sınıfına geçirilmelidir.

Kanca işlevinin özelleştirilmesi gerekli değildir.

> [!NOTE]
> Bazı yüklemelerde, `CColorDialog` diğer nesneleri gri hale getirmek için çerçevesini kullandıysanız nesne gri bir arka planla görüntülenmez `CDialog` .

Kullanma hakkında daha fazla bilgi için `CColorDialog` bkz. [ortak Iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[Ccommoniletişim kutusu](../../mfc/reference/ccommondialog-class.md)

`CColorDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs. h

## <a name="ccolordialogccolordialog"></a><a name="ccolordialog"></a>CColorDialog:: CColorDialog

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
İletişim kutusunun işlevini ve görünümünü özelleştiren bir bayrak kümesi. Daha fazla bilgi için Windows SDK [choosecolor](/windows/win32/api/commdlg/ns-commdlg-choosecolora-r1) yapısına bakın.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresine yönelik bir işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]

## <a name="ccolordialogdomodal"></a><a name="domodal"></a>CColorDialog::D oModal

Windows ortak renk iletişim kutusunu göstermek ve kullanıcının bir renk seçmesine izin vermek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

IDOK veya ıDCANCEL. IDCANCEL döndürülürse, bir hatanın oluşup oluşmadığını öğrenmek için Windows [Commıdextendebir](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini çağırın.

IDOK ve ıDCANCEL, kullanıcının Tamam veya Iptal düğmesini seçip seçmediğini belirten sabitlerdir.

### <a name="remarks"></a>Açıklamalar

[M_cc](#m_cc) yapısının üyelerini ayarlayarak çeşitli renk iletişim kutusu seçeneklerini başlatmak istiyorsanız, bunu çağırmadan önce, `DoModal` ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir.

Öğesini çağırdıktan sonra `DoModal` , Kullanıcı tarafından iletişim kutusuna ayarları veya bilgi girişini almak için diğer üye işlevlerini çağırabilirsiniz.

### <a name="example"></a>Örnek

  [CColorDialog:: CColorDialog](#ccolordialog)örneğine bakın.

## <a name="ccolordialoggetcolor"></a><a name="getcolor"></a>CColorDialog:: GetColor

`DoModal`Kullanıcının seçtiği renkle ilgili bilgileri almak için çağrıldıktan sonra bu işlevi çağırın.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Renk iletişim kutusunda seçilen rengin RGB bilgilerini içeren [colorref](/windows/win32/gdi/colorref) değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]

## <a name="ccolordialoggetsavedcustomcolors"></a><a name="getsavedcustomcolors"></a>CColorDialog:: GetSavedCustomColors

`CColorDialog`nesneler kullanıcıya izin verir, renkleri seçmeye ek olarak 16 özel renk tanımlar.

```
static COLORREF* PASCAL GetSavedCustomColors();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tarafından oluşturulan özel renkleri depolayan 16 RGB renk değeri dizisine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`GetSavedCustomColors`Üye işlevi bu renklere erişim sağlar. Bu renkler, [DoModal](#domodal) IDOK öğesini döndürdüğünden alınabilir.

Döndürülen dizideki her 16 RGB değeri, RGB (255255255) (beyaz) olarak başlatılır. Kullanıcı tarafından seçilen özel renkler yalnızca uygulamanın içindeki iletişim kutusu etkinleştirmeleri arasında kaydedilir. Bu renkleri uygulamanın etkinleştirmeleri arasında kaydetmek isterseniz, bunları bir başlatma (. gibi) gibi başka bir şekilde kaydetmelisiniz. INI) dosyası.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]

## <a name="ccolordialogm_cc"></a><a name="m_cc"></a>CColorDialog:: m_cc

Üyeleri iletişim kutusunun özelliklerini ve değerlerini depolayan [choosecolor](/windows/win32/api/commdlg/ns-commdlg-choosecolora-r1)türünde bir yapı.

```
CHOOSECOLOR m_cc;
```

### <a name="remarks"></a>Açıklamalar

Bir nesne oluşturduktan sonra `CColorDialog` , [DoModal](#domodal) üye işlevini çağırmadan önce iletişim kutusunun çeşitli yönlerini ayarlamak için *m_cc* kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]

## <a name="ccolordialogoncolorok"></a><a name="oncolorok"></a>CColorDialog:: OnColorOK

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

Geçersiz kılma `OnColorOK` , kullanıcının uygulamaya özgü nedenlerle ortak bir renk iletişim kutusuna girdiği rengi reddetmesini sağlar.

Normalde, bu işlevi kullanmanız gerekmez, çünkü Framework renklerin varsayılan doğrulamasını sağlar ve geçersiz bir renk girilirse bir ileti kutusu görüntüler.

Renk seçimini zorlamak için içinden [SetCurrentColor](#setcurrentcolor) öğesini çağırabilirsiniz `OnColorOK` . Başlatıldıktan sonra `OnColorOK` (diğer bir deyişle, Kullanıcı renk değişikliğini kabul etmek Için **Tamam** ' a tıkladığında), yeni rengin rgb değerini almak için [GetColor](#getcolor) öğesini çağırabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]

## <a name="ccolordialogsetcurrentcolor"></a><a name="setcurrentcolor"></a>CColorDialog:: SetCurrentColor

`DoModal`Geçerli renk seçimini *clr*'de belirtilen renk değerine zorlamak için çağrıldıktan sonra bu işlevi çağırın.

```cpp
void SetCurrentColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*clr*<br/>
Bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev bir ileti işleyicisi veya içinden çağrılır `OnColorOK` . İletişim kutusu, kullanıcının seçimini *clr* parametresinin değerine göre otomatik olarak güncelleştirir.

### <a name="example"></a>Örnek

  [CColorDialog:: OnColorOK](#oncolorok)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek DRAWCLı](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
