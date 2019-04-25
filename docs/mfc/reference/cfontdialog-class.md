---
title: CFontDialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- CFontDialog
- AFXDLGS/CFontDialog
- AFXDLGS/CFontDialog::CFontDialog
- AFXDLGS/CFontDialog::DoModal
- AFXDLGS/CFontDialog::GetCharFormat
- AFXDLGS/CFontDialog::GetColor
- AFXDLGS/CFontDialog::GetCurrentFont
- AFXDLGS/CFontDialog::GetFaceName
- AFXDLGS/CFontDialog::GetSize
- AFXDLGS/CFontDialog::GetStyleName
- AFXDLGS/CFontDialog::GetWeight
- AFXDLGS/CFontDialog::IsBold
- AFXDLGS/CFontDialog::IsItalic
- AFXDLGS/CFontDialog::IsStrikeOut
- AFXDLGS/CFontDialog::IsUnderline
- AFXDLGS/CFontDialog::m_cf
helpviewer_keywords:
- CFontDialog [MFC], CFontDialog
- CFontDialog [MFC], DoModal
- CFontDialog [MFC], GetCharFormat
- CFontDialog [MFC], GetColor
- CFontDialog [MFC], GetCurrentFont
- CFontDialog [MFC], GetFaceName
- CFontDialog [MFC], GetSize
- CFontDialog [MFC], GetStyleName
- CFontDialog [MFC], GetWeight
- CFontDialog [MFC], IsBold
- CFontDialog [MFC], IsItalic
- CFontDialog [MFC], IsStrikeOut
- CFontDialog [MFC], IsUnderline
- CFontDialog [MFC], m_cf
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
ms.openlocfilehash: b711ca65e552d495e466ea2e46a6779cf43ecbe3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182127"
---
# <a name="cfontdialog-class"></a>CFontDialog sınıfı

