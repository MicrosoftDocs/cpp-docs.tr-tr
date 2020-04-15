---
title: CFindReplaceDialog Sınıfı
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
ms.openlocfilehash: 7a12d0520d070d74afd9fa91e828970d14c82700
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373852"
---
# <a name="cfindreplacedialog-class"></a>CFindReplaceDialog Sınıfı

Uygulamanızda standart dize Bul/Değiştir iletişim kutularını uygulamanızı sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFindReplaceDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|Bir `CFindReplaceDialog` nesne oluşturmak için bu işlevi çağırın.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFindReplaceDialog::Oluştur](#create)|Bir `CFindReplaceDialog` iletişim kutusu oluşturur ve görüntüler.|
|[CFindReplaceDialog::FindNext](#findnext)|Kullanıcının bul dizesinin bir sonraki oluşumunu bulmak isteyip istemediğini belirlemek için bu işlevi arayın.|
|[CFindReplaceDialog::GetFindString](#getfindstring)|Geçerli bul dizesini almak için bu işlevi arayın.|
|[CFindReplaceDialog::GetNotifier](#getnotifier)|Kayıtlı ileti işleyicinizdeki yapıyı `FINDREPLACE` almak için bu işlevi arayın.|
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|Geçerli değiştirme dizesini almak için bu işlevi çağırın.|
|[CFindReplaceDialog::IsTerminating](#isterminating)|İletişim kutusunun sonlandırma olup olmadığını belirlemek için bu işlevi arayın.|
|[CFindReplaceDialog::MatchCase](#matchcase)|Kullanıcının bul dizesinin karşısına tam olarak uyacak olup olmadığını belirlemek için bu işlevi arayın.|
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|Kullanıcının yalnızca tüm sözcükleri eşleştirmek isteyip istemediğini belirlemek için bu işlevi arayın.|
|[CFindReplaceDialog::ReplaceAll](#replaceall)|Kullanıcının dizedeki tüm oluşumların değiştirilmesini isteyip istemediğini belirlemek için bu işlevi arayın.|
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|Kullanıcının geçerli sözcüğün değiştirilmesini isteyip istemediğini belirlemek için bu işlevi arayın.|
|[CFindReplaceDialog::SearchDown](#searchdown)|Kullanıcının aramanın aşağı yönde ilerlemesini isteyip istemediğini belirlemek için bu işlevi arayın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CFindReplaceDialog::m_fr](#m_fr)|Nesneyi özelleştirmek için `CFindReplaceDialog` kullanılan bir yapı.|

## <a name="remarks"></a>Açıklamalar

Diğer Windows ortak iletişim kutularının aksine, `CFindReplaceDialog` nesneler modsuzdur ve kullanıcıların ekrandayken diğer pencerelerle etkileşimkurmasını sağlar. İki tür `CFindReplaceDialog` nesne vardır: İletişim kutularını bulun ve iletişim kutularını bul/değiştir. İletişim kutuları kullanıcının arama ve arama/değiştirme dizeleri girişine/değiştirmesine izin vermesine rağmen, arama veya değiştirme işlevlerinin hiçbirini gerçekleştirmez. Bunları uygulamaya eklemeniz gerekir.

Bir `CFindReplaceDialog` nesne oluşturmak için, sağlanan oluşturucuyu (bağımsız değişkeni olmayan) kullanın. Bu modeless iletişim kutusu olduğundan, yığın yerine **yeni** işleci kullanarak yığın üzerinde nesne tahsis.

Bir `CFindReplaceDialog` nesne oluşturulduktan sonra, iletişim kutusunu oluşturmak ve görüntülemek için Üye [Oluştur](#create) işlevini aramanız gerekir.

Aramadan [m_fr](#m_fr) `Create`önce iletişim kutusunu başlatmak için m_fr yapısını kullanın. Yapısı `m_fr` [FINDREPLACE](/windows/win32/api/commdlg/ns-commdlg-findreplacew)türündedir. Bu yapı hakkında daha fazla bilgi için Windows SDK'ya bakın.

Üst pencerenin bul/değiştir isteklerihakkında bilgilendirilebilmesi için Windows [RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew) işlevini kullanmanız ve çerçeve pencerenizde bu kayıtlı iletiyi işleyen [ON_REGISTERED_MESSAGE](message-map-macros-mfc.md#on_registered_message) ileti-eşlemi makrounu kullanmanız gerekir.

Kullanıcının `IsTerminating` üye işlevle iletişim kutusunu sonlandırmaya karar verip vermediğini belirleyebilirsiniz.

`CFindReplaceDialog`COMMDLG'ye dayanır. DLL dosyası, Windows sürümleri 3.1 ve sonraki sürümlerle birlikte iletin.

İletişim kutusunu özelleştirmek için, bir sınıf `CFindReplaceDialog`türetin, özel bir iletişim şablonu sağlayın ve genişletilmiş denetimlerden gelen bildirim iletilerini işlemek için bir ileti eşlemi ekleyin. İşlenmemiş iletiler taban sınıfa geçirilmelidir.

Kanca işlevini özelleştirmek gerekli değildir.

Kullanma `CFindReplaceDialog`hakkında daha fazla bilgi için [Ortak İletişim Sınıfları'na](../../mfc/common-dialog-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFindReplaceDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs.h

## <a name="cfindreplacedialogcfindreplacedialog"></a><a name="cfindreplacedialog"></a>CFindReplaceDialog::CFindReplaceDialog

Bir `CFindReplaceDialog` nesne inşa eder.

```
CFindReplaceDialog();
```

### <a name="remarks"></a>Açıklamalar

`CFindReplaceDialog` Nesne modeless iletişim kutusu olduğundan, **yeni** işleci kullanarak yığın üzerinde oluşturmanız gerekir.

Yıkım sırasında, çerçeve iletişim kutusunuişaretçi üzerinde **bu silme** gerçekleştirmeye çalışır. Yığındaki iletişim kutusunu oluşturduysanız, **bu** işaretçi yok ve tanımlanmamış davranış neden olabilir.

`CFindReplaceDialog` Nesnelerin yapısı hakkında daha fazla bilgi için [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) genel bakış bölümüne bakın. [CFindReplaceDialog'u kullanın::İletişim](#create) kutusunu görüntülemek için üye işlev oluşturun.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]

## <a name="cfindreplacedialogcreate"></a><a name="create"></a>CFindReplaceDialog::Oluştur

'nin değerine bağlı olarak bir Bul veya Bul/Değiştir iletişim `bFindDialogOnly`kutusu nesnesi oluşturur ve görüntüler.

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
**Bul** iletişim kutusunu görüntülemek için bu parametreyi TRUE olarak ayarlayın. **Bul/Değiştir** iletişim kutusunu görüntülemek için FALSE olarak ayarlayın.

*lpszFindWhat*<br/>
İletişim kutusu göründüğünde varsayılan arama dizesini işaretleyin. NULL ise, iletişim kutusu varsayılan bir arama dizesi içermez.

*lpszReplaceWith*<br/>
İletişim kutusu göründüğünde varsayılan değiştirme dizesini işaretleyin. NULL ise, iletişim kutusu varsayılan bir değiştirme dizesi içermez.

*Dwflags*<br/>
Bitwise OR işleci kullanarak birlikte iletişim kutusunun ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayrak. Varsayılan değer, aramanın aşağı yönde ilerleyecek olduğunu belirten FR_DOWN. Bu bayraklar hakkında daha fazla bilgi için Windows SDK'daki [FINDREPLACE](/windows/win32/api/commdlg/ns-commdlg-findreplacew) yapısına bakın.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresiiçin bir işaretçi. Bu, bul/değiştir eyleminin istendiğini belirten özel ileti yi alacak penceredir. NULL ise, uygulamanın ana penceresi kullanılır.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu nesnesi başarıyla oluşturulduysa sıfıra değil; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Üst pencerenin bul/değiştir isteklerihakkında bilgilendirilebilmesi için, iade değeri uygulamaörneğine özgü bir ileti numarası olan Windows [RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew) işlevini kullanmanız gerekir. Çerçeve pencerenizde, bu kayıtlı iletiyi işleyen geri `OnFindReplace` arama işlevini (aşağıdaki örnekte) bildiren bir ileti eşlemi girişi olmalıdır. Aşağıdaki kod parçası adlı `CMyRichEditView`bir çerçeve penceresi sınıfı için bunu yapmak için nasıl bir örnektir:

[!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]

[!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]

[!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]

Işleviniz `OnFindReplace` dahilinde, [CFindReplaceDialog::FindNext](#findnext) ve [CFindReplaceDialog::IsTerminating](#isterminating) yöntemlerini kullanarak kullanıcının niyetlerini yorumlarsınız ve bulma/değiştirme işlemleri için kod oluşturursunuz.

### <a name="example"></a>Örnek

  [CFindReplaceDialog örneğine bakın:CFindReplaceDialog](#cfindreplacedialog).

## <a name="cfindreplacedialogfindnext"></a><a name="findnext"></a>CFindReplaceDialog::FindNext

Kullanıcının arama dizesinin bir sonraki oluşumunu bulmak isteyip istemediğini belirlemek için geri arama işlevinizden bu işlevi arayın.

```
BOOL FindNext() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı arama dizesinin bir sonraki oluşumunu bulmak istiyorsa sıfıra inme; aksi takdirde 0.

## <a name="cfindreplacedialoggetfindstring"></a><a name="getfindstring"></a>CFindReplaceDialog::GetFindString

Bulmak için varsayılan dize almak için geri arama işlevinden bu işlevi arayın.

```
CString GetFindString() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulmak için varsayılan dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

## <a name="cfindreplacedialoggetnotifier"></a><a name="getnotifier"></a>CFindReplaceDialog::GetNotifier

Geçerli Değiştir iletişim kutusunu bul için bir işaretçi almak için bu işlevi arayın.

```
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*Lparam*<br/>
Çerçeve penceresinin `OnFindReplace` üye işlevine geçirilen *lparam* değeri.

### <a name="return-value"></a>Dönüş Değeri

Geçerli iletişim kutusunun işaretçisi.

### <a name="remarks"></a>Açıklamalar

Geçerli iletişim kutusuna erişmek, üye işlevlerini aramak ve `m_fr` yapıya erişmek için geri arama işleviniz içinde kullanılmalıdır.

### <a name="example"></a>Örnek

Bkz. [CFindReplaceDialog::Değiştir'i](#create) Bul iletişim kutusundan bildirimler almak için OnFindReplace işleyicisini nasıl kaydedebilirsiniz bir örneği için oluşturun.

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

## <a name="cfindreplacedialoggetreplacestring"></a><a name="getreplacestring"></a>CFindReplaceDialog::GetReplaceString

Geçerli değiştirme dizesini almak için bu işlevi çağırın.

```
CString GetReplaceString() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunan dizeleri değiştirmek için varsayılan dize.

### <a name="example"></a>Örnek

  [CFindReplaceDialog örneğine bakın:GetFindString](#getfindstring).

## <a name="cfindreplacedialogisterminating"></a><a name="isterminating"></a>CFindReplaceDialog::IsTerminating

Kullanıcının iletişim kutusunu sonlandırmaya karar verip vermediğini belirlemek için geri arama işleviniz içinde bu işlevi arayın.

```
BOOL IsTerminating() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı iletişim kutusunu sonlandırmaya karar verdiyse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev sıfırsız dönerse, geçerli `DestroyWindow` iletişim kutusunun üye işlevini aramalı ve herhangi bir iletişim kutusu işaretçideğişkenini NULL'a ayarlamanız gerekir. İsteğe bağlı olarak, en son girilen metni bul/değiştir'i de saklayabilir ve bir sonraki bul/değiştir iletişim kutusunu açmak için kullanabilirsiniz.

### <a name="example"></a>Örnek

  [CFindReplaceDialog örneğine bakın:GetFindString](#getfindstring).

## <a name="cfindreplacedialogm_fr"></a><a name="m_fr"></a>CFindReplaceDialog::m_fr

Nesneyi `CFindReplaceDialog` özelleştirmek için kullanılır.

```
FINDREPLACE m_fr;
```

### <a name="remarks"></a>Açıklamalar

`m_fr`findreplace türünde [FINDREPLACE](/windows/win32/api/commdlg/ns-commdlg-findreplacew)bir yapıdır. Üyeleri iletişim kutusu nesnesinin özelliklerini saklar. Bir `CFindReplaceDialog` nesne yaptıktan sonra, `m_fr` iletişim kutusundaçeşitli değerleri değiştirmek için kullanabilirsiniz.

Bu yapı hakkında daha fazla `FINDREPLACE` bilgi için Windows SDK'daki yapıya bakın.

### <a name="example"></a>Örnek

  [CFindReplaceDialog örneğine bakın:CFindReplaceDialog](#cfindreplacedialog).

## <a name="cfindreplacedialogmatchcase"></a><a name="matchcase"></a>CFindReplaceDialog::MatchCase

Kullanıcının bul dizesinin karşısına tam olarak uyacak olup olmadığını belirlemek için bu işlevi arayın.

```
BOOL MatchCase() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı arama dizesinin arama dizesinin durumuyla tam olarak eşleşen oluşumları bulmak istiyorsa sıfır alamayacak; aksi takdirde 0.

## <a name="cfindreplacedialogmatchwholeword"></a><a name="matchwholeword"></a>CFindReplaceDialog::MatchWholeWord

Kullanıcının yalnızca tüm sözcükleri eşleştirmek isteyip istemediğini belirlemek için bu işlevi arayın.

```
BOOL MatchWholeWord() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı yalnızca arama dizesinin tüm sözcüklerini eşleştirmek istiyorsa sıfıra inme; aksi takdirde 0.

## <a name="cfindreplacedialogreplaceall"></a><a name="replaceall"></a>CFindReplaceDialog::ReplaceAll

Kullanıcının dizedeki tüm oluşumların değiştirilmesini isteyip istemediğini belirlemek için bu işlevi arayın.

```
BOOL ReplaceAll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı değiştirme dizeleriyle eşleşen tüm dizeleri değiştirilmesini istediyse sıfır olmayan; aksi takdirde 0.

## <a name="cfindreplacedialogreplacecurrent"></a><a name="replacecurrent"></a>CFindReplaceDialog::ReplaceCurrent

Kullanıcının geçerli sözcüğün değiştirilmesini isteyip istemediğini belirlemek için bu işlevi arayın.

```
BOOL ReplaceCurrent() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı, şu anda seçili dize değiştirip değiştirme dizesi ile değiştirilmesini talep ettiyse sıfır alamayın; aksi takdirde 0.

## <a name="cfindreplacedialogsearchdown"></a><a name="searchdown"></a>CFindReplaceDialog::SearchDown

Kullanıcının aramanın aşağı yönde ilerlemesini isteyip istemediğini belirlemek için bu işlevi arayın.

```
BOOL SearchDown() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı aramanın aşağı yönde ilerlemesini istiyorsa sıfıra inme; Kullanıcı aramanın yukarı yönde ilerlemesini istiyorsa 0.

## <a name="see-also"></a>Ayrıca bkz.

[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
