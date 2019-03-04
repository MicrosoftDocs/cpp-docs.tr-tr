---
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
ms.openlocfilehash: f4a5e6b88527dad8606092ccebd4899bba5181f6
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289344"
---
# <a name="cwinformsview-class"></a>CWinFormsView sınıfı

Windows Forms denetimlerinin MFC görünümü olarak barındırılması için genel işlevler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CWinFormsView : public CView;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWinFormsView::CWinFormsView](#cwinformsview)|Oluşturur bir `CWinFormsView` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinFormsView::GetControl](#getcontrol)|Windows Forms denetimini bir işaretçi alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad||
|----------|-|
|[CWinFormsView::operator denetim ^](#operator_control)|Bir tür, bir Windows Forms denetimi için bir işaretçi olarak yayınlar.|

## <a name="remarks"></a>Açıklamalar

MFC kullanan `CWinFormsView` MFC görünümü içinde .NET Framework Windows Forms denetimi barındırma sınıfı. Denetim yerel görünümün alt ve MFC Görünümü tüm istemci alanını kaplar. Sonuç aşağıdakine benzer bir `CFormView` görünümü, Windows Form Tasarımcısı'nın yararlanın ve form tabanlı zengin görünümler oluşturmak için çalıştırma etmenize imkan sağlar.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

> [!NOTE]
>  MFC Windows Forms tümleştirme çalışır yalnızca MFC ile dinamik olarak bağlama projeleri (Proje AFXDLL tanımlanır).

> [!NOTE]
>  CWinFormsView MFC ayırıcı penceresi desteklemez ( [CSplitterWnd sınıfı](../../mfc/reference/csplitterwnd-class.md)). Şu anda yalnızca Windows Forms denetimi desteklenir ayırıcı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h

##  <a name="cwinformsview"></a>  CWinFormsView::CWinFormsView

Oluşturur bir `CWinFormsView` nesne.

```
CWinFormsView(System::Type^ pManagedViewType);
```

### <a name="parameters"></a>Parametreler

*pManagedViewType*<br/>
Windows Forms kullanıcı denetimi veri türü bir işaretçi.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, `CUserView` sınıfının devraldığı `CWinFormsView` ve türünü geçirir `UserControl1` için `CWinFormsView` Oluşturucusu. `UserControl1` ControlLibrary1.dll içinde özel olarak geliştirilmiş bir denetimdir.

[!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]

[!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]

##  <a name="getcontrol"></a>  CWinFormsView::GetControl

Windows Forms denetimini bir işaretçi alır.

```
System::Windows::Forms::Control^ GetControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `System.Windows.Forms.Control` nesne.

### <a name="remarks"></a>Açıklamalar

Windows Forms kullanma örneği için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="operator_control"></a>  CWinFormsView::operator denetim ^

Bir tür, bir Windows Forms denetimi için bir işaretçi olarak yayınlar.

```
operator System::Windows::Forms::Control^() const;
```

### <a name="remarks"></a>Açıklamalar

Bu işleç geçirmenize olanak bir `CWinFormsView` görünümü, bir Windows Forms Denetim türü için bir işaretçi kabul eden işlevlere <xref:System.Windows.Forms.Control>.

### <a name="example"></a>Örnek

  Bkz: [CWinFormsView::GetControl](#getcontrol).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWinFormsControl Sınıfı](../../mfc/reference/cwinformscontrol-class.md)<br/>
[CWinFormsDialog Sınıfı](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CFormView Sınıfı](../../mfc/reference/cformview-class.md)
