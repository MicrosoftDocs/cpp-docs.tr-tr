---
title: CMFCRibbonMainPanel Sınıfı
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
ms.openlocfilehash: 0fd1cd2fec31f9da0c2bec36d08586780f4f95c3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753572"
---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel Sınıfı

[CMFCRibbonApplicationButton'ı](../../mfc/reference/cmfcribbonapplicationbutton-class.md)tıklattığınızda görüntüleyen bir şerit paneli uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonMainPanel : public CMFCRibbonPanel
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Varsayılan oluşturucu.|
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonMainPanel::Ekle](#add)|Uygulama düğmesi panelinin sol bölmesine bir şerit öğesi ekler. [(CMFCRibbonPanel geçersiz kılar::Ekle](../../mfc/reference/cmfcribbonpanel-class.md#add).)|
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|Son dosyalar listesi menüsüne bir metin dizesi ekler.|
|[CMFCRibbonMainPanel::Addtobottom](#addtobottom)|Şerit uygulama panelinin alt bölmesine bir şerit öğesi ekler.|
|[CMFCRibbonMainPanel::Addtoright](#addtoright)|Uygulama düğmesi panelinin sağ bölmesine bir şerit öğesi ekler.|
|`CMFCRibbonMainPanel::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|Şerit ana panelin alanını temsil eden bir dikdörtgen döndürür.|
|`CMFCRibbonMainPanel::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|

## <a name="remarks"></a>Açıklamalar

Çerçeve, uygulama `CMFCRibbonMainPanel` panelini ne zaman açtığınızı görüntüler. Üç bölme içerir:

- Sol bölmede **Aç,** **Kaydet,** **Yazdır**ve **Kapat**gibi dosyalarla ilişkili komutlar bulunur. Bu bölmeye komut eklemek için [CMFCRibbonMainPanel'i arayın:Ekle.](#add)

- Sağ bölme, sol bölmede tıklattıkladığınız komutu değiştiren seçenekler içerir. Örneğin, sol bölmeden **Farklı Kaydet'i** tıklattığınızda, sağ bölme kullanılabilir dosya türlerini görüntüleyebilir. Bu bölmeye bir öğe eklemek için [CMFCRibbonMainPanel'i arayın::AddToRight.](#addtoright)

- Alt bölmede, uygulamanın ayarlarını değiştirmenize ve programdan çıkmanıza olanak tanıyan düğmeler yer alıyor. Bu bölmeye bir öğe eklemek için [CMFCRibbonMainPanel'i arayın::AddToBottom.](#addtobottom)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)

[CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonMainPanel.h

## <a name="cmfcribbonmainpaneladd"></a><a name="add"></a>CMFCRibbonMainPanel::Ekle

Uygulama düğmesi panelinin sol bölmesine bir şerit öğesi ekler.

```
virtual void Add(CMFCRibbonBaseElement* pElem);
```

### <a name="parameters"></a>Parametreler

*pElem*<br/>
[içinde, dışarı] Ana panele eklemek için şerit öğesiiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Panele bir şerit öğesi ekler. Bu yöntem kullanılarak eklenen öğeler ana panelin sol sütununda yer alır.

## <a name="cmfcribbonmainpaneladdrecentfileslist"></a><a name="addrecentfileslist"></a>CMFCRibbonMainPanel::AddRecentFilesList

Son dosyalar listesi menüsüne bir metin dizesi ekler.

```cpp
void AddRecentFilesList(
    LPCTSTR lpszLabel,
    int nWidth = 300);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
Son dosyalar listesine eklemek için dize belirtir.

*Nwidth*<br/>
Son dosya listesi panelinin piksel olarak genişliğini belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonmainpaneladdtobottom"></a><a name="addtobottom"></a>CMFCRibbonMainPanel::Addtobottom

Şerit uygulama panelinin alt bölmesine bir şerit öğesi ekler.

```cpp
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```

### <a name="parameters"></a>Parametreler

*pElem*<br/>
[içinde, dışarı] Ana panelin altına eklemek için şerit öğesiiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonmainpaneladdtoright"></a><a name="addtoright"></a>CMFCRibbonMainPanel::Addtoright

Uygulama düğmesi panelinin sağ bölmesine bir şerit öğesi ekler.

```cpp
void AddToRight(
    CMFCRibbonBaseElement* pElem,
    int nWidth = 300);
```

### <a name="parameters"></a>Parametreler

*pElem*<br/>
Ana panelin sağ tarafına eklenecek bir şerit öğesi için bir işaretçi.

*Nwidth*<br/>
Piksel olarak, doğru panelin genişliğini belirtir.

### <a name="remarks"></a>Açıklamalar

Sağ panele bir şerit öğesi eklemek için bu işlevi kullanın. Sağ panel genellikle en son dosya listesini görüntüler, ancak buraya başka bir şerit öğesi ekleyebilirsiniz.

## <a name="cmfcribbonmainpanelgetcommandsframe"></a><a name="getcommandsframe"></a>CMFCRibbonMainPanel::GetCommandsFrame

Şerit ana panelin alanını temsil eden bir dikdörtgen döndürür.

```
CRect GetCommandsFrame() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit ana panelin alanını temsil eden bir dikdörtgen.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonPanel Sınıfı](../../mfc/reference/cmfcribbonpanel-class.md)
