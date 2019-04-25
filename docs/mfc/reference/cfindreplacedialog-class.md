---
title: CFindReplaceDialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
helpviewer_keywords:
- CFindReplaceDialog [MFC], CFindReplaceDialog
- CFindReplaceDialog [MFC], Create
- CFindReplaceDialog [MFC], FindNext
- CFindReplaceDialog [MFC], GetFindString
- CFindReplaceDialog [MFC], GetNotifier
- CFindReplaceDialog [MFC], GetReplaceString
- CFindReplaceDialog [MFC], IsTerminating
- CFindReplaceDialog [MFC], MatchCase
- CFindReplaceDialog [MFC], MatchWholeWord
- CFindReplaceDialog [MFC], ReplaceAll
- CFindReplaceDialog [MFC], ReplaceCurrent
- CFindReplaceDialog [MFC], SearchDown
- CFindReplaceDialog [MFC], m_fr
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
ms.openlocfilehash: de48d8f495802bdf1c5f69e7a4edc41153c9599f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206019"
---
# <a name="cfindreplacedialog-class"></a>CFindReplaceDialog sınıfı

Standart dize Bul/Değiştir iletişim kutuları uygulamanıza olanak sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFindReplaceDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|Oluşturmak için bu işlevi çağırın bir `CFindReplaceDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFindReplaceDialog::Create](#create)|Oluşturur ve görüntüler bir `CFindReplaceDialog` iletişim kutusu.|
|[CFindReplaceDialog::FindNext](#findnext)|Sonrakini Bul dizesi bulmak kullanıcının istediği olup olmadığını belirlemek için bu işlevi çağırın.|
|[CFindReplaceDialog::GetFindString](#getfindstring)|Geçerli bulma dizesini almak için bu işlevi çağırın.|
|[CFindReplaceDialog::GetNotifier](#getnotifier)|Almak için bu işlevi çağırın `FINDREPLACE` yapısında, kayıtlı bir ileti işleyicisi.|
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|Geçerli değiştirme dizesini almak için bu işlevi çağırın.|
|[CFindReplaceDialog::IsTerminating](#isterminating)|İletişim kutusu sonlandırma olup olmadığını belirlemek için bu işlevi çağırın.|
|[CFindReplaceDialog::MatchCase](#matchcase)|Kullanıcı Bul dizenin biçimi tam olarak eşleşmesi isteyip istemediğini belirlemek için bu işlevi çağırın.|
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|Kullanıcı yalnızca tüm sözcükleri eşleştirmeyi isteyip istemediğini belirlemek için bu işlevi çağırın.|
|[CFindReplaceDialog::ReplaceAll](#replaceall)|Kullanıcının değiştirilecek dizenin tüm oluşumlarını istediği olup olmadığını belirlemek için bu işlevi çağırın.|
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|Kullanıcının değiştirilmesi geçerli kelimenin istediği olup olmadığını belirlemek için bu işlevi çağırın.|
|[CFindReplaceDialog::SearchDown](#searchdown)|Kullanıcı Arama aşağı yönde devam etmek isteyip istemediğini belirlemek için bu işlevi çağırın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CFindReplaceDialog::m_fr](#m_fr)|Özelleştirmek için kullanılan bir yapının bir `CFindReplaceDialog` nesne.|

## <a name="remarks"></a>Açıklamalar

Diğer Windows ortak iletişim kutuları, farklı `CFindReplaceDialog` nesnelerdir geçici, kullanıcıların ekranda sırasında diğer windows ile etkileşim kurmasına izin verme. İki tür vardır, `CFindReplaceDialog` nesneler: İletişim kutuları ve Bul/Değiştir iletişim kutuları bulun. Kullanıcı Giriş arama ve arama/yer değiştirme dizeleri için iletişim kutularını izin verse de, bunlar herhangi bir arama veya değiştirme işlevleri gerçekleştirmeyin. Bu uygulamaya eklemeniz gerekir.

Oluşturmak için bir `CFindReplaceDialog` nesne, (herhangi bir bağımsız değişken olan) sağlanan bir oluşturucu kullanın. Bu modsuz iletişim kutusu olduğundan, nesne yığını kullanarak şirket ayrılamadı **yeni** işleç yerine yığında.

Bir kez bir `CFindReplaceDialog` nesne oluşturulur, çağırmalısınız [Oluştur](#create) oluşturmak ve iletişim kutusunu görüntülemek için üye işlevi.

Kullanım [m_fr](#m_fr) çağırmadan önce iletişim kutusunu başlatmak için yapı `Create`. `m_fr` Yapısıdır türünü [FINDREPLACE](/windows/desktop/api/commdlg/ns-commdlg-tagfindreplacea). Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.

Ana pencereyi Bul/Değiştir isteklerini almak için sırada Windows kullanmalısınız [RegisterWindowMessage](/windows/desktop/api/winuser/nf-winuser-registerwindowmessagea) işlev ve kullanmak [on_regıstered_message](message-map-macros-mfc.md#on_registered_message) çerçeveniz içinde ileti eşleme makrosu Bu kayıtlı ileti işler penceresini açın.

Kullanıcı iletişim kutusu sonlandırmak verdi olup olmadığını belirlemek `IsTerminating` üye işlevi.

`CFindReplaceDialog` üzerinde COMMDLG kullanır. Windows 3.1 ve sonraki sürümleri ile birlikte gelen DLL dosyası.

Özelleştir iletişim kutusu için öğesinden bir sınıf türetin `CFindReplaceDialog`, bir özel iletişim şablonu sağlar ve genişletilmiş denetimlerden bildirim iletilerini işlemek için ileti eşlemesi ekleyin. İşlenmemiş tüm iletiler için temel sınıf geçirilmelidir.

Kanca işlevini özelleştirme gerekli değildir.

Kullanma hakkında daha fazla bilgi için `CFindReplaceDialog`, bkz: [ortak iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFindReplaceDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdlgs.h

##  <a name="cfindreplacedialog"></a>  CFindReplaceDialog::CFindReplaceDialog

Oluşturur bir `CFindReplaceDialog` nesne.

```
CFindReplaceDialog();
```

### <a name="remarks"></a>Açıklamalar

Çünkü `CFindReplaceDialog` nesnesinin modsuz iletişim kutusu, kullanarak, yığında oluşturmalıdır **yeni** işleci.

Yok etme sırasında framework gerçekleştirmeye bir **bu silme** işaretçinin iletişim kutusu. İletişim kutusu yığına oluşturduysanız **bu** işaretçi yok ve tanımsız davranışa neden olabilir.

Oluşumu hakkında daha fazla bilgi için `CFindReplaceDialog` nesneleri bkz [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) genel bakış. Kullanım [CFindReplaceDialog::Create](#create) iletişim kutusunu görüntülemek için üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]

##  <a name="create"></a>  CFindReplaceDialog::Create

Oluşturur ve Bul veya Bul/Değiştir iletişim kutusu nesnesini değerine bağlı olarak görüntüler `bFindDialogOnly`.

```
virtual BOOL Create(
    BOOL bFindDialogOnly,
    LPCTSTR lpszFindWhat,
    LPCTSTR lpszReplaceWith = NULL,
    DWORD dwFlags = FR_DOWN,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*bFindDialogOnly*<br/>
Bu parametre görüntülemek için TRUE olarak ayarlanmış bir **Bul** iletişim kutusu. Görüntülemek için FALSE olarak ayarlanmış bir **Bul/Değiştir** iletişim kutusu.

*lpszFindWhat*<br/>
İletişim kutusu görüntülendiğinde varsayılan arama dizeye yönelik işaretçi. NULL ise, iletişim kutusunda varsayılan arama dizesini içermiyor.

*lpszReplaceWith*<br/>
İletişim kutusu görüntülendiğinde varsayılan değiştirilen dizeye yönelik işaretçi. NULL ise varsayılan bir değiştirme dizesi iletişim kutusu içermiyor.

*CertOpenStore*<br/>
Bit düzeyinde OR işleci kullanılarak birleştirilen iletişim kutusunun ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayraklar. Arama aşağı yönde devam etmek üzere olduğunu belirten FR_DOWN varsayılan değerdir. Bkz: [FINDREPLACE](/windows/desktop/api/commdlg/ns-commdlg-tagfindreplacea) yapısı içinde bu bayraklar hakkında daha fazla bilgi için Windows SDK'sı.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresine bir işaretçi. Bu bulma/değiştirme eylemi istenip istenmediğini belirten özel ileti alacak penceredir. NULL ise, uygulamanın ana pencere kullanılır.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu nesne başarıyla oluşturuldu olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Ana pencereyi Bul/Değiştir isteklerini almak için sırada Windows kullanmalısınız [RegisterWindowMessage](/windows/desktop/api/winuser/nf-winuser-registerwindowmessagea) işlevi dönüş değeri olan uygulama örneği için benzersiz bir ileti numarası. Geri çağırma işlevi bildiren bir ileti eşleme girişi, çerçeve penceresi olmalıdır ( `OnFindReplace` örnekte) kayıtlı bu iletiyi işleyen. Aşağıdaki kod parçası adlı bir çerçeve penceresi sınıfı için bunun nasıl yapılacağını örneğidir `CMyRichEditView`:

[!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]

[!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]

[!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]

İçinde `OnFindReplace` işlevini kullanarak kullanıcının amaçları yorumlama [CFindReplaceDialog::FindNext](#findnext) ve [CFindReplaceDialog::IsTerminating](#isterminating) yöntemleri ve kod oluşturma Bul/Değiştir işlemleri için.

### <a name="example"></a>Örnek

  Örneğin bakın [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).

##  <a name="findnext"></a>  CFindReplaceDialog::FindNext

Kullanıcı arama dizesinin sonraki oluşumunu bulur isteyip istemediğini belirlemek için geri çağırma işlevinizden bu işlevi çağırın.

```
BOOL FindNext() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arama dizesinin sonraki oluşumunu bulmak kullanıcının istediği olursa sıfır dışı; Aksi durumda 0.

##  <a name="getfindstring"></a>  CFindReplaceDialog::GetFindString

Bu işlevi bulmak için varsayılan dizesini almak için geri çağırma işlevini çağırın.

```
CString GetFindString() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulmak için varsayılan dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

##  <a name="getnotifier"></a>  CFindReplaceDialog::GetNotifier

Geçerli Bul Değiştir iletişim kutusu için bir işaretçi almak için bu işlevi çağırın.

```
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*lParam*<br/>
*Lparam* çerçeve penceresinin için geçirilen değer `OnFindReplace` üye işlevi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli iletişim kutusu için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu, geri çağırma işlevi içinde kullanılması gereken geçerli iletişim kutusuna erişmek için kendi üye işlevleri ve erişim çağırın `m_fr` yapısı.

### <a name="example"></a>Örnek

Bkz: [CFindReplaceDialog::Create](#create) Bul Değiştir iletişim kutusundan bildirimleri almak için OnFindReplace işleyicisini kaydetmek bir örnek.

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

##  <a name="getreplacestring"></a>  CFindReplaceDialog::GetReplaceString

Geçerli değiştirme dizesini almak için bu işlevi çağırın.

```
CString GetReplaceString() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birlikte bulunan dizeleri değiştirmek varsayılan dize.

### <a name="example"></a>Örnek

  Örneğin bakın [CFindReplaceDialog::GetFindString](#getfindstring).

##  <a name="isterminating"></a>  CFindReplaceDialog::IsTerminating

Kullanıcı iletişim kutusu sonlandırmak verdi olup olmadığını belirlemek için geri çağırma işlevi içinde bu işlevi çağırın.

```
BOOL IsTerminating() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı iletişim kutusu sonlandırmak verdi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, sıfır dışı döndürürse, çağırmalıdır `DestroyWindow` üye işlevi geçerli iletişim kutusunu ve tüm iletişim kutusu işaretçi değişkeninin NULL olarak ayarlayın. İsteğe bağlı olarak, ayrıca en son girilen Bul/Değiştir metin depolamak ve sonraki Bul/Değiştir iletişim kutusunu başlatmak için kullanın.

### <a name="example"></a>Örnek

  Örneğin bakın [CFindReplaceDialog::GetFindString](#getfindstring).

##  <a name="m_fr"></a>  CFindReplaceDialog::m_fr

Özelleştirmek için kullanılan bir `CFindReplaceDialog` nesne.

```
FINDREPLACE m_fr;
```

### <a name="remarks"></a>Açıklamalar

`m_fr` bir yapı türü [FINDREPLACE](/windows/desktop/api/commdlg/ns-commdlg-tagfindreplacea). Özellikleri iletişim kutusu nesnesinin üyeleri depolayın. Oluşturma sonrasında bir `CFindReplaceDialog` nesne kullanabileceğiniz `m_fr` iletişim kutusunda çeşitli değerleri değiştirmek için.

Bu yapı hakkında daha fazla bilgi için bkz. `FINDREPLACE` Windows SDK'sındaki yapısı.

### <a name="example"></a>Örnek

  Örneğin bakın [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).

##  <a name="matchcase"></a>  CFindReplaceDialog::MatchCase

Kullanıcı Bul dizenin biçimi tam olarak eşleşmesi isteyip istemediğini belirlemek için bu işlevi çağırın.

```
BOOL MatchCase() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arama dizesinin tam olarak harf arama dizesinin oluşumlarını bulmak kullanıcının istediği olursa sıfır dışı; Aksi durumda 0.

##  <a name="matchwholeword"></a>  CFindReplaceDialog::MatchWholeWord

Kullanıcı yalnızca tüm sözcükleri eşleştirmeyi isteyip istemediğini belirlemek için bu işlevi çağırın.

```
BOOL MatchWholeWord() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcının yalnızca arama dizesinin tüm sözcükleri eşleştirmeyi istediği olursa sıfır dışı; Aksi durumda 0.

##  <a name="replaceall"></a>  CFindReplaceDialog::ReplaceAll

Kullanıcının değiştirilecek dizenin tüm oluşumlarını istediği olup olmadığını belirlemek için bu işlevi çağırın.

```
BOOL ReplaceAll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı değiştirme dizesi ile eşleşen tüm dizeleri değiştirilmesi isteğinde olursa sıfır dışı; Aksi durumda 0.

##  <a name="replacecurrent"></a>  CFindReplaceDialog::ReplaceCurrent

Kullanıcının değiştirilmesi geçerli kelimenin istediği olup olmadığını belirlemek için bu işlevi çağırın.

```
BOOL ReplaceCurrent() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı şu anda seçili dizeyi değiştirme dizesi ile değiştirilmesi isteğinde olursa sıfır dışı; Aksi durumda 0.

##  <a name="searchdown"></a>  CFindReplaceDialog::SearchDown

Kullanıcı Arama aşağı yönde devam etmek isteyip istemediğini belirlemek için bu işlevi çağırın.

```
BOOL SearchDown() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı aşağı yönde devam etmek için arama isterse sıfır; Kullanıcı bir yukarı yönde devam etmek için arama isterse 0.

## <a name="see-also"></a>Ayrıca bkz.

[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
