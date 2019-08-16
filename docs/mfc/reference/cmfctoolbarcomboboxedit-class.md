---
title: CMFCToolBarComboBoxEdit sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit
helpviewer_keywords:
- CMFCToolBarComboBoxEdit [MFC], CMFCToolBarComboBoxEdit
ms.assetid: 4789c34a-ce58-48ba-a26f-38748b601352
ms.openlocfilehash: 2a0ab1766f42d34c86339cffb86f876358c97a4a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504874"
---
# <a name="cmfctoolbarcomboboxedit-class"></a>CMFCToolBarComboBoxEdit sınıfı

Framework, `CMFCToolBarComboBoxEdit` düzenlenebilir Birleşik giriş kutusu denetimi gibi davranan bir araç çubuğu düğmesi oluşturmak için sınıfını kullanır.

## <a name="syntax"></a>Sözdizimi

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

Düzenleme işlemlerini özelleştirmek için `CMFCToolBarComboBoxEdit` sınıftan bir sınıf türetirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbarcomboboxbutton. h

##  <a name="cmfctoolbarcomboboxedit"></a>CMFCToolBarComboBoxEdit:: CMFCToolBarComboBoxEdit

Bir `CMFCToolBarComboBoxEdit` nesnesi oluşturur.

```
CMFCToolBarComboBoxEdit(CMFCToolBarComboBoxButton& combo);
```

### <a name="parameters"></a>Parametreler

*geçir*<br/>
'ndaki Bir kombo kutusu denetimi içeren bir araç çubuğu düğmesi olan [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) nesnesine başvuru.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCToolBarComboBoxEdit` sınıfının bir nesnesinin nasıl oluşturulduğunu gösterir. Bu kod parçacığı, [IE demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_IEDemo#5](../../mfc/reference/codesnippet/cpp/cmfctoolbarcomboboxedit-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarComboBoxButton Sınıfı](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)
