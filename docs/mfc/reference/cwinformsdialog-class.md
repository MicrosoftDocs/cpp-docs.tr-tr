---
title: CWinFormsDialog Sınıfı
ms.date: 03/27/2019
f1_keywords:
- CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::GetControl
- AFXWINFORMS/CWinFormsDialog::GetControlHandle
- AFXWINFORMS/CWinFormsDialog::OnInitDialog
helpviewer_keywords:
- CWinFormsDialog [MFC], CWinFormsDialog
- CWinFormsDialog [MFC], GetControl
- CWinFormsDialog [MFC], GetControlHandle
- CWinFormsDialog [MFC], OnInitDialog
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
ms.openlocfilehash: 3772033df59e065cedca61012cd479c812cf5b66
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367433"
---
# <a name="cwinformsdialog-class"></a>CWinFormsDialog Sınıfı

Windows Forms kullanıcı denetimini barındıran bir MFC iletişim sınıfı için sarıcı.

## <a name="syntax"></a>Sözdizimi

```
template <typename TManagedControl>
class CWinFormsDialog :
    public CDialog
```

#### <a name="parameters"></a>Parametreler

*TManagedControl*<br/>
.NET Framework kullanıcı denetimi MFC uygulamasında görüntülenecektir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CWinFormsDialog::CWinFormsDialog](#cwinformsdialog)|Bir `CWinFormsDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CWinFormsDialog::GetControl](#getcontrol)|Windows Forms kullanıcı denetimine bir başvuru alır.|
|[CWinFormsDialog::GetControlHandle](#getcontrolhandle)|Windows Forms kullanıcı denetimine bir pencere tutamacı alır.|
|[CWinFormsDialog::OnInitDialog](#oninitdialog)|Üzerinde Windows Forms kullanıcı denetimi oluşturup barındırarak MFC iletişim kutusunu başolarak yanıtlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı||
|----------|-|
|[CWinFormsDialog::operatör -&gt;](#operator_-_gt)|[CWinFormsDialog değiştirir::GetControl](#getcontrol) ifadelerinde.|
|[CWinFormsDialog::operatör TManagedControl^](#operator-tmanagedcontrol-hat)|Bir türü Windows Forms kullanıcı denetimine başvuru olarak atar.|

## <a name="remarks"></a>Açıklamalar

`CWinFormsDialog`Windows Forms kullanıcı denetimini barındıran bir MFC iletişim sınıfının [(CDialog)](../../mfc/reference/cdialog-class.md)sarıcıdır. Bu, modal veya modeless MFC iletişim kutusunda .NET Framework denetimlerinin görüntülenmesini sağlar.

Windows Formlarını kullanma hakkında daha fazla bilgi için bkz: [MFC'de Windows Form Kullanıcı Denetimi Kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md) ve Windows Form Kullanıcı Denetimini [MFC İletişim Kutusu Olarak Barındırma.](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms.h

## <a name="cwinformsdialogcwinformsdialog"></a><a name="cwinformsdialog"></a>CWinFormsDialog::CWinFormsDialog

Bir `CWinFormsDialog` nesne inşa eder.

```
CWinFormsDialog(UINT nIDTemplate = IDD);
```

### <a name="parameters"></a>Parametreler

*nIDTemplate*<br/>
İletişim kutusu şablon kaynağının kimliğini içerir. İletişim şablonu oluşturmak ve uygulamanın kaynak komut dosyası dosyası nda depolamak için iletişim düzenleyicisini kullanın. İletişim şablonları hakkında daha fazla bilgi için [CDialog Class'a](../../mfc/reference/cdialog-class.md)bakın.

## <a name="cwinformsdialoggetcontrol"></a><a name="getcontrol"></a>CWinFormsDialog::GetControl

Windows Forms kullanıcı denetimine bir başvuru alır.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

MFC iletişim kutusundawindows forms denetimine başvuru verir.

## <a name="cwinformsdialoggetcontrolhandle"></a><a name="getcontrolhandle"></a>CWinFormsDialog::GetControlHandle

Windows Forms kullanıcı denetimine bir pencere tutamacı alır.

```
inline HWND GetControlHandle() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Windows Forms kullanıcı denetimine bir pencere tutamacı döndürür.

## <a name="cwinformsdialogoninitdialog"></a><a name="oninitdialog"></a>CWinFormsDialog::OnInitDialog

Üzerinde Windows Forms kullanıcı denetimi oluşturup barındırarak MFC iletişim kutusunu başolarak yanıtlar.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın giriş odağı iletişim kutusundaki denetimlerden birine ayarlayıp ayarlamadığını belirten bir Boolean değeri. Sıfırsız `OnInitDialog` dönerse, Windows giriş odağı iletişim kutusundaki ilk denetime ayarlar. Bu yöntem, yalnızca uygulama giriş odağı açıkça iletişim kutusundaki denetimlerden birine ayarlanmışsa 0 döndürebilir.

### <a name="remarks"></a>Açıklamalar

MFC iletişim kutusu oluşturulduğunda [(Create](../../mfc/reference/cdialog-class.md#create), [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect)veya [CDialog'dan](../../mfc/reference/cdialog-class.md)devralınan [DoModal](../../mfc/reference/cdialog-class.md#domodal) yöntemi kullanılarak), WM_INITDIALOG bir ileti gönderilir ve bu yöntem çağrılır. İletişim kutusunda Windows Forms denetimi örneği oluşturur ve kullanıcı denetiminin boyutuna uyacak şekilde iletişim kutusunun boyutunu ayarlar. Ardından MFC iletişim kutusunda yeni denetimi barındırır.

İletişim kutusu başharfe geçtiğinde özel işlem gerçekleştirmeniz gerekiyorsa bu üye işlevi geçersiz kılın. Bu yöntemi kullanma hakkında daha fazla bilgi için [Bkz. CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog).

## <a name="cwinformsdialogoperator--gt"></a><a name="operator_-_gt"></a>CWinFormsDialog::operatör -&gt;

[CWinFormsDialog değiştirir::GetControl](#getcontrol) ifadelerinde.

```
inline TManagedControl^  operator->() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç ifadeler `GetControl` yerine uygun bir sözdizimi sağlar.

Windows Formlarını kullanma hakkında daha fazla bilgi için [bkz.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

## <a name="cwinformsdialogoperator-tmanagedcontrol"></a><a name="operator-tmanagedcontrol-hat"></a>CWinFormsDialog::operatör TManagedControl^

Bir türü Windows Forms kullanıcı denetimine başvuru olarak atar.

```
inline operator TManagedControl^() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, windows forms denetimine başvuru olarak bir tür atar. Bir `CWinFormsDialog<TManagedControl>` iletişim kutusunu, Windows Forms kullanıcı denetim nesnesine işaretçi kabul eden işlevlere geçirmek için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CWinFormsView Sınıfı](../../mfc/reference/cwinformsview-class.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
