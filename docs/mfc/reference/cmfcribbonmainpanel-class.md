---
description: 'Daha fazla bilgi edinin: CMFCRibbonMainPanel sınıfı'
title: CMFCRibbonMainPanel sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
helpviewer_keywords:
- CMFCRibbonMainPanel [MFC], Add
- CMFCRibbonMainPanel [MFC], AddRecentFilesList
- CMFCRibbonMainPanel [MFC], AddToBottom
- CMFCRibbonMainPanel [MFC], AddToRight
- CMFCRibbonMainPanel [MFC], GetCommandsFrame
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
ms.openlocfilehash: 823a1ce8a8684ca791f838346a1fb50727096a62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321818"
---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel sınıfı

[CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)öğesine tıkladığınızda görüntülenen şerit panelini uygular.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonMainPanel : public CMFCRibbonPanel
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Varsayılan Oluşturucu.|
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonMainPanel:: Add](#add)|Uygulama düğmesi bölmesinin sol bölmesine bir şerit öğesi ekler. ( [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).) geçersiz kılar|
|[CMFCRibbonMainPanel:: AddRecentFilesList](#addrecentfileslist)|Son Dosyalar liste menüsüne bir metin dizesi ekler.|
|[CMFCRibbonMainPanel:: AddToBottom](#addtobottom)|Şerit uygulama panelinin alt bölmesine bir şerit öğesi ekler.|
|[CMFCRibbonMainPanel:: AddToRight](#addtoright)|Uygulama düğmesi panelinin sağ bölmesine bir şerit öğesi ekler.|
|`CMFCRibbonMainPanel::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|[CMFCRibbonMainPanel:: GetCommandsFrame](#getcommandsframe)|Şerit Ana bölmesinin alanını temsil eden bir dikdörtgen döndürür.|
|`CMFCRibbonMainPanel::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|

## <a name="remarks"></a>Açıklamalar

Çerçeve, `CMFCRibbonMainPanel` uygulama panelini açtığınızda öğesini görüntüler. Üç bölme içerir:

- Sol bölmede, **açma**, **kaydetme**, **yazdırma** ve **kapatma** gibi dosyalarla ilişkili komutlar bulunur. Bu bölmeye bir komut eklemek için [CMFCRibbonMainPanel:: Add](#add)' i çağırın.

- Sağ bölmede, sol bölmede tıkladınız komutu değiştiren seçenekler bulunur. Örneğin, sol bölmedeki **farklı kaydet** ' e tıklarsanız sağ bölme kullanılabilir dosya türlerini görüntüleyebilir. Bu bölmeye bir öğe eklemek için [CMFCRibbonMainPanel:: AddToRight](#addtoright)' ı çağırın.

- Alt bölmede, uygulamanın ayarlarını değiştirmenize ve programdan çıkmasına imkan tanıyan düğmeler bulunur. Bu bölmeye bir öğe eklemek için [CMFCRibbonMainPanel:: AddToBottom](#addtobottom)' ı çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[Cmfcribbonpaneli](../../mfc/reference/cmfcribbonpanel-class.md)

[CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonMainPanel. h

## <a name="cmfcribbonmainpaneladd"></a><a name="add"></a> CMFCRibbonMainPanel:: Add

Uygulama düğmesi bölmesinin sol bölmesine bir şerit öğesi ekler.

```
virtual void Add(CMFCRibbonBaseElement* pElem);
```

### <a name="parameters"></a>Parametreler

*Peled*<br/>
[in, out] Ana panele eklemek için şerit öğesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Panele bir şerit öğesi ekler. Bu yöntem kullanılarak eklenen öğeler ana bölmenin sol sütununda yer alır.

## <a name="cmfcribbonmainpaneladdrecentfileslist"></a><a name="addrecentfileslist"></a> CMFCRibbonMainPanel:: AddRecentFilesList

Son Dosyalar liste menüsüne bir metin dizesi ekler.

```cpp
void AddRecentFilesList(
    LPCTSTR lpszLabel,
    int nWidth = 300);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
Son dosyalar listesine eklenecek dizeyi belirtir.

*nWidth*<br/>
Son kullanılan dosyalar liste panelinin genişliğini piksel cinsinden belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonmainpaneladdtobottom"></a><a name="addtobottom"></a> CMFCRibbonMainPanel:: AddToBottom

Şerit uygulama panelinin alt bölmesine bir şerit öğesi ekler.

```cpp
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```

### <a name="parameters"></a>Parametreler

*Peled*<br/>
[in, out] Ana bölmenin altına eklenecek Ribbon öğesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonmainpaneladdtoright"></a><a name="addtoright"></a> CMFCRibbonMainPanel:: AddToRight

Uygulama düğmesi panelinin sağ bölmesine bir şerit öğesi ekler.

```cpp
void AddToRight(
    CMFCRibbonBaseElement* pElem,
    int nWidth = 300);
```

### <a name="parameters"></a>Parametreler

*Peled*<br/>
Ana bölmenin sağ tarafına eklenecek şerit öğesine yönelik bir işaretçi.

*nWidth*<br/>
Sağ bölmenin genişliğini piksel cinsinden belirtir.

### <a name="remarks"></a>Açıklamalar

Sağ panele bir şerit öğesi eklemek için bu işlevi kullanın. Sağ panel genellikle en son dosyalar listesini görüntüler, ancak buraya diğer Şerit öğelerini ekleyebilirsiniz.

## <a name="cmfcribbonmainpanelgetcommandsframe"></a><a name="getcommandsframe"></a> CMFCRibbonMainPanel:: GetCommandsFrame

Şerit Ana bölmesinin alanını temsil eden bir dikdörtgen döndürür.

```
CRect GetCommandsFrame() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit Ana bölmesinin alanını temsil eden dikdörtgen.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonPanel sınıfı](../../mfc/reference/cmfcribbonpanel-class.md)
