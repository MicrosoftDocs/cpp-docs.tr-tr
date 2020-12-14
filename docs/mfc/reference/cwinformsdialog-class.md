---
description: 'Daha fazla bilgi edinin: CWinFormsDialog Class'
title: CWinFormsDialog sınıfı
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
ms.openlocfilehash: 501f9c354bd6f0b7a628aabb93f4680155f74a69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342627"
---
# <a name="cwinformsdialog-class"></a>CWinFormsDialog sınıfı

Windows Forms Kullanıcı denetimini barındıran MFC iletişim sınıfı için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
template <typename TManagedControl>
class CWinFormsDialog :
    public CDialog
```

#### <a name="parameters"></a>Parametreler

*TManagedControl*<br/>
MFC uygulamasında görüntülenmek üzere .NET Framework Kullanıcı denetimi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWinFormsDialog:: CWinFormsDialog](#cwinformsdialog)|Bir `CWinFormsDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinFormsDialog:: GetControl](#getcontrol)|Windows Forms Kullanıcı denetimine bir başvuru alır.|
|[CWinFormsDialog:: GetControlHandle](#getcontrolhandle)|Windows Forms Kullanıcı denetimine bir pencere tutamacı alır.|
|[CWinFormsDialog:: OnInitDialog](#oninitdialog)|Üzerinde Windows Forms bir kullanıcı denetimi oluşturup barındırarak MFC iletişim kutusunu başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-|
|[CWinFormsDialog:: operator-&gt;](#operator_-_gt)|İfadelerde [CWinFormsDialog:: GetControl](#getcontrol) yerini alır.|
|[CWinFormsDialog:: operator TManagedControl ^](#operator-tmanagedcontrol-hat)|Bir Windows Forms Kullanıcı denetimine başvuru olarak bir tür yayınlar.|

## <a name="remarks"></a>Açıklamalar

`CWinFormsDialog` , bir Windows Forms Kullanıcı denetimini barındıran MFC iletişim sınıfı ( [CDialog](../../mfc/reference/cdialog-class.md)) için bir sarmalayıcıdır. Bu, kalıcı veya kalıcı olmayan MFC iletişim kutusunda .NET Framework denetimlerinin görüntülenmesini sağlar.

Windows Forms kullanma hakkında daha fazla bilgi için, bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md) ve [MFC Iletişim kutusu olarak Windows formu Kullanıcı denetimi barındırma](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms. h

## <a name="cwinformsdialogcwinformsdialog"></a><a name="cwinformsdialog"></a> CWinFormsDialog:: CWinFormsDialog

Bir `CWinFormsDialog` nesnesi oluşturur.

```
CWinFormsDialog(UINT nIDTemplate = IDD);
```

### <a name="parameters"></a>Parametreler

*Nıdtemplate*<br/>
İletişim kutusu şablon kaynağının KIMLIĞINI içerir. İletişim kutusu şablonunu oluşturmak ve uygulamanın kaynak betik dosyasında depolamak için iletişim düzenleyicisini kullanın. İletişim şablonları hakkında daha fazla bilgi için bkz. [CDialog sınıfı](../../mfc/reference/cdialog-class.md).

## <a name="cwinformsdialoggetcontrol"></a><a name="getcontrol"></a> CWinFormsDialog:: GetControl

Windows Forms Kullanıcı denetimine bir başvuru alır.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

MFC iletişim kutusunda Windows Forms denetimine bir başvuru döndürür.

## <a name="cwinformsdialoggetcontrolhandle"></a><a name="getcontrolhandle"></a> CWinFormsDialog:: GetControlHandle

Windows Forms Kullanıcı denetimine bir pencere tutamacı alır.

```
inline HWND GetControlHandle() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Windows Forms Kullanıcı denetimine bir pencere tutamacı döndürür.

## <a name="cwinformsdialogoninitdialog"></a><a name="oninitdialog"></a> CWinFormsDialog:: OnInitDialog

Üzerinde Windows Forms bir kullanıcı denetimi oluşturup barındırarak MFC iletişim kutusunu başlatır.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın giriş odağını iletişim kutusundaki denetimlerden birine ayarlayıp ayarlamadığını belirten bir Boole değeri. `OnInitDialog`Sıfır dışında bir değer döndürürse, Windows giriş odağını iletişim kutusundaki ilk denetime ayarlar. Bu yöntem, yalnızca uygulama giriş odağını iletişim kutusundaki denetimlerden birine açıkça ayarlamışsa 0 döndürebilir.

### <a name="remarks"></a>Açıklamalar

MFC iletişim kutusu oluşturulduğunda ( [CDialog](../../mfc/reference/cdialog-class.md)'Dan devralınan [Create](../../mfc/reference/cdialog-class.md#create), [createdolaylı](../../mfc/reference/cdialog-class.md#createindirect)veya [DoModal](../../mfc/reference/cdialog-class.md#domodal) yöntemi kullanılarak) WM_INITDIALOG bir ileti gönderilir ve bu yöntem çağrılır. İletişim kutusunda bir Windows Forms denetiminin örneğini oluşturur ve iletişim kutusunun boyutunu Kullanıcı denetiminin boyutuna uyacak şekilde ayarlar. Ardından MFC iletişim kutusunda yeni denetimi barındırır.

İletişim kutusu başlatıldığında özel işlem gerçekleştirmeniz gerekiyorsa, bu üye işlevi geçersiz kılın. Bu yöntemi kullanma hakkında daha fazla bilgi için bkz. [CDialog:: OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog).

## <a name="cwinformsdialogoperator--gt"></a><a name="operator_-_gt"></a> CWinFormsDialog:: operator-&gt;

İfadelerde [CWinFormsDialog:: GetControl](#getcontrol) yerini alır.

```
inline TManagedControl^  operator->() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, ifadelerde yerini alan kullanışlı bir sözdizimi sağlar `GetControl` .

Windows Forms kullanımı hakkında bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="cwinformsdialogoperator-tmanagedcontrol"></a><a name="operator-tmanagedcontrol-hat"></a> CWinFormsDialog:: operator TManagedControl ^

Bir Windows Forms Kullanıcı denetimine başvuru olarak bir tür yayınlar.

```
inline operator TManagedControl^() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir türü Windows Forms denetimine başvuru olarak çevirir. Bir `CWinFormsDialog<TManagedControl>` Windows Forms Kullanıcı denetimi nesnesine bir işaretçi kabul eden işlevlere bir iletişim kutusu geçirmek için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CWinFormsView sınıfı](../../mfc/reference/cwinformsview-class.md)<br/>
[CDialog sınıfı](../../mfc/reference/cdialog-class.md)
