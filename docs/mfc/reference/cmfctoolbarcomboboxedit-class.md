---
description: 'Daha fazla bilgi edinin: CMFCToolBarComboBoxEdit sınıfı'
title: CMFCToolBarComboBoxEdit sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit
helpviewer_keywords:
- CMFCToolBarComboBoxEdit [MFC], CMFCToolBarComboBoxEdit
ms.assetid: 4789c34a-ce58-48ba-a26f-38748b601352
ms.openlocfilehash: f5b54c8c9eb13baf335c52074b1f529bb4f9dab7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143474"
---
# <a name="cmfctoolbarcomboboxedit-class"></a>CMFCToolBarComboBoxEdit sınıfı

Framework, `CMFCToolBarComboBoxEdit` düzenlenebilir Birleşik giriş kutusu denetimi gibi davranan bir araç çubuğu düğmesi oluşturmak için sınıfını kullanır.

## <a name="syntax"></a>Syntax

```
class CMFCToolBarComboBoxEdit : public CEdit
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarComboBoxEdit:: CMFCToolBarComboBoxEdit](#cmfctoolbarcomboboxedit)|Bir `CMFCToolBarComboBoxEdit` nesnesi oluşturur.|
|`CMFCToolBarComboBoxEdit::~CMFCToolBarComboBoxEdit`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCToolBarComboBoxEdit::PreTranslateMessage`|[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine dağıtılmadan önce pencere iletilerini çevirir. ( [CWnd::P reTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)geçersiz kılar.)|

### <a name="remarks"></a>Açıklamalar

`CMFCToolBarComboBoxEdit`Düzenleme işlemlerini özelleştirmek için sınıftan bir sınıf türetirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbarcomboboxbutton. h

## <a name="cmfctoolbarcomboboxeditcmfctoolbarcomboboxedit"></a><a name="cmfctoolbarcomboboxedit"></a> CMFCToolBarComboBoxEdit:: CMFCToolBarComboBoxEdit

Bir `CMFCToolBarComboBoxEdit` nesnesi oluşturur.

```
CMFCToolBarComboBoxEdit(CMFCToolBarComboBoxButton& combo);
```

### <a name="parameters"></a>Parametreler

*geçir*<br/>
'ndaki Bir kombo kutusu denetimi içeren bir araç çubuğu düğmesi olan [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) nesnesine başvuru.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu gösterir `CMFCToolBarComboBoxEdit` . Bu kod parçacığı, [IE demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_IEDemo#5](../../mfc/reference/codesnippet/cpp/cmfctoolbarcomboboxedit-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarComboBoxButton sınıfı](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)
