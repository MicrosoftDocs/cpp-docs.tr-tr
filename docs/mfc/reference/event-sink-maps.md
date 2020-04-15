---
title: Olay İç Havuz Eşlemeleri
ms.date: 11/04/2016
helpviewer_keywords:
- event sink maps [MFC]
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
ms.openlocfilehash: 731ed2403aae3332e81702673d1181e9e52399a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365730"
---
# <a name="event-sink-maps"></a>Olay İç Havuz Eşlemeleri

Katıştırılmış bir OLE denetimi bir olayı ateşlediğinde, denetimin kapsayıcısı olayı MFC tarafından sağlanan "olay lavabo haritası" adı verilen bir mekanizma kullanarak alır. Bu olay lavabo eşlemi, her belirli olay için işleyici işlevlerinin yanı sıra bu olayların parametrelerini belirtir. Olay lavabo haritaları hakkında daha fazla bilgi için [ActiveX Denetim Kapları](../../mfc/activex-control-containers.md)makalesine bakın.

### <a name="event-sink-maps"></a>Olay İç Havuz Eşlemeleri

|||
|-|-|
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|Olay lavabo haritasının tanımını başlatır.|
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|Olay lavabo haritasını bildirir.|
|[END_EVENTSINK_MAP](#end_eventsink_map)|Olay lavabo haritasının tanımını sona erdirer.|
|[ON_EVENT](#on_event)|Belirli bir olay için olay işleyicisi tanımlar.|
|[ON_EVENT_RANGE](#on_event_range)|Bir dizi OLE denetiminden ateşlenen belirli bir olay için bir olay işleyicisi tanımlar.|
|[ON_EVENT_REFLECT](#on_event_reflect)|Denetim inkontu tarafından işlenmeden önce denetim tarafından ateşlenen olayları alır.|
|[ON_PROPNOTIFY](#on_propnotify)|OLE denetiminden özellik bildirimlerini işlemek için bir işleyici tanımlar.|
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|Bir dizi OLE denetiminden özellik bildirimlerini işlemek için bir işleyici tanımlar.|
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|Denetim kapsayıcısı tarafından işlenmeden önce denetim tarafından gönderilen özellik bildirimlerini alır.|

## <a name="begin_eventsink_map"></a><a name="begin_eventsink_map"></a>BEGIN_EVENTSINK_MAP

Olay lavabo haritanızın tanımını başlayır.

```
BEGIN_EVENTSINK_MAP(theClass, baseClass)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Olay lavabo haritası bu olan denetim sınıfının adını belirtir.

*Baseclass*<br/>
*Sınıfın*taban sınıfının adını belirtir.

### <a name="remarks"></a>Açıklamalar

Sınıfınızın üye işlevlerini tanımlayan uygulama (.cpp) dosyasında, olay BEGIN_EVENTSINK_MAP makrosuyla olay lavabo haritasını başlatın, ardından bildirilecek her olay için makro girişleri ekleyin ve END_EVENTSINK_MAP makrosuyla olay lavabo haritasını tamamlayın.

Olay lavabo haritaları ve OLE kontrol kapları hakkında daha fazla bilgi için [ActiveX Kontrol Kapları](../../mfc/activex-control-containers.md)makalesine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="declare_eventsink_map"></a><a name="declare_eventsink_map"></a>DECLARE_EVENTSINK_MAP

Bir OLE kapsayıcısı, kapsayıcınızın bilgilendirileceği olayları belirtmek için bir olay lavabo haritası sağlayabilir.

```
DECLARE_EVENTSINK_MAP()
```

### <a name="remarks"></a>Açıklamalar

Sınıf bildirgenizin sonundaki DECLARE_EVENTSINK_MAP makroyu kullanın. Sonra, içinde. Sınıfın üye işlevlerini tanımlayan CPP dosyası, BEGIN_EVENTSINK_MAP makroyu, bildirilecek olayların her biri için makro girişlerini ve olay lavabo listesinin sonunu bildirmek için END_EVENTSINK_MAP makroyu kullanır.

Olay lavabo haritaları hakkında daha fazla bilgi için [ActiveX Denetim Kapları](../../mfc/activex-control-containers.md)makalesine bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="end_eventsink_map"></a><a name="end_eventsink_map"></a>END_EVENTSINK_MAP

Olay lavabo haritanızın tanımını sona erdirer.

```
END_EVENTSINK_MAP()
```

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="on_event"></a><a name="on_event"></a>ON_EVENT

OLE denetimi tarafından ateşlenen bir olay için olay işleyicisi işlevini tanımlamak için ON_EVENT makroyu kullanın.

```
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Bu olayın haritayı batırdığı sınıf ait.

*Kimliği*<br/>
OLE denetiminin kontrol kimliği.

*Dıspıd*<br/>
Kontrol tarafından ateşlenen olayın sevk kimliği.

*pfnHandler*<br/>
Olayı işleyen bir üye işlevi işaretçi. Bu işlev, bir BOOL dönüş türüne ve olayın parametrelerine uyan parametre türlerine sahip olmalıdır (bkz. *vtsParams).* Olay işlendi belirtmek için işlev TRUE döndürmelidir; aksi takdirde YANLIŞ.

*vtsParams*<br/>
Olayın parametrelerinin türlerini belirten **VTS_** sabitleri dizisi. Bunlar, DISP_FUNCTION gibi gönderme eşlemi girişlerinde kullanılan sabitlerle aynıdır.

### <a name="remarks"></a>Açıklamalar

*vtsParams* bağımsız **değişkeni, VTS_** sabitlerinden gelen değerlerin boşluktan ayrılmış bir listesidir. Boşluklarla ayrılan bu değerlerden biri veya birkaçı (virgül değil) işlevin parametre listesini belirtir. Örneğin:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

kısa bir tamsayı içeren bir liste ve ardından BOOL belirtir.

**VTS_** sabitlerin listesi için [EVENT_CUSTOM](event-maps.md#event_custom)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="on_event_range"></a><a name="on_event_range"></a>ON_EVENT_RANGE

Bitişik bir kimlik aralığında denetim kimliğine sahip herhangi bir OLE denetimi tarafından ateşlenen bir olay için bir olay işleyicisi işlevini tanımlamak için ON_EVENT_RANGE makroyu kullanın.

```
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Bu olayın haritayı batırdığı sınıf ait.

*idFirst*<br/>
Aralıktaki ilk OLE denetiminin kontrol kimliği.

*idSon*<br/>
Aralıktaki son OLE denetiminin kontrol kimliği.

*Dıspıd*<br/>
Kontrol tarafından ateşlenen olayın sevk kimliği.

*pfnHandler*<br/>
Olayı işleyen bir üye işlevi işaretçi. Bu işlev, BOOL dönüş türüne, UINT türünün ilk parametresine (denetim kimliği için) ve olayın parametrelerine uyan ek parametre türlerine sahip olmalıdır (bkz. *vtsParams).* Olay işlendi belirtmek için işlev TRUE döndürmelidir; aksi takdirde YANLIŞ.

*vtsParams*<br/>
Olayın parametrelerinin türlerini belirten **VTS_** sabitleri dizisi. Kontrol kimliği için ilk sabit VTS_I4 türü olmalıdır. Bunlar, DISP_FUNCTION gibi gönderme eşlemi girişlerinde kullanılan sabitlerle aynıdır.

### <a name="remarks"></a>Açıklamalar

*vtsParams* bağımsız **değişkeni, VTS_** sabitlerinden gelen değerlerin boşluktan ayrılmış bir listesidir. Boşluklarla ayrılan bu değerlerden biri veya birkaçı (virgül değil) işlevin parametre listesini belirtir. Örneğin:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

kısa bir tamsayı içeren bir liste ve ardından BOOL belirtir.

**VTS_** sabitlerin listesi için [EVENT_CUSTOM](event-maps.md#event_custom)bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, Üç denetim için uygulanan MouseDown olayı için bir olay işleyicisi (IDC_MYCTRL3 ile IDC_MYCTRL1) gösterir. Olay işleyicisi `OnRangeMouseDown`işlevi, iletişim sınıfının üstbilgi dosyasında `CMyDlg`( ) olarak bildirilir:

[!code-cpp[NVC_MFCAutomation#12](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]

Aşağıdaki kod iletişim sınıfının uygulama dosyasında tanımlanır.

[!code-cpp[NVC_MFCAutomation#13](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="on_event_reflect"></a><a name="on_event_reflect"></a>ON_EVENT_REFLECT

ON_EVENT_REFLECT makrosu, bir OLE denetiminin sarıcı sınıfının olay lavabo haritasında kullanıldığında, denetimin kapsayıcısı tarafından işlenmeden önce denetim tarafından ateşlenen olayları alır.

```
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Bu olayın haritayı batırdığı sınıf ait.

*Dıspıd*<br/>
Kontrol tarafından ateşlenen olayın sevk kimliği.

*pfnHandler*<br/>
Olayı işleyen bir üye işlevi işaretçi. Bu işlev, olayın parametrelerine uyan bir BOOL dönüş türüne ve parametre türlerine sahip olmalıdır (bkz. *vtsParams).* Olay işlendi belirtmek için işlev TRUE döndürmelidir; aksi takdirde YANLIŞ.

*vtsParams*<br/>
Olayın parametrelerinin türlerini belirten **VTS_** sabitleri dizisi. Bunlar, DISP_FUNCTION gibi gönderme eşlemi girişlerinde kullanılan sabitlerle aynıdır.

### <a name="remarks"></a>Açıklamalar

*vtsParams* bağımsız **değişkeni, VTS_** sabitlerinden gelen değerlerin boşluktan ayrılmış bir listesidir.

Boşluklarla ayrılan bu değerlerden biri veya birkaçı (virgül değil) işlevin parametre listesini belirtir. Örneğin:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

kısa bir tamsayı içeren bir liste ve ardından BOOL belirtir.

**VTS_** sabitlerin listesi için [EVENT_CUSTOM](event-maps.md#event_custom)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="on_propnotify"></a><a name="on_propnotify"></a>ON_PROPNOTIFY

OLE denetiminden özellik bildirimlerini işlemek için bir olay lavabo eşleme girişi tanımlamak için ON_PROPNOTIFY makroyu kullanın.

```
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Bu olayın haritayı batırdığı sınıf ait.

*Kimliği*<br/>
OLE denetiminin kontrol kimliği.

*Dıspıd*<br/>
Bildirimde yer alan özelliğin sevk kimliği.

*pfnRequest*<br/>
Bu özellik için `OnRequestEdit` bildirimi işleyen bir üye işlevi işaretçisi. Bu işlevbir BOOL dönüş türüne ve **BOOL** <strong>\*</strong> parametresine sahip olmalıdır. Bu işlev, özelliğin değişmesine ve FALSE'un izin vermemesine izin vermek için parametreyi TRUE olarak ayarlamalıdır. İşlev, bildirimin işleneceğini belirtmek için TRUE döndürmelidir; aksi takdirde YANLIŞ.

*pfnDeğiştirildi*<br/>
Bu özellik için `OnChanged` bildirimi işleyen bir üye işlevi işaretçisi. İşlev bool dönüş türüne ve UINT parametreye sahip olmalıdır. Bildirimin işleneceğini belirtmek için işlev TRUE döndürmelidir; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

*vtsParams* bağımsız **değişkeni, VTS_** sabitlerinden gelen değerlerin boşluktan ayrılmış bir listesidir. Boşluklarla ayrılan bu değerlerden biri veya birkaçı (virgül değil) işlevin parametre listesini belirtir. Örneğin:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

kısa bir tamsayı içeren bir liste ve ardından BOOL belirtir.

**VTS_** sabitlerin listesi için [EVENT_CUSTOM](event-maps.md#event_custom)bakın.

## <a name="on_propnotify_range"></a><a name="on_propnotify_range"></a>ON_PROPNOTIFY_RANGE

Bitişik bir kimlik aralığında denetim kimliğine sahip herhangi bir OLE denetiminden gelen özellik bildirimlerini işlemek için bir olay lavabo haritası girişi tanımlamak için ON_PROPNOTIFY_RANGE makroyu kullanın.

```

ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Bu olayın haritayı batırdığı sınıf ait.

*idFirst*<br/>
Aralıktaki ilk OLE denetiminin kontrol kimliği.

*idSon*<br/>
Aralıktaki son OLE denetiminin kontrol kimliği.

*Dıspıd*<br/>
Bildirimde yer alan özelliğin sevk kimliği.

*pfnRequest*<br/>
Bu özellik için `OnRequestEdit` bildirimi işleyen bir üye işlevi işaretçisi. Bu işlevin `BOOL` bir dönüş `UINT` `BOOL*` türü ve parametreleri olmalıdır. İşlev, özelliğin değişmesine ve FALSE'un izin vermemesine izin vermek için parametreyi TRUE olarak ayarlamalıdır. Bildirimin işleneceğini belirtmek için işlev TRUE döndürmelidir; aksi takdirde YANLIŞ.

*pfnDeğiştirildi*<br/>
Bu özellik için `OnChanged` bildirimi işleyen bir üye işlevi işaretçisi. İşlevin bir `BOOL` dönüş türü `UINT` ve bir parametresi olmalıdır. Bildirimin işleneceğini belirtmek için işlev TRUE döndürmelidir; aksi takdirde YANLIŞ.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="on_propnotify_reflect"></a><a name="on_propnotify_reflect"></a>ON_PROPNOTIFY_REFLECT

ON_PROPNOTIFY_REFLECT makrosu, bir OLE denetiminin sarıcı sınıfının olay lavabo haritasında kullanıldığında, denetim kapsayıcısı tarafından işlenmeden önce denetim tarafından gönderilen özellik bildirimlerini alır.

```

ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Bu olayın haritayı batırdığı sınıf ait.

*Dıspıd*<br/>
Bildirimde yer alan özelliğin sevk kimliği.

*pfnRequest*<br/>
Bu özellik için `OnRequestEdit` bildirimi işleyen bir üye işlevi işaretçisi. Bu işlevbir BOOL dönüş türüne ve **BOOL** <strong>\*</strong> parametresine sahip olmalıdır. Bu işlev, özelliğin değişmesine ve FALSE'un izin vermemesine izin vermek için parametreyi TRUE olarak ayarlamalıdır. İşlev, bildirimin işleneceğini belirtmek için TRUE döndürmelidir; aksi takdirde YANLIŞ.

*pfnDeğiştirildi*<br/>
Bu özellik için `OnChanged` bildirimi işleyen bir üye işlevi işaretçisi. İşlev bool dönüş türüne sahip olmalı ve parametreleri olmamalıdır. İşlev, bildirimin işleneceğini belirtmek için TRUE döndürmelidir; aksi takdirde YANLIŞ.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
