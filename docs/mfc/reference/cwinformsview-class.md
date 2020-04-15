---
title: CWinFormsView Sınıfı
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
ms.openlocfilehash: 6eb6b9e385e9dbc96eb3b62ffb80909e54569e97
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369601"
---
# <a name="cwinformsview-class"></a>CWinFormsView Sınıfı

MFC görünümü olarak Windows Forms denetiminin barındırılamıiçin genel işlevsellik sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CWinFormsView : public CView;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CWinFormsView::CWinFormsView](#cwinformsview)|Bir `CWinFormsView` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CWinFormsView::GetControl](#getcontrol)|Windows Forms denetimi için bir işaretçi alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı||
|----------|-|
|[CWinFormsView::operatör Kontrolü^](#operator_control)|Bir türü Windows Forms denetimine işaretçi olarak atar.|

## <a name="remarks"></a>Açıklamalar

MFC, `CWinFormsView` bir MFC görünümünde bir .NET Framework Windows Forms denetimini barındırmak için sınıfı kullanır. Denetim, yerel görünümün bir alt alanıdır ve MFC görünümünün tüm istemci alanını kaplar. Sonuç, Windows Forms `CFormView` tasarımcısından yararlanmanızı ve zengin form tabanlı görünümler oluşturmak için zamanı çalıştırmanızı sağlayan bir görünüme benzer.

Windows Formlarını kullanma hakkında daha fazla bilgi [için](../../dotnet/using-a-windows-form-user-control-in-mfc.md)bkz.

> [!NOTE]
> MFC Windows Forms tümleştirmesi yalnızca MFC ile dinamik olarak bağlantı sağlayan projelerde çalışır (AFXDLL'nin tanımlandığı projeler).

> [!NOTE]
> CWinFormsView MFC ayırıcı penceresini desteklemez ( [CSplitterWnd Class).](../../mfc/reference/csplitterwnd-class.md) Şu anda yalnızca Windows Forms Splitter denetimi desteklenir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms.h

## <a name="cwinformsviewcwinformsview"></a><a name="cwinformsview"></a>CWinFormsView::CWinFormsView

Bir `CWinFormsView` nesne inşa eder.

```
CWinFormsView(System::Type^ pManagedViewType);
```

### <a name="parameters"></a>Parametreler

*pManagedViewType*<br/>
Windows Forms kullanıcı denetiminin veri türüne işaretçi.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, `CUserView` sınıf `CWinFormsView` devralır `CWinFormsView` ve yapı `UserControl1` oluşturucuya türü geçer. `UserControl1`ControlLibrary1.dll'de özel olarak oluşturulmuş bir denetimdir.

[!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]

[!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]

## <a name="cwinformsviewgetcontrol"></a><a name="getcontrol"></a>CWinFormsView::GetControl

Windows Forms denetimi için bir işaretçi alır.

```
System::Windows::Forms::Control^ GetControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `System.Windows.Forms.Control` nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Windows Formlarının nasıl kullanılacağına bir örnek [için](../../dotnet/using-a-windows-form-user-control-in-mfc.md)bkz.

## <a name="cwinformsviewoperator-control"></a><a name="operator_control"></a>CWinFormsView::operatör Kontrolü^

Bir türü Windows Forms denetimine işaretçi olarak atar.

```
operator System::Windows::Forms::Control^() const;
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, windows `CWinFormsView` forms türü <xref:System.Windows.Forms.Control>denetimine işaretçi kabul eden işlevlere bir görünüm geçirmenize olanak tanır.

### <a name="example"></a>Örnek

  Bkz. [CWinFormsView::GetControl](#getcontrol).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWinFormsControl Sınıfı](../../mfc/reference/cwinformscontrol-class.md)<br/>
[CWinFormsDialog Sınıfı](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CFormView Sınıfı](../../mfc/reference/cformview-class.md)
