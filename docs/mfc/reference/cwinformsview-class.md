---
description: 'Daha fazla bilgi edinin: CWinFormsView Class'
title: CWinFormsView sınıfı
ms.date: 11/04/2016
f1_keywords:
- CWinFormsView
- AFXWINFORMS/CWinFormsView
- AFXWINFORMS/CWinFormsView::CWinFormsView
- AFXWINFORMS/CWinFormsView::GetControl
helpviewer_keywords:
- CWinFormsView [MFC], CWinFormsView
- CWinFormsView [MFC], GetControl
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
ms.openlocfilehash: 09dad434ebe0e0011fef5836196fd15e25390536
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318435"
---
# <a name="cwinformsview-class"></a>CWinFormsView sınıfı

Bir Windows Forms denetimini MFC görünümü olarak barındırmak için genel işlevsellik sağlar.

## <a name="syntax"></a>Syntax

```
class CWinFormsView : public CView;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWinFormsView:: CWinFormsView](#cwinformsview)|Bir `CWinFormsView` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinFormsView:: GetControl](#getcontrol)|Windows Forms denetimine bir işaretçi alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-|
|[CWinFormsView:: operator denetimi ^](#operator_control)|Bir türü Windows Forms denetimine işaretçi olarak yayınlar.|

## <a name="remarks"></a>Açıklamalar

MFC, bir `CWinFormsView` MFC görünümü içinde .NET Framework Windows Forms denetimini barındırmak için sınıfını kullanır. Denetim, yerel görünümün bir alt öğesidir ve MFC görünümündeki istemci alanının tamamını kaplar. Sonuç bir görünüme benzer ve `CFormView` zengin form tabanlı görünümler oluşturmak için Windows Forms Tasarımcısı ve çalışma zamanı avantajlarından yararlanmanıza olanak tanır.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

> [!NOTE]
> MFC Windows Forms tümleştirmesi yalnızca MFC ile (AFXDLL tanımlı olan projeler) dinamik olarak bağlanan projelerde işe yarar.

> [!NOTE]
> CWinFormsView, MFC bölücü penceresini ( [CSplitterWnd sınıfı](../../mfc/reference/csplitterwnd-class.md)) desteklemez. Şu anda yalnızca Windows Forms Bölümlendirici denetimi desteklenir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms. h

## <a name="cwinformsviewcwinformsview"></a><a name="cwinformsview"></a> CWinFormsView:: CWinFormsView

Bir `CWinFormsView` nesnesi oluşturur.

```
CWinFormsView(System::Type^ pManagedViewType);
```

### <a name="parameters"></a>Parametreler

*pManagedViewType*<br/>
Windows Forms Kullanıcı denetiminin veri türüne yönelik bir işaretçi.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, `CUserView` sınıfı öğesinden devralır `CWinFormsView` ve türü `UserControl1` oluşturucuya geçirir `CWinFormsView` . `UserControl1` , ControlLibrary1.dll içinde özel olarak oluşturulmuş bir denetimdir.

[!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]

[!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]

## <a name="cwinformsviewgetcontrol"></a><a name="getcontrol"></a> CWinFormsView:: GetControl

Windows Forms denetimine bir işaretçi alır.

```
System::Windows::Forms::Control^ GetControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `System.Windows.Forms.Control` nesne işaretçisi.

### <a name="remarks"></a>Açıklamalar

Windows Forms nasıl kullanılacağına ilişkin bir örnek için, bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="cwinformsviewoperator-control"></a><a name="operator_control"></a> CWinFormsView:: operator denetimi ^

Bir türü Windows Forms denetimine işaretçi olarak yayınlar.

```
operator System::Windows::Forms::Control^() const;
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, `CWinFormsView` türünde Windows Forms denetimine yönelik bir işaretçi kabul eden işlevlere bir görünüm geçirmenize olanak sağlar <xref:System.Windows.Forms.Control> .

### <a name="example"></a>Örnek

  Bkz. [CWinFormsView:: GetControl](#getcontrol).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWinFormsControl sınıfı](../../mfc/reference/cwinformscontrol-class.md)<br/>
[CWinFormsDialog sınıfı](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CFormView sınıfı](../../mfc/reference/cformview-class.md)
