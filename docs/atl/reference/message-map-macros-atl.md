---
title: İleti eşleme makroları (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d87a3b0e4ed9c5c558c90a2935c538b4fb826be
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201686"
---
# <a name="message-map-macros-atl"></a>İleti eşleme makroları (ATL)
İleti eşlemeleri ve girişleri bu makroları tanımlar.  
  
|||  
|-|-|  
|[ALT_MSG_MAP](#alt_msg_map)|Bir diğer ileti eşlemesi başlangıcını işaretler.|  
|[BEGIN_MSG_MAP](#begin_msg_map)|Varsayılan ileti eşlemesi başlangıcını işaretler.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Bir diğer ileti eşlemesi temel sınıfta yetkilisine zincirleme bağlanır.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Zincirleri için alternatif bir ileti sınıfının veri üyesi eşleyin.|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Varsayılan ileti eşlemesi'temel sınıfında yetkilisine zincirleme bağlanır.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Çalışma zamanında başka bir sınıf ileti eşlemede yetkilisine zincirleme bağlanır.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Sınıf veri üyesi varsayılan ileti eşlemede yetkilisine zincirleme bağlanır.|  
|[COMMAND_CODE_HANDLER](#command_code_handler)|WM_COMMAND ileti bildirimi koduna göre bir işleyici işlevi eşlenir.|  
|[COMMAND_HANDLER](#command_handler)|WM_COMMAND ileti bildirimi kodunu ve menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısını dayalı bir işleyici işlevi eşlenir.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|WM_COMMAND ileti menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısına göre bir işleyici işlevi eşlenir.|  
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|WM_COMMAND ileti bildirimi kodunu ve bir aralıkta denetimi tanımlayıcıları temel alan bir işleyici işlevi eşlenir.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|WM_COMMAND ileti denetim tanımlayıcıların bitişik bir aralığı tabanlı bir işleyici işlevi eşlenir.|  
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|Boş ileti eşleme uygular.|  
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|Aksi takdirde işlenmez yansımış iletiler için varsayılan işleyici sağlar.|  
|[END_MSG_MAP](#end_msg_map)|İleti eşlemesi sonunu işaretler.|  
|[FORWARD_NOTIFICATIONS](#forward_notifications)|Bildirim iletilerini üst penceresine iletir.|  
|[MESSAGE_HANDLER](#message_handler)|Windows ileti işleyici işlevine eşler.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Bitişik Windows iletileri için bir işleyici işlevi eşler.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Wm_notıfy iletisi bildirimi koduna göre bir işleyici işlevi eşlenir.|  
|[NOTIFY_HANDLER](#notify_handler)|Wm_notıfy iletisi bildirimi kodunu ve denetim tanımlayıcısı dayalı bir işleyici işlevi eşlenir.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Wm_notıfy iletisi denetim tanımlayıcısına göre bir işleyici işlevi eşlenir.|  
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|Wm_notıfy iletisi bildirimi kodunu ve bir aralıkta denetimi tanımlayıcıları temel alan bir işleyici işlevi eşlenir.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Wm_notıfy iletisi denetim tanımlayıcıların bitişik bir aralığı tabanlı bir işleyici işlevi eşlenir.|  
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|Bildirim iletilerini gönderen penceresine dönüp yansıtır.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Yansımış bir WM_COMMAND ileti bildirimi koduna göre bir işleyici işlevi eşlenir.|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Yansımış bir WM_COMMAND ileti bildirimi kodunu ve menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısını dayalı bir işleyici işlevi eşlenir.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Yansımış bir WM_COMMAND ileti menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısına göre bir işleyici işlevi eşlenir.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Yansımış bir WM_COMMAND ileti bildirimi kodunu ve bir aralıkta denetimi tanımlayıcıları temel alan bir işleyici işlevi eşlenir.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Yansımış bir WM_COMMAND ileti denetim tanımlayıcıların bitişik bir aralığı tabanlı bir işleyici işlevi eşlenir.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Yansıtılan bir wm_notıfy iletisi bildirimi koduna göre bir işleyici işlevi eşlenir.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Yansıtılan bir wm_notıfy iletisi bildirimi kodunu ve denetim tanımlayıcısı dayalı bir işleyici işlevi eşlenir.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Yansıtılan bir wm_notıfy iletisi denetim tanımlayıcısına göre bir işleyici işlevi eşlenir.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Yansıtılan bir wm_notıfy iletisi bildirimi kodunu ve bir aralıkta denetimi tanımlayıcıları temel alan bir işleyici işlevi eşlenir.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Yansıtılan bir wm_notıfy iletisi denetim tanımlayıcıların bitişik bir aralığı tabanlı bir işleyici işlevi eşlenir.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="alt_msg_map"></a>  ALT_MSG_MAP  
 Bir diğer ileti eşlemesi başlangıcını işaretler.  
  
```
ALT_MSG_MAP(msgMapID)
```  
  
### <a name="parameters"></a>Parametreler  
 *msgMapID*  
 [in] İleti eşleme tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL her ileti eşlemesi bir sayı olarak tanımlar. Varsayılan ileti eşlemesi (ile BEGIN_MSG_MAP makrosu bildirildi) 0 ile tanımlanır. Bir diğer ileti eşlemesi tarafından tanımlanan *msgMapID*.  
  
 İleti eşlemeleri bir pencereye gönderilen iletileri işlemek için kullanılır. Örneğin, [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) ileti eşlemesi tanımlayıcısını içeren nesneyi belirtmenizi sağlar. [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc) ardından uygun bir işleyici işlevi veya başka bir ileti eşlemesi kapsanan pencerenin iletileri yönlendirmek için bu ileti eşlemesi kullanır. İşleyici işlevlerini bildirme makroları listesi için bkz. [BEGIN_MSG_MAP](#begin_msg_map).  
  
 Her zaman bir ileti eşlemesi BEGIN_MSG_MAP ile başlar. Ardından, sonraki diğer ileti eşlemeleri bildirebilirsiniz.  
  
 [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemede sonunu işaretler. Her zaman tam olarak bir örneği BEGIN_MSG_MAP ve END_MSG_MAP dikkat edin.  
  
 ATL ileti eşlemeleri hakkında daha fazla bilgi için bkz. [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, varsayılan ileti eşlemesi ve her bir işleyici işlevi içeren bir diğer ileti eşlemesi gösterir:  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 Sonraki örnek, iki farklı ileti eşlemeleri gösterir. Varsayılan ileti eşlemesi yok.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   

##  <a name="begin_msg_map"></a>  BEGIN_MSG_MAP  
 Varsayılan ileti eşlemesi başlangıcını işaretler.  
  
```
BEGIN_MSG_MAP(theClass)
```  
  
### <a name="parameters"></a>Parametreler  
 *Sınıfın*  
 [in] İleti eşlemesi içeren sınıfın adı.  
  
### <a name="remarks"></a>Açıklamalar  
 [CWindowImpl::WindowProc](cwindowimpl-class.md#windowproc) penceresine gönderilen iletileri işlemek için varsayılan ileti eşlemesi kullanır. İleti eşlemesi uygun işleyici işlevine veya başka bir ileti haritasına iletileri yönlendirir.  

  
 Aşağıdaki makro bir işleyici işlevine bir ileti eşleyin. Bu işlev tanımlanmalıdır *sınıfın*.  
  
|Makrosu|Açıklama|  
|-----------|-----------------|  
|[MESSAGE_HANDLER](#message_handler)|Windows ileti işleyici işlevine eşler.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Bitişik Windows iletileri için bir işleyici işlevi eşler.|  
|[COMMAND_HANDLER](#command_handler)|WM_COMMAND ileti bildirimi kodunu ve menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısını dayalı bir işleyici işlevi eşlenir.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|WM_COMMAND ileti menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısına göre bir işleyici işlevi eşlenir.|  
|[COMMAND_CODE_HANDLER](#command_handler)|WM_COMMAND ileti bildirimi koduna göre bir işleyici işlevi eşlenir.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısına göre bir işleyici işlevi, bitişik WM_COMMAND iletileri eşlenir.|  
|[NOTIFY_HANDLER](#notify_handler)|Wm_notıfy iletisi bildirimi kodunu ve denetim tanımlayıcısı dayalı bir işleyici işlevi eşlenir.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Wm_notıfy iletisi denetim tanımlayıcısına göre bir işleyici işlevi eşlenir.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Wm_notıfy iletisi bildirimi koduna göre bir işleyici işlevi eşlenir.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Denetim tanımlayıcısına göre bir işleyici işlevi, bitişik wm_notıfy iletileri eşlenir.|  
  
 Aşağıdaki makroları, başka bir ileti haritasına iletileri doğrudan. Bu işlem "bağlama" olarak adlandırılır  
  
|Makrosu|Açıklama|  
|-----------|-----------------|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Varsayılan ileti eşlemesi'temel sınıfında yetkilisine zincirleme bağlanır.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Sınıf veri üyesi varsayılan ileti eşlemede yetkilisine zincirleme bağlanır.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Bir diğer ileti eşlemesi temel sınıfta yetkilisine zincirleme bağlanır.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Zincirleri için alternatif bir ileti sınıfının veri üyesi eşleyin.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Çalışma zamanında başka bir sınıfın varsayılan ileti eşlemede yetkilisine zincirleme bağlanır.|  
  
 Aşağıdaki makroları üst pencere iletileri "yansıtılan" doğrudan. Örneğin, bir denetim normalde bildirim iletilerini üst pencereye işleme gönderir, ancak üst pencere ileti denetim yansıtabilir.  
  
|Makrosu|Açıklama|  
|-----------|-----------------|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Yansımış bir WM_COMMAND ileti bildirimi kodunu ve menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısını dayalı bir işleyici işlevi eşlenir.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Yansımış bir WM_COMMAND ileti menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısına göre bir işleyici işlevi eşlenir.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Yansımış bir WM_COMMAND ileti bildirimi koduna göre bir işleyici işlevi eşlenir.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Yansımış bir WM_COMMAND ileti denetim tanımlayıcıların bitişik bir aralığı tabanlı bir işleyici işlevi eşlenir.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Yansımış bir WM_COMMAND ileti bildirimi kodunu ve bir aralıkta denetimi tanımlayıcıları temel alan bir işleyici işlevi eşlenir.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Yansıtılan bir wm_notıfy iletisi bildirimi kodunu ve denetim tanımlayıcısı dayalı bir işleyici işlevi eşlenir.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Yansıtılan bir wm_notıfy iletisi denetim tanımlayıcısına göre bir işleyici işlevi eşlenir.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Yansıtılan bir wm_notıfy iletisi bildirimi koduna göre bir işleyici işlevi eşlenir.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Yansıtılan bir wm_notıfy iletisi denetim tanımlayıcıların bitişik bir aralığı tabanlı bir işleyici işlevi eşlenir.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Yansıtılan bir wm_notıfy iletisi bildirimi kodunu ve bir aralıkta denetimi tanımlayıcıları temel alan bir işleyici işlevi eşlenir.|  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]  
  
 Olduğunda bir `CMyExtWindow` nesnesi WM_PAINT iletisini aldığında, iletiyi yönlendirildiği `CMyExtWindow::OnPaint` gerçek işleme için. Varsa `OnPaint` ileti gerekli daha fazla işleme, ileti gösterir sonra varsayılan ileti eşlemede yönlendirilebilir `CMyBaseWindow`.  
  
 Varsayılan ileti eşlemesi ek olarak, bir diğer ileti eşlemesi ile tanımlayabilirsiniz [ALT_MSG_MAP](#alt_msg_map). Her zaman bir ileti eşlemesi BEGIN_MSG_MAP ile başlar. Ardından, sonraki diğer ileti eşlemeleri bildirebilirsiniz. Aşağıdaki örnek, varsayılan ileti eşlemesi ve her bir işleyici işlevi içeren bir diğer ileti eşlemesi gösterir:  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 Sonraki örnek, iki farklı ileti eşlemeleri gösterir. Varsayılan ileti eşlemesi yok.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
 [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemede sonunu işaretler. Her zaman tam olarak bir örneği BEGIN_MSG_MAP ve END_MSG_MAP dikkat edin.  
  
 ATL ileti eşlemeleri hakkında daha fazla bilgi için bkz. [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="chain_msg_map_alt"></a>  CHAIN_MSG_MAP_ALT  
 Bir giriş ileti eşlemede tanımlar.  
  
```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```  
  
### <a name="parameters"></a>Parametreler  
 *theChainClass*  
 [in] İleti eşlemesi içeren temel sınıfın adı.  
  
 *msgMapID*  
 [in] İleti eşleme tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 CHAIN_MSG_MAP_ALT bir temel sınıfta bir diğer ileti haritasına iletileri yönlendirir. Bu alternatif ileti eşlemesi ile bildirilen gerekir [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Temel sınıfın varsayılan ileti haritasına iletileri yönlendirmek için (ile bildirilen [BEGIN_MSG_MAP](#begin_msg_map)), CHAIN_MSG_MAP kullanın. Bir örnek için bkz. [CHAIN_MSG_MAP](#chain_msg_map).  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi BEGIN_MSG_MAP ile başlar. Ardından, sonraki diğer ileti eşlemeleri ile ALT_MSG_MAP bildirebilirsiniz. [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemede sonunu işaretler. Her ileti eşlemesi BEGIN_MSG_MAP ve END_MSG_MAP tek bir örneği olması gerekir.  
  
 ATL ileti eşlemeleri hakkında daha fazla bilgi için bkz. [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="chain_msg_map_alt_member"></a>  CHAIN_MSG_MAP_ALT_MEMBER  
 Bir giriş ileti eşlemede tanımlar.  
  
```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```  
  
### <a name="parameters"></a>Parametreler  
 *theChainMember*  
 [in] İleti eşlemesi içeren veri üyesinin adı.  
  
 *msgMapID*  
 [in] İleti eşleme tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 CHAIN_MSG_MAP_ALT_MEMBER veri üyesi bir diğer ileti haritasına iletileri yönlendirir. Bu alternatif ileti eşlemesi ile bildirilen gerekir [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Bir veri üyesinin varsayılan ileti haritasına iletileri yönlendirmek için (ile bildirilen [BEGIN_MSG_MAP](#begin_msg_map)), CHAIN_MSG_MAP_MEMBER kullanın. Bir örnek için bkz. [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member).  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi BEGIN_MSG_MAP ile başlar. Ardından, sonraki diğer ileti eşlemeleri ile ALT_MSG_MAP bildirebilirsiniz. [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemede sonunu işaretler. Her ileti eşlemesi BEGIN_MSG_MAP ve END_MSG_MAP tek bir örneği olması gerekir.  
  
 ATL ileti eşlemeleri hakkında daha fazla bilgi için bkz. [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="chain_msg_map"></a>  CHAIN_MSG_MAP  
 Bir giriş ileti eşlemede tanımlar.  
  
```
CHAIN_MSG_MAP(theChainClass)
```  
  
### <a name="parameters"></a>Parametreler  
 *theChainClass*  
 [in] İleti eşlemesi içeren temel sınıfın adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel sınıfın varsayılan ileti haritasına iletileri CHAIN_MSG_MAP yönlendirir (ile bildirilen [BEGIN_MSG_MAP](#begin_msg_map)). Temel sınıfın diğer ileti haritasına iletileri yönlendirmek için (ile bildirilen [ALT_MSG_MAP](#alt_msg_map)), kullanın [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt).  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi BEGIN_MSG_MAP ile başlar. Ardından, sonraki diğer ileti eşlemeleri ile ALT_MSG_MAP bildirebilirsiniz. [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemede sonunu işaretler. Her ileti eşlemesi BEGIN_MSG_MAP ve END_MSG_MAP tek bir örneği olması gerekir.  
  
 ATL ileti eşlemeleri hakkında daha fazla bilgi için bkz. [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]  
  
 Bu örnekte aşağıda gösterilmektedir:  
  
-   Bir pencere yordamını kullanıyorsa `CMyClass`ait varsayılan ileti eşlemesi ve `OnPaint` bir ileti, ileti yönlendirilir tanıtıcısı yok `CMyBaseClass`'s işleme için varsayılan ileti eşlemesi.  
  
-   Pencere yordamı ilk diğer ileti eşlemede kullanıp kullanmadığını `CMyClass`, tüm iletileri yönlendirilmiş `CMyBaseClass`ait varsayılan ileti eşlemesi.  
  
-   Bir pencere yordamını kullanıyorsa `CMyClass`ikinci alternatif bir ileti kullanıcının harita ve `OnChar` bir ileti, ileti belirtilen diğer ileti eşlemede yönlendirilir tanıtıcı mu `CMyBaseClass`. `CMyBaseClass` Bu ileti eşlemesi ALT_MSG_MAP(1) ile bildirilen gerekir.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="chain_msg_map_dynamic"></a>  CHAIN_MSG_MAP_DYNAMIC  
 Bir giriş ileti eşlemede tanımlar.  
  
```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```  
  
### <a name="parameters"></a>Parametreler  
 *dynaChainID*  
 [in] Bir nesnenin ileti eşlemesi için benzersiz tanımlayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 CHAIN_MSG_MAP_DYNAMIC çalışma zamanında, başka bir nesneye varsayılan ileti haritasına iletileri yönlendirir. Nesne ve onun ileti eşlemesi ile ilişkili *dynaChainID*, aracılığıyla tanımladığınız [CDynamicChain::SetChainEntry](cdynamicchain-class.md#setchainentry). Sizin sınıfınızdan türetilmelidir `CDynamicChain` CHAIN_MSG_MAP_DYNAMIC kullanmak için. Bir örnek için bkz. [CDynamicChain](../../atl/reference/cdynamicchain-class.md) genel bakış.  

  
> [!NOTE]
>  Her zaman bir ileti eşlemesi ile başlayan [BEGIN_MSG_MAP](#begin_msg_map). Ardından, sonraki diğer ileti eşlemeleri ile ALT_MSG_MAP bildirebilirsiniz. [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemede sonunu işaretler. Her ileti eşlemesi BEGIN_MSG_MAP ve END_MSG_MAP tek bir örneği olması gerekir.  
  
 ATL ileti eşlemeleri hakkında daha fazla bilgi için bkz. [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="chain_msg_map_member"></a>  CHAIN_MSG_MAP_MEMBER  
 Bir giriş ileti eşlemede tanımlar.  
  
```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```  
  
### <a name="parameters"></a>Parametreler  
 *theChainMember*  
 [in] İleti eşlemesi içeren veri üyesinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir veri üyesinin varsayılan ileti haritasına iletileri CHAIN_MSG_MAP_MEMBER yönlendirir (ile bildirilen [BEGIN_MSG_MAP](#begin_msg_map)). Bir veri üyesinin diğer ileti haritasına iletileri yönlendirmek için (ile bildirilen [ALT_MSG_MAP](#alt_msg_map)), kullanın [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member).  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi BEGIN_MSG_MAP ile başlar. Ardından, sonraki diğer ileti eşlemeleri ile ALT_MSG_MAP bildirebilirsiniz. [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemede sonunu işaretler. Her ileti eşlemesi BEGIN_MSG_MAP ve END_MSG_MAP tek bir örneği olması gerekir.  
  
 ATL ileti eşlemeleri hakkında daha fazla bilgi için bkz. [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]  
  
 Bu örnekte aşağıda gösterilmektedir:  
  
-   Bir pencere yordamını kullanıyorsa `CMyClass`ait varsayılan ileti eşlemesi ve `OnPaint` bir ileti, ileti yönlendirilir tanıtıcısı yok `m_obj`'s işleme için varsayılan ileti eşlemesi.  
  
-   Pencere yordamı ilk diğer ileti eşlemede kullanıp kullanmadığını `CMyClass`, tüm iletileri yönlendirilmiş `m_obj`ait varsayılan ileti eşlemesi.  
  
-   Bir pencere yordamını kullanıyorsa `CMyClass`ikinci alternatif bir ileti kullanıcının harita ve `OnChar` bir ileti, ileti belirtilen diğer ileti Haritası yönlendirilmiş tanıtıcı mu `m_obj`. Sınıf `CMyContainedClass` bu ileti eşlemesi ALT_MSG_MAP(1) ile bildirilen gerekir.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="command_code_handler"></a>  COMMAND_CODE_HANDLER  
 Benzer şekilde [COMMAND_HANDLER](#command_handler), ancak eşleyen bir [WM_COMMAND](/windows/desktop/menurc/wm-command) ileti tabanlı yalnızca bildirim kod.  
  
```
COMMAND_CODE_HANDLER(code, func)
```  
  
### <a name="parameters"></a>Parametreler  
 *Kod*  
 [in] Uyarı kodu.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="command_handler"></a>  COMMAND_HANDLER  
 Bir giriş ileti eşlemede tanımlar.  
  
```
COMMAND_HANDLER(id, code, func)
```    
  
### <a name="parameters"></a>Parametreler  
 *id*  
 [in] Menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısı.  
  
 *Kod*  
 [in] Uyarı kodu.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 COMMAND_HANDLER eşleyen bir [WM_COMMAND](/windows/desktop/menurc/wm-command) bildirim kodu ve denetim tanımlayıcısına göre belirtilen işleyici işlevine ileti. Örneğin:  
  
 [!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]  
  
 COMMAND_HANDLER makroda belirtilen herhangi bir işlev gibi tanımlanmış olması gerekir:  
  
 `LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`  
  
 İleti eşleme kümeleri `bHandled` önce true `CommandHandler` çağrılır. Varsa `CommandHandler` tam iletiyi işlemez ayarlamanız gerekir `bHandled` ihtiyaç daha fazla işleme belirtmek için false.  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi ile başlayan [BEGIN_MSG_MAP](#begin_msg_map). Ardından, sonraki diğer ileti eşlemeleri ile bildirebilirsiniz [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemede sonunu işaretler. Her ileti eşlemesi BEGIN_MSG_MAP ve END_MSG_MAP tek bir örneği olması gerekir.  
  
 COMMAND_HANDLER ek olarak, kullandığınız [MESSAGE_HANDLER](#message_handler) tanımlayıcı veya kod bakılmaksızın WM_COMMAND ileti eşlemek için. Bu durumda, `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` tüm WM_COMMAND iletileri yönlendirecek `OnHandlerFunction`.  
  
 ATL ileti eşlemeleri hakkında daha fazla bilgi için bkz. [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="command_id_handler"></a>  COMMAND_ID_HANDLER  
 Benzer şekilde [COMMAND_HANDLER](#command_handler), ancak eşleyen bir [WM_COMMAND](/windows/desktop/menurc/wm-command) ileti tabanlı menü öğesi, denetim ya da Hızlandırıcı, yalnızca tanımlayıcısı.  
  
```
COMMAND_ID_HANDLER(id, func)
```  
  
### <a name="parameters"></a>Parametreler  
 *id*  
 [in] Menü öğesi, denetim ya da Hızlandırıcı iletiyi gönderen tanımlayıcısı.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="command_range_code_handler"></a>  COMMAND_RANGE_CODE_HANDLER  
 Benzer şekilde [COMMAND_RANGE_HANDLER](#command_range_handler), ancak haritaları [WM_COMMAND](/windows/desktop/menurc/wm-command) iletileri kod içeren bir özel bildirim denetimlerini aralığından tek işleyici işlevi.  
  
```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```    
  
### <a name="parameters"></a>Parametreler  
 *idFirst*  
 [in] Bir aralıkta denetimi tanımlayıcıları başlangıcını işaretler.  
  
 *idLast*  
 [in] Denetim tanımlayıcıların bitişik bir aralığın sonunu işaretler.  
  
 *Kod*  
 [in] Uyarı kodu.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu aralık, menü öğesi, denetim ya da ileti gönderilirken Hızlandırıcı tanıtıcısı temel alır.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="command_range_handler"></a>  COMMAND_RANGE_HANDLER  
 Benzer şekilde [COMMAND_HANDLER](#command_handler), ancak haritaları [WM_COMMAND](/windows/desktop/menurc/wm-command) iletileri denetimleri aralığından tek işleyici işlevi.  
  
```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```    
  
### <a name="parameters"></a>Parametreler  
 *idFirst*  
 [in] Bir aralıkta denetimi tanımlayıcıları başlangıcını işaretler.  
  
 *idLast*  
 [in] Denetim tanımlayıcıların bitişik bir aralığın sonunu işaretler.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu aralık, menü öğesi, denetim ya da ileti gönderilirken Hızlandırıcı tanıtıcısı temel alır.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="declare_empty_msg_map"></a>  DECLARE_EMPTY_MSG_MAP  
 Bir boş ileti eşlemesi bildirir.  
  
```
DECLARE_EMPTY_MSG_MAP()
```  
  
### <a name="remarks"></a>Açıklamalar  
 DECLARE_EMPTY_MSG_MAP makroları çağıran bir makrodur kolaylık [BEGIN_MSG_MAP](#begin_msg_map) ve [END_MSG_MAP](#end_msg_map) bir boş ileti eşlemesi oluşturmak için:  
  
 [!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]  
  
##  <a name="default_reflection_handler"></a>  DEFAULT_REFLECTION_HANDLER  
 Yansımış iletileri alacak alt pencerenin (Denetim) için bir varsayılan işleyici sağlar. işleyici düzgün bir şekilde işlenmemiş iletiler geçer `DefWindowProc`.  
  
```
DEFAULT_REFLECTION_HANDLER()
```  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="end_msg_map"></a>  END_MSG_MAP  
 İleti eşlemesi sonunu işaretler.  
  
```
END_MSG_MAP()
```  
  
### <a name="remarks"></a>Açıklamalar  
 Her zaman [BEGIN_MSG_MAP](#begin_msg_map) makrosu ileti eşlemesi başlangıcını işaretler. Kullanım [ALT_MSG_MAP](#alt_msg_map) sonraki diğer ileti eşlemeleri bildirmek için.  
  
 Her zaman tam olarak bir örneği BEGIN_MSG_MAP ve END_MSG_MAP dikkat edin.  
  
 ATL ileti eşlemeleri hakkında daha fazla bilgi için bkz. [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, varsayılan ileti eşlemesi ve her bir işleyici işlevi içeren bir diğer ileti eşlemesi gösterir:  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 Sonraki örnek, iki farklı ileti eşlemeleri gösterir. Varsayılan ileti eşlemesi yok.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="forward_notifications"></a>  FORWARD_NOTIFICATIONS  
 Bildirim iletilerini üst penceresine iletir.  
  
```
FORWARD_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makro, ileti eşlemesi bir parçası olarak belirtin.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="message_handler"></a>  MESSAGE_HANDLER  
 Bir giriş ileti eşlemede tanımlar.  
  
```
MESSAGE_HANDLER( msg, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *ileti*  
 [in] Windows ileti.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 MESSAGE_HANDLER belirtilen işleyici işlevine bir Windows ileti eşlemeleri.  
  
 MESSAGE_HANDLER makroda belirtilen herhangi bir işlev gibi tanımlanmış olması gerekir:  
  
 `LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`  
  
 İleti eşleme kümeleri `bHandled` önce true `MessageHandler` çağrılır. Varsa `MessageHandler` tam iletiyi işlemez ayarlamanız gerekir `bHandled` ihtiyaç daha fazla işleme belirtmek için false.  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi ile başlayan [BEGIN_MSG_MAP](#begin_msg_map). Ardından, sonraki diğer ileti eşlemeleri ile bildirebilirsiniz [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemede sonunu işaretler. Her ileti eşlemesi BEGIN_MSG_MAP ve END_MSG_MAP tek bir örneği olması gerekir.  
  
 MESSAGE_HANDLER ek olarak, kullandığınız [COMMAND_HANDLER](#command_handler) ve [NOTIFY_HANDLER](#notify_handler) eşlemek için [WM_COMMAND](/windows/desktop/menurc/wm-command) ve [wm_notıfy](https://msdn.microsoft.com/library/windows/desktop/bb775583) iletileri , sırasıyla.  
  
 ATL ileti eşlemeleri hakkında daha fazla bilgi için bkz. [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="message_range_handler"></a>  MESSAGE_RANGE_HANDLER  
 Benzer şekilde [MESSAGE_HANDLER](#message_handler), ancak, bir aralık Windows iletileri bir tek işleyicisi işlevini eşlemeleri.  
  
```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *msgFirst*  
 [in] İletileri bir aralıkta başlangıcını işaretler.  
  
 *msgLast*  
 [in] İletilerin bitişik bir aralığın sonunu işaretler.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="notify_code_handler"></a>  NOTIFY_CODE_HANDLER  
 Benzer şekilde [NOTIFY_HANDLER](#notify_handler), ancak eşleyen bir [wm_notıfy](https://msdn.microsoft.com/library/windows/desktop/bb775583) ileti tabanlı yalnızca bildirim kod.  
  
```
NOTIFY_CODE_HANDLER(cd, func)
```  
  
### <a name="parameters"></a>Parametreler  
 *CD*  
 [in] Uyarı kodu.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="notify_handler"></a>  NOTIFY_HANDLER  
 Bir giriş ileti eşlemede tanımlar.  
  
```
NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *id*  
 [in] İletiyi gönderen denetim tanımlayıcısı.  
  
 *CD*  
 [in] Uyarı kodu.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 NOTIFY_HANDLER eşleyen bir [wm_notıfy](https://msdn.microsoft.com/library/windows/desktop/bb775583) bildirim kodu ve denetim tanımlayıcısına göre belirtilen işleyici işlevine ileti.  
  
 NOTIFY_HANDLER makroda belirtilen herhangi bir işlev gibi tanımlanmış olması gerekir:  
  
 `LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`  
  
 İleti eşleme kümeleri `bHandled` önce true `NotifyHandler` çağrılır. Varsa `NotifyHandler` tam iletiyi işlemez ayarlamanız gerekir `bHandled` ihtiyaç daha fazla işleme belirtmek için false.  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi ile başlayan [BEGIN_MSG_MAP](#begin_msg_map). Ardından, sonraki diğer ileti eşlemeleri ile bildirebilirsiniz [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemede sonunu işaretler. Her ileti eşlemesi BEGIN_MSG_MAP ve END_MSG_MAP tek bir örneği olması gerekir.  
  
 NOTIFY_HANDLER ek olarak, kullandığınız [MESSAGE_HANDLER](#message_handler) tanımlayıcı veya kod bakılmaksızın bir wm_notıfy iletisi eşlemek için. Bu durumda, `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` tüm wm_notıfy iletileri yönlendirecek `OnHandlerFunction`.  
  
 ATL ileti eşlemeleri hakkında daha fazla bilgi için bkz. [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="notify_id_handler"></a>  NOTIFY_ID_HANDLER  
 Benzer şekilde [NOTIFY_HANDLER](#notify_handler), ancak eşleyen bir [wm_notıfy](https://msdn.microsoft.com/library/windows/desktop/bb775583) ileti tabanlı yalnızca denetim tanımlayıcısı.  
  
```
NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *id*  
 [in] İletiyi gönderen denetim tanımlayıcısı.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="notify_range_code_handler"></a>  NOTIFY_RANGE_CODE_HANDLER  
 Benzer şekilde [NOTIFY_RANGE_HANDLER](#notify_range_handler), ancak haritaları [wm_notıfy](https://msdn.microsoft.com/library/windows/desktop/bb775583) iletileri kod içeren bir özel bildirim denetimlerini aralığından tek işleyici işlevi.  
  
```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *idFirst*  
 [in] Bir aralıkta denetimi tanımlayıcıları başlangıcını işaretler.  
  
 *idLast*  
 [in] Denetim tanımlayıcıların bitişik bir aralığın sonunu işaretler.  
  
 *CD*  
 [in] Uyarı kodu.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu aralık, ileti gönderilirken denetimin tanımlayıcının temel alır.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="notify_range_handler"></a>  NOTIFY_RANGE_HANDLER  
 Benzer şekilde [NOTIFY_HANDLER](#notify_handler), ancak haritaları [wm_notıfy](https://msdn.microsoft.com/library/windows/desktop/bb775583) iletileri denetimleri aralığından tek işleyici işlevi.  
  
```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *idFirst*  
 [in] Bir aralıkta denetimi tanımlayıcıları başlangıcını işaretler.  
  
 *idLast*  
 [in] Denetim tanımlayıcıların bitişik bir aralığın sonunu işaretler.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu aralık, ileti gönderilirken denetimin tanımlayıcının temel alır.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="reflect_notifications"></a>  REFLECT_NOTIFICATIONS  
 Bildirim iletileri gönderen alt penceresine dönüp (Denetim) yansıtır.  
  
```
REFLECT_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makro, üst pencere ileti eşlemesi bir parçası olarak belirtin.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="reflected_command_code_handler"></a>  REFLECTED_COMMAND_CODE_HANDLER  
 Benzer şekilde [COMMAND_CODE_HANDLER](#command_code_handler), ancak üst penceresinden yansıtılan komutları eşler.  
  
```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *Kod*  
 [in] Uyarı kodu.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
   
##  <a name="reflected_command_handler"></a>  REFLECTED_COMMAND_HANDLER  
 Benzer şekilde [COMMAND_HANDLER](#command_handler), ancak üst penceresinden yansıtılan komutları eşler.  
  
```
REFLECTED_COMMAND_HANDLER( id, code, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *id*  
 [in] Menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısı.  
  
 *Kod*  
 [in] Uyarı kodu.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_command_id_handler"></a>  REFLECTED_COMMAND_ID_HANDLER  
 Benzer şekilde [COMMAND_ID_HANDLER](#command_id_handler), ancak üst penceresinden yansıtılan komutları eşler.  
  
```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *id*  
 [in] Menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısı.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_command_range_code_handler"></a>  REFLECTED_COMMAND_RANGE_CODE_HANDLER  
 Benzer şekilde [COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler), ancak üst penceresinden yansıtılan komutları eşler.  
  
```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *idFirst*  
 [in] Bir aralıkta denetimi tanımlayıcıları başlangıcını işaretler.  
  
 *idLast*  
 [in] Denetim tanımlayıcıların bitişik bir aralığın sonunu işaretler.  
  
 *Kod*  
 [in] Uyarı kodu.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_command_range_handler"></a>  REFLECTED_COMMAND_RANGE_HANDLER  
 Benzer şekilde [COMMAND_RANGE_HANDLER](#command_range_handler), ancak üst penceresinden yansıtılan komutları eşler.  
  
```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *idFirst*  
 [in] Bir aralıkta denetimi tanımlayıcıları başlangıcını işaretler.  
  
 *idLast*  
 [in] Denetim tanımlayıcıların bitişik bir aralığın sonunu işaretler.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_notify_code_handler"></a>  REFLECTED_NOTIFY_CODE_HANDLER  
 Benzer şekilde [NOTIFY_CODE_HANDLER](#notify_code_handler), ancak üst penceresinden yansıtılan bildirimleri eşler.  
  
```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *CD*  
 [in] Uyarı kodu.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_notify_handler"></a>  REFLECTED_NOTIFY_HANDLER  
 Benzer şekilde [NOTIFY_HANDLER](#notify_handler), ancak üst penceresinden yansıtılan bildirimleri eşler.  
  
```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *id*  
 [in] Menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısı.  
  
 *CD*  
 [in] Uyarı kodu.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_notify_id_handler"></a>  REFLECTED_NOTIFY_ID_HANDLER  
 Benzer şekilde [NOTIFY_ID_HANDLER](#notify_id_handler), ancak üst penceresinden yansıtılan bildirimleri eşler.  
  
```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *id*  
 [in] Menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısı.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_notify_range_code_handler"></a>  REFLECTED_NOTIFY_RANGE_CODE_HANDLER  
 Benzer şekilde [NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler), ancak üst penceresinden yansıtılan bildirimleri eşler.  
  
```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```    
  
### <a name="parameters"></a>Parametreler  
 *idFirst*  
 [in] Bir aralıkta denetimi tanımlayıcıları başlangıcını işaretler.  
  
 *idLast*  
 [in] Denetim tanımlayıcıların bitişik bir aralığın sonunu işaretler.  
  
 *CD*  
 [in] Uyarı kodu.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="reflected_notify_range_handler"></a>  REFLECTED_NOTIFY_RANGE_HANDLER  
 Benzer şekilde [NOTIFY_RANGE_HANDLER](#notify_range_handler), ancak üst penceresinden yansıtılan bildirimleri eşler.  
  
```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *idFirst*  
 [in] Bir aralıkta denetimi tanımlayıcıları başlangıcını işaretler.  
  
 *idLast*  
 [in] Denetim tanımlayıcıların bitişik bir aralığın sonunu işaretler.  
  
 *FUNC*  
 [in] İleti işleyici işlevinin adı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
