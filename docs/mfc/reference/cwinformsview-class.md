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
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79420864"
---
# <a name="cwinformsview-class"></a>CWinFormsView sınıfı

Bir Windows Forms denetimini MFC görünümü olarak barındırmak için genel işlevsellik sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CWinFormsView : public CView;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CWinFormsView:: CWinFormsView](#cwinformsview)|`CWinFormsView` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CWinFormsView:: GetControl](#getcontrol)|Windows Forms denetimine bir işaretçi alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Name||
|----------|-|
|[CWinFormsView:: operator denetimi ^](#operator_control)|Bir türü Windows Forms denetimine işaretçi olarak yayınlar.|

## <a name="remarks"></a>Açıklamalar

MFC, MFC görünümü içinde bir .NET Framework Windows Forms denetimini barındırmak için `CWinFormsView` sınıfını kullanır. Denetim, yerel görünümün bir alt öğesidir ve MFC görünümündeki istemci alanının tamamını kaplar. Sonuç `CFormView` görünümüne benzer ve zengin form tabanlı görünümler oluşturmak için Windows Forms tasarlayıcısından ve çalışma zamanından yararlanmanızı sağlar.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

> [!NOTE]
>  MFC Windows Forms tümleştirmesi yalnızca MFC ile (AFXDLL tanımlı olan projeler) dinamik olarak bağlanan projelerde işe yarar.

> [!NOTE]
>  CWinFormsView, MFC bölücü penceresini ( [CSplitterWnd sınıfı](../../mfc/reference/csplitterwnd-class.md)) desteklemez. Şu anda yalnızca Windows Forms Bölümlendirici denetimi desteklenir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms. h

##  <a name="cwinformsview"></a>CWinFormsView:: CWinFormsView

`CWinFormsView` nesnesi oluşturur.

```
CWinFormsView(System::Type^ pManagedViewType);
```

### <a name="parameters"></a>Parametreler

*pManagedViewType*<br/>
Windows Forms Kullanıcı denetiminin veri türüne yönelik bir işaretçi.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, `CUserView` sınıfı `CWinFormsView` devralır ve `UserControl1` türünü `CWinFormsView` oluşturucusuna geçirir. `UserControl1`, ControlLibrary1. dll içinde özel olarak oluşturulmuş bir denetimdir.

[!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]

[!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]

##  <a name="getcontrol"></a>CWinFormsView:: GetControl

Windows Forms denetimine bir işaretçi alır.

```
System::Windows::Forms::Control^ GetControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

`System.Windows.Forms.Control` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Windows Forms nasıl kullanılacağına ilişkin bir örnek için, bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="operator_control"></a>CWinFormsView:: operator denetimi ^

Bir türü Windows Forms denetimine işaretçi olarak yayınlar.

```
operator System::Windows::Forms::Control^() const;
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, <xref:System.Windows.Forms.Control>türünde bir Windows Forms denetimine yönelik bir işaretçi kabul eden işlevlere `CWinFormsView` görünümünü geçirmenize olanak sağlar.

### <a name="example"></a>Örnek

  Bkz. [CWinFormsView:: GetControl](#getcontrol).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWinFormsControl Sınıfı](../../mfc/reference/cwinformscontrol-class.md)<br/>
[CWinFormsDialog Sınıfı](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CFormView Sınıfı](../../mfc/reference/cformview-class.md)
