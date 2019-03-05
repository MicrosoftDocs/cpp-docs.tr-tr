---
title: Olay İç Havuz Eşlemeleri
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.maps
helpviewer_keywords:
- event sink maps [MFC]
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
ms.openlocfilehash: 8e33636253b269692f87f99980b9da0cd60867ee
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285587"
---
# <a name="event-sink-maps"></a>Olay İç Havuz Eşlemeleri

Katıştırılmış bir OLE denetim bir olay oluşturulduğunda, denetimin kapsayıcısı "MFC tarafından sağlanan bir olay havuzu eşlemesi," adlı bir mekanizma kullanarak olayı alır. Bu olay havuzu eşlemesi işleyici işlevlerini her özel olay yanı sıra bu olayların parametreleri belirtir. Olay iç havuz eşlemeleri hakkında daha fazla bilgi için bkz [ActiveX denetim kapsayıcıları](../../mfc/activex-control-containers.md).

### <a name="event-sink-maps"></a>Olay İç Havuz Eşlemeleri

|||
|-|-|
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|Bir olay havuzu eşlemesi tanımını başlatır.|
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|Bir olay havuzu eşlemesi bildirir.|
|[END_EVENTSINK_MAP](#end_eventsink_map)|Bir olay havuzu eşlemesi tanımını sonlandırır.|
|[ON_EVENT](#on_event)|Belirli bir olay için bir olay işleyicisi tanımlar.|
|[ON_EVENT_RANGE](#on_event_range)|OLE denetimleri kümesinden harekete belirli bir olay için bir olay işleyicisi tanımlar.|
|[ON_EVENT_REFLECT](#on_event_reflect)|Önce denetimin kapsayıcı tarafından işlenen denetim tarafından tetiklenen olayları alır.|
|[ON_PROPNOTIFY](#on_propnotify)|Bir OLE denetim özelliği bildirimleri işlemek için bir işleyici tanımlar.|
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|OLE denetimleri bir dizi özellik bildirimleri işlemek için bir işleyici tanımlar.|
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|Denetimin kapsayıcı tarafından işlenen önce bir denetim tarafından gönderilen özellik bildirimleri alır.|

##  <a name="begin_eventsink_map"></a>  BEGIN_EVENTSINK_MAP

Olay havuzu haritanızı tanımını başlar.

```
BEGIN_EVENTSINK_MAP(theClass, baseClass)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Bu eşleme olan olay havuzu denetim sınıfın adını belirtir.

*baseClass*<br/>
Taban sınıfının adını belirtir *sınıfın*.

### <a name="remarks"></a>Açıklamalar

Sınıfınız için üye işlevleri tanımlayan uygulama dosyasında (.cpp), olay havuzu eşlemesi begın_eventsınk_map makrosu ile Başlat sonra her olay, bildirim almak için makro girişler ekleyin ve olay havuzu eşlemesi end_eventsınk_map makrosu ile tamamlayın.

Olay iç havuz eşlemeleri ve OLE denetimi kapsayıcıları hakkında daha fazla bilgi için bkz [ActiveX denetim kapsayıcıları](../../mfc/activex-control-containers.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="declare_eventsink_map"></a>  DECLARE_EVENTSINK_MAP

OLE kapsayıcısı kapsayıcınızı, bildirim olayları belirtmek için bir olay havuzu eşlemesi sağlayabilir.

```
DECLARE_EVENTSINK_MAP()
```

### <a name="remarks"></a>Açıklamalar

Declare_eventsınk_map makrosu, sınıf bildiriminin sonuna kullanın. Ardından. Sınıfın üye işlevleri tanımlar CPP dosyasını kullanmak begın_eventsınk_map makrosu, makro girişleri her bildirilmesini olayları ve olay havuzu listesinin sonuna bildirmek için end_eventsınk_map makrosu.

Olay iç havuz eşlemeleri hakkında daha fazla bilgi için bkz [ActiveX denetim kapsayıcıları](../../mfc/activex-control-containers.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="end_eventsink_map"></a>  END_EVENTSINK_MAP

Olay havuzu haritanızı tanımını sonlandırır.

```
END_EVENTSINK_MAP()
```

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="on_event"></a>  ON_EVENT

ON_EVENT makrosu, bir olay işleyici işlevi için bir OLE denetimi tarafından tetiklenen bir olayı tanımlamak için kullanın.

```
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Bu olay havuzu eşlemesi ait olduğu sınıf.

*id*<br/>
OLE denetim denetiminin kimliği.

*DISPID*<br/>
Denetim tarafından harekete geçirilen olay gönderme kimliği.

*pfnHandler*<br/>
Olayı işleyen bir üye işlevi işaretçisi. Bu işlev dönüş türü ve olay parametreleriyle eşleşen parametre türleri BOOL olmalıdır (bkz *vtsParams*). İşlevi, olay işlendiğini göstermek için TRUE döndürmelidir; Aksi durumda FALSE.

*vtsParams*<br/>
Bir dizi **VTS_** sabitler parametreler için olay türlerini belirtir. Bu dağıtım eşleme girişleri dısp_functıon gibi kullanılan aynı sabittir.

### <a name="remarks"></a>Açıklamalar

*VtsParams* bağımsız değişken değerlerini boşlukla ayrılmış bir listesi verilmiştir **VTS_** sabitler. Bir veya daha fazla boşluk (virgül değil) ile ayırarak bu değerleri işlevin parametre listesi belirtir. Örneğin:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

BOOL tarafından izlenen bir kısa tamsayı içeren bir liste belirtir.

Bir listesi için **VTS_** sabitleri bkz [EVENT_CUSTOM](event-maps.md#event_custom).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="on_event_range"></a>  ON_EVENT_RANGE

ON_EVENT_RANGE makrosu, bir olay işleyici işlevi bitişik olarak kimlikleri aralığı içinde bir denetim Kimliğine sahip herhangi bir OLE denetimi tarafından tetiklenen bir olayı tanımlamak için kullanın.

```
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Bu olay havuzu eşlemesi ait olduğu sınıf.

*idFirst*<br/>
Aralığın ilk OLE denetim denetiminin kimliği.

*idLast*<br/>
Aralıktaki son OLE denetim denetiminin kimliği.

*DISPID*<br/>
Denetim tarafından harekete geçirilen olay gönderme kimliği.

*pfnHandler*<br/>
Olayı işleyen bir üye işlevi işaretçisi. Bu işlev dönüş türü, ilk parametre türü UINT (için denetim kimliği) ve olay parametreleriyle eşleşen ek parametre türleri olarak BOOL olmalıdır (bkz *vtsParams*). İşlevi, olay işlendiğini göstermek için TRUE döndürmelidir; Aksi durumda FALSE.

*vtsParams*<br/>
Bir dizi **VTS_** sabitler parametreler için olay türlerini belirtir. Denetim Kimliği VTS_I4, türünün ilk sabiti olmalıdır Bu dağıtım eşleme girişleri dısp_functıon gibi kullanılan aynı sabittir.

### <a name="remarks"></a>Açıklamalar

*VtsParams* bağımsız değişken değerlerini boşlukla ayrılmış bir listesi verilmiştir **VTS_** sabitler. Bir veya daha fazla boşluk (virgül değil) ile ayırarak bu değerleri işlevin parametre listesi belirtir. Örneğin:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

BOOL tarafından izlenen bir kısa tamsayı içeren bir liste belirtir.

Bir listesi için **VTS_** sabitleri bkz [EVENT_CUSTOM](event-maps.md#event_custom).

### <a name="example"></a>Örnek

Aşağıdaki örnek, üç denetim için uygulanan MouseDown olayı için bir olay işleyicisi gösterir (IDC_MYCTRL1 IDC_MYCTRL3 aracılığıyla). Olay işleyici işlevi `OnRangeMouseDown`, iletişim kutusu sınıfı üstbilgi dosyasında bildirilen ( `CMyDlg`) olarak:

[!code-cpp[NVC_MFCAutomation#12](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]

Aşağıdaki kod, iletişim kutusu sınıfı uygulama dosyasında tanımlanır.

[!code-cpp[NVC_MFCAutomation#13](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="on_event_reflect"></a>  ON_EVENT_REFLECT

Olay bir OLE denetim sarmalayıcı sınıfı, havuz haritasını kullanıldığında ON_EVENT_REFLECT makrosu önce denetimin kapsayıcı tarafından işlenen denetim tarafından tetiklenen olayları alır.

```
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Bu olay havuzu eşlemesi ait olduğu sınıf.

*DISPID*<br/>
Denetim tarafından harekete geçirilen olay gönderme kimliği.

*pfnHandler*<br/>
Olayı işleyen bir üye işlevi işaretçisi. Bu işlev dönüş türü ve olay parametreleriyle eşleşen parametre türleri BOOL olmalıdır (bkz *vtsParams*). İşlevi, olay işlendiğini göstermek için TRUE döndürmelidir; Aksi durumda FALSE.

*vtsParams*<br/>
Bir dizi **VTS_** sabitler parametreler için olay türlerini belirtir. Bu dağıtım eşleme girişleri dısp_functıon gibi kullanılan aynı sabittir.

### <a name="remarks"></a>Açıklamalar

*VtsParams* bağımsız değişken değerlerini boşlukla ayrılmış bir listesi verilmiştir **VTS_** sabitler.

Bir veya daha fazla boşluk (virgül değil) ile ayırarak bu değerleri işlevin parametre listesi belirtir. Örneğin:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

BOOL tarafından izlenen bir kısa tamsayı içeren bir liste belirtir.

Bir listesi için **VTS_** sabitleri bkz [EVENT_CUSTOM](event-maps.md#event_custom).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="on_propnotify"></a>  ON_PROPNOTIFY

On_propnotıfy makrosu bir OLE denetim özelliği bildirimleri işlemek için bir olay havuzu eşleme girişi tanımlamak için kullanın.

```
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Bu olay havuzu eşlemesi ait olduğu sınıf.

*id*<br/>
OLE denetim denetiminin kimliği.

*DISPID*<br/>
Özellik bildiriminde ilgili dağıtım kimliği.

*pfnRequest*<br/>
İşleme bir üye işlevi işaretçisi `OnRequestEdit` bu özellik için bildirim. Bu işlev dönüş türü BOOL olmalıdır ve bir **BOOL** <strong>\*</strong> parametresi. Bu işlev, parametre değiştirme özelliğine izin vermek için TRUE ve FALSE izin vermeyecek şekilde ayarlamanız gerekir. İşlev bildirim işlendiğini göstermek için TRUE döndürmelidir; Aksi durumda FALSE.

*pfnChanged*<br/>
İşleme bir üye işlevi işaretçisi `OnChanged` bu özellik için bildirim. İşlev dönüş türü ve UINT parametre bir Boole olmalıdır. İşlev bildirim işlendiğini göstermek için TRUE döndürmelidir; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

*VtsParams* bağımsız değişken değerlerini boşlukla ayrılmış bir listesi verilmiştir **VTS_** sabitler. Bir veya daha fazla boşluk (virgül değil) ile ayırarak bu değerleri işlevin parametre listesi belirtir. Örneğin:

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

BOOL tarafından izlenen bir kısa tamsayı içeren bir liste belirtir.

Bir listesi için **VTS_** sabitleri bkz [EVENT_CUSTOM](event-maps.md#event_custom).

##  <a name="on_propnotify_range"></a>  ON_PROPNOTIFY_RANGE

On_propnotıfy_range makrosu bitişik olarak kimlikleri aralığı içinde bir denetim Kimliğine sahip herhangi bir OLE denetimi özellik bildirimleri işlemek için bir olay havuzu eşleme girişi tanımlamak için kullanın.

```

ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Bu olay havuzu eşlemesi ait olduğu sınıf.

*idFirst*<br/>
Aralığın ilk OLE denetim denetiminin kimliği.

*idLast*<br/>
Aralıktaki son OLE denetim denetiminin kimliği.

*DISPID*<br/>
Özellik bildiriminde ilgili dağıtım kimliği.

*pfnRequest*<br/>
İşleme bir üye işlevi işaretçisi `OnRequestEdit` bu özellik için bildirim. Bu işlev olmalıdır bir `BOOL` dönüş türü ve `UINT` ve `BOOL*` parametreleri. İşlev parametre değiştirme özelliğine izin vermek için TRUE ve FALSE izin vermeyecek şekilde ayarlamanız gerekir. İşlev bildirim işlendiğini göstermek için TRUE döndürmelidir; Aksi durumda FALSE.

*pfnChanged*<br/>
İşleme bir üye işlevi işaretçisi `OnChanged` bu özellik için bildirim. İşlev olmalıdır bir `BOOL` dönüş türü ve `UINT` parametresi. İşlev bildirim işlendiğini göstermek için TRUE döndürmelidir; Aksi durumda FALSE.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="on_propnotify_reflect"></a>  ON_PROPNOTIFY_REFLECT

Olay bir OLE denetim sarmalayıcı sınıfı, havuz haritasını kullanıldığında on_propnotıfy_reflect makrosu önce denetimin kapsayıcı tarafından işlenen denetim tarafından gönderilen özellik bildirimleri alır.

```

ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Bu olay havuzu eşlemesi ait olduğu sınıf.

*DISPID*<br/>
Özellik bildiriminde ilgili dağıtım kimliği.

*pfnRequest*<br/>
İşleme bir üye işlevi işaretçisi `OnRequestEdit` bu özellik için bildirim. Bu işlev dönüş türü BOOL olmalıdır ve bir **BOOL** <strong>\*</strong> parametresi. Bu işlev, parametre değiştirme özelliğine izin vermek için TRUE ve FALSE izin vermeyecek şekilde ayarlamanız gerekir. İşlev bildirim işlendiğini göstermek için TRUE döndürmelidir; Aksi durumda FALSE.

*pfnChanged*<br/>
İşleme bir üye işlevi işaretçisi `OnChanged` bu özellik için bildirim. İşlev dönüş türü ve parametre bir Boole olmalıdır. İşlev bildirim işlendiğini göstermek için TRUE döndürmelidir; Aksi durumda FALSE.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
