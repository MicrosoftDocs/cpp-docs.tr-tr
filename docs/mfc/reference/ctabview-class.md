---
description: 'Daha fazla bilgi edinin: CTabView sınıfı'
title: CTabView sınıfı
ms.date: 11/04/2016
f1_keywords:
- CTabView
- AFXTABVIEW/CTabView
- AFXTABVIEW/CTabView::AddView
- AFXTABVIEW/CTabView::FindTab
- AFXTABVIEW/CTabView::GetActiveView
- AFXTABVIEW/CTabView::GetTabControl
- AFXTABVIEW/CTabView::RemoveView
- AFXTABVIEW/CTabView::SetActiveView
- AFXTABVIEW/CTabView::IsScrollBar
- AFXTABVIEW/CTabView::OnActivateView
helpviewer_keywords:
- CTabView [MFC], AddView
- CTabView [MFC], FindTab
- CTabView [MFC], GetActiveView
- CTabView [MFC], GetTabControl
- CTabView [MFC], RemoveView
- CTabView [MFC], SetActiveView
- CTabView [MFC], IsScrollBar
- CTabView [MFC], OnActivateView
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
ms.openlocfilehash: 59d4169bae108575fcf4844ec7c5c6e1e6681e28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345062"
---
# <a name="ctabview-class"></a>CTabView sınıfı

`CTabView`Sınıfı, MFC 'nin belge/görünüm mimarisini kullanan uygulamalarda Tab denetim sınıfının ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) kullanımını basitleştirir.

## <a name="syntax"></a>Syntax

```
class CTabbedView : public CView
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTabView:: AddView](#addview)|Sekme denetimine yeni bir görünüm ekler.|
|[CTabView:: FindTab](#findtab)|Sekme denetimindeki belirtilen görünümün dizinini döndürür.|
|[CTabView:: GetActiveView](#getactiveview)|Şu anda etkin görünüme bir işaretçi döndürür|
|[CTabView:: GetTabControl](#gettabcontrol)|Görünümle ilişkili Sekme denetimine bir başvuru döndürür.|
|[CTabView:: RemoveView](#removeview)|Sekme denetiminden görünümü kaldırır.|
|[CTabView:: SetActiveView](#setactiveview)|Bir görünümü etkin hale getirir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTabView:: IsScrollBar](#isscrollbar)|Sekme görünümünün paylaşılan bir yatay kaydırma çubuğuna sahip olup olmadığını anlamak için bir sekme görünümü oluştururken Framework tarafından çağırılır.|
|[CTabView:: OnActivateView](#onactivateview)|Sekme görünümü etkin veya devre dışı olduğunda Framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf bir belge/görünüm uygulamasına sekmeli Görünüm eklemenizi kolaylaştırır. `CTabView` , `CView` gömülü bir nesne içeren, türetilmiş bir sınıftır `CMFCTabCtrl` . `CTabView` nesneyi desteklemek için gereken tüm iletileri işler `CMFCTabCtrl` . ' Dan bir sınıf türetebilir `CTabView` ve uygulamanıza ekleyip, sonra `CView` yöntemi kullanarak türetilmiş sınıflar ekleyin `AddView` . Sekme denetimi bu görünümleri sekme olarak görüntüler.

Örneğin, farklı yollarla gösterilebilen bir belgeniz olabilir: elektronik tablo, grafik, düzenlenebilir form ve benzeri. Gerektiğinde verileri çizerek bireysel görünümler oluşturabilir, bunları `CTabView` türetilmiş nesneye ekleyebilir ve bunları ek bir kodlama yapmadan sekmeli hale getirebilirsiniz.

[TabbedView örneği: mfc sekmeli Görünüm uygulaması](../../overview/visual-cpp-samples.md) öğesinin kullanımını gösterir `CTabView` .

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CTabView` TabbedView örneğinde nasıl kullanıldığını gösterir.

