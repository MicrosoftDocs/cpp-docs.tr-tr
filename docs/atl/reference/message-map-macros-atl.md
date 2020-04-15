---
title: İleti Eşleme Makroları (ATL)
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
ms.openlocfilehash: 157812fa6625869c86dd8a27156a2970a3dc8d4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326223"
---
# <a name="message-map-macros-atl"></a>İleti Eşleme Makroları (ATL)

Bu makrolar ileti eşlemlerini ve girişleri tanımlar.

|||
|-|-|
|[ALT_MSG_MAP](#alt_msg_map)|Alternatif bir ileti haritasının başlangıcını işaretler.|
|[Begın_msg_map](#begin_msg_map)|Varsayılan ileti haritasının başlangıcını işaretler.|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Taban sınıfta alternatif bir ileti haritasına zincirler.|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Sınıfın bir veri üyesinde alternatif bir ileti haritasına zincirler.|
|[CHAIN_MSG_MAP](#chain_msg_map)|Taban sınıftavarsayılan ileti eşlemi için zincirler.|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Çalışma zamanında başka bir sınıftaki ileti haritasına zincirler.|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Sınıfın bir veri üyesinde varsayılan ileti haritasına zincirler.|
|[COMMAND_CODE_HANDLER](#command_code_handler)|Bildirim kodunu temel alan bir işleyici işlevine WM_COMMAND ileti eşler.|
|[COMMAND_HANDLER](#command_handler)|Bildirim kodunu ve menü öğesinin, denetiminin veya hızlandırıcının tanımlayıcısını temel alan bir işleyici işlevine WM_COMMAND ileti eşler.|
|[COMMAND_ID_HANDLER](#command_id_handler)|WM_COMMAND iletisini, menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısını temel alan bir işleyici işleviyle eşler.|
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|Bildirim kodunu ve bitişik denetim tanımlayıcıları aralığını temel alan bir işleyici işlevine WM_COMMAND ileti eşler.|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|WM_COMMAND iletisini bitişik denetim tanımlayıcılarını temel alan bir işleyici işleviyle eşler.|
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|Boş bir ileti eşlemi uygular.|
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|Aksi şekilde işlenmeyen yansıtılmış iletiler için varsayılan işleyicisağlar.|
|[END_MSG_MAP](#end_msg_map)|İleti haritasının sonunu işaretler.|
|[FORWARD_NOTIFICATIONS](#forward_notifications)|Bildirim iletilerini üst pencereye iletin.|
|[MESSAGE_HANDLER](#message_handler)|Windows iletisini işleyici işleviyle eşler.|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Bitişik bir Windows ileti aralığını işleyici işleviyle eşler.|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Bildirim kodunu temel alan bir işleyici işlevine WM_NOTIFY ileti eşler.|
|[NOTIFY_HANDLER](#notify_handler)|Bildirim kodunu ve denetim tanımlayıcısını temel alan bir işleyici işlevine WM_NOTIFY ileti eşler.|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|WM_NOTIFY iletisini denetim tanımlayıcısını temel alan işleyici işleviyle eşler.|
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|Bildirim kodunu ve bitişik denetim tanımlayıcıları aralığını temel alan bir işleyici işlevine WM_NOTIFY ileti eşler.|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|WM_NOTIFY iletisini bitişik denetim tanımlayıcılarını temel alan bir işleyici işleviyle eşler.|
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|Bildirim iletilerini gönderen pencereye geri yansıtır.|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Yansıyan WM_COMMAND iletiyi bildirim kodunu temel alan işleyici işleviyle eşler.|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Yansıyan WM_COMMAND iletiyi, bildirim kodunu ve menü öğesinin, denetimiveya hızlandırıcısının tanımlayıcısını temel alan bir işleyici işlevine eşler.|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Yansıtılan WM_COMMAND iletiyi, menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısını temel alan işleyici işleviyle eşler.|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Yansıyan WM_COMMAND iletiyi, bildirim koduna ve bitişik denetim tanımlayıcılarını temel alan bir işleyici işlevine eşler.|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Yansıtılmış bir WM_COMMAND iletiyi bitişik denetim tanımlayıcıları aralığına göre işleyici işleviyle eşler.|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Yansıyan WM_NOTIFY iletiyi bildirim kodunu temel alan işleyici işleviyle eşler.|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Yansıyan WM_NOTIFY iletiyi bildirim koduna ve denetim tanımlayıcısına göre işleyici işleviyle eşler.|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Yansıtılmış WM_NOTIFY iletisini denetim tanımlayıcısını temel alan işleyici işleviyle eşler.|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Yansıyan WM_NOTIFY iletiyi bildirim koduna ve bitişik denetim tanımlayıcılarını temel alan bir işleyici işlevine eşler.|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Yansıtılan WM_NOTIFY iletiyi bitişik denetim tanımlayıcıları aralığına göre işleyici işleviyle eşler.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="alt_msg_map"></a><a name="alt_msg_map"></a>ALT_MSG_MAP

Alternatif bir ileti haritasının başlangıcını işaretler.

```
ALT_MSG_MAP(msgMapID)
```

### <a name="parameters"></a>Parametreler

*msgMapID*<br/>
[içinde] İleti eşlemi tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

ATL her ileti haritasını bir sayıyla tanımlar. Varsayılan ileti haritası (BEGIN_MSG_MAP makrosuyla birlikte bildirilir) 0 ile tanımlanır. Alternatif bir ileti haritası *msgMapID*tarafından tanımlanır.

İleti eşlemleri, pencereye gönderilen iletileri işlemek için kullanılır. Örneğin, [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) içeren nesnede bir ileti eşlemi tanımlayıcısını belirtmenize olanak tanır. [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc) daha sonra bu ileti eşlemi kullanır ve içerdiği pencerenin iletilerini uygun işleyici işlevine veya başka bir ileti eşlemesi için yönlendirir. İşleyici işlevlerini bildiren makroların listesi [için bkz. BEGIN_MSG_MAP.](#begin_msg_map)

Her zaman BEGIN_MSG_MAP ile bir ileti haritası başlatın. Daha sonra sonraki alternatif ileti eşlemlerini bildirebilirsiniz.

[END_MSG_MAP](#end_msg_map) makrosu ileti haritasının sonunu işaretler. Her zaman tam olarak bir BEGIN_MSG_MAP ve END_MSG_MAP örneği olduğunu unutmayın.

ATL'de ileti eşlemlerini kullanma hakkında daha fazla bilgi için [İleti Haritaları'na](../../atl/message-maps-atl.md)bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnekte varsayılan ileti eşlemi ve her biri bir işleyici işlevi içeren bir alternatif ileti eşlemi gösterilmektedir:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

Sonraki örnekte iki alternatif ileti eşlemi gösterilmektedir. Varsayılan ileti eşlemi boş.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="begin_msg_map"></a><a name="begin_msg_map"></a>Begın_msg_map

Varsayılan ileti haritasının başlangıcını işaretler.

```
BEGIN_MSG_MAP(theClass)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
[içinde] İleti eşlemini içeren sınıfın adı.

### <a name="remarks"></a>Açıklamalar

[CWindowImpl::WindowProc,](cwindowimpl-class.md#windowproc) pencereye gönderilen iletileri işlemek için varsayılan ileti eşlesini kullanır. İleti eşlemi, iletileri uygun işleyici işlevine veya başka bir ileti eşlemine yönlendirir.

Aşağıdaki makrolar bir işleyici işlevi için bir ileti eşler. Bu işlev *Class'ta*tanımlanmalıdır.

|Makro|Açıklama|
|-----------|-----------------|
|[MESSAGE_HANDLER](#message_handler)|Windows iletisini işleyici işleviyle eşler.|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Bitişik bir Windows ileti aralığını işleyici işleviyle eşler.|
|[COMMAND_HANDLER](#command_handler)|Bildirim kodunu ve menü öğesinin, denetiminin veya hızlandırıcının tanımlayıcısını temel alan bir işleyici işlevine WM_COMMAND ileti eşler.|
|[COMMAND_ID_HANDLER](#command_id_handler)|WM_COMMAND iletisini, menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısını temel alan bir işleyici işleviyle eşler.|
|[COMMAND_CODE_HANDLER](#command_handler)|Bildirim kodunu temel alan bir işleyici işlevine WM_COMMAND ileti eşler.|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısını temel alan bitişik bir WM_COMMAND ileti aralığını işleyici işleviyle eşler.|
|[NOTIFY_HANDLER](#notify_handler)|Bildirim kodunu ve denetim tanımlayıcısını temel alan bir işleyici işlevine WM_NOTIFY ileti eşler.|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|WM_NOTIFY iletisini denetim tanımlayıcısını temel alan işleyici işleviyle eşler.|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Bildirim kodunu temel alan bir işleyici işlevine WM_NOTIFY ileti eşler.|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Denetim tanımlayıcısını temel alan bitişik bir WM_NOTIFY ileti aralığını işleyici işleviyle eşler.|

Aşağıdaki makrolar iletileri başka bir ileti haritasına yönlendirir. Bu işleme "zincirleme" adı verilir.

|Makro|Açıklama|
|-----------|-----------------|
|[CHAIN_MSG_MAP](#chain_msg_map)|Taban sınıftavarsayılan ileti eşlemi için zincirler.|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Sınıfın bir veri üyesinde varsayılan ileti haritasına zincirler.|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Taban sınıfta alternatif bir ileti haritasına zincirler.|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Sınıfın bir veri üyesinde alternatif bir ileti haritasına zincirler.|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Çalışma zamanında başka bir sınıftaki varsayılan ileti haritasına zincirler.|

Aşağıdaki makrolar üst pencereden "yansıyan" iletileri yönlendirir. Örneğin, denetim normalde işlem için üst penceresine bildirim iletileri gönderir, ancak üst pencere iletiyi denetime geri yansıtabilir.

|Makro|Açıklama|
|-----------|-----------------|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Yansıyan WM_COMMAND iletiyi, bildirim kodunu ve menü öğesinin, denetimiveya hızlandırıcısının tanımlayıcısını temel alan bir işleyici işlevine eşler.|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Yansıtılan WM_COMMAND iletiyi, menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısını temel alan işleyici işleviyle eşler.|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Yansıyan WM_COMMAND iletiyi bildirim kodunu temel alan işleyici işleviyle eşler.|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Yansıtılmış bir WM_COMMAND iletiyi bitişik denetim tanımlayıcıları aralığına göre işleyici işleviyle eşler.|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Yansıyan WM_COMMAND iletiyi, bildirim koduna ve bitişik denetim tanımlayıcılarını temel alan bir işleyici işlevine eşler.|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Yansıyan WM_NOTIFY iletiyi bildirim koduna ve denetim tanımlayıcısına göre işleyici işleviyle eşler.|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Yansıtılmış WM_NOTIFY iletisini denetim tanımlayıcısını temel alan işleyici işleviyle eşler.|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Yansıyan WM_NOTIFY iletiyi bildirim kodunu temel alan işleyici işleviyle eşler.|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Yansıtılan WM_NOTIFY iletiyi bitişik denetim tanımlayıcıları aralığına göre işleyici işleviyle eşler.|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Yansıyan WM_NOTIFY iletiyi bildirim koduna ve bitişik denetim tanımlayıcılarını temel alan bir işleyici işlevine eşler.|

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]

Bir `CMyExtWindow` nesne WM_PAINT iletisi aldığında, ileti `CMyExtWindow::OnPaint` gerçek işleme için yönlendirilir. İletinin daha fazla işlenmesi gerektiğini `OnPaint` gösterirse, ileti daha sonra `CMyBaseWindow`'daki varsayılan ileti haritasına yönlendirilir.

Varsayılan ileti eşlemine ek olarak, [ALT_MSG_MAP](#alt_msg_map)ile alternatif bir ileti eşlemi tanımlayabilirsiniz. Her zaman BEGIN_MSG_MAP ile bir ileti haritası başlatın. Daha sonra sonraki alternatif ileti eşlemlerini bildirebilirsiniz. Aşağıdaki örnekte varsayılan ileti eşlemi ve her biri bir işleyici işlevi içeren bir alternatif ileti eşlemi gösterilmektedir:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

Sonraki örnekte iki alternatif ileti eşlemi gösterilmektedir. Varsayılan ileti eşlemi boş.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

[END_MSG_MAP](#end_msg_map) makrosu ileti haritasının sonunu işaretler. Her zaman tam olarak bir BEGIN_MSG_MAP ve END_MSG_MAP örneği olduğunu unutmayın.

ATL'de ileti eşlemlerini kullanma hakkında daha fazla bilgi için [İleti Haritaları'na](../../atl/message-maps-atl.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="chain_msg_map_alt"></a><a name="chain_msg_map_alt"></a>CHAIN_MSG_MAP_ALT

İleti haritasındaki bir girişi tanımlar.

```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```

### <a name="parameters"></a>Parametreler

*theChainClass*<br/>
[içinde] İleti eşlemini içeren taban sınıfın adı.

*msgMapID*<br/>
[içinde] İleti eşlemi tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

CHAIN_MSG_MAP_ALT, iletileri taban sınıftaalternatif bir ileti haritasına yönlendirir. Bu alternatif ileti haritasını [ALT_MSG_MAP (msgMapID)](#alt_msg_map)ile beyan etmiş olmalısınız. İletileri taban sınıfın varsayılan ileti haritasına [(BEGIN_MSG_MAP](#begin_msg_map)ile birlikte bildirilen) yönlendirmek için CHAIN_MSG_MAP kullanın. Örneğin, [bkz. CHAIN_MSG_MAP.](#chain_msg_map)

> [!NOTE]
> Her zaman BEGIN_MSG_MAP ile bir ileti haritası başlatın. Daha sonra sonraki alternatif ileti eşlemlerini ALT_MSG_MAP ile bildirebilirsiniz. [END_MSG_MAP](#end_msg_map) makrosu ileti haritasının sonunu işaretler. Her ileti haritasında tam olarak bir BEGIN_MSG_MAP ve END_MSG_MAP bir örneği olmalıdır.

ATL'de ileti eşlemlerini kullanma hakkında daha fazla bilgi için [İleti Haritaları'na](../../atl/message-maps-atl.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="chain_msg_map_alt_member"></a><a name="chain_msg_map_alt_member"></a>CHAIN_MSG_MAP_ALT_MEMBER

İleti haritasındaki bir girişi tanımlar.

```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```

### <a name="parameters"></a>Parametreler

*theChainMember*<br/>
[içinde] İleti eşlemini içeren veri üyesinin adı.

*msgMapID*<br/>
[içinde] İleti eşlemi tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

CHAIN_MSG_MAP_ALT_MEMBER, iletileri bir veri üyesinde alternatif bir ileti haritasına yönlendirir. Bu alternatif ileti haritasını [ALT_MSG_MAP (msgMapID)](#alt_msg_map)ile beyan etmiş olmalısınız. İletileri bir veri üyesinin varsayılan ileti haritasına [(BEGIN_MSG_MAP](#begin_msg_map)ile birlikte bildirilen) yönlendirmek için CHAIN_MSG_MAP_MEMBER kullanın. Örneğin, [bkz. CHAIN_MSG_MAP_MEMBER.](#chain_msg_map_member)

> [!NOTE]
> Her zaman BEGIN_MSG_MAP ile bir ileti haritası başlatın. Daha sonra sonraki alternatif ileti eşlemlerini ALT_MSG_MAP ile bildirebilirsiniz. [END_MSG_MAP](#end_msg_map) makrosu ileti haritasının sonunu işaretler. Her ileti haritasında tam olarak bir BEGIN_MSG_MAP ve END_MSG_MAP bir örneği olmalıdır.

ATL'de ileti eşlemlerini kullanma hakkında daha fazla bilgi için [İleti Haritaları'na](../../atl/message-maps-atl.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="chain_msg_map"></a><a name="chain_msg_map"></a>CHAIN_MSG_MAP

İleti haritasındaki bir girişi tanımlar.

```
CHAIN_MSG_MAP(theChainClass)
```

### <a name="parameters"></a>Parametreler

*theChainClass*<br/>
[içinde] İleti eşlemini içeren taban sınıfın adı.

### <a name="remarks"></a>Açıklamalar

CHAIN_MSG_MAP iletileri taban sınıfın varsayılan ileti haritasına yönlendirir [(BEGIN_MSG_MAP](#begin_msg_map)ile birlikte bildirilir). İletileri taban sınıfın alternatif ileti haritasına [(ALT_MSG_MAP](#alt_msg_map)ile birlikte bildirilen) yönlendirmek için [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)kullanın.

> [!NOTE]
> Her zaman BEGIN_MSG_MAP ile bir ileti haritası başlatın. Daha sonra sonraki alternatif ileti eşlemlerini ALT_MSG_MAP ile bildirebilirsiniz. [END_MSG_MAP](#end_msg_map) makrosu ileti haritasının sonunu işaretler. Her ileti haritasında tam olarak bir BEGIN_MSG_MAP ve END_MSG_MAP bir örneği olmalıdır.

ATL'de ileti eşlemlerini kullanma hakkında daha fazla bilgi için [İleti Haritaları'na](../../atl/message-maps-atl.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]

Bu örnekaşağıdakileri göstermektedir:

- Bir pencere yordamı `CMyClass`'varsayılan ileti `OnPaint` eşlemi kullanıyorsa ve bir `CMyBaseClass`iletiyi işlemiyorsa, ileti işleme için varsayılan ileti haritasına yönlendirilir.

- Bir pencere yordamı ilk alternatif ileti `CMyClass`eşlemi kullanıyorsa, tüm iletiler 'varsayılan ileti eşlenine `CMyBaseClass`yönlendirilir.

- Bir pencere yordamı `CMyClass`'ikinci alternatif ileti `OnChar` eşlemi kullanıyorsa ve bir iletiyi işlemiyorsa, ileti ' deki `CMyBaseClass`belirtilen alternatif ileti eşlemesi için yönlendirilir. `CMyBaseClass`bu mesaj haritasını ALT_MSG_MAP(1) ile bildirmiş olmalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="chain_msg_map_dynamic"></a><a name="chain_msg_map_dynamic"></a>CHAIN_MSG_MAP_DYNAMIC

İleti haritasındaki bir girişi tanımlar.

```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```

### <a name="parameters"></a>Parametreler

*dynaChainID*<br/>
[içinde] Bir nesnenin ileti eşlemi için benzersiz tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

CHAIN_MSG_MAP_DYNAMIC, iletileri çalışma zamanında başka bir nesnedeki varsayılan ileti eşlemi'ne yönlendirir. Nesne ve mesaj haritası *dynaChainID*ile ilişkilidir , [CDynamicChain ile tanımladığınız::SetChainEntry](cdynamicchain-class.md#setchainentry). CHAIN_MSG_MAP_DYNAMIC `CDynamicChain` kullanabilmek için sınıfınızı oradan almalısınız. Örneğin, [CDynamicChain](../../atl/reference/cdynamicchain-class.md) genel görünümüne bakın.

> [!NOTE]
> Her zaman [BEGIN_MSG_MAP](#begin_msg_map)ile bir ileti haritası başlatın. Daha sonra sonraki alternatif ileti eşlemlerini ALT_MSG_MAP ile bildirebilirsiniz. [END_MSG_MAP](#end_msg_map) makrosu ileti haritasının sonunu işaretler. Her ileti haritasında tam olarak bir BEGIN_MSG_MAP ve END_MSG_MAP bir örneği olmalıdır.

ATL'de ileti eşlemlerini kullanma hakkında daha fazla bilgi için [İleti Haritaları'na](../../atl/message-maps-atl.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="chain_msg_map_member"></a><a name="chain_msg_map_member"></a>CHAIN_MSG_MAP_MEMBER

İleti haritasındaki bir girişi tanımlar.

```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```

### <a name="parameters"></a>Parametreler

*theChainMember*<br/>
[içinde] İleti eşlemini içeren veri üyesinin adı.

### <a name="remarks"></a>Açıklamalar

CHAIN_MSG_MAP_MEMBER iletileri bir veri üyesinin varsayılan ileti haritasına yönlendirir [(BEGIN_MSG_MAP](#begin_msg_map)ile birlikte bildirilir). İletileri bir veri üyesinin alternatif ileti haritasına [(ALT_MSG_MAP](#alt_msg_map)ile birlikte bildirilen) yönlendirmek için [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)kullanın.

> [!NOTE]
> Her zaman BEGIN_MSG_MAP ile bir ileti haritası başlatın. Daha sonra sonraki alternatif ileti eşlemlerini ALT_MSG_MAP ile bildirebilirsiniz. [END_MSG_MAP](#end_msg_map) makrosu ileti haritasının sonunu işaretler. Her ileti haritasında tam olarak bir BEGIN_MSG_MAP ve END_MSG_MAP bir örneği olmalıdır.

ATL'de ileti eşlemlerini kullanma hakkında daha fazla bilgi için [İleti Haritaları'na](../../atl/message-maps-atl.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]

Bu örnekaşağıdakileri göstermektedir:

- Bir pencere yordamı `CMyClass`'varsayılan ileti `OnPaint` eşlemi kullanıyorsa ve bir `m_obj`iletiyi işlemiyorsa, ileti işleme için varsayılan ileti haritasına yönlendirilir.

- Bir pencere yordamı ilk alternatif ileti `CMyClass`eşlemi kullanıyorsa, tüm iletiler 'varsayılan ileti eşlenine `m_obj`yönlendirilir.

- Bir pencere yordamı `CMyClass`'ikinci alternatif ileti `OnChar` eşlemi kullanıyorsa ve bir iletiyi işlemiyorsa, ileti belirtilen alternatif ileti haritasına `m_obj`yönlendirilir. Sınıf `CMyContainedClass` bu ileti eşlemi ALT_MSG_MAP(1) ile bildirmiş olmalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="command_code_handler"></a><a name="command_code_handler"></a>COMMAND_CODE_HANDLER

[COMMAND_HANDLER](#command_handler)benzer, ancak yalnızca bildirim koduna dayalı [bir WM_COMMAND](/windows/win32/menurc/wm-command) iletisi eşler.

```
COMMAND_CODE_HANDLER(code, func)
```

### <a name="parameters"></a>Parametreler

*Kod*<br/>
[içinde] Bildirim kodu.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="command_handler"></a><a name="command_handler"></a>COMMAND_HANDLER

İleti haritasındaki bir girişi tanımlar.

```
COMMAND_HANDLER(id, code, func)
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] Menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*Kod*<br/>
[içinde] Bildirim kodu.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="remarks"></a>Açıklamalar

COMMAND_HANDLER, bildirim kodunu ve denetim tanımlayıcısını temel alan, belirtilen işleyici işlevine [WM_COMMAND](/windows/win32/menurc/wm-command) bir ileti eşler. Örneğin:

[!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]

bir COMMAND_HANDLER makroda belirtilen herhangi bir işlev aşağıdaki gibi tanımlanmalıdır:

`LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`

İleti haritası, `bHandled` daha `CommandHandler` önce TRUE olarak ayarlanır. İletiyi tam olarak `CommandHandler` işlemiyorsa, iletinin daha fazla işlenmesi gerektiğini belirtmek için FALSE olarak ayarlanmalıdır. `bHandled`

> [!NOTE]
> Her zaman [BEGIN_MSG_MAP](#begin_msg_map)ile bir ileti haritası başlatın. Daha sonra sonraki alternatif ileti eşlemlerini [ALT_MSG_MAP](#alt_msg_map)ile bildirebilirsiniz. [END_MSG_MAP](#end_msg_map) makrosu ileti haritasının sonunu işaretler. Her ileti haritasında tam olarak bir BEGIN_MSG_MAP ve END_MSG_MAP bir örneği olmalıdır.

COMMAND_HANDLER ek olarak, bir tanımlayıcı veya koda bakılmaksızın WM_COMMAND bir iletiyi eşlemek için [MESSAGE_HANDLER](#message_handler) kullanabilirsiniz. Bu durumda, `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` tüm WM_COMMAND iletileri `OnHandlerFunction`' ye yönlendirir.

ATL'de ileti eşlemlerini kullanma hakkında daha fazla bilgi için [İleti Haritaları'na](../../atl/message-maps-atl.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="command_id_handler"></a><a name="command_id_handler"></a>COMMAND_ID_HANDLER

[COMMAND_HANDLER](#command_handler)benzer, ancak yalnızca menü öğesi, denetim veya hızlandırıcı tanımlayıcısını temel alan [bir WM_COMMAND](/windows/win32/menurc/wm-command) iletieşler.

```
COMMAND_ID_HANDLER(id, func)
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] İletiyi gönderen menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="command_range_code_handler"></a><a name="command_range_code_handler"></a>COMMAND_RANGE_CODE_HANDLER

[COMMAND_RANGE_HANDLER](#command_range_handler)benzer, ancak bir denetim aralığından tek bir işleyici işlevine belirli bir bildirim kodu ile [WM_COMMAND](/windows/win32/menurc/wm-command) iletileri eşler.

```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```

### <a name="parameters"></a>Parametreler

*idFirst*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının başlangıcını işaretler.

*idSon*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının sonunu işaretler.

*Kod*<br/>
[içinde] Bildirim kodu.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="remarks"></a>Açıklamalar

Bu aralık, menü öğesinin, denetimin veya iletiyi gönderen hızlandırıcının tanımlayıcısını temel adatır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="command_range_handler"></a><a name="command_range_handler"></a>COMMAND_RANGE_HANDLER

[COMMAND_HANDLER](#command_handler)benzer, ancak bir dizi denetimden tek bir işleyici işlevine [iletileri WM_COMMAND](/windows/win32/menurc/wm-command) eşler.

```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```

### <a name="parameters"></a>Parametreler

*idFirst*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının başlangıcını işaretler.

*idSon*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının sonunu işaretler.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="remarks"></a>Açıklamalar

Bu aralık, menü öğesinin, denetimin veya iletiyi gönderen hızlandırıcının tanımlayıcısını temel adatır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="declare_empty_msg_map"></a><a name="declare_empty_msg_map"></a>DECLARE_EMPTY_MSG_MAP

Boş bir ileti eşlemi bildirir.

```
DECLARE_EMPTY_MSG_MAP()
```

### <a name="remarks"></a>Açıklamalar

DECLARE_EMPTY_MSG_MAP, makroları [BEGIN_MSG_MAP](#begin_msg_map) çağıran ve boş bir ileti eşlemi oluşturmaya [END_MSG_MAP](#end_msg_map) bir kolaylık makrosudur:

[!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]

## <a name="default_reflection_handler"></a><a name="default_reflection_handler"></a>DEFAULT_REFLECTION_HANDLER

Yansıyan iletileri alacak alt pencere (denetim) için varsayılan işleyici sağlar; işleyici, işlenmemiş iletileri `DefWindowProc`düzgün bir şekilde .

```
DEFAULT_REFLECTION_HANDLER()
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="end_msg_map"></a><a name="end_msg_map"></a>END_MSG_MAP

İleti haritasının sonunu işaretler.

```
END_MSG_MAP()
```

### <a name="remarks"></a>Açıklamalar

İleti haritasının başlangıcını işaretlemek için her zaman [BEGIN_MSG_MAP](#begin_msg_map) makroyu kullanın. Sonraki alternatif ileti eşlemlerini bildirmek için [ALT_MSG_MAP](#alt_msg_map) kullanın.

Her zaman tam olarak bir BEGIN_MSG_MAP ve END_MSG_MAP örneği olduğunu unutmayın.

ATL'de ileti eşlemlerini kullanma hakkında daha fazla bilgi için [İleti Haritaları'na](../../atl/message-maps-atl.md)bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnekte varsayılan ileti eşlemi ve her biri bir işleyici işlevi içeren bir alternatif ileti eşlemi gösterilmektedir:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

Sonraki örnekte iki alternatif ileti eşlemi gösterilmektedir. Varsayılan ileti eşlemi boş.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="forward_notifications"></a><a name="forward_notifications"></a>FORWARD_NOTIFICATIONS

Bildirim iletilerini üst pencereye iletin.

```
FORWARD_NOTIFICATIONS()
```

### <a name="remarks"></a>Açıklamalar

İleti haritanızın bir parçası olarak bu makroyu belirtin.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="message_handler"></a><a name="message_handler"></a>MESSAGE_HANDLER

İleti haritasındaki bir girişi tanımlar.

```
MESSAGE_HANDLER( msg, func )
```

### <a name="parameters"></a>Parametreler

*msg*<br/>
[içinde] Windows iletisi.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="remarks"></a>Açıklamalar

MESSAGE_HANDLER, windows iletisini belirtilen işleyici işleviyle eşler.

MESSAGE_HANDLER makroda belirtilen herhangi bir işlev aşağıdaki gibi tanımlanmalıdır:

`LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`

İleti haritası, `bHandled` daha `MessageHandler` önce TRUE olarak ayarlanır. İletiyi tam olarak `MessageHandler` işlemiyorsa, iletinin daha fazla işlenmesi gerektiğini belirtmek için FALSE olarak ayarlanmalıdır. `bHandled`

> [!NOTE]
> Her zaman [BEGIN_MSG_MAP](#begin_msg_map)ile bir ileti haritası başlatın. Daha sonra sonraki alternatif ileti eşlemlerini [ALT_MSG_MAP](#alt_msg_map)ile bildirebilirsiniz. [END_MSG_MAP](#end_msg_map) makrosu ileti haritasının sonunu işaretler. Her ileti haritasında tam olarak bir BEGIN_MSG_MAP ve END_MSG_MAP bir örneği olmalıdır.

MESSAGE_HANDLER ek olarak, [sırasıyla WM_COMMAND](/windows/win32/menurc/wm-command) ve [WM_NOTIFY](/windows/win32/controls/wm-notify) iletileri eşlemek için [COMMAND_HANDLER](#command_handler) ve [NOTIFY_HANDLER](#notify_handler) kullanabilirsiniz.

ATL'de ileti eşlemlerini kullanma hakkında daha fazla bilgi için [İleti Haritaları'na](../../atl/message-maps-atl.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="message_range_handler"></a><a name="message_range_handler"></a>MESSAGE_RANGE_HANDLER

[MESSAGE_HANDLER](#message_handler)benzer, ancak windows iletileri bir dizi tek bir işleyici işlevi eşler.

```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```

### <a name="parameters"></a>Parametreler

*msgİlk*<br/>
[içinde] Bitişik bir ileti aralığının başlangıcını işaretler.

*msgSon*<br/>
[içinde] Bitişik bir ileti aralığının sonunu işaretler.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="notify_code_handler"></a><a name="notify_code_handler"></a>NOTIFY_CODE_HANDLER

[NOTIFY_HANDLER](#notify_handler)benzer, ancak yalnızca bildirim koduna dayalı [bir WM_NOTIFY](/windows/win32/controls/wm-notify) iletieşler.

```
NOTIFY_CODE_HANDLER(cd, func)
```

### <a name="parameters"></a>Parametreler

*Cd*<br/>
[içinde] Bildirim kodu.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="notify_handler"></a><a name="notify_handler"></a>NOTIFY_HANDLER

İleti haritasındaki bir girişi tanımlar.

```
NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] İletiyi gönderen denetimin tanımlayıcısı.

*Cd*<br/>
[içinde] Bildirim kodu.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="remarks"></a>Açıklamalar

NOTIFY_HANDLER, bildirim kodu ve denetim tanımlayıcısını temel alan, belirtilen işleyici işlevine [WM_NOTIFY](/windows/win32/controls/wm-notify) bir ileti eşler.

NOTIFY_HANDLER makroda belirtilen herhangi bir işlev aşağıdaki gibi tanımlanmalıdır:

`LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`

İleti haritası, `bHandled` daha `NotifyHandler` önce TRUE olarak ayarlanır. İletiyi tam olarak `NotifyHandler` işlemiyorsa, iletinin daha fazla işlenmesi gerektiğini belirtmek için FALSE olarak ayarlanmalıdır. `bHandled`

> [!NOTE]
> Her zaman [BEGIN_MSG_MAP](#begin_msg_map)ile bir ileti haritası başlatın. Daha sonra sonraki alternatif ileti eşlemlerini [ALT_MSG_MAP](#alt_msg_map)ile bildirebilirsiniz. [END_MSG_MAP](#end_msg_map) makrosu ileti haritasının sonunu işaretler. Her ileti haritasında tam olarak bir BEGIN_MSG_MAP ve END_MSG_MAP bir örneği olmalıdır.

NOTIFY_HANDLER ek olarak, bir tanımlayıcı veya koda bakılmaksızın WM_NOTIFY bir iletiyi eşlemek için [MESSAGE_HANDLER](#message_handler) kullanabilirsiniz. Bu durumda, `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` tüm WM_NOTIFY iletileri `OnHandlerFunction`.

ATL'de ileti eşlemlerini kullanma hakkında daha fazla bilgi için [İleti Haritaları'na](../../atl/message-maps-atl.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="notify_id_handler"></a><a name="notify_id_handler"></a>NOTIFY_ID_HANDLER

[NOTIFY_HANDLER](#notify_handler)benzer, ancak yalnızca denetim tanımlayıcısını temel alan [WM_NOTIFY](/windows/win32/controls/wm-notify) bir iletiyi eşler.

```
NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] İletiyi gönderen denetimin tanımlayıcısı.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="notify_range_code_handler"></a><a name="notify_range_code_handler"></a>NOTIFY_RANGE_CODE_HANDLER

[NOTIFY_RANGE_HANDLER](#notify_range_handler)benzer, ancak bir denetim aralığından tek bir işleyici işlevine belirli bir bildirim kodu ile [WM_NOTIFY](/windows/win32/controls/wm-notify) iletileri eşler.

```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>Parametreler

*idFirst*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının başlangıcını işaretler.

*idSon*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının sonunu işaretler.

*Cd*<br/>
[içinde] Bildirim kodu.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="remarks"></a>Açıklamalar

Bu aralık, iletiyi gönderen denetimin tanımlayıcısını temel adar.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="notify_range_handler"></a><a name="notify_range_handler"></a>NOTIFY_RANGE_HANDLER

[NOTIFY_HANDLER](#notify_handler)benzer, ancak eşler tek bir işleyici işlevi için denetimleri bir dizi [WM_NOTIFY.](/windows/win32/controls/wm-notify)

```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Parametreler

*idFirst*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının başlangıcını işaretler.

*idSon*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının sonunu işaretler.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="remarks"></a>Açıklamalar

Bu aralık, iletiyi gönderen denetimin tanımlayıcısını temel adar.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="reflect_notifications"></a><a name="reflect_notifications"></a>REFLECT_NOTIFICATIONS

Bildirim iletilerini gönderen alt pencereye (denetim) geri yansıtır.

```
REFLECT_NOTIFICATIONS()
```

### <a name="remarks"></a>Açıklamalar

Bu makroyu ana pencerenin ileti eşleminin bir parçası olarak belirtin.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="reflected_command_code_handler"></a><a name="reflected_command_code_handler"></a>REFLECTED_COMMAND_CODE_HANDLER

[COMMAND_CODE_HANDLER](#command_code_handler)benzer, ancak eşlem komutları üst pencereden yansıtılır.

```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```

### <a name="parameters"></a>Parametreler

*Kod*<br/>
[içinde] Bildirim kodu.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="reflected_command_handler"></a><a name="reflected_command_handler"></a>REFLECTED_COMMAND_HANDLER

[COMMAND_HANDLER](#command_handler)benzer, ancak eşlem komutları üst pencereden yansıtılır.

```
REFLECTED_COMMAND_HANDLER( id, code, func )
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] Menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*Kod*<br/>
[içinde] Bildirim kodu.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="reflected_command_id_handler"></a><a name="reflected_command_id_handler"></a>REFLECTED_COMMAND_ID_HANDLER

[COMMAND_ID_HANDLER](#command_id_handler)benzer, ancak eşlem komutları üst pencereden yansıtılır.

```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] Menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="reflected_command_range_code_handler"></a><a name="reflected_command_range_code_handler"></a>REFLECTED_COMMAND_RANGE_CODE_HANDLER

[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)benzer, ancak eşlem komutları üst pencereden yansıtılır.

```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```

### <a name="parameters"></a>Parametreler

*idFirst*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının başlangıcını işaretler.

*idSon*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının sonunu işaretler.

*Kod*<br/>
[içinde] Bildirim kodu.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="reflected_command_range_handler"></a><a name="reflected_command_range_handler"></a>REFLECTED_COMMAND_RANGE_HANDLER

[COMMAND_RANGE_HANDLER](#command_range_handler)benzer, ancak eşlem komutları üst pencereden yansıtılır.

```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Parametreler

*idFirst*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının başlangıcını işaretler.

*idSon*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının sonunu işaretler.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="reflected_notify_code_handler"></a><a name="reflected_notify_code_handler"></a>REFLECTED_NOTIFY_CODE_HANDLER

[NOTIFY_CODE_HANDLER](#notify_code_handler)benzer, ancak ana pencereden yansıyan bildirimleri eşler.

```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```

### <a name="parameters"></a>Parametreler

*Cd*<br/>
[içinde] Bildirim kodu.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="reflected_notify_handler"></a><a name="reflected_notify_handler"></a>REFLECTED_NOTIFY_HANDLER

[NOTIFY_HANDLER](#notify_handler)benzer, ancak ana pencereden yansıyan bildirimleri eşler.

```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] Menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*Cd*<br/>
[içinde] Bildirim kodu.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="reflected_notify_id_handler"></a><a name="reflected_notify_id_handler"></a>REFLECTED_NOTIFY_ID_HANDLER

[NOTIFY_ID_HANDLER](#notify_id_handler)benzer, ancak ana pencereden yansıyan bildirimleri eşler.

```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] Menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="reflected_notify_range_code_handler"></a><a name="reflected_notify_range_code_handler"></a>REFLECTED_NOTIFY_RANGE_CODE_HANDLER

[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)benzer, ancak ana pencereden yansıyan bildirimleri eşler.

```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>Parametreler

*idFirst*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının başlangıcını işaretler.

*idSon*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının sonunu işaretler.

*Cd*<br/>
[içinde] Bildirim kodu.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="reflected_notify_range_handler"></a><a name="reflected_notify_range_handler"></a>REFLECTED_NOTIFY_RANGE_HANDLER

[NOTIFY_RANGE_HANDLER](#notify_range_handler)benzer, ancak ana pencereden yansıyan bildirimleri eşler.

```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Parametreler

*idFirst*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının başlangıcını işaretler.

*idSon*<br/>
[içinde] Bitişik bir denetim tanımlayıcıaralığının sonunu işaretler.

*func*<br/>
[içinde] İleti işleyiciişlevinin adı.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
