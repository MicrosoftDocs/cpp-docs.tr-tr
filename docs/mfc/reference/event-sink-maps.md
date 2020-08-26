---
title: Olay İç Havuz Eşlemeleri
ms.date: 11/04/2016
helpviewer_keywords:
- event sink maps [MFC]
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
ms.openlocfilehash: 2cbfbc70ae14ccda95c377cb1587bf9d2a1ad3e6
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837270"
---
# <a name="event-sink-maps"></a>Olay İç Havuz Eşlemeleri

Katıştırılmış OLE denetimi bir olayı harekete tetikledikten sonra, denetimin kapsayıcısı MFC tarafından sağlanan "olay havuzu eşlemesi" olarak adlandırılan bir mekanizmayı kullanarak olayı alır. Bu olay havuzu eşlemesi, her belirli olay için işleyici işlevlerini ve bu olayların parametrelerini belirler. Olay havuzu haritaları hakkında daha fazla bilgi için, [ActiveX denetim kapsayıcıları](../../mfc/activex-control-containers.md)makalesine bakın.

### <a name="event-sink-maps"></a>Olay İç Havuz Eşlemeleri

|Ad|Açıklama|
|-|-|
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|Bir olay havuzu haritasının tanımını başlatır.|
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|Bir olay havuzu eşlemesi bildirir.|
|[END_EVENTSINK_MAP](#end_eventsink_map)|Bir olay havuzu haritasının tanımını sonlandırır.|
|[ON_EVENT](#on_event)|Belirli bir olay için olay işleyicisini tanımlar.|
|[ON_EVENT_RANGE](#on_event_range)|OLE denetimleri kümesinden tetiklenen belirli bir olay için olay işleyicisini tanımlar.|
|[ON_EVENT_REFLECT](#on_event_reflect)|Denetimin kapsayıcısı tarafından işlenebilmeleri için denetim tarafından tetiklenen olayları alır.|
|[ON_PROPNOTIFY](#on_propnotify)|OLE denetiminden Özellik bildirimlerini işlemek için bir işleyici tanımlar.|
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|Bir OLE denetimleri kümesinden Özellik bildirimlerini işlemek için bir işleyici tanımlar.|
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|Denetimin kapsayıcısı tarafından işlenmek üzere denetim tarafından gönderilen Özellik bildirimlerini alır.|

## <a name="begin_eventsink_map"></a><a name="begin_eventsink_map"></a> BEGIN_EVENTSINK_MAP

Olay havuzu haritaınızın tanımını başlatır.

```
BEGIN_EVENTSINK_MAP(theClass, baseClass)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Olay havuzu eşleme bu olan denetim sınıfının adını belirtir.

*baseClass*<br/>
Sınıfın temel sınıfının adını *belirtir.*

### <a name="remarks"></a>Açıklamalar

Sınıfınız için üye işlevlerini tanımlayan uygulama (. cpp) dosyasında, olay havuzu haritasını BEGIN_EVENTSINK_MAP makroyla başlatın, ardından bildirilecek her olay için makro girişleri ekleyin ve olay havuzu haritasını END_EVENTSINK_MAP makroyla doldurun.

Olay havuzu haritaları ve OLE denetim kapsayıcıları hakkında daha fazla bilgi için, [ActiveX denetim kapsayıcıları](../../mfc/activex-control-containers.md)makalesine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="declare_eventsink_map"></a><a name="declare_eventsink_map"></a> DECLARE_EVENTSINK_MAP

OLE kapsayıcısı, kapsayıcınıza bildirilecek olayları belirtmek için bir olay havuzu eşlemesi sağlayabilir.

```
DECLARE_EVENTSINK_MAP()
```

### <a name="remarks"></a>Açıklamalar

Sınıf bildirimindeki sonundaki DECLARE_EVENTSINK_MAP makrosunu kullanın. Ardından içinde. Sınıf için üye işlevlerini tanımlayan CPP dosyası BEGIN_EVENTSINK_MAP makrosunu, bildirilmesi gereken her olay için makro girişlerini ve olay havuzu listesinin sonunu bildirmek için END_EVENTSINK_MAP makrosunu kullanın.

Olay havuzu haritaları hakkında daha fazla bilgi için, [ActiveX denetim kapsayıcıları](../../mfc/activex-control-containers.md)makalesine bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="end_eventsink_map"></a><a name="end_eventsink_map"></a> END_EVENTSINK_MAP

Olay havuzu haritaınızın tanımını sonlandırır.

```
END_EVENTSINK_MAP()
```

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="on_event"></a><a name="on_event"></a> ON_EVENT

OLE denetimi tarafından tetiklenen bir olay için olay işleyicisi işlevini tanımlamak üzere ON_EVENT makrosunu kullanın.

```
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Bu olay havuzu eşlemesinin ait olduğu sınıf.

*id*<br/>
OLE denetiminin denetim KIMLIĞI.

*dı*<br/>
Denetim tarafından tetiklenen olayın dağıtım KIMLIĞI.

*pfnHandler*<br/>
Olayı işleyen bir üye işlevine yönelik işaretçi. Bu işlev bir BOOL dönüş türüne ve olayın parametreleriyle eşleşen parametre türlerine sahip olmalıdır (bkz. *vtsParams*). İşlevin, olayın işlendiğini belirtmek için TRUE döndürmesi gerekir; Aksi halde yanlış.

*vtsParams*<br/>
Olay için parametrelerin türlerini belirten **VTS_** sabitleri dizisi. Bunlar, DISP_FUNCTION gibi dağıtım eşleme girişlerinde kullanılan sabit değerlerdir.

### <a name="remarks"></a>Açıklamalar

*VtsParams* bağımsız değişkeni, **VTS_** sabitlerinden alınan değerlerin boşlukla ayrılmış bir listesidir. Boşluklarla (virgüller değil) ayrılmış bir veya daha fazla değer, işlevin parametre listesini belirtir. Örnek:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

bir BOOL tarafından izlenen kısa tamsayı içeren bir liste belirtir.

**VTS_** sabitlerin listesi için bkz. [event_custom](event-maps.md#event_custom).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="on_event_range"></a><a name="on_event_range"></a> ON_EVENT_RANGE

Ardışık bir kimlik aralığı içinde denetim KIMLIĞI olan herhangi bir OLE denetimi tarafından tetiklenen bir olay için olay işleyicisi işlevini tanımlamak üzere ON_EVENT_RANGE makrosunu kullanın.

```
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Bu olay havuzu eşlemesinin ait olduğu sınıf.

*Önce ıdden*<br/>
Aralıktaki ilk OLE denetiminin denetim KIMLIĞI.

*ıdlast*<br/>
Aralıktaki son OLE denetiminin denetim KIMLIĞI.

*dı*<br/>
Denetim tarafından tetiklenen olayın dağıtım KIMLIĞI.

*pfnHandler*<br/>
Olayı işleyen bir üye işlevine yönelik işaretçi. Bu işlev bir BOOL dönüş türüne, UINT türünde bir ilk parametreye (denetim KIMLIĞI için) ve olay parametreleriyle eşleşen ek parametre türlerine sahip olmalıdır (bkz. *vtsParams*). İşlevin, olayın işlendiğini belirtmek için TRUE döndürmesi gerekir; Aksi halde yanlış.

*vtsParams*<br/>
Olay için parametrelerin türlerini belirten **VTS_** sabitleri dizisi. İlk sabit, denetim KIMLIĞI için VTS_I4 türünde olmalıdır. Bunlar, DISP_FUNCTION gibi dağıtım eşleme girişlerinde kullanılan sabit değerlerdir.

### <a name="remarks"></a>Açıklamalar

*VtsParams* bağımsız değişkeni, **VTS_** sabitlerinden alınan değerlerin boşlukla ayrılmış bir listesidir. Boşluklarla (virgüller değil) ayrılmış bir veya daha fazla değer, işlevin parametre listesini belirtir. Örnek:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

bir BOOL tarafından izlenen kısa tamsayı içeren bir liste belirtir.

**VTS_** sabitlerin listesi için bkz. [event_custom](event-maps.md#event_custom).

### <a name="example"></a>Örnek

Aşağıdaki örnek, üç denetim (IDC_MYCTRL3 üzerinden IDC_MYCTRL1) için uygulanan MouseDown olayı için bir olay işleyicisini gösterir. Olay işleyici işlevi, `OnRangeMouseDown` iletişim kutusu sınıfının başlık dosyasında ( `CMyDlg` ) şöyle belirtilir:

[!code-cpp[NVC_MFCAutomation#12](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]

Aşağıdaki kod, iletişim kutusu sınıfının uygulama dosyasında tanımlanmıştır.

[!code-cpp[NVC_MFCAutomation#13](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="on_event_reflect"></a><a name="on_event_reflect"></a> ON_EVENT_REFLECT

OLE denetiminin sarmalayıcı sınıfının olay havuzu eşlemesinde kullanılan ON_EVENT_REFLECT makrosu, denetimin kapsayıcısı tarafından işlenebilmeleri için denetim tarafından tetiklenen olayları alır.

```
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Bu olay havuzu eşlemesinin ait olduğu sınıf.

*dı*<br/>
Denetim tarafından tetiklenen olayın dağıtım KIMLIĞI.

*pfnHandler*<br/>
Olayı işleyen bir üye işlevine yönelik işaretçi. Bu işlev, olayın parametreleriyle eşleşen bir BOOL dönüş türüne ve parametre türlerine sahip olmalıdır (bkz. *vtsParams*). İşlevin, olayın işlendiğini belirtmek için TRUE döndürmesi gerekir; Aksi halde yanlış.

*vtsParams*<br/>
Olay için parametrelerin türlerini belirten **VTS_** sabitleri dizisi. Bunlar, DISP_FUNCTION gibi dağıtım eşleme girişlerinde kullanılan sabit değerlerdir.

### <a name="remarks"></a>Açıklamalar

*VtsParams* bağımsız değişkeni, **VTS_** sabitlerinden alınan değerlerin boşlukla ayrılmış bir listesidir.

Boşluklarla (virgüller değil) ayrılmış bir veya daha fazla değer, işlevin parametre listesini belirtir. Örnek:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

bir BOOL tarafından izlenen kısa tamsayı içeren bir liste belirtir.

**VTS_** sabitlerin listesi için bkz. [event_custom](event-maps.md#event_custom).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="on_propnotify"></a><a name="on_propnotify"></a> ON_PROPNOTIFY

OLE denetiminden Özellik bildirimlerini işlemek için bir olay havuzu eşleme girişi tanımlamak üzere ON_PROPNOTIFY makrosunu kullanın.

```
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Bu olay havuzu eşlemesinin ait olduğu sınıf.

*id*<br/>
OLE denetiminin denetim KIMLIĞI.

*dı*<br/>
Bildirimde yer alan özelliğin dağıtım KIMLIĞI.

*PF*<br/>
Bu özellik için bildirimi işleyen bir üye işlevi işaretçisi `OnRequestEdit` . Bu işlev bir BOOL dönüş türüne ve **bool** <strong>\*</strong> parametresine sahip olmalıdır. Bu işlev, özelliğin değiştirilmesine ve yanlış olmasına izin vermek için parametresini TRUE olarak ayarlanmalıdır. İşlevin, bildirimin işlendiğini belirtmek için TRUE döndürmesi gerekir; Aksi halde yanlış.

*pfnChanged*<br/>
Bu özellik için bildirimi işleyen bir üye işlevi işaretçisi `OnChanged` . İşlevin bir BOOL dönüş türü ve bir UINT parametresi olmalıdır. İşlevin bildirimin işlendiğini göstermek için TRUE döndürmesi gerekir; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

*VtsParams* bağımsız değişkeni, **VTS_** sabitlerinden alınan değerlerin boşlukla ayrılmış bir listesidir. Boşluklarla (virgüller değil) ayrılmış bir veya daha fazla değer, işlevin parametre listesini belirtir. Örnek:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

bir BOOL tarafından izlenen kısa tamsayı içeren bir liste belirtir.

**VTS_** sabitlerin listesi için bkz. [event_custom](event-maps.md#event_custom).

## <a name="on_propnotify_range"></a><a name="on_propnotify_range"></a> ON_PROPNOTIFY_RANGE

Sürekli bir kimlik aralığı içinde denetim KIMLIĞI olan herhangi bir OLE denetiminden Özellik bildirimlerini işlemek için bir olay havuzu eşleme girişi tanımlamak üzere ON_PROPNOTIFY_RANGE makrosunu kullanın.

```

ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Bu olay havuzu eşlemesinin ait olduğu sınıf.

*Önce ıdden*<br/>
Aralıktaki ilk OLE denetiminin denetim KIMLIĞI.

*ıdlast*<br/>
Aralıktaki son OLE denetiminin denetim KIMLIĞI.

*dı*<br/>
Bildirimde yer alan özelliğin dağıtım KIMLIĞI.

*PF*<br/>
Bu özellik için bildirimi işleyen bir üye işlevi işaretçisi `OnRequestEdit` . Bu işlevin `BOOL` dönüş türü ve `UINT` `BOOL*` parametreleri olmalıdır. Özelliğin değiştirilmesine ve yanlış olmasına izin vermek için, işlevin parametresi TRUE olarak ayarlanmalıdır. İşlevin bildirimin işlendiğini göstermek için TRUE döndürmesi gerekir; Aksi halde yanlış.

*pfnChanged*<br/>
Bu özellik için bildirimi işleyen bir üye işlevi işaretçisi `OnChanged` . İşlevin `BOOL` dönüş türü ve `UINT` parametresi olmalıdır. İşlevin bildirimin işlendiğini göstermek için TRUE döndürmesi gerekir; Aksi halde yanlış.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="on_propnotify_reflect"></a><a name="on_propnotify_reflect"></a> ON_PROPNOTIFY_REFLECT

OLE denetiminin sarmalayıcı sınıfının olay havuzu eşlemesinde kullanılan ON_PROPNOTIFY_REFLECT makrosu, denetimin kapsayıcısı tarafından işlenebilmeleri için denetim tarafından gönderilen Özellik bildirimlerini alır.

```

ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Bu olay havuzu eşlemesinin ait olduğu sınıf.

*dı*<br/>
Bildirimde yer alan özelliğin dağıtım KIMLIĞI.

*PF*<br/>
Bu özellik için bildirimi işleyen bir üye işlevi işaretçisi `OnRequestEdit` . Bu işlev bir BOOL dönüş türüne ve **bool** <strong>\*</strong> parametresine sahip olmalıdır. Bu işlev, özelliğin değiştirilmesine ve yanlış olmasına izin vermek için parametresini TRUE olarak ayarlanmalıdır. İşlevin, bildirimin işlendiğini belirtmek için TRUE döndürmesi gerekir; Aksi halde yanlış.

*pfnChanged*<br/>
Bu özellik için bildirimi işleyen bir üye işlevi işaretçisi `OnChanged` . İşlevin BOOL dönüş türü ve parametre olmaması gerekir. İşlevin, bildirimin işlendiğini belirtmek için TRUE döndürmesi gerekir; Aksi halde yanlış.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
