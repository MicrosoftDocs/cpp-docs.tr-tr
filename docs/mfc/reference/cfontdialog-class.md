---
title: CFontDialog Sınıfı
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
ms.openlocfilehash: 6a8e24b68f377235c1f1e21fbcd5618aebbe299a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755017"
---
# <a name="cfontdialog-class"></a>CFontDialog Sınıfı

Uygulamanıza bir yazı tipi seçimi iletişim kutusu dahil etmenizi sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFontDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFontDialog::CFontDialog](#cfontdialog)|Bir `CFontDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFontDialog::DoModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmasına izin verir.|
|[CFontDialog::GetCharFormat](#getcharformat)|Seçili yazı tipinin karakter biçimlendirmesini alır.|
|[CFontDialog::GetColor](#getcolor)|Seçili yazı tipinin rengini verir.|
|[CFontDialog::GetCurrentFont](#getcurrentfont)|Şu anda seçili yazı tipinin özelliklerini bir `LOGFONT` yapıya atar.|
|[CFontDialog::GetFaceName](#getfacename)|Seçili yazı tipinin yüz adını döndürür.|
|[CFontDialog::GetSize](#getsize)|Seçili yazı tipinin nokta boyutunu döndürür.|
|[CFontDialog::GetStyleName](#getstylename)|Seçili yazı tipinin stil adını döndürür.|
|[CFontDialog::GetWeight](#getweight)|Seçili yazı tipinin ağırlığını verir.|
|[CFontDialog::IsBold](#isbold)|Yazı tipinin kalın olup olmadığını belirler.|
|[CFontDialog::IsItalic](#isitalic)|Yazı tipinin italik olup olmadığını belirler.|
|[CFontDialog::IsStrikeOut](#isstrikeout)|Yazı tipinin grevle görüntülenip görüntülenmediğini belirler.|
|[CFontDialog::Underline](#isunderline)|Yazı tipinin altı çizili olup olmadığını belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CFontDialog::m_cf](#m_cf)|Nesneyi özelleştirmek için `CFontDialog` kullanılan bir yapı.|

## <a name="remarks"></a>Açıklamalar

`CFontDialog` Nesne, şu anda sistemde yüklü olan yazı tiplerinin listesini içeren bir iletişim kutusudur. Kullanıcı listeden belirli bir yazı tipi seçebilir ve bu seçim uygulamaya geri bildirilir.

Bir `CFontDialog` nesne oluşturmak için, sağlanan oluşturucuyu kullanın veya yeni bir alt sınıf türetin ve kendi özel oluşturucunuzu kullanın.

Bir `CFontDialog` nesne oluşturulduktan sonra, iletişim `m_cf` kutusundaki denetim değerlerini veya durumlarını açmak için yapıyı kullanabilirsiniz. m_cf [m_cf](#m_cf) yapısı [CHOOSEFONT](/windows/win32/api/commdlg/ns-commdlg-choosefontw)türündedir. Bu yapı hakkında daha fazla bilgi için Windows SDK'ya bakın.

İletişim nesnesinin denetimlerini aldıktan sonra, `DoModal` iletişim kutusunu görüntülemek için üye işlevi arayın ve kullanıcının bir yazı tipi seçmesine izin verin. `DoModal`kullanıcıok (IDOK) veya İptal (IDCANCEL) düğmesini seçip seçmediğini döndürür.

`DoModal` IDOK'u döndürürse, kullanıcı tarafından bilgi girdisini almak için `CFontDialog`'üye işlevlerden birini kullanabilirsiniz.

İletişim kutusunun başlatılması sırasında bir hata oluşup oluşmadığını belirlemek ve hata hakkında daha fazla bilgi edinmek için Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini kullanabilirsiniz. Bu işlev hakkında daha fazla bilgi için Windows SDK'ya bakın.

`CFontDialog`COMMDLG'ye dayanır. DLL dosyası, Windows sürümleri 3.1 ve sonraki sürümlerle birlikte iletin.

İletişim kutusunu özelleştirmek için, bir sınıf `CFontDialog`türetin, özel bir iletişim şablonu sağlayın ve genişletilmiş denetimlerden gelen bildirim iletilerini işlemek için bir ileti eşlemi ekleyin. İşlenmemiş iletiler taban sınıfa geçirilmelidir.

Kanca işlevini özelleştirmek gerekli değildir.

Kullanma `CFontDialog`hakkında daha fazla bilgi için [Ortak İletişim Sınıfları'na](../../mfc/common-dialog-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFontDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs.h

## <a name="cfontdialogcfontdialog"></a><a name="cfontdialog"></a>CFontDialog::CFontDialog

Bir `CFontDialog` nesne inşa eder.

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
Yazı tipinin bazı özelliklerini ayarlamanızı sağlayan [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) veri yapısına işaretçi.

*Charformat*<br/>
Yazı tipinin bazı özelliklerini zengin bir denetimde ayarlamanızı sağlayan [CHARFORMAT](/windows/win32/api/richedit/ns-richedit-charformata) veri yapısına işaretçi.

*Dwflags*<br/>
Bir veya daha fazla seçim yazı tipi bayraklarını belirtir. Bir veya daha fazla önceden ayarlanmış değer bitwise OR işleci kullanılarak birleştirilebilir. S yapı `m_cf.Flag`üyesini değiştirirseniz, varsayılan davranışı sağlam tutmak için değişikliklerinizde bitwise VEYA işleci kullandığınızdan emin olun. Bu bayrakların her biriyle ilgili ayrıntılar için Windows SDK'daki [CHOOSEFONT](/windows/win32/api/commdlg/ns-commdlg-choosefontw) yapısının açıklamasına bakın.

*pdcYazıcı*<br/>
Yazıcı aygıtı bağlamına işaretçi. Bu parametre sağlandığı takdirde, yazı tiplerinin seçilmeye başlandığı yazıcı için yazıcı aygıtı bağlamını işaret eder.

*pParentWnd*<br/>
Yazı tipi iletişim kutusunun üst veya sahip penceresiiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Oluşturucunun `CHOOSEFONT` yapının üyelerini otomatik olarak doldurduğunu unutmayın. Bunları yalnızca varsayılandan farklı bir yazı tipi iletişim kutusu istiyorsanız değiştirmeniz gerekir.

> [!NOTE]
> Bu işlevin ilk sürümü yalnızca zengin bir edit denetimi desteği olmadığında bulunur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#78](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]

## <a name="cfontdialogdomodal"></a><a name="domodal"></a>CFontDialog::DoModal

Windows ortak yazı tipi iletişim kutusunu görüntülemek ve kullanıcının bir yazı tipi seçmesine izin vermek için bu işlevi arayın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İDOK veya IDCANCEL. IDCANCEL döndürülürse, bir hata oluşup oluşmadığını belirlemek için Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini arayın.

IDOK ve IDCANCEL, kullanıcının Ok veya İptal düğmesini seçip seçmediğini gösteren sabitlerdir.

### <a name="remarks"></a>Açıklamalar

[m_cf](#m_cf) yapısının üyelerini ayarlayarak çeşitli yazı tipi iletişim denetimlerini başlatmayı istiyorsanız, `DoModal`bunu çağırmadan önce, ancak iletişim nesnesi oluşturulduktan sonra yapmalısınız.

`DoModal` IDOK'u döndürürse, kullanıcı tarafından iletişim kutusuna ayar veya bilgi girişi almak için diğer üye işlevleri arayabilirsiniz.

### <a name="example"></a>Örnek

  [CFontDialog::CFontDialog](#cfontdialog) ve [CFontDialog::GetColor](#getcolor)için örneklere bakın.

## <a name="cfontdialoggetcharformat"></a><a name="getcharformat"></a>CFontDialog::GetCharFormat

Seçili yazı tipinin karakter biçimlendirmesini alır.

```cpp
void GetCharFormat(CHARFORMAT& cf) const;
```

### <a name="parameters"></a>Parametreler

*Cf*<br/>
Seçili yazı tipinin karakter biçimlendirmesi hakkında bilgi içeren [bir CHARFORMAT](/windows/win32/api/richedit/ns-richedit-charformata) yapısı.

## <a name="cfontdialoggetcolor"></a><a name="getcolor"></a>CFontDialog::GetColor

Seçili yazı tipi rengini almak için bu işlevi arayın.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipinin rengi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#79](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]

## <a name="cfontdialoggetcurrentfont"></a><a name="getcurrentfont"></a>CFontDialog::GetCurrentFont

Şu anda seçili yazı tipinin özelliklerini [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısının üyelerine atamak için bu işlevi arayın.

```cpp
void GetCurrentFont(LPLOGFONT lplf);
```

### <a name="parameters"></a>Parametreler

*lplf*<br/>
Bir yapıiçin `LOGFONT` bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli `CFontDialog` yazı tipinin tek tek özelliklerine erişmek için diğer üye işlevler sağlanır.

Bu işlev [DoModal'a](#domodal)bir çağrı sırasında çağrılırsa, geçerli seçimi o anda döndürür (kullanıcının iletişim kutusunda gördükleri veya değiştirdiği şey). Bu işlev bir çağrıdan `DoModal` sonra çağrılırsa (yalnızca IDOK `DoModal` döndürürse), kullanıcının gerçekte seçtiği şeyi döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#80](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]

## <a name="cfontdialoggetfacename"></a><a name="getfacename"></a>CFontDialog::GetFaceName

Seçili yazı tipinin yüz adını almak için bu işlevi arayın.

```
CString GetFaceName() const;
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunda seçilen yazı tipinin `CFontDialog` yüz adı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#81](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]

## <a name="cfontdialoggetsize"></a><a name="getsize"></a>CFontDialog::GetSize

Seçili yazı tipinin boyutunu almak için bu işlevi arayın.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazı tipinin boyutu, bir noktanın onda birinde.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#82](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]

## <a name="cfontdialoggetstylename"></a><a name="getstylename"></a>CFontDialog::GetStyleName

Seçili yazı tipinin stil adını almak için bu işlevi çağırın.

```
CString GetStyleName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazı tipinin stil adı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#83](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]

## <a name="cfontdialoggetweight"></a><a name="getweight"></a>CFontDialog::GetWeight

Seçili yazı tipinin ağırlığını almak için bu işlevi arayın.

```
int GetWeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipinin ağırlığı.

### <a name="remarks"></a>Açıklamalar

Bir yazı tipinin ağırlığı hakkında daha fazla bilgi için [CFont::CreateFont'a](../../mfc/reference/cfont-class.md#createfont)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#84](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]

## <a name="cfontdialogisbold"></a><a name="isbold"></a>CFontDialog::IsBold

Seçili yazı tipinin kalın olup olmadığını belirlemek için bu işlevi arayın.

```
BOOL IsBold() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipinde Kalın özelliği etkinse sıfır olmayan; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#85](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]

## <a name="cfontdialogisitalic"></a><a name="isitalic"></a>CFontDialog::IsItalic

Seçili yazı tipinin italik olup olmadığını belirlemek için bu işlevi arayın.

```
BOOL IsItalic() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipiitalik özelliğe etkinse sıfır olmayan; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#86](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]

## <a name="cfontdialogisstrikeout"></a><a name="isstrikeout"></a>CFontDialog::IsStrikeOut

Seçili yazı tipinin strikeout ile görüntülenip görüntülenmeyeyiş için bu işlevi arayın.

```
BOOL IsStrikeOut() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipi Strikeout özelliği etkinse sıfır olmayan; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#87](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]

## <a name="cfontdialogisunderline"></a><a name="isunderline"></a>CFontDialog::Underline

Seçili yazı tipinin altı çizili olup olmadığını belirlemek için bu işlevi arayın.

```
BOOL IsUnderline() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipinde Altı çizili özellik etkinse sıfır olmayan; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#88](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]

## <a name="cfontdialogm_cf"></a><a name="m_cf"></a>CFontDialog::m_cf

Üyeleri iletişim nesnesinin özelliklerini depolayan bir yapı.

```
CHOOSEFONT m_cf;
```

### <a name="remarks"></a>Açıklamalar

Bir `CFontDialog` nesne yaptıktan sonra, `m_cf` `DoModal` üye işlevi çağırmadan önce iletişim kutusunun çeşitli yönlerini değiştirmek için kullanabilirsiniz. Bu yapı hakkında daha fazla bilgi için Windows SDK'daki [CHOOSEFONT'a](/windows/win32/api/commdlg/ns-commdlg-choosefontw) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#89](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