[!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxTabView. h

## <a name="ctabviewaddview"></a><a name="addview"></a> CTabView:: AddView

Sekme denetimine bir görünüm ekler.

```
int AddView(
    CRuntimeClass* pViewClass,
    const CString& strViewLabel,
    int iIndex=-1,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>Parametreler

*pViewClass*<br/>
'ndaki Ekli görünümün çalışma zamanı sınıfına yönelik bir işaretçi.

*Strviewetiketi*<br/>
'ndaki Sekmenin metnini belirtir.

*IIndex*<br/>
'ndaki Görünümün ekleneceği sıfır tabanlı konumu belirtir. Konum-1 ise, yeni sekme sonuna eklenir.

*pContext*<br/>
'ndaki Görünümün bir işaretçisi `CCreateContext` .

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa bir görünüm dizini. Aksi takdirde,-1.

### <a name="remarks"></a>Açıklamalar

Bir çerçeveye gömülü Sekme denetimine bir görünüm eklemek için bu işlevi çağırın.

## <a name="ctabviewfindtab"></a><a name="findtab"></a> CTabView:: FindTab

Sekme denetimindeki belirtilen görünümün dizinini döndürür.

```
int FindTab(HWND hWndView) const;
```

### <a name="parameters"></a>Parametreler

*hWndView*<br/>
'ndaki Görünümün tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Bulunursa görünümün dizini; Aksi takdirde,-1.

### <a name="remarks"></a>Açıklamalar

Belirtilen tanıtıcıya sahip bir görünümün dizinini almak için bu işlevi çağırın.

## <a name="ctabviewgetactiveview"></a><a name="getactiveview"></a> CTabView:: GetActiveView

Şu anda etkin görünüme bir işaretçi döndürür.

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkin görünüm için geçerli bir işaretçi veya etkin görünüm yoksa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="ctabviewgettabcontrol"></a><a name="gettabcontrol"></a> CTabView:: GetTabControl

Görünümle ilişkili Sekme denetimine bir başvuru döndürür.

```
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```

### <a name="return-value"></a>Dönüş Değeri

Görünümle ilişkili Sekme denetimine başvuru.

## <a name="ctabviewisscrollbar"></a><a name="isscrollbar"></a> CTabView:: IsScrollBar

Sekme görünümünün paylaşılan bir yatay kaydırma çubuğuna sahip olup olmadığını anlamak için bir sekme görünümü oluştururken Framework tarafından çağırılır.

```
virtual BOOL IsScrollBar() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme görünümü bir paylaşılan kaydırma çubuğuyla birlikte oluşturulup oluşturulmadıysa TRUE. Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bir *CTabView* nesnesi oluşturulurken Framework bu yöntemi çağırır.

*CTabView* ile türetilmiş bir sınıftaki *IsScrollBar* yöntemini geçersiz kılın ve paylaşılan yatay kaydırma çubuğu olan bir görünüm oluşturmak istiyorsanız true değerini döndürün.

## <a name="ctabviewonactivateview"></a><a name="onactivateview"></a> CTabView:: OnActivateView

Sekme görünümü etkin veya devre dışı olduğunda Framework tarafından çağırılır.

```
virtual void OnActivateView(CView* view);
```

### <a name="parameters"></a>Parametreler

*görünümü*<br/>
'ndaki Görünüme yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz. `CTabView`Bu bildirimi işlemek için bu yöntemi, türetilmiş bir sınıfta geçersiz kılın.

## <a name="ctabviewremoveview"></a><a name="removeview"></a> CTabView:: RemoveView

Sekme denetiminden görünümü kaldırır.

```
BOOL RemoveView(int iTabNum);
```

### <a name="parameters"></a>Parametreler

*ıtabnum*<br/>
'ndaki Kaldırılacak görünümün dizini.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa kaldırılan görünümün dizini. Aksi takdirde-1.

### <a name="remarks"></a>Açıklamalar

## <a name="ctabviewsetactiveview"></a><a name="setactiveview"></a> CTabView:: SetActiveView

Bir görünümü etkin hale getirir.

```
BOOL SetActiveView(int iTabNum);
```

### <a name="parameters"></a>Parametreler

*ıtabnum*<br/>
'ndaki Sekme görünümünün sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen Görünüm etkin yapıldıysa TRUE, görünümün dizini geçersizse FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [CMFCTabCtrl:: SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTabCtrl](../../mfc/reference/ctabview-class.md)<br/>
[CView sınıfı](../../mfc/reference/cview-class.md)
