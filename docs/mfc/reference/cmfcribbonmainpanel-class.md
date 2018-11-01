---
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
ms.openlocfilehash: 101c718d25a2e06461156045deea5f42d85e2f4d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638223"
---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel sınıfı

' A tıkladığınızda görüntülenen bir Şerit paneli uygular [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md).

## <a name="syntax"></a>Sözdizimi

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
|[CMFCRibbonMainPanel::Add](#add)|Uygulama düğmesi bölmenin sol bölmeye Şerit öğesi ekler. (Geçersiz kılmaları [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).)|
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|Bir metin dizesi son dosyalar listesini menüsüne ekler.|
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|Şerit uygulama panelinde en alt bölmesi için bir Şerit öğesi ekler.|
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|Uygulama düğmesi panelin sağ bölmeye Şerit öğesi ekler.|
|`CMFCRibbonMainPanel::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|Şerit ana bölmesi alanını temsil eden bir dikdörtgen döndürür.|
|`CMFCRibbonMainPanel::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|

## <a name="remarks"></a>Açıklamalar

Framework görüntüler `CMFCRibbonMainPanel` uygulama panelinde açtığınızda. Üç bölme aşağıdakileri içerir:

- Sol bölmede dosyalarıyla ilişkili komutları içeren **açık**, **Kaydet**, **yazdırma**, ve **Kapat**. Bu bölme için bir komut eklemek için çağrı [CMFCRibbonMainPanel::Add](#add).

- Sağ bölmede, sol bölmede tıklayın komutu değiştiren seçenek içerir. Örneğin, tıklarsanız **Kaydet** sol bölmede, sağ bölmede kullanılabilir dosya türlerini görüntülemek için. Bu bölme için bir öğe eklemek için çağrı [CMFCRibbonMainPanel::AddToRight](#addtoright).

- Alt bölme, uygulama ayarlarını değiştirmek için ve programdan çıkmak için izin düğmeleri içerir. Bu bölme için bir öğe eklemek için çağrı [CMFCRibbonMainPanel::AddToBottom](#addtobottom).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)

[CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxRibbonMainPanel.h

##  <a name="add"></a>  CMFCRibbonMainPanel::Add

Uygulama düğmesi bölmenin sol bölmeye Şerit öğesi ekler.

```
virtual void Add(CMFCRibbonBaseElement* pElem);
```

### <a name="parameters"></a>Parametreler

*pElem*<br/>
[out içinde] Ana panele eklemek için Şerit öğesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Panele bir Şerit öğesi ekler. Bu yöntem kullanılarak eklenen öğeleri ana bölmenin sol sütunda yer alır.

##  <a name="addrecentfileslist"></a>  CMFCRibbonMainPanel::AddRecentFilesList

Bir metin dizesi son dosyalar listesini menüsüne ekler.

```
void AddRecentFilesList(
    LPCTSTR lpszLabel,
    int nWidth = 300);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
Son dosya listesine eklenecek dizeyi belirtir.

*nWidth*<br/>
Son dosyalar listesini panelini piksel cinsinden genişliğini belirtir.

### <a name="remarks"></a>Açıklamalar

##  <a name="addtobottom"></a>  CMFCRibbonMainPanel::AddToBottom

Şerit uygulama panelinde en alt bölmesi için bir Şerit öğesi ekler.

```
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```

### <a name="parameters"></a>Parametreler

*pElem*<br/>
[out içinde] Ana panelinin altına eklemek için Şerit öğesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

##  <a name="addtoright"></a>  CMFCRibbonMainPanel::AddToRight

Uygulama düğmesi panelin sağ bölmeye Şerit öğesi ekler.

```
void AddToRight(
    CMFCRibbonBaseElement* pElem,
    int nWidth = 300);
```

### <a name="parameters"></a>Parametreler

*pElem*<br/>
Ana panelin sağ tarafına eklenecek bir Şerit öğesi için bir işaretçi.

*nWidth*<br/>
Sağ panelde piksel cinsinden genişliğini belirtir.

### <a name="remarks"></a>Açıklamalar

Sağ bölmenin Şerit öğesi eklemek için bu işlevi kullanın. Sağ panelde genellikle en son dosyalar listesini görüntüler, ancak tüm diğer Şerit öğesi buraya ekleyebilirsiniz.

##  <a name="getcommandsframe"></a>  CMFCRibbonMainPanel::GetCommandsFrame

Şerit ana bölmesi alanını temsil eden bir dikdörtgen döndürür.

```
CRect GetCommandsFrame() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit ana bölmesi alanını temsil eden bir dikdörtgen.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonPanel Sınıfı](../../mfc/reference/cmfcribbonpanel-class.md)
