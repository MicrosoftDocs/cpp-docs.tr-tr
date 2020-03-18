---
title: İleti eşleme makroları (ATL)
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::ALT_MSG_MAP
- atlwin/ATL::BEGIN_MSG_MAP
- atlwin/ATL::CHAIN_MSG_MAP_ALT
- atlwin/ATL::CHAIN_MSG_MAP_ALT_MEMBER
- atlwin/ATL::CHAIN_MSG_MAP
- atlwin/ATL::CHAIN_MSG_MAP_DYNAMIC
- atlwin/ATL::CHAIN_MSG_MAP_MEMBER
- atlwin/ATL::COMMAND_CODE_HANDLER
- atlwin/ATL::COMMAND_HANDLER
- atlwin/ATL::COMMAND_ID_HANDLER
- atlwin/ATL::COMMAND_RANGE_CODE_HANDLER
- atlwin/ATL::COMMAND_RANGE_HANDLER
- atlwin/ATL::DECLARE_EMPTY_MSG_MAP
- atlwin/ATL::DEFAULT_REFLECTION_HANDLER
- atlwin/ATL::END_MSG_MAP
- atlwin/ATL::FORWARD_NOTIFICATIONS
- atlwin/ATL::MESSAGE_HANDLER
- atlwin/ATL::MESSAGE_RANGE_HANDLER
- atlwin/ATL::NOTIFY_CODE_HANDLER
- atlwin/ATL::NOTIFY_HANDLER
- atlwin/ATL::NOTIFY_ID_HANDLER
- atlwin/ATL::NOTIFY_RANGE_CODE_HANDLER
- atlwin/ATL::NOTIFY_RANGE_HANDLER
- atlwin/ATL::REFLECT_NOTIFICATIONS
- atlwin/ATL::REFLECTED_COMMAND_CODE_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_ID_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_RANGE_CODE_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_RANGE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_CODE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_ID_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_RANGE_CODE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_RANGE_HANDLER
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
ms.openlocfilehash: 42fdc7a3f09568b641229e897a2a493994a7ba8a
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417595"
---
# <a name="message-map-macros-atl"></a>İleti eşleme makroları (ATL)

Bu makrolar ileti haritaları ve girdileri tanımlar.

