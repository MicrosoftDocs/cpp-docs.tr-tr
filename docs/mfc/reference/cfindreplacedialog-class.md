---
description: 'Daha fazla bilgi edinin: CFindReplaceDialog sınıfı'
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
ms.openlocfilehash: 3deeb485a9048ba986f548ed66329b66bd039c08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184484"
---
# <a name="cfindreplacedialog-class"></a>CFindReplaceDialog sınıfı

Uygulamanızda standart dize Bul/Değiştir iletişim kutuları uygulamanıza olanak tanır.

## <a name="syntax"></a>Syntax

```
class CFindReplaceDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFindReplaceDialog:: CFindReplaceDialog](#cfindreplacedialog)|Bir nesne oluşturmak için bu işlevi çağırın `CFindReplaceDialog` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFindReplaceDialog:: Create](#create)|Bir iletişim kutusu oluşturur ve görüntüler `CFindReplaceDialog` .|
|[CFindReplaceDialog:: Sonrabul](#findnext)|Kullanıcının bulma dizesinin bir sonraki oluşumunu bulmak isteyip istemediğini öğrenmek için bu işlevi çağırın.|
|[CFindReplaceDialog:: GetFindString](#getfindstring)|Geçerli bulma dizesini almak için bu işlevi çağırın.|
|[CFindReplaceDialog:: Getbildiricisi](#getnotifier)|`FINDREPLACE`Kayıtlı ileti işleyicinizdeki yapıyı almak için bu işlevi çağırın.|
|[CFindReplaceDialog:: GetReplaceString](#getreplacestring)|Geçerli değiştirme dizesini almak için bu işlevi çağırın.|
|[CFindReplaceDialog:: ısating](#isterminating)|İletişim kutusunun sonlandıranıp sonlandırılmadığını öğrenmek için bu işlevi çağırın.|
|[CFindReplaceDialog:: MatchCase](#matchcase)|Kullanıcının bul dizesinin durumunu tam olarak eşleştirmek isteyip istemediğini öğrenmek için bu işlevi çağırın.|
|[CFindReplaceDialog:: MatchWholeWord](#matchwholeword)|Kullanıcının yalnızca tüm sözcükleri eşleştirmek isteyip istemediğini öğrenmek için bu işlevi çağırın.|
|[CFindReplaceDialog:: ReplaceAll](#replaceall)|Kullanıcının dizenin tüm tekrarlarının değiştirilmesini isteyip istemediğini öğrenmek için bu işlevi çağırın.|
|[CFindReplaceDialog:: Replacececurkiralık](#replacecurrent)|Kullanıcının geçerli sözcüğün değiştirilmesini isteyip istemediğini öğrenmek için bu işlevi çağırın.|
|[CFindReplaceDialog:: SearchKey](#searchdown)|Kullanıcının aramanın aşağı doğru bir yönde devam etmesini isteyip istemediğini öğrenmek için bu işlevi çağırın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CFindReplaceDialog:: m_fr](#m_fr)|Bir nesneyi özelleştirmek için kullanılan bir yapı `CFindReplaceDialog` .|

## <a name="remarks"></a>Açıklamalar

Diğer Windows ortak iletişim kutularının aksine `CFindReplaceDialog` nesneler modsuz olduğundan, kullanıcıların ekrandayken diğer pencereler ile etkileşime geçmesini sağlar. İki tür `CFindReplaceDialog` nesne vardır: iletişim kutularını bul ve Bul/Değiştir iletişim kutuları. İletişim kutuları kullanıcının arama ve arama/değiştirme dizelerini eklemesine izin verse de, arama veya değiştirme işlevlerini gerçekleştirmez. Bunları uygulamaya eklemeniz gerekir.

Bir nesne oluşturmak için `CFindReplaceDialog` , sunulan oluşturucuyu (bağımsız değişken olmayan) kullanın. Bu engelleyici olmayan bir iletişim kutusu olduğundan, nesneyi yığında değil işlecini kullanarak yığında ayırın **`new`** .

Bir nesne oluşturulduktan sonra `CFindReplaceDialog` iletişim kutusunu oluşturmak ve göstermek için üye [Oluştur](#create) işlevini çağırmanız gerekir.

' İ çağırmadan önce iletişim kutusunu başlatmak için [m_fr](#m_fr) yapısını kullanın `Create` . `m_fr`Yapı [FindReplace](/windows/win32/api/commdlg/ns-commdlg-findreplacew)türüdür. Bu yapı hakkında daha fazla bilgi için Windows SDK bakın.

Üst pencereye Bul/Değiştir isteklerinin bildirilmesi için, Windows [RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew) işlevini kullanmanız ve bu kayıtlı iletiyi işleyen çerçeve pencerenizde [ON_REGISTERED_MESSAGE](message-map-macros-mfc.md#on_registered_message) ileti eşleme makrosunu kullanmanız gerekir.

Kullanıcının, iletişim kutusunu üye işleviyle sonlandırmayı kararması olup olmadığını belirleyebilirsiniz `IsTerminating` .

`CFindReplaceDialog` , 3,1 ve üzeri Windows sürümleriyle birlikte gelen COMMDLG.DLL dosyasını kullanır.

İletişim kutusunu özelleştirmek için, öğesinden bir sınıf türetebilir `CFindReplaceDialog` , özel bir iletişim kutusu şablonu sağlayın ve genişletilmiş denetimlerden gelen bildirim iletilerini işlemek için bir ileti eşlemesi ekleyin. İşlenmemiş tüm iletiler taban sınıfına geçirilmelidir.

Kanca işlevinin özelleştirilmesi gerekli değildir.

Kullanma hakkında daha fazla bilgi için `CFindReplaceDialog` bkz. [ortak Iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[Ccommoniletişim kutusu](../../mfc/reference/ccommondialog-class.md)

`CFindReplaceDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs. h

