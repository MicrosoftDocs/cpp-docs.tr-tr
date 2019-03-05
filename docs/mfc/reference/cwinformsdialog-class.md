---
title: CWinFormsDialog sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 4d0731e40a622f0d360cabc03b68b0fe74c1ebc9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57277124"
---
# <a name="cwinformsdialog-class"></a>CWinFormsDialog sınıfı

Bir Windows Forms kullanıcı denetimi barındıran MFC iletişim kutusu sınıfı için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
template <typename TManagedControl>
class CWinFormsDialog :
    public CDialog
```

#### <a name="parameters"></a>Parametreler

*TManagedControl*<br/>
MFC uygulamasında görüntülenecek .NET Framework kullanıcı denetimi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWinFormsDialog::CWinFormsDialog](#cwinformsdialog)|Oluşturur bir `CWinFormsDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinFormsDialog::GetControl](#getcontrol)|Windows Forms kullanıcı denetimi için bir başvuru alır.|
|[CWinFormsDialog::GetControlHandle](#getcontrolhandle)|Windows Forms kullanıcı denetimi için bir pencere tutucu alır.|
|[CWinFormsDialog::OnInitDialog](#oninitdialog)|MFC iletişim kutusu, oluşturarak ve üzerindeki bir Windows Forms kullanıcı denetimi barındırma başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad||
|----------|-|
|[CWinFormsDialog::operator-&gt;](#operator_-_gt)|Değiştirir [CWinFormsDialog::GetControl](#getcontrol) ifadelerde.|
|[CWinFormsDialog::operator TManagedControl ^](#operator_tmanagedcontrol)|Bir Windows Forms kullanıcı denetimi başvuru olarak bir tür çevirir.|

## <a name="remarks"></a>Açıklamalar

`CWinFormsDialog` bir MFC iletişim kutusu sınıfı için bir sarmalayıcı olan ( [CDialog](../../mfc/reference/cdialog-class.md)) bir Windows Forms kullanıcı denetimi barındıran. Bu, .NET Framework kalıcı veya geçici bir MFC iletişim kutusunda denetimlere görüntülenmesini sağlar.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md) ve [bir MFC iletişim kutusu olarak Windows formu kullanıcı denetimi barındırma](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h

##  <a name="cwinformsdialog"></a>  CWinFormsDialog::CWinFormsDialog

Oluşturur bir `CWinFormsDialog` nesne.

```
CWinFormsDialog(UINT nIDTemplate = IDD);
```

### <a name="parameters"></a>Parametreler

*nIDTemplate*<br/>
Bir iletişim kutusu şablonu kaynak Kimliğini içerir. İletişim kutusu Düzenleyicisi iletişim şablonu oluşturmak ve uygulamanın kaynak betik dosyasını depolamak için kullanın. İletişim kutusu şablonları hakkında daha fazla bilgi için bkz. [CDialog sınıfı](../../mfc/reference/cdialog-class.md).

##  <a name="getcontrol"></a>  CWinFormsDialog::GetControl

Windows Forms kullanıcı denetimi için bir başvuru alır.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

MFC iletişim kutusunda Windows Forms denetimini bir başvuru döndürür.

##  <a name="getcontrolhandle"></a>  CWinFormsDialog::GetControlHandle

Windows Forms kullanıcı denetimi için bir pencere tutucu alır.

```
inline HWND GetControlHandle() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir pencere tutucu Windows Forms kullanıcı denetimini döndürür.

##  <a name="oninitdialog"></a>  CWinFormsDialog::OnInitDialog

MFC iletişim kutusu, oluşturarak ve üzerindeki bir Windows Forms kullanıcı denetimi barındırma başlatır.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama giriş odağını denetimlerden birini iletişim kutusunda ayarladı olup olmadığını belirten bir Boole değeri. Varsa `OnInitDialog` sıfır döndürür, Windows ayarlar giriş odağını ilk denetime iletişim kutusunda. Bu yöntem, yalnızca uygulama açıkça giriş odağını denetimlerden birini iletişim kutusunda ayarladıysa 0 döndürebilir.

### <a name="remarks"></a>Açıklamalar

MFC iletişim kutusu oluşturulduğunda (kullanarak [Oluştur](../../mfc/reference/cdialog-class.md#create), [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect), veya [DoModal](../../mfc/reference/cdialog-class.md#domodal) yöntemi öğesinden devralınan [CDialog](../../mfc/reference/cdialog-class.md)), bir WM_ INITDIALOG ileti gönderilir ve bu yöntem çağrılır. Bu iletişim kutusunda bir Windows Forms Denetim örneği oluşturur ve kullanıcı denetiminin boyutunu barındırmak için iletişim kutusunun boyutunu ayarlar. Ardından MFC iletişim kutusunda yeni denetim barındırır.

İletişim kutusu başlatılırken özel işlem yapmanız gerekiyorsa bu üye işlevini geçersiz kılar. Bu yöntemi kullanma hakkında daha fazla bilgi için bkz. [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog).

##  <a name="operator_-_gt"></a>  CWinFormsDialog::operator-&gt;

Değiştirir [CWinFormsDialog::GetControl](#getcontrol) ifadelerde.

```
inline TManagedControl^  operator->() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç yerini alan bir kullanışlı bir söz dizimi sağlar `GetControl` ifadelerde.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="operator_tmanagedcontrol_xor"></a>  CWinFormsDialog::operator TManagedControl ^

Bir Windows Forms kullanıcı denetimi başvuru olarak bir tür çevirir.

```
inline operator TManagedControl^() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir Windows Forms denetimini bir başvuru olarak bir tür çevirir. İletmek için kullanılan bir `CWinFormsDialog<TManagedControl>` iletişim kutusu bir Windows Forms kullanıcı denetimi nesneye bir işaretçi kabul eden işlevlere.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CWinFormsView Sınıfı](../../mfc/reference/cwinformsview-class.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