|||
|-|-|
|[ALT_MSG_MAP](#alt_msg_map)|Alternatif ileti eşlemesinin başlangıcını işaretler.|
|[BEGIN_MSG_MAP](#begin_msg_map)|Varsayılan ileti eşlemesinin başlangıcını işaretler.|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Temel sınıftaki alternatif bir ileti eşlemesine zincirler.|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Sınıfının bir veri üyesinde alternatif bir ileti eşlemesine zincirler.|
|[CHAIN_MSG_MAP](#chain_msg_map)|Temel sınıftaki varsayılan ileti eşlemesine zincirler.|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Çalışma zamanında başka bir sınıftaki ileti eşlemesine zincirler.|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Sınıfının bir veri üyesinde varsayılan ileti eşlemesine zincirler.|
|[COMMAND_CODE_HANDLER](#command_code_handler)|Bildirim koduna göre WM_COMMAND bir iletiyi bir işleyici işleviyle eşler.|
|[COMMAND_HANDLER](#command_handler)|Bildirim koduna ve menü öğesi, denetim ya da Hızlandırıcı tanıtıcısına göre WM_COMMAND bir iletiyi bir işleyici işleviyle eşler.|
|[COMMAND_ID_HANDLER](#command_id_handler)|Bir WM_COMMAND iletisini, menü öğesi, denetim veya hızlandırıcı tanıtıcısına göre bir işleyici işleviyle eşler.|
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|Bildirim koduna ve bitişik denetim tanımlayıcılarına bir aralığa göre WM_COMMAND bir iletiyi bir işleyici işleviyle eşler.|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Bir WM_COMMAND iletisini, bir dizi denetim tanımlayıcılarına göre bir işleyici işleviyle eşler.|
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|Boş bir ileti eşlemesi uygular.|
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|Aksi halde işlenmemiş iletiler için varsayılan bir işleyici sağlar.|
|[END_MSG_MAP](#end_msg_map)|İleti eşlemesinin sonunu işaretler.|
|[FORWARD_NOTIFICATIONS](#forward_notifications)|Bildirim iletilerini ana pencereye iletir.|
|[MESSAGE_HANDLER](#message_handler)|Bir Windows iletisini bir işleyici işleviyle eşler.|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Bir dizi Windows iletisini bir işleyici işlevine eşler.|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Bildirim koduna göre WM_NOTIFY bir iletiyi bir işleyici işleviyle eşler.|
|[NOTIFY_HANDLER](#notify_handler)|Bildirim koduna ve denetim tanımlayıcısına göre WM_NOTIFY bir iletiyi bir işleyici işleviyle eşler.|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Denetim tanımlayıcısına göre WM_NOTIFY bir iletiyi bir işleyici işleviyle eşler.|
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|Bildirim koduna ve bitişik denetim tanımlayıcılarına bir aralığa göre WM_NOTIFY bir iletiyi bir işleyici işleviyle eşler.|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Bir WM_NOTIFY iletisini, bir dizi denetim tanımlayıcılarına göre bir işleyici işleviyle eşler.|
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|Bildirim iletilerini gönderen pencereye geri yansıtır.|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Yansıtılan bir WM_COMMAND iletisini, bildirim koduna göre bir işleyici işlevine eşler.|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Yansıtılan bir WM_COMMAND iletisini, bildirim koduna ve menü öğesi, denetim ya da Hızlandırıcı tanıtıcısına göre bir işleyici işlevine eşler.|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Yansıtılan bir WM_COMMAND iletisini, menü öğesi, denetim veya hızlandırıcı tanıtıcısına göre bir işleyici işlevine eşler.|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Yansıtılan bir WM_COMMAND iletisini, bildirim koduna ve bitişik denetim tanımlayıcılarına göre bir işleyici işlevine eşler.|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Yansıtılan bir WM_COMMAND iletisini, bir dizi denetim tanımlayıcılarına göre bir işleyici işlevine eşler.|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Yansıtılan bir WM_NOTIFY iletisini, bildirim koduna göre bir işleyici işlevine eşler.|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Yansıtılan bir WM_NOTIFY iletisini, bildirim koduna ve denetim tanımlayıcısına göre bir işleyici işlevine eşler.|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Yansıtılan bir WM_NOTIFY iletisini, denetim tanımlayıcısına göre bir işleyici işlevine eşler.|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Yansıtılan bir WM_NOTIFY iletisini, bildirim koduna ve bitişik denetim tanımlayıcılarına göre bir işleyici işlevine eşler.|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Yansıtılan bir WM_NOTIFY iletisini, bir dizi denetim tanımlayıcılarına göre bir işleyici işlevine eşler.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="alt_msg_map"></a>ALT_MSG_MAP

Alternatif ileti eşlemesinin başlangıcını işaretler.

```
ALT_MSG_MAP(msgMapID)
```

### <a name="parameters"></a>Parametreler

*msgMapID*<br/>
'ndaki İleti eşleme tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

ATL her ileti eşlemini bir sayıyla tanımlar. Varsayılan ileti eşlemesi (BEGIN_MSG_MAP makrosu ile belirtilen) 0 ile tanımlanır. Alternatif bir ileti eşlemesi *msgMapID*tarafından tanımlanır.

İleti haritaları bir pencereye gönderilen iletileri işlemek için kullanılır. Örneğin, [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) , kapsayan nesne içindeki bir ileti eşlemesinin tanımlayıcısını belirtmenize olanak tanır. [CContainedWindow:: WindowProc](ccontainedwindowt-class.md#windowproc) daha sonra içerilen pencerenin iletilerini uygun işleyici işlevine ya da başka bir ileti eşlemesine yönlendirmek için bu ileti haritasını kullanır. İşleyici işlevleri bildiren makroların bir listesi için bkz. [BEGIN_MSG_MAP](#begin_msg_map).

BEGIN_MSG_MAP bir ileti eşlemesine her zaman başlayın. Ardından, sonraki alternatif ileti eşlemelerini bildirebilirsiniz.

[End_msg_map](#end_msg_map) makro ileti eşlemesinin sonunu işaretler. BEGIN_MSG_MAP ve END_MSG_MAP her zaman tam olarak bir örneği olduğunu unutmayın.

ATL 'de ileti eşlemelerini kullanma hakkında daha fazla bilgi için bkz. [Ileti haritaları](../../atl/message-maps-atl.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, her biri bir işleyici işlevi içeren varsayılan ileti eşlemesini ve bir alternatif ileti haritasını gösterir:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

Sonraki örnekte, iki alternatif ileti haritası gösterilmektedir. Varsayılan ileti eşlemesi boş.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="begin_msg_map"></a>BEGIN_MSG_MAP

Varsayılan ileti eşlemesinin başlangıcını işaretler.

```
BEGIN_MSG_MAP(theClass)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
'ndaki İleti eşlemesini içeren sınıfın adı.

### <a name="remarks"></a>Açıklamalar

[CWindowImpl:: WindowProc](cwindowimpl-class.md#windowproc) , pencereye gönderilen iletileri işlemek için varsayılan ileti eşlemesini kullanır. İleti eşleme, iletileri uygun işleyici işlevine ya da başka bir ileti eşlemesine yönlendirir.

Aşağıdaki makrolar bir iletiyi bir işleyici işlevine eşler. Bu işlev, bir *sınıf*içinde tanımlanmalıdır.

|Makrosu|Açıklama|
|-----------|-----------------|
|[MESSAGE_HANDLER](#message_handler)|Bir Windows iletisini bir işleyici işleviyle eşler.|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Bir dizi Windows iletisini bir işleyici işlevine eşler.|
|[COMMAND_HANDLER](#command_handler)|Bildirim koduna ve menü öğesi, denetim ya da Hızlandırıcı tanıtıcısına göre WM_COMMAND bir iletiyi bir işleyici işleviyle eşler.|
|[COMMAND_ID_HANDLER](#command_id_handler)|Bir WM_COMMAND iletisini, menü öğesi, denetim veya hızlandırıcı tanıtıcısına göre bir işleyici işleviyle eşler.|
|[COMMAND_CODE_HANDLER](#command_handler)|Bildirim koduna göre WM_COMMAND bir iletiyi bir işleyici işleviyle eşler.|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Menü öğesi, denetim veya hızlandırıcı tanıtıcısına göre, ardışık bir WM_COMMAND ileti aralığını bir işleyici işlevine eşler.|
|[NOTIFY_HANDLER](#notify_handler)|Bildirim koduna ve denetim tanımlayıcısına göre WM_NOTIFY bir iletiyi bir işleyici işleviyle eşler.|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Denetim tanımlayıcısına göre WM_NOTIFY bir iletiyi bir işleyici işleviyle eşler.|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Bildirim koduna göre WM_NOTIFY bir iletiyi bir işleyici işleviyle eşler.|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Denetim tanımlayıcısına bağlı olarak, ardışık bir WM_NOTIFY ileti aralığını bir işleyici işlevine eşler.|

Aşağıdaki makrolar iletileri başka bir ileti eşlemesine yönlendirir. Bu işleme "zincirleme" adı verilir.

|Makrosu|Açıklama|
|-----------|-----------------|
|[CHAIN_MSG_MAP](#chain_msg_map)|Temel sınıftaki varsayılan ileti eşlemesine zincirler.|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Sınıfının bir veri üyesinde varsayılan ileti eşlemesine zincirler.|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Temel sınıftaki alternatif bir ileti eşlemesine zincirler.|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Sınıfının bir veri üyesinde alternatif bir ileti eşlemesine zincirler.|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Çalışma zamanında başka bir sınıftaki varsayılan ileti eşlemesine zincirler.|

Aşağıdaki makrolar, ana penceredeki "yansıtılan" iletileri doğrudan yönlendirir. Örneğin, bir denetim genellikle bildirim iletilerini işlenmek üzere üst penceresine gönderir, ancak üst pencere iletiyi denetime geri yansıtabilir.

|Makrosu|Açıklama|
|-----------|-----------------|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Yansıtılan bir WM_COMMAND iletisini, bildirim koduna ve menü öğesi, denetim ya da Hızlandırıcı tanıtıcısına göre bir işleyici işlevine eşler.|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Yansıtılan bir WM_COMMAND iletisini, menü öğesi, denetim veya hızlandırıcı tanıtıcısına göre bir işleyici işlevine eşler.|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Yansıtılan bir WM_COMMAND iletisini, bildirim koduna göre bir işleyici işlevine eşler.|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Yansıtılan bir WM_COMMAND iletisini, bir dizi denetim tanımlayıcılarına göre bir işleyici işlevine eşler.|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Yansıtılan bir WM_COMMAND iletisini, bildirim koduna ve bitişik denetim tanımlayıcılarına göre bir işleyici işlevine eşler.|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Yansıtılan bir WM_NOTIFY iletisini, bildirim koduna ve denetim tanımlayıcısına göre bir işleyici işlevine eşler.|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Yansıtılan bir WM_NOTIFY iletisini, denetim tanımlayıcısına göre bir işleyici işlevine eşler.|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Yansıtılan bir WM_NOTIFY iletisini, bildirim koduna göre bir işleyici işlevine eşler.|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Yansıtılan bir WM_NOTIFY iletisini, bir dizi denetim tanımlayıcılarına göre bir işleyici işlevine eşler.|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Yansıtılan bir WM_NOTIFY iletisini, bildirim koduna ve bitişik denetim tanımlayıcılarına göre bir işleyici işlevine eşler.|

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]

`CMyExtWindow` nesne WM_PAINT bir ileti aldığında, ileti gerçek işleme için `CMyExtWindow::OnPaint` yönlendirilir. `OnPaint` iletinin daha fazla işlem gerektirdiğini gösteriyorsa, ileti `CMyBaseWindow`varsayılan ileti eşlemesine yönlendirilir.

Varsayılan ileti eşlemesine ek olarak, [ALT_MSG_MAP](#alt_msg_map)ile alternatif bir ileti haritası tanımlayabilirsiniz. BEGIN_MSG_MAP bir ileti eşlemesine her zaman başlayın. Ardından, sonraki alternatif ileti eşlemelerini bildirebilirsiniz. Aşağıdaki örnek, her biri bir işleyici işlevi içeren varsayılan ileti eşlemesini ve bir alternatif ileti haritasını gösterir:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

Sonraki örnekte, iki alternatif ileti haritası gösterilmektedir. Varsayılan ileti eşlemesi boş.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

[End_msg_map](#end_msg_map) makro ileti eşlemesinin sonunu işaretler. BEGIN_MSG_MAP ve END_MSG_MAP her zaman tam olarak bir örneği olduğunu unutmayın.

ATL 'de ileti eşlemelerini kullanma hakkında daha fazla bilgi için bkz. [Ileti haritaları](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="chain_msg_map_alt"></a>CHAIN_MSG_MAP_ALT

İleti eşlemesindeki bir girdiyi tanımlar.

```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```

### <a name="parameters"></a>Parametreler

*theChainClass*<br/>
'ndaki İleti haritasını içeren temel sınıfın adı.

*msgMapID*<br/>
'ndaki İleti eşleme tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

CHAIN_MSG_MAP_ALT, iletileri temel sınıftaki alternatif bir ileti eşlemesine yönlendirir. Bu alternatif ileti haritasını [ALT_MSG_MAP (msgMapID)](#alt_msg_map)ile bildirmeli. İletileri bir temel sınıfın varsayılan ileti eşlemesine ( [BEGIN_MSG_MAP](#begin_msg_map)ile belirtilen) yönlendirmek için CHAIN_MSG_MAP kullanın. Bir örnek için bkz. [CHAIN_MSG_MAP](#chain_msg_map).

> [!NOTE]
>  BEGIN_MSG_MAP bir ileti eşlemesine her zaman başlayın. Daha sonra, ALT_MSG_MAP ile sonraki alternatif ileti eşlemelerini bildirebilirsiniz. [End_msg_map](#end_msg_map) makro ileti eşlemesinin sonunu işaretler. Her ileti eşlemesinin BEGIN_MSG_MAP ve END_MSG_MAP tam olarak bir örneği olmalıdır.

ATL 'de ileti eşlemelerini kullanma hakkında daha fazla bilgi için bkz. [Ileti haritaları](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="chain_msg_map_alt_member"></a>CHAIN_MSG_MAP_ALT_MEMBER

İleti eşlemesindeki bir girdiyi tanımlar.

```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```

### <a name="parameters"></a>Parametreler

*theChainMember*<br/>
'ndaki İleti haritasını içeren veri üyesinin adı.

*msgMapID*<br/>
'ndaki İleti eşleme tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

CHAIN_MSG_MAP_ALT_MEMBER, iletileri bir veri üyesinde alternatif bir ileti eşlemesine yönlendirir. Bu alternatif ileti haritasını [ALT_MSG_MAP (msgMapID)](#alt_msg_map)ile bildirmeli. İletileri bir veri üyesinin varsayılan ileti eşlemesine ( [BEGIN_MSG_MAP](#begin_msg_map)ile belirtilen) yönlendirmek için CHAIN_MSG_MAP_MEMBER kullanın. Bir örnek için bkz. [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member).

> [!NOTE]
>  BEGIN_MSG_MAP bir ileti eşlemesine her zaman başlayın. Daha sonra, ALT_MSG_MAP ile sonraki alternatif ileti eşlemelerini bildirebilirsiniz. [End_msg_map](#end_msg_map) makro ileti eşlemesinin sonunu işaretler. Her ileti eşlemesinin BEGIN_MSG_MAP ve END_MSG_MAP tam olarak bir örneği olmalıdır.

ATL 'de ileti eşlemelerini kullanma hakkında daha fazla bilgi için bkz. [Ileti haritaları](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="chain_msg_map"></a>CHAIN_MSG_MAP

İleti eşlemesindeki bir girdiyi tanımlar.

```
CHAIN_MSG_MAP(theChainClass)
```

### <a name="parameters"></a>Parametreler

*theChainClass*<br/>
'ndaki İleti haritasını içeren temel sınıfın adı.

### <a name="remarks"></a>Açıklamalar

CHAIN_MSG_MAP iletileri bir temel sınıfın varsayılan ileti eşlemesine yönlendirir ( [BEGIN_MSG_MAP](#begin_msg_map)ile bildirilmiştir). İletileri bir temel sınıfın alternatif ileti eşlemesine ( [ALT_MSG_MAP](#alt_msg_map)ile belirtilen) yönlendirmek için [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)kullanın.

> [!NOTE]
>  BEGIN_MSG_MAP bir ileti eşlemesine her zaman başlayın. Daha sonra, ALT_MSG_MAP ile sonraki alternatif ileti eşlemelerini bildirebilirsiniz. [End_msg_map](#end_msg_map) makro ileti eşlemesinin sonunu işaretler. Her ileti eşlemesinin BEGIN_MSG_MAP ve END_MSG_MAP tam olarak bir örneği olmalıdır.

ATL 'de ileti eşlemelerini kullanma hakkında daha fazla bilgi için bkz. [Ileti haritaları](../../atl/message-maps-atl.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]

Bu örnekte aşağıdakiler gösterilmektedir:

- Bir pencere yordamı `CMyClass`varsayılan ileti haritasını kullanıyorsa ve `OnPaint` bir iletiyi işlemezse ileti, işlenmek üzere `CMyBaseClass`varsayılan ileti eşlemesine yönlendirilir.

- Bir pencere yordamı `CMyClass`ilk alternatif ileti haritasını kullanıyorsa, tüm iletiler `CMyBaseClass`varsayılan ileti eşlemesine yönlendirilir.

- Bir pencere yordamı `CMyClass`ikinci alternatif ileti haritasını kullanıyorsa ve `OnChar` bir iletiyi işlemezse, ileti `CMyBaseClass`belirtilen alternatif ileti eşlemesine yönlendirilir. `CMyBaseClass`, bu ileti haritasını ALT_MSG_MAP (1) ile bildirmeli.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="chain_msg_map_dynamic"></a>CHAIN_MSG_MAP_DYNAMIC

İleti eşlemesindeki bir girdiyi tanımlar.

```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```

### <a name="parameters"></a>Parametreler

*dynaChainID*<br/>
'ndaki Bir nesnenin ileti eşlemesi için benzersiz tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

CHAIN_MSG_MAP_DYNAMIC, çalışma zamanında iletileri başka bir nesnede varsayılan ileti eşlemesine yönlendirir. Nesnesi ve ileti eşlemesi, [Cdynamiczincirde:: SetChainEntry](cdynamicchain-class.md#setchainentry)aracılığıyla tanımladığınız *dynaChainID*ile ilişkilendirilir. CHAIN_MSG_MAP_DYNAMIC kullanabilmeniz için sınıfınızı `CDynamicChain` türetmeniz gerekir. Bir örnek için, [Cdynamiczincirine](../../atl/reference/cdynamicchain-class.md) genel bakış bölümüne bakın.

> [!NOTE]
>  [BEGIN_MSG_MAP](#begin_msg_map)bir ileti eşlemesine her zaman başlayın. Daha sonra, ALT_MSG_MAP ile sonraki alternatif ileti eşlemelerini bildirebilirsiniz. [End_msg_map](#end_msg_map) makro ileti eşlemesinin sonunu işaretler. Her ileti eşlemesinin BEGIN_MSG_MAP ve END_MSG_MAP tam olarak bir örneği olmalıdır.

ATL 'de ileti eşlemelerini kullanma hakkında daha fazla bilgi için bkz. [Ileti haritaları](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="chain_msg_map_member"></a>CHAIN_MSG_MAP_MEMBER

İleti eşlemesindeki bir girdiyi tanımlar.

```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```

### <a name="parameters"></a>Parametreler

*theChainMember*<br/>
'ndaki İleti haritasını içeren veri üyesinin adı.

### <a name="remarks"></a>Açıklamalar

CHAIN_MSG_MAP_MEMBER, iletileri bir veri üyesinin varsayılan ileti eşlemesine yönlendirir ( [BEGIN_MSG_MAP](#begin_msg_map)ile bildirilmiştir). İletileri bir veri üyesinin alternatif ileti eşlemesine ( [ALT_MSG_MAP](#alt_msg_map)ile belirtilen) yönlendirmek için [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)kullanın.

> [!NOTE]
>  BEGIN_MSG_MAP bir ileti eşlemesine her zaman başlayın. Daha sonra, ALT_MSG_MAP ile sonraki alternatif ileti eşlemelerini bildirebilirsiniz. [End_msg_map](#end_msg_map) makro ileti eşlemesinin sonunu işaretler. Her ileti eşlemesinin BEGIN_MSG_MAP ve END_MSG_MAP tam olarak bir örneği olmalıdır.

ATL 'de ileti eşlemelerini kullanma hakkında daha fazla bilgi için bkz. [Ileti haritaları](../../atl/message-maps-atl.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]

Bu örnekte aşağıdakiler gösterilmektedir:

- Bir pencere yordamı `CMyClass`varsayılan ileti haritasını kullanıyorsa ve `OnPaint` bir iletiyi işlemezse ileti, işlenmek üzere `m_obj`varsayılan ileti eşlemesine yönlendirilir.

- Bir pencere yordamı `CMyClass`ilk alternatif ileti haritasını kullanıyorsa, tüm iletiler `m_obj`varsayılan ileti eşlemesine yönlendirilir.

- Bir pencere yordamı `CMyClass`ikinci alternatif ileti haritasını kullanıyorsa ve `OnChar` bir iletiyi işlemezse, ileti `m_obj`belirtilen alternatif ileti eşlemesine yönlendirilir. `CMyContainedClass` sınıfı bu ileti haritasını ALT_MSG_MAP (1) ile bildirmeli.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="command_code_handler"></a>COMMAND_CODE_HANDLER

[COMMAND_HANDLER](#command_handler)benzer, ancak yalnızca bildirim koduna dayalı bir [WM_COMMAND](/windows/win32/menurc/wm-command) iletisi eşler.

```
COMMAND_CODE_HANDLER(code, func)
```

### <a name="parameters"></a>Parametreler

*kodudur*<br/>
'ndaki Bildirim kodu.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="command_handler"></a>COMMAND_HANDLER

İleti eşlemesindeki bir girdiyi tanımlar.

```
COMMAND_HANDLER(id, code, func)
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki Menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*kodudur*<br/>
'ndaki Bildirim kodu.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="remarks"></a>Açıklamalar

COMMAND_HANDLER, bildirim koduna ve denetim tanımlayıcısına göre [WM_COMMAND](/windows/win32/menurc/wm-command) bir iletiyi belirtilen işleyici işlevine eşler. Örneğin:

[!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]

COMMAND_HANDLER makroda belirtilen herhangi bir işlev aşağıdaki şekilde tanımlanmalıdır:

`LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`

İleti eşlemesi, `CommandHandler` çağrılmadan önce TRUE olarak ayarlanır `bHandled`. `CommandHandler` iletiyi tam olarak işlemez, iletinin daha fazla işleme ihtiyacı olduğunu göstermek için `bHandled` FALSE olarak ayarlanmalıdır.

> [!NOTE]
>  [BEGIN_MSG_MAP](#begin_msg_map)bir ileti eşlemesine her zaman başlayın. Daha sonra, [ALT_MSG_MAP](#alt_msg_map)ile sonraki alternatif ileti eşlemelerini bildirebilirsiniz. [End_msg_map](#end_msg_map) makro ileti eşlemesinin sonunu işaretler. Her ileti eşlemesinin BEGIN_MSG_MAP ve END_MSG_MAP tam olarak bir örneği olmalıdır.

COMMAND_HANDLER ek olarak, bir tanımlayıcı veya kodla ilgili olarak WM_COMMAND iletisi eşlemek için [message_handler](#message_handler) kullanabilirsiniz. Bu durumda `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)`, tüm WM_COMMAND iletilerinin `OnHandlerFunction`'e yönlendiracaktır.

ATL 'de ileti eşlemelerini kullanma hakkında daha fazla bilgi için bkz. [Ileti haritaları](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="command_id_handler"></a>COMMAND_ID_HANDLER

[COMMAND_HANDLER](#command_handler)benzer, ancak yalnızca menü öğesi, denetim veya hızlandırıcı tanıtıcısına dayalı bir [WM_COMMAND](/windows/win32/menurc/wm-command) iletisi eşler.

```
COMMAND_ID_HANDLER(id, func)
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki İletiyi gönderen menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="command_range_code_handler"></a>COMMAND_RANGE_CODE_HANDLER

[COMMAND_RANGE_HANDLER](#command_range_handler)benzer, ancak belirli bir bildirim koduna sahip [WM_COMMAND](/windows/win32/menurc/wm-command) iletileri bir denetim aralığından tek bir işleyici işlevine eşler.

```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```

### <a name="parameters"></a>Parametreler

*Önce ıdden*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının başlangıcını işaretler.

*ıdlast*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının sonunu işaretler.

*kodudur*<br/>
'ndaki Bildirim kodu.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Bu Aralık, ileti gönderen menü öğesi, denetim veya hızlandırıcı tanımlayıcısını temel alır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="command_range_handler"></a>COMMAND_RANGE_HANDLER

[COMMAND_HANDLER](#command_handler)benzer, ancak bir denetim aralığından [WM_COMMAND](/windows/win32/menurc/wm-command) iletileri tek bir işleyici işlevine eşler.

```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```

### <a name="parameters"></a>Parametreler

*Önce ıdden*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının başlangıcını işaretler.

*ıdlast*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının sonunu işaretler.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Bu Aralık, ileti gönderen menü öğesi, denetim veya hızlandırıcı tanımlayıcısını temel alır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="declare_empty_msg_map"></a>DECLARE_EMPTY_MSG_MAP

Boş bir ileti eşlemesi bildirir.

```
DECLARE_EMPTY_MSG_MAP()
```

### <a name="remarks"></a>Açıklamalar

DECLARE_EMPTY_MSG_MAP, makroları [BEGIN_MSG_MAP](#begin_msg_map) ve boş bir ileti eşlemesi oluşturmak için [end_msg_map](#end_msg_map) makrolar çağıran kolay bir makrodur:

[!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]

##  <a name="default_reflection_handler"></a>DEFAULT_REFLECTION_HANDLER

, Yansıtılan iletileri alacak alt pencere (denetim) için varsayılan bir işleyici sağlar; işleyici, işlenmemiş iletileri `DefWindowProc`'e doğru şekilde geçilecektir.

```
DEFAULT_REFLECTION_HANDLER()
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="end_msg_map"></a>END_MSG_MAP

İleti eşlemesinin sonunu işaretler.

```
END_MSG_MAP()
```

### <a name="remarks"></a>Açıklamalar

İleti eşlemesinin başlangıcını işaretlemek için [BEGIN_MSG_MAP](#begin_msg_map) makrosunu her zaman kullanın. Sonraki alternatif ileti eşlemelerini bildirmek için [ALT_MSG_MAP](#alt_msg_map) kullanın.

BEGIN_MSG_MAP ve END_MSG_MAP her zaman tam olarak bir örneği olduğunu unutmayın.

ATL 'de ileti eşlemelerini kullanma hakkında daha fazla bilgi için bkz. [Ileti haritaları](../../atl/message-maps-atl.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, her biri bir işleyici işlevi içeren varsayılan ileti eşlemesini ve bir alternatif ileti haritasını gösterir:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

Sonraki örnekte, iki alternatif ileti haritası gösterilmektedir. Varsayılan ileti eşlemesi boş.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="forward_notifications"></a>FORWARD_NOTIFICATIONS

Bildirim iletilerini ana pencereye iletir.

```
FORWARD_NOTIFICATIONS()
```

### <a name="remarks"></a>Açıklamalar

İleti Haritalarınızın bir parçası olarak bu makroyu belirtin.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="message_handler"></a>MESSAGE_HANDLER

İleti eşlemesindeki bir girdiyi tanımlar.

```
MESSAGE_HANDLER( msg, func )
```

### <a name="parameters"></a>Parametreler

*MS*<br/>
'ndaki Windows iletisi.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="remarks"></a>Açıklamalar

MESSAGE_HANDLER, bir Windows iletisini belirtilen işleyici işlevine eşler.

MESSAGE_HANDLER makroda belirtilen herhangi bir işlev aşağıdaki şekilde tanımlanmalıdır:

`LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`

İleti eşlemesi, `MessageHandler` çağrılmadan önce TRUE olarak ayarlanır `bHandled`. `MessageHandler` iletiyi tam olarak işlemez, iletinin daha fazla işleme ihtiyacı olduğunu göstermek için `bHandled` FALSE olarak ayarlanmalıdır.

> [!NOTE]
>  [BEGIN_MSG_MAP](#begin_msg_map)bir ileti eşlemesine her zaman başlayın. Daha sonra, [ALT_MSG_MAP](#alt_msg_map)ile sonraki alternatif ileti eşlemelerini bildirebilirsiniz. [End_msg_map](#end_msg_map) makro ileti eşlemesinin sonunu işaretler. Her ileti eşlemesinin BEGIN_MSG_MAP ve END_MSG_MAP tam olarak bir örneği olmalıdır.

MESSAGE_HANDLER ek olarak, sırasıyla [WM_COMMAND](/windows/win32/menurc/wm-command) ve [WM_NOTIFY](/windows/win32/controls/wm-notify) iletilerini eşlemek için [COMMAND_HANDLER](#command_handler) ve [NOTIFY_HANDLER](#notify_handler) kullanabilirsiniz.

ATL 'de ileti eşlemelerini kullanma hakkında daha fazla bilgi için bkz. [Ileti haritaları](../../atl/message-maps-atl.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="message_range_handler"></a>MESSAGE_RANGE_HANDLER

[Message_handler](#message_handler)benzer, ancak bir dizi Windows iletisini tek bir işleyici işlevine eşler.

```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```

### <a name="parameters"></a>Parametreler

*önce msg*<br/>
'ndaki Bitişik bir ileti aralığının başlangıcını işaretler.

*msgLast*<br/>
'ndaki Bitişik bir ileti aralığının sonunu işaretler.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="notify_code_handler"></a>NOTIFY_CODE_HANDLER

[NOTIFY_HANDLER](#notify_handler)benzer, ancak yalnızca bildirim koduna dayalı bir [WM_NOTIFY](/windows/win32/controls/wm-notify) iletisi eşler.

```
NOTIFY_CODE_HANDLER(cd, func)
```

### <a name="parameters"></a>Parametreler

*CD*<br/>
'ndaki Bildirim kodu.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="notify_handler"></a>NOTIFY_HANDLER

İleti eşlemesindeki bir girdiyi tanımlar.

```
NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki İletiyi gönderen denetimin tanımlayıcısı.

*CD*<br/>
'ndaki Bildirim kodu.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="remarks"></a>Açıklamalar

NOTIFY_HANDLER, bildirim koduna ve denetim tanımlayıcısına göre [WM_NOTIFY](/windows/win32/controls/wm-notify) bir iletiyi belirtilen işleyici işlevine eşler.

NOTIFY_HANDLER makroda belirtilen herhangi bir işlev aşağıdaki şekilde tanımlanmalıdır:

`LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`

İleti eşlemesi, `NotifyHandler` çağrılmadan önce TRUE olarak ayarlanır `bHandled`. `NotifyHandler` iletiyi tam olarak işlemez, iletinin daha fazla işleme ihtiyacı olduğunu göstermek için `bHandled` FALSE olarak ayarlanmalıdır.

> [!NOTE]
>  [BEGIN_MSG_MAP](#begin_msg_map)bir ileti eşlemesine her zaman başlayın. Daha sonra, [ALT_MSG_MAP](#alt_msg_map)ile sonraki alternatif ileti eşlemelerini bildirebilirsiniz. [End_msg_map](#end_msg_map) makro ileti eşlemesinin sonunu işaretler. Her ileti eşlemesinin BEGIN_MSG_MAP ve END_MSG_MAP tam olarak bir örneği olmalıdır.

NOTIFY_HANDLER ek olarak, bir tanımlayıcı veya kodla ilgili olarak WM_NOTIFY iletisi eşlemek için [message_handler](#message_handler) kullanabilirsiniz. Bu durumda `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)`, tüm WM_NOTIFY iletilerinin `OnHandlerFunction`'e yönlendiracaktır.

ATL 'de ileti eşlemelerini kullanma hakkında daha fazla bilgi için bkz. [Ileti haritaları](../../atl/message-maps-atl.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="notify_id_handler"></a>NOTIFY_ID_HANDLER

[NOTIFY_HANDLER](#notify_handler)benzer, ancak bir [WM_NOTIFY](/windows/win32/controls/wm-notify) iletisini yalnızca denetim tanımlayıcısına göre eşler.

```
NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki İletiyi gönderen denetimin tanımlayıcısı.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="notify_range_code_handler"></a>NOTIFY_RANGE_CODE_HANDLER

[NOTIFY_RANGE_HANDLER](#notify_range_handler)benzer, ancak belirli bir bildirim koduna sahip [WM_NOTIFY](/windows/win32/controls/wm-notify) iletileri bir denetim aralığından tek bir işleyici işlevine eşler.

```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>Parametreler

*Önce ıdden*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının başlangıcını işaretler.

*ıdlast*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının sonunu işaretler.

*CD*<br/>
'ndaki Bildirim kodu.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Bu Aralık, iletiyi gönderen denetimin tanımlayıcısını temel alır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="notify_range_handler"></a>NOTIFY_RANGE_HANDLER

[NOTIFY_HANDLER](#notify_handler)benzer, ancak bir denetim aralığından [WM_NOTIFY](/windows/win32/controls/wm-notify) iletileri tek bir işleyici işlevine eşler.

```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Parametreler

*Önce ıdden*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının başlangıcını işaretler.

*ıdlast*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının sonunu işaretler.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="remarks"></a>Açıklamalar

Bu Aralık, iletiyi gönderen denetimin tanımlayıcısını temel alır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="reflect_notifications"></a>REFLECT_NOTIFICATIONS

Bildirim iletilerini gönderilen alt pencereye (denetim) geri yansıtır.

```
REFLECT_NOTIFICATIONS()
```

### <a name="remarks"></a>Açıklamalar

Bu makroyu, ana pencerenin ileti eşlemesinin bir parçası olarak belirtin.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="reflected_command_code_handler"></a>REFLECTED_COMMAND_CODE_HANDLER

[COMMAND_CODE_HANDLER](#command_code_handler)benzer, ancak üst pencereden yansıtılan komutları eşleştirir.

```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```

### <a name="parameters"></a>Parametreler

*kodudur*<br/>
'ndaki Bildirim kodu.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="reflected_command_handler"></a>REFLECTED_COMMAND_HANDLER

[COMMAND_HANDLER](#command_handler)benzer, ancak üst pencereden yansıtılan komutları eşleştirir.

```
REFLECTED_COMMAND_HANDLER( id, code, func )
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki Menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*kodudur*<br/>
'ndaki Bildirim kodu.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="reflected_command_id_handler"></a>REFLECTED_COMMAND_ID_HANDLER

[COMMAND_ID_HANDLER](#command_id_handler)benzer, ancak üst pencereden yansıtılan komutları eşleştirir.

```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki Menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="reflected_command_range_code_handler"></a>REFLECTED_COMMAND_RANGE_CODE_HANDLER

[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)benzer, ancak üst pencereden yansıtılan komutları eşleştirir.

```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```

### <a name="parameters"></a>Parametreler

*Önce ıdden*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının başlangıcını işaretler.

*ıdlast*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının sonunu işaretler.

*kodudur*<br/>
'ndaki Bildirim kodu.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="reflected_command_range_handler"></a>REFLECTED_COMMAND_RANGE_HANDLER

[COMMAND_RANGE_HANDLER](#command_range_handler)benzer, ancak üst pencereden yansıtılan komutları eşleştirir.

```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Parametreler

*Önce ıdden*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının başlangıcını işaretler.

*ıdlast*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının sonunu işaretler.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="reflected_notify_code_handler"></a>REFLECTED_NOTIFY_CODE_HANDLER

[NOTIFY_CODE_HANDLER](#notify_code_handler)benzer, ancak üst pencereden yansıtılan bildirimleri eşler.

```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```

### <a name="parameters"></a>Parametreler

*CD*<br/>
'ndaki Bildirim kodu.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="reflected_notify_handler"></a>REFLECTED_NOTIFY_HANDLER

[NOTIFY_HANDLER](#notify_handler)benzer, ancak üst pencereden yansıtılan bildirimleri eşler.

```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki Menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*CD*<br/>
'ndaki Bildirim kodu.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="reflected_notify_id_handler"></a>REFLECTED_NOTIFY_ID_HANDLER

[NOTIFY_ID_HANDLER](#notify_id_handler)benzer, ancak üst pencereden yansıtılan bildirimleri eşler.

```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki Menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="reflected_notify_range_code_handler"></a>REFLECTED_NOTIFY_RANGE_CODE_HANDLER

[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)benzer, ancak üst pencereden yansıtılan bildirimleri eşler.

```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>Parametreler

*Önce ıdden*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının başlangıcını işaretler.

*ıdlast*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının sonunu işaretler.

*CD*<br/>
'ndaki Bildirim kodu.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="reflected_notify_range_handler"></a>REFLECTED_NOTIFY_RANGE_HANDLER

[NOTIFY_RANGE_HANDLER](#notify_range_handler)benzer, ancak üst pencereden yansıtılan bildirimleri eşler.

```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Parametreler

*Önce ıdden*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının başlangıcını işaretler.

*ıdlast*<br/>
'ndaki Bitişik denetim tanımlayıcılarının aralığının sonunu işaretler.

*func*<br/>
'ndaki İleti işleyici işlevinin adı.

## <a name="see-also"></a>Ayrıca bkz.

[Larının](../../atl/reference/atl-macros.md)
