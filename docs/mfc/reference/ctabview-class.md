---
title: CtabView Sınıfı
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
ms.openlocfilehash: ad30cbbf5de195708d2d357a76c38b661d095c2f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365918"
---
# <a name="ctabview-class"></a>CtabView Sınıfı

Sınıf, `CTabView` MFC'nin belge/görünüm mimarisini kullanan uygulamalarda sekme denetim sınıfının [(CMFCTabCtrl)](../../mfc/reference/ctabview-class.md)kullanımını basitleştirir.

## <a name="syntax"></a>Sözdizimi

```
class CTabbedView : public CView
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CTabView::AddView](#addview)|Sekme denetimine yeni bir görünüm ekler.|
|[CTabView::FindTab](#findtab)|Sekme denetiminde belirtilen görünümün dizini döndürür.|
|[CTabView::GetActiveView](#getactiveview)|İşaretçiyi şu anda etkin görünüme döndürür|
|[CTabView::GetTabControl](#gettabcontrol)|Görünümle ilişkili sekme denetimine bir başvuru verir.|
|[CTabView::RemoveView](#removeview)|Görünümü sekme denetiminden kaldırır.|
|[CTabView::SetActiveView](#setactiveview)|Görünümü etkin hale getirir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CtabView::IsScrollBar](#isscrollbar)|Sekme görünümünde paylaşılan yatay kaydırma çubuğu olup olmadığını belirlemek için bir sekme görünümü oluşturulurken çerçeve tarafından çağrılır.|
|[CtabView::OnactivateView](#onactivateview)|Sekme görünümü etkin veya etkin olmadığında çerçeve tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir belge/görünüm uygulamasına sekmeli görünüm koymayı kolaylaştırır. `CTabView`katıştırılmış bir nesne `CMFCTabCtrl` içeren türetilmiş bir `CView`sınıftır. `CTabView``CMFCTabCtrl` nesneyi desteklemek için gereken tüm iletileri işler. Sadece bir sınıf `CTabView` türetmek ve uygulamanıza takın, sonra `CView` `AddView` yöntemi kullanarak -türetilmiş sınıflar ekleyin. Sekme denetimi bu görünümleri sekme olarak görüntüler.

Örneğin, farklı şekillerde gösterilebilen bir belgeniz olabilir: elektronik tablo, grafik, değiştirilebilir form ve benzeri. Verileri gerektiği gibi çizerek tek tek görünümler `CTabView`oluşturabilir, bunları türetilmiş nesnenize ekleyebilir ve ek kodlama yapmadan sekmeli hale getirebilirsiniz.

[TabbedView Örnek: MFC Sekmeli Görünüm](../../overview/visual-cpp-samples.md) `CTabView`Uygulaması kullanımını göstermektedir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte `CTabView` TabbedView örneğinde nasıl kullanıldığı gösterilmektedir.

[!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxTabView.h

## <a name="ctabviewaddview"></a><a name="addview"></a>CTabView::AddView

Sekme denetimine görünüm ekler.

```
int AddView(
    CRuntimeClass* pViewClass,
    const CString& strViewLabel,
    int iIndex=-1,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>Parametreler

*pViewClass*<br/>
[içinde] Eklenen görünümün çalışma zamanı sınıfına işaretçi.

*strViewEtiket*<br/>
[içinde] Sekme metnini belirtir.

*ıındex*<br/>
[içinde] Görünümü eklemek için sıfır tabanlı konumu belirtir. Konum -1 ise, yeni sekme sonuna eklenir.

*Pcontext*<br/>
[içinde] Görünümün işaretçisi. `CCreateContext`

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa bir görünüm dizini. Aksi takdirde, -1.

### <a name="remarks"></a>Açıklamalar

Bir çerçeveye katıştırılmış sekme denetimine görünüm eklemek için bu işlevi arayın.

## <a name="ctabviewfindtab"></a><a name="findtab"></a>CTabView::FindTab

Sekme denetiminde belirtilen görünümün dizini döndürür.

```
int FindTab(HWND hWndView) const;
```

### <a name="parameters"></a>Parametreler

*hWndView*<br/>
[içinde] Görünümün tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Bulunursa görünümün dizin; aksi takdirde, -1.

### <a name="remarks"></a>Açıklamalar

Belirtilen bir tanıtıcıya sahip bir görünümün dizinini almak için bu işlevi çağırın.

## <a name="ctabviewgetactiveview"></a><a name="getactiveview"></a>CTabView::GetActiveView

Bir işaretçiyi şu anda etkin görünüme döndürür.

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkin görünüm için geçerli bir işaretçi veya etkin görünüm yoksa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="ctabviewgettabcontrol"></a><a name="gettabcontrol"></a>CTabView::GetTabControl

Görünümle ilişkili sekme denetimine bir başvuru verir.

```
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```

### <a name="return-value"></a>Dönüş Değeri

Görünümle ilişkili sekme denetimine başvuru.

## <a name="ctabviewisscrollbar"></a><a name="isscrollbar"></a>CtabView::IsScrollBar

Sekme görünümünde paylaşılan yatay kaydırma çubuğu olup olmadığını belirlemek için bir sekme görünümü oluşturulurken çerçeve tarafından çağrılır.

```
virtual BOOL IsScrollBar() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme görünümü paylaşılan bir kaydırma çubuğuyla birlikte oluşturulacaksa DOĞRU. Aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bir *CTabView* nesnesi oluşturulurken çerçeve bu yöntemi çağırır.

*CTabView*türetilmiş bir sınıfta *IsScrollBar* yöntemini geçersiz kılın ve paylaşılan yatay kaydırma çubuğuna sahip bir görünüm oluşturmak istiyorsanız TRUE döndürün.

## <a name="ctabviewonactivateview"></a><a name="onactivateview"></a>CtabView::OnactivateView

Sekme görünümü etkin veya etkin olmadığında çerçeve tarafından çağrılır.

```
virtual void OnActivateView(CView* view);
```

### <a name="parameters"></a>Parametreler

*görünüm*<br/>
[içinde] Görünümiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz. Bu bildirimi işlemek `CTabView`için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctabviewremoveview"></a><a name="removeview"></a>CTabView::RemoveView

Görünümü sekme denetiminden kaldırır.

```
BOOL RemoveView(int iTabNum);
```

### <a name="parameters"></a>Parametreler

*iTabNum*<br/>
[içinde] Kaldırılacak görünümün dizini.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa kaldırılan görünümün dizin. Aksi takdirde -1.

### <a name="remarks"></a>Açıklamalar

## <a name="ctabviewsetactiveview"></a><a name="setactiveview"></a>CTabView::SetActiveView

Görünümü etkin hale getirir.

```
BOOL SetActiveView(int iTabNum);
```

### <a name="parameters"></a>Parametreler

*iTabNum*<br/>
[içinde] Sekme görünümünün sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen görünüm etkin yapılmışsa DOĞRU, görünümün dizin geçersizsi FALSE.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [cmfctabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTabCtrl](../../mfc/reference/ctabview-class.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)