Bir yazı tipi seçimi iletişim kutusunu uygulamanıza eklemenize olanak sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFontDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFontDialog::CFontDialog](#cfontdialog)|Oluşturur bir `CFontDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFontDialog::DoModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmanıza izin verir.|
|[CFontDialog::GetCharFormat](#getcharformat)|Karakter biçimlendirme seçili yazı tipini alır.|
|[CFontDialog::GetColor](#getcolor)|Seçili yazı tipinin rengini döndürür.|
|[CFontDialog::GetCurrentFont](#getcurrentfont)|Şu anda seçili yazı tipinin özelliklerini atar bir `LOGFONT` yapısı.|
|[CFontDialog::GetFaceName](#getfacename)|Seçili yazı tipinin yüz adını döndürür.|
|[CFontDialog::GetSize](#getsize)|Seçili yazı tipinin punto boyutunu döndürür.|
|[CFontDialog::GetStyleName](#getstylename)|Seçili yazı stili adını döndürür.|
|[CFontDialog::GetWeight](#getweight)|Seçili yazı tipinin kalınlığı döndürür.|
|[CFontDialog::IsBold](#isbold)|Kalın yazı tipi olup olmadığını belirler.|
|[CFontDialog::IsItalic](#isitalic)|İtalik yazı tipi olup olmadığını belirler.|
|[CFontDialog::IsStrikeOut](#isstrikeout)|Yazı tipi üstü çizili ile görüntülenip görüntülenmeyeceğini belirler.|
|[CFontDialog::IsUnderline](#isunderline)|Yazı tipi altı çizili olup olmadığını belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CFontDialog::m_cf](#m_cf)|Özelleştirmek için kullanılan bir yapının bir `CFontDialog` nesne.|

## <a name="remarks"></a>Açıklamalar

A `CFontDialog` nesnedir, sistemde yüklenmiş olan yazı tiplerinin bir listesini içeren bir iletişim kutusu. Kullanıcı belirli bir yazı tipi listeden seçebilirsiniz ve bu seçimi daha sonra geri uygulamaya bildirilir.

Oluşturmak için bir `CFontDialog` nesne, sağlanan bir oluşturucu kullanın veya yeni bir alt sınıf türetin ve kendi özel Oluşturucu kullanın.

Bir kez bir `CFontDialog` nesne oluşturulur, kullanabileceğiniz `m_cf` yapısı değerleri veya durumları iletişim kutusundaki denetimlerin başlatılamadı. [M_cf](#m_cf) yapısıdır türünü [CHOOSEFONT](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta). Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.

İletişim nesnenin denetimleri başlatılıyor sonra çağrı `DoModal` üye işlevi iletişim kutusunu görüntülemek ve bir yazı tipi Seç izin verin. `DoModal` Kullanıcı Tamam (IDOK) veya iptal edin (IDCANCEL) düğmesi seçili olup olmadığını döndürür.

Varsa `DoModal` IDOK, döndürür birini kullanabilirsiniz `CFontDialog`ait üye işlevleri tarafından kullanıcı giriş bilgileri alınamıyor.

Windows kullanabileceğiniz [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) işlevi bir hata iletişim kutusunun başlatma sırasında oluşup oluşmadığını belirleyin ve hata hakkında daha fazla bilgi edinin. Bu işlev hakkında daha fazla bilgi için Windows SDK'sı bakın.

`CFontDialog` üzerinde COMMDLG kullanır. Windows 3.1 ve sonraki sürümleri ile birlikte gelen DLL dosyası.

Özelleştir iletişim kutusu için öğesinden bir sınıf türetin `CFontDialog`, bir özel iletişim şablonu sağlar ve genişletilmiş denetimlerden bildirim iletileri işlemek üzere bir ileti eşlemesi ekleyin. İşlenmemiş tüm iletiler için temel sınıf geçirilmelidir.

Kanca işlevini özelleştirme gerekli değildir.

Kullanma hakkında daha fazla bilgi için `CFontDialog`, bkz: [ortak iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFontDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdlgs.h

##  <a name="cfontdialog"></a>  CFontDialog::CFontDialog

Oluşturur bir `CFontDialog` nesne.

```
CFontDialog(
    LPLOGFONT lplfInitial = NULL,
    DWORD dwFlags = CF_EFFECTS | CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);

CFontDialog(
    const CHARFORMAT& charformat,
    DWORD dwFlags = CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*plfInitial*<br/>
Bir işaretçi bir [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) veri yapısı, bazı yazı tipinin özelliklerini ayarlamanıza olanak tanır.

*charFormat*<br/>
Bir işaretçi bir [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) düzenleme denetimi veri yapısı, bazı yazı tipinin özelliklerine zengin içinde ayarlamanıza olanak tanır.

*CertOpenStore*<br/>
Bir veya daha fazla seçin-yazı tipi bayrakları belirtir. Bir veya daha fazla hazır değer Bitsel OR operatörü kullanılarak birleştirilebilir. Değiştirirseniz `m_cf.Flag`s yapı üyesi, varsayılan davranışı korumak için değişikliklerinizi bir bit düzeyinde OR işleci kullandığınızdan emin olun. Bu bayrakların her hakkında daha fazla bilgi için açıklamasına bakın [CHOOSEFONT](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta) Windows SDK'sı yapısında.

*pdcPrinter*<br/>
Bir yazıcı cihaz bağlamı için bir işaretçi. Bu parametre belirtilirse, seçilmesi olan yazı tiplerinin yazıcı için bir yazıcı cihaz bağlamı gösteriyor.

*pParentWnd*<br/>
Yazı tipi iletişim kutusunun üst veya sahip penceresine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Oluşturucu içinde üyelerini otomatik olarak doldurur. Not `CHOOSEFONT` yapısı. Bunlar yalnızca varsayılandan farklı bir yazı tipi iletişim kutusu isterseniz değiştirmelisiniz.

> [!NOTE]
>  Hiçbir zengin düzenleme denetimi desteği olduğunda bu işlev ilk sürümü yalnızca bulunmaktadır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#78](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]

##  <a name="domodal"></a>  CFontDialog::DoModal

Windows ortak yazı tipi iletişim kutusu görüntülemek ve bir yazı tipi seçmesine izin vermek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

IDOK veya IDCANCEL. IDCANCEL döndürülürse, Windows Arama [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) hata oluşup oluşmadığını belirlemek için işlevi.

IDOK ve IDCANCEL kullanıcı Tamam'ı veya iptal düğmesi seçili olup olmadığını gösteren sabittir.

### <a name="remarks"></a>Açıklamalar

Üyeleri ayarlayarak farklı yazı tipi iletişim kutusu denetimleri başlatmak istiyorsanız [m_cf](#m_cf) yapısı, bunu çağırmadan önce yapmalısınız `DoModal`, ancak iletişim nesnesi oluşturulur.

Varsa `DoModal` döndürür IDOK, diğer üye işlevleri, kullanıcı giriş bilgileri ve Ayarları iletişim kutusuna alınacak çağırabilirsiniz.

### <a name="example"></a>Örnek

  Örnekler için bkz: [CFontDialog::CFontDialog](#cfontdialog) ve [CFontDialog::GetColor](#getcolor).

##  <a name="getcharformat"></a>  CFontDialog::GetCharFormat

Karakter biçimlendirme seçili yazı tipini alır.

```
void GetCharFormat(CHARFORMAT& cf) const;
```

### <a name="parameters"></a>Parametreler

*cf*<br/>
A [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) karakter seçili yazı tipini biçimlendirme hakkında bilgi içeren yapıya.

##  <a name="getcolor"></a>  CFontDialog::GetColor

Seçili yazı tipi rengini almak için bu işlevi çağırın.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipi rengi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#79](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]

##  <a name="getcurrentfont"></a>  CFontDialog::GetCurrentFont

Şu anda seçili yazı tipinin özellikleri üyelerine atamak için bu işlevi çağırın bir [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) yapısı.

```
void GetCurrentFont(LPLOGFONT lplf);
```

### <a name="parameters"></a>Parametreler

*lplf*<br/>
Bir işaretçi bir `LOGFONT` yapısı.

### <a name="remarks"></a>Açıklamalar

Diğer `CFontDialog` üye işlevleri, geçerli yazı tipi tek tek özelliklere erişmek için sağlanır.

Bu işlev çağrısı sırasında çağrılırsa [DoModal](#domodal), seçilen zaman döndürür (hangi kullanıcı görür veya sahip iletişim kutusunda değiştirildi). Bu işlev çağrısı yapıldıktan sonra çağrılırsa `DoModal` (yalnızca `DoModal` IDOK döndürür), aslında seçili kullanıcı döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#80](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]

##  <a name="getfacename"></a>  CFontDialog::GetFaceName

Seçili yazı tipinin yüz adını almak için bu işlevi çağırın.

```
CString GetFaceName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipinin yüz adı `CFontDialog` iletişim kutusu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#81](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]

##  <a name="getsize"></a>  CFontDialog::GetSize

Seçili yazı tipinin boyutunu almak için bu işlevi çağırın.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir noktanın onda yazı tipinin boyutu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#82](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]

##  <a name="getstylename"></a>  CFontDialog::GetStyleName

Seçili yazı stili adını almak için bu işlevi çağırın.

```
CString GetStyleName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi stili adı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#83](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]

##  <a name="getweight"></a>  CFontDialog::GetWeight

Seçili yazı tipinin kalınlığı almak için bu işlevi çağırın.

```
int GetWeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipinin kalınlığı.

### <a name="remarks"></a>Açıklamalar

Bir yazı tipi ağırlığı hakkında daha fazla bilgi için bkz. [CFont::CreateFont](../../mfc/reference/cfont-class.md#createfont).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#84](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]

##  <a name="isbold"></a>  CFontDialog::IsBold

Seçili yazı tipinin kalın olup olmadığını belirlemek için bu işlevi çağırın.

```
BOOL IsBold() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipinin kalın özelliği etkin olan olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#85](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]

##  <a name="isitalic"></a>  CFontDialog::IsItalic

Seçili yazı italik olup olmadığını belirlemek için bu işlevi çağırın.

```
BOOL IsItalic() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı italik özelliği etkin olan olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#86](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]

##  <a name="isstrikeout"></a>  CFontDialog::IsStrikeOut

Seçili yazı üstü çizili ile gösterilip gösterilmediğini belirlemek için bu işlevi çağırın.

```
BOOL IsStrikeOut() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı üstü çizili özelliği etkin olan olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#87](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]

##  <a name="isunderline"></a>  CFontDialog::IsUnderline

Seçili yazı altı çizili olup olmadığını belirlemek için bu işlevi çağırın.

```
BOOL IsUnderline() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı altı çizili özelliği etkin olan olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#88](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]

##  <a name="m_cf"></a>  CFontDialog::m_cf

Üyeleri iletişim nesnesinin özelliklerini depolamak için bir yapı.

```
CHOOSEFONT m_cf;
```

### <a name="remarks"></a>Açıklamalar

Oluşturma sonrasında bir `CFontDialog` nesne kullanabileceğiniz `m_cf` çağırmadan önce iletişim kutusu çeşitli yönlerini değiştirmek için `DoModal` üye işlevi. Bu yapı hakkında daha fazla bilgi için bkz. [CHOOSEFONT](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#89](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
