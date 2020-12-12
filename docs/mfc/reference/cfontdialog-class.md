---
description: 'Daha fazla bilgi edinin: CFontDialog sınıfı'
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
ms.openlocfilehash: c1f8637a6106db9220721dffe67a2ed1d53b26b7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184354"
---
# <a name="cfontdialog-class"></a>CFontDialog sınıfı

Uygulamanıza bir yazı tipi seçme iletişim kutusu eklemenize olanak sağlar.

## <a name="syntax"></a>Syntax

```
class CFontDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFontDialog:: CFontDialog](#cfontdialog)|Bir `CFontDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFontDialog::D oModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmasına izin verir.|
|[CFontDialog:: GetCharFormat](#getcharformat)|Seçili yazı tipinin karakter biçimlendirmesini alır.|
|[CFontDialog:: GetColor](#getcolor)|Seçilen yazı tipinin rengini döndürür.|
|[CFontDialog:: GetCurrentFont](#getcurrentfont)|Seçili olan yazı tipinin karakteristiklerini bir `LOGFONT` yapıya atar.|
|[CFontDialog:: GetFaceName](#getfacename)|Seçili yazı tipinin yüz adını döndürür.|
|[CFontDialog:: GetSize](#getsize)|Seçilen yazı tipinin punto boyutunu döndürür.|
|[CFontDialog:: GetStyleName](#getstylename)|Seçilen fontun stil adını döndürür.|
|[CFontDialog:: GetWeight](#getweight)|Seçilen yazı tipinin kalınlığını döndürür.|
|[CFontDialog:: IsBold](#isbold)|Yazı tipinin kalın olup olmadığını belirler.|
|[CFontDialog:: ısitalik](#isitalic)|Yazı tipinin italik olup olmadığını belirler.|
|[CFontDialog:: ısüstü çizili](#isstrikeout)|Yazı tipinin üstü çizili ile görüntülenip görüntülenmeyeceğini belirler.|
|[CFontDialog:: ısaltıya](#isunderline)|Yazı tipinin altı çizili olup olmadığını belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CFontDialog:: m_cf](#m_cf)|Bir nesneyi özelleştirmek için kullanılan bir yapı `CFontDialog` .|

## <a name="remarks"></a>Açıklamalar

Bir `CFontDialog` nesne, sistemde yüklü olan yazı tiplerinin listesini içeren bir iletişim kutusudur. Kullanıcı listeden belirli bir yazı tipi seçebilir ve bu seçim daha sonra uygulamaya geri bildirilir.

Bir nesne oluşturmak için `CFontDialog` , belirtilen oluşturucuyu kullanın veya yeni bir alt sınıf türetebilir ve kendi özel oluşturucuyu kullanın.

Bir nesne oluşturulduktan sonra `CFontDialog` , `m_cf` iletişim kutusundaki denetimlerin değerlerini veya durumlarını başlatmak için yapıyı kullanabilirsiniz. [M_cf](#m_cf) yapısı [CHOOSEFONT](/windows/win32/api/commdlg/ns-commdlg-choosefontw)türündedir. Bu yapı hakkında daha fazla bilgi için Windows SDK bakın.

İletişim kutusu nesnesinin denetimlerini başlattıktan sonra, `DoModal` iletişim kutusunu göstermek ve kullanıcının bir yazı tipi seçmesine izin vermek için üye işlevini çağırın. `DoModal` kullanıcının Tamam (IDOK) veya Cancel (ıDCANCEL) düğmesini seçmediğini döndürür.

`DoModal`IDOK döndürürse, `CFontDialog` Kullanıcı tarafından bilgi girişi almak için üye işlevlerinden birini kullanabilirsiniz.

İletişim kutusunun başlatılması sırasında oluşan bir hata olup olmadığını ve hata hakkında daha fazla bilgi edinmek için Windows [Commdlextende,](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini kullanabilirsiniz. Bu işlev hakkında daha fazla bilgi için Windows SDK bakın.

`CFontDialog` , 3,1 ve üzeri Windows sürümleriyle birlikte gelen COMMDLG.DLL dosyasını kullanır.

İletişim kutusunu özelleştirmek için, öğesinden bir sınıf türetebilir `CFontDialog` , özel bir iletişim kutusu şablonu sağlayın ve bildirim iletilerini genişletilmiş denetimlerden işlemek üzere bir ileti eşlemesi ekleyin. İşlenmemiş tüm iletiler taban sınıfına geçirilmelidir.

Kanca işlevinin özelleştirilmesi gerekli değildir.

Kullanma hakkında daha fazla bilgi için `CFontDialog` bkz. [ortak Iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[Ccommoniletişim kutusu](../../mfc/reference/ccommondialog-class.md)

`CFontDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs. h

## <a name="cfontdialogcfontdialog"></a><a name="cfontdialog"></a> CFontDialog:: CFontDialog

Bir `CFontDialog` nesnesi oluşturur.

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

*Plfinial*<br/>
Yazı tipinin bazı özelliklerini ayarlamanıza olanak sağlayan [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) veri yapısına yönelik bir işaretçi.

*charFormat*<br/>
Bir zengin düzenleme denetimindeki bazı yazı tipi özelliklerini ayarlamanıza olanak sağlayan bir [Charformat](/windows/win32/api/richedit/ns-richedit-charformata) veri yapısına yönelik işaretçi.

*dwFlags*<br/>
Bir veya daha fazla seçim-yazı tipi bayrağını belirtir. Bir veya daha fazla önceden ayarlanmış değer bit düzeyinde OR işleci kullanılarak birleştirilebilir. `m_cf.Flag`S yapı üyesini değiştirirseniz, varsayılan davranışı dokunulmadan korumak için değişikliklerinizin bit DÜZEYINDE veya işlecini kullandığınızdan emin olun. Bu bayrakların her biri hakkında ayrıntılar için Windows SDK [CHOOSEFONT](/windows/win32/api/commdlg/ns-commdlg-choosefontw) yapısının açıklamasına bakın.

*pdcPrinter*<br/>
Yazıcı-cihaz bağlamına yönelik bir işaretçi. Bu parametre, belirtilmişse, üzerine yazı tiplerinin seçildiği yazıcı için bir yazıcı cihazı bağlamını işaret eder.

*pParentWnd*<br/>
Yazı tipi iletişim kutusunun üst veya sahip penceresi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Oluşturucunun, yapının üyelerini otomatik olarak doldurduğunu unutmayın `CHOOSEFONT` . Bunu yalnızca, varsayılandan farklı bir yazı tipi iletişim kutusu istiyorsanız değiştirmelisiniz.

> [!NOTE]
> Bu işlevin ilk sürümü yalnızca zengin düzenleme denetimi desteği olmadığında bulunur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#78](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]

## <a name="cfontdialogdomodal"></a><a name="domodal"></a> CFontDialog::D oModal

Windows ortak yazı tipi iletişim kutusunu göstermek ve kullanıcının bir yazı tipi seçmesine izin vermek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

IDOK veya ıDCANCEL. IDCANCEL döndürülürse, bir hatanın oluşup oluşmadığını öğrenmek için Windows [Commıdextendebir](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini çağırın.

IDOK ve ıDCANCEL, kullanıcının Tamam veya Iptal düğmesini seçip seçmediğini belirten sabitlerdir.

### <a name="remarks"></a>Açıklamalar

[M_cf](#m_cf) yapısının üyelerini ayarlayarak çeşitli yazı tipi iletişim denetimlerini başlatmak isterseniz, bunu çağırmadan önce `DoModal` , ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir.

`DoModal`IDOK döndürürse, Kullanıcı tarafından ayarları veya bilgi girişini iletişim kutusuna almak için diğer üye işlevlerini çağırabilirsiniz.

### <a name="example"></a>Örnek

  [CFontDialog:: CFontDialog](#cfontdialog) ve [CFontDialog:: GetColor](#getcolor)örneklerine bakın.

## <a name="cfontdialoggetcharformat"></a><a name="getcharformat"></a> CFontDialog:: GetCharFormat

Seçili yazı tipinin karakter biçimlendirmesini alır.

```cpp
void GetCharFormat(CHARFORMAT& cf) const;
```

### <a name="parameters"></a>Parametreler

*CF*<br/>
Seçili yazı tipinin karakter biçimlendirmesi hakkında bilgi içeren bir [Charformat](/windows/win32/api/richedit/ns-richedit-charformata) yapısı.

## <a name="cfontdialoggetcolor"></a><a name="getcolor"></a> CFontDialog:: GetColor

Seçilen yazı tipi rengini almak için bu işlevi çağırın.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçilen yazı tipinin rengi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#79](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]

## <a name="cfontdialoggetcurrentfont"></a><a name="getcurrentfont"></a> CFontDialog:: GetCurrentFont

Şu anda seçili olan yazı tipinin özelliklerini [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısının üyelerine atamak için bu işlevi çağırın.

```cpp
void GetCurrentFont(LPLOGFONT lplf);
```

### <a name="parameters"></a>Parametreler

*lplf*<br/>
Bir yapıya yönelik işaretçi `LOGFONT` .

### <a name="remarks"></a>Açıklamalar

`CFontDialog`Geçerli yazı tipinin tek özelliklerine erişmek için diğer üye işlevleri sağlanır.

Bu işlev, [DoModal](#domodal)çağrısı sırasında çağrılırsa, geçerli seçimi (kullanıcının iletişim kutusunda gördüğü veya değiştiği) döndürür. Bu işlev bir çağrısından sonra çağrılırsa `DoModal` (yalnızca `DoModal` IDOK döndürürse), kullanıcının gerçekten seçili olduğunu döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#80](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]

## <a name="cfontdialoggetfacename"></a><a name="getfacename"></a> CFontDialog:: GetFaceName

Seçilen yazı tipinin yüz adını almak için bu işlevi çağırın.

```
CString GetFaceName() const;
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunda seçilen yazı tipinin yüz adı `CFontDialog` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#81](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]

## <a name="cfontdialoggetsize"></a><a name="getsize"></a> CFontDialog:: GetSize

Seçilen yazı tipinin boyutunu almak için bu işlevi çağırın.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazı tipinin, bir noktanın onda boyutu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#82](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]

## <a name="cfontdialoggetstylename"></a><a name="getstylename"></a> CFontDialog:: GetStyleName

Seçili yazı tipinin stil adını almak için bu işlevi çağırın.

```
CString GetStyleName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazı tipinin stil adı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#83](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]

## <a name="cfontdialoggetweight"></a><a name="getweight"></a> CFontDialog:: GetWeight

Seçilen yazı tipinin ağırlığını almak için bu işlevi çağırın.

```
int GetWeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçilen yazı tipinin ağırlığı.

### <a name="remarks"></a>Açıklamalar

Bir yazı tipinin ağırlığı hakkında daha fazla bilgi için bkz. [CFont:: CreateFont](../../mfc/reference/cfont-class.md#createfont).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#84](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]

## <a name="cfontdialogisbold"></a><a name="isbold"></a> CFontDialog:: IsBold

Seçilen yazı tipinin kalın olup olmadığını öğrenmek için bu işlevi çağırın.

```
BOOL IsBold() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipinin kalın özelliği etkinse sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#85](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]

## <a name="cfontdialogisitalic"></a><a name="isitalic"></a> CFontDialog:: ısitalik

Seçili yazı tipinin italik olup olmadığını öğrenmek için bu işlevi çağırın.

```
BOOL IsItalic() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipi Italik özelliği etkinse sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#86](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]

## <a name="cfontdialogisstrikeout"></a><a name="isstrikeout"></a> CFontDialog:: ısüstü çizili

Seçili yazı tipinin üstü çizili ile görüntülenip görüntülenmediğini öğrenmek için bu işlevi çağırın.

```
BOOL IsStrikeOut() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipinin üstü çizili özelliği etkinse sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#87](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]

## <a name="cfontdialogisunderline"></a><a name="isunderline"></a> CFontDialog:: ısaltıya

Seçili yazı tipinin altı çizili olup olmadığını öğrenmek için bu işlevi çağırın.

```
BOOL IsUnderline() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipinin altı çizili özelliği etkinse sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#88](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]

## <a name="cfontdialogm_cf"></a><a name="m_cf"></a> CFontDialog:: m_cf

Üyeleri iletişim kutusu nesnesinin özelliklerini depolayan bir yapı.

```
CHOOSEFONT m_cf;
```

### <a name="remarks"></a>Açıklamalar

Bir nesne oluşturduktan sonra `CFontDialog` , `m_cf` üye işlevini çağırmadan önce iletişim kutusunun çeşitli yönlerini değiştirmek için kullanabilirsiniz `DoModal` . Bu yapı hakkında daha fazla bilgi için Windows SDK [CHOOSEFONT](/windows/win32/api/commdlg/ns-commdlg-choosefontw) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#89](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
