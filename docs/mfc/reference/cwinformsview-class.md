---
title: CWinFormsView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWinFormsView
- AFXWINFORMS/CWinFormsView
- AFXWINFORMS/CWinFormsView::CWinFormsView
- AFXWINFORMS/CWinFormsView::GetControl
dev_langs:
- C++
helpviewer_keywords:
- CWinFormsView [MFC], CWinFormsView
- CWinFormsView [MFC], GetControl
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd0af17faf3eb4a7206f50d81753e1def508aed4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370555"
---
# <a name="cwinformsview-class"></a>CWinFormsView sınıfı
MFC görünümü olarak Windows Forms denetimi barındırma için genel işlevler sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CWinFormsView : public CView;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinFormsView::CWinFormsView](#cwinformsview)|Oluşturan bir `CWinFormsView` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinFormsView::GetControl](#getcontrol)|Windows Forms denetimi için bir işaretçi alır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad||  
|----------|-|  
|[CWinFormsView::operator denetim ^](#operator_control)|Bir Windows Forms denetimi için bir işaretçi olarak bir tür çevirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 MFC kullanan `CWinFormsView` MFC görünümü içinde .NET Framework Windows Forms denetimi barındırma sınıfı. Denetim yerel görünüm alt ve MFC Görünümü tüm istemci alanını kaplar. Sonuç benzer bir `CFormView` görünümü, Windows Form Tasarımcısı yararlanabilir ve zengin form tabanlı görünümler oluşturmak için çalıştırma olanak tanır.  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
> [!NOTE]
>  MFC Windows Forms tümleştirme çalışır, ile MFC'ye dinamik olarak projelerine (Proje AFXDLL tanımlanır).  
  
> [!NOTE]
>  CWinFormsView MFC Bölümlendirici pencere desteklemez ( [CSplitterWnd sınıfı](../../mfc/reference/csplitterwnd-class.md)). Şu anda yalnızca Windows Forms denetimi desteklenir Bölümlendirici.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwinforms.h  
  
##  <a name="cwinformsview"></a>  CWinFormsView::CWinFormsView  
 Oluşturan bir `CWinFormsView` nesnesi.  
  
```  
CWinFormsView(System::Type^ pManagedViewType);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pManagedViewType`  
 Windows Forms kullanıcı denetimi veri türü için bir işaretçi.   
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte, `CUserView` sınıfının devraldığı `CWinFormsView` ve türünü geçirir `UserControl1` için `CWinFormsView` Oluşturucusu. `UserControl1` ControlLibrary1.dll içinde özel olarak geliştirilmiş bir denetimdir.  
  
 [!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]  
  
 [!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]  
  
##  <a name="getcontrol"></a>  CWinFormsView::GetControl  
 Windows Forms denetimi için bir işaretçi alır.  
  
```  
System::Windows::Forms::Control^ GetControl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `System.Windows.Forms.Control` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows Forms kullanma örneği için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_control"></a>  CWinFormsView::operator denetim ^  
 Bir Windows Forms denetimi için bir işaretçi olarak bir tür çevirir.  
  
```  
operator System::Windows::Forms::Control^() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç, geçirmenizi sağlar bir `CWinFormsView` bir Windows Forms Denetim türü için bir işaretçi kabul işlevleri görünümüne <xref:System.Windows.Forms.Control>.  
  
### <a name="example"></a>Örnek  
  Bkz: [CWinFormsView::GetControl](#getcontrol).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Ddx_managedcontrol sınıfı](../../mfc/reference/cwinformscontrol-class.md)   
 [CWinFormsDialog sınıfı](../../mfc/reference/cwinformsdialog-class.md)   
 [CFormView Sınıfı](../../mfc/reference/cformview-class.md)