## <a name="cfindreplacedialogcfindreplacedialog"></a><a name="cfindreplacedialog"></a> CFindReplaceDialog:: CFindReplaceDialog

Bir `CFindReplaceDialog` nesnesi oluşturur.

```
CFindReplaceDialog();
```

### <a name="remarks"></a>Açıklamalar

`CFindReplaceDialog`Nesnesi kalıcı olmayan bir iletişim kutusu olduğundan, işlecini kullanarak yığın üzerinde oluşturmanız gerekir **`new`** .

Yok etme sırasında, çerçeve iletişim kutusu işaretçisi üzerinde **bunu silme** işlemini gerçekleştirmeye çalışır. Yığın üzerinde iletişim kutusunu oluşturduysanız **`this`** işaretçi yok ve tanımsız davranış ortaya çıkabilir.

Nesnelerin oluşturulması hakkında daha fazla bilgi için `CFindReplaceDialog` bkz. [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) genel bakış. İletişim kutusunu göstermek için [CFindReplaceDialog:: Create](#create) member işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]

## <a name="cfindreplacedialogcreate"></a><a name="create"></a> CFindReplaceDialog:: Create

Değerine bağlı olarak bir bul veya Bul/Değiştir iletişim kutusu nesnesi oluşturur ve görüntüler `bFindDialogOnly` .

```
virtual BOOL Create(
    BOOL bFindDialogOnly,
    LPCTSTR lpszFindWhat,
    LPCTSTR lpszReplaceWith = NULL,
    DWORD dwFlags = FR_DOWN,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*yalnızca bfinddialog*<br/>
Bir **bul** iletişim kutusunu göstermek için bu parametreyi true olarak ayarlayın. **Bul/Değiştir** iletişim kutusunu göstermek IÇIN bu değeri false olarak ayarlayın.

*lpszFindWhat*<br/>
İletişim kutusu göründüğünde varsayılan arama dizesinin işaretçisi. NULL ise, iletişim kutusu varsayılan arama dizesi içermez.

*lpszReplaceWith*<br/>
İletişim kutusu göründüğünde varsayılan değiştirme dizesinin işaretçisi. NULL ise, iletişim kutusu varsayılan bir değiştirme dizesi içermez.

*dwFlags*<br/>
Bit düzeyinde OR işleci kullanılarak birleştirilen iletişim kutusunun ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayrak. Varsayılan değer FR_DOWN, aramanın aşağı yönde devam etmek için olduğunu belirtir. Bu bayraklar hakkında daha fazla bilgi için Windows SDK [FindReplace](/windows/win32/api/commdlg/ns-commdlg-findreplacew) yapısına bakın.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresine yönelik bir işaretçi. Bu, bir Bul/Değiştir eyleminin istendiğini belirten özel iletiyi alacak olan penceresidir. NULL ise uygulamanın ana penceresi kullanılır.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu nesnesi başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Üst pencereye Bul/Değiştir isteklerinin bildirilmesi için, dönüş değeri uygulamanın örneğine özgü bir ileti numarası olan Windows [RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew) işlevini kullanmanız gerekir. Çerçeve pencerenizin, `OnFindReplace` Bu kayıtlı iletiyi işleyen geri çağırma işlevini (aşağıdaki örnekte) bildiren bir ileti eşleme girişi olmalıdır. Aşağıdaki kod parçası, şunu adlı bir çerçeve penceresi sınıfı için bunun nasıl yapılacağını gösteren bir örnektir `CMyRichEditView` :

[!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]

[!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]

[!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]

`OnFindReplace`İşlevinizde [CFindReplaceDialog:: sonrakini](#findnext) ve [CFindReplaceDialog:: ısating](#isterminating) yöntemlerini kullanarak kullanıcının amaçları 'nı yorumlayıp bulma/değiştirme işlemleri için kodu oluşturursunuz.

### <a name="example"></a>Örnek

  [CFindReplaceDialog:: CFindReplaceDialog](#cfindreplacedialog)örneğine bakın.

## <a name="cfindreplacedialogfindnext"></a><a name="findnext"></a> CFindReplaceDialog:: Sonrabul

Kullanıcının arama dizesinin bir sonraki tekrarını bulmak isteyip istemediğini öğrenmek için bu işlevi geri çağırma işlevinizden çağırın.

```
BOOL FindNext() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı, arama dizesinin bir sonraki tekrarını bulmak isterse sıfır dışı. Aksi takdirde 0.

## <a name="cfindreplacedialoggetfindstring"></a><a name="getfindstring"></a> CFindReplaceDialog:: GetFindString

Bulunacak varsayılan dizeyi almak için bu işlevi geri çağırma işlevinizden çağırın.

```
CString GetFindString() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunacak varsayılan dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

## <a name="cfindreplacedialoggetnotifier"></a><a name="getnotifier"></a> CFindReplaceDialog:: Getbildiricisi

Geçerli Bul Değiştir iletişim kutusuna bir işaretçi almak için bu işlevi çağırın.

```
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*lParam*<br/>
Çerçeve penceresinin üye işlevine geçirilen *lParam* değeri `OnFindReplace` .

### <a name="return-value"></a>Dönüş Değeri

Geçerli iletişim kutusu işaretçisi.

### <a name="remarks"></a>Açıklamalar

Geçerli iletişim kutusuna erişmek, üye işlevlerini çağırmak ve yapıya erişmek için geri çağırma işlevinizde kullanılması gerekir `m_fr` .

### <a name="example"></a>Örnek

Değiştirme yerini bul iletişim kutusundan bildirimleri almak için OnFindReplace işleyicisinin nasıl kaydedileceği hakkında bir örnek için bkz. [CFindReplaceDialog:: Create](#create) .

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

## <a name="cfindreplacedialoggetreplacestring"></a><a name="getreplacestring"></a> CFindReplaceDialog:: GetReplaceString

Geçerli değiştirme dizesini almak için bu işlevi çağırın.

```
CString GetReplaceString() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunan dizelerin yerine geçecek varsayılan dize.

### <a name="example"></a>Örnek

  [CFindReplaceDialog:: GetFindString](#getfindstring)örneğine bakın.

## <a name="cfindreplacedialogisterminating"></a><a name="isterminating"></a> CFindReplaceDialog:: ısating

Kullanıcının iletişim kutusunu sonlandırmaya karar verip içermediğini öğrenmek için bu işlevi geri çağırma işlevinizde çağırın.

```
BOOL IsTerminating() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı iletişim kutusunu sonlandırmayı kararmışsa sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev sıfır dışında bir değer döndürürse, `DestroyWindow` geçerli iletişim kutusunun üye işlevini çağırmanız ve iletişim kutusu işaretçisi DEĞIŞKENINI null olarak ayarlamanız gerekir. İsteğe bağlı olarak, Bul/Değiştir metnini de saklayabilir ve sonraki Bul/Değiştir iletişim kutusunu başlatmak için onu kullanabilirsiniz.

### <a name="example"></a>Örnek

  [CFindReplaceDialog:: GetFindString](#getfindstring)örneğine bakın.

## <a name="cfindreplacedialogm_fr"></a><a name="m_fr"></a> CFindReplaceDialog:: m_fr

Bir nesneyi özelleştirmek için kullanılır `CFindReplaceDialog` .

```
FINDREPLACE m_fr;
```

### <a name="remarks"></a>Açıklamalar

`m_fr` , [FindReplace](/windows/win32/api/commdlg/ns-commdlg-findreplacew)türünde bir yapıdır. Üyeleri iletişim kutusu nesnesinin özelliklerini depolar. Bir nesne oluşturduktan sonra `CFindReplaceDialog` `m_fr` iletişim kutusundaki çeşitli değerleri değiştirmek için kullanabilirsiniz.

Bu yapı hakkında daha fazla bilgi için `FINDREPLACE` Windows SDK yapıya bakın.

### <a name="example"></a>Örnek

  [CFindReplaceDialog:: CFindReplaceDialog](#cfindreplacedialog)örneğine bakın.

## <a name="cfindreplacedialogmatchcase"></a><a name="matchcase"></a> CFindReplaceDialog:: MatchCase

Kullanıcının bul dizesinin durumunu tam olarak eşleştirmek isteyip istemediğini öğrenmek için bu işlevi çağırın.

```
BOOL MatchCase() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı, arama dizesinin durumuyla tam olarak eşleşen arama dizesinin tekrarlamalarını bulmak isterse sıfır dışında; Aksi takdirde 0.

## <a name="cfindreplacedialogmatchwholeword"></a><a name="matchwholeword"></a> CFindReplaceDialog:: MatchWholeWord

Kullanıcının yalnızca tüm sözcükleri eşleştirmek isteyip istemediğini öğrenmek için bu işlevi çağırın.

```
BOOL MatchWholeWord() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı yalnızca arama dizesinin tüm sözcüklerini eşleştirmek isterse, sıfır dışı. Aksi takdirde 0.

## <a name="cfindreplacedialogreplaceall"></a><a name="replaceall"></a> CFindReplaceDialog:: ReplaceAll

Kullanıcının dizenin tüm tekrarlarının değiştirilmesini isteyip istemediğini öğrenmek için bu işlevi çağırın.

```
BOOL ReplaceAll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı Değiştirme dizesiyle eşleşen tüm dizelerin değiştirilmesini istediyse sıfır dışında olur; Aksi takdirde 0.

## <a name="cfindreplacedialogreplacecurrent"></a><a name="replacecurrent"></a> CFindReplaceDialog:: Replacececurkiralık

Kullanıcının geçerli sözcüğün değiştirilmesini isteyip istemediğini öğrenmek için bu işlevi çağırın.

```
BOOL ReplaceCurrent() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı şu anda seçili dizenin değiştirme dizesiyle değiştirilmesini istediyse sıfır dışında; Aksi takdirde 0.

## <a name="cfindreplacedialogsearchdown"></a><a name="searchdown"></a> CFindReplaceDialog:: SearchKey

Kullanıcının aramanın aşağı doğru bir yönde devam etmesini isteyip istemediğini öğrenmek için bu işlevi çağırın.

```
BOOL SearchDown() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı aramanın aşağı doğru bir yönde devam etmesini istiyorsa sıfır dışı; Kullanıcı aramanın daha yukarı yönde devam etmesini istiyorsa 0.

## <a name="see-also"></a>Ayrıca bkz.

[CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
