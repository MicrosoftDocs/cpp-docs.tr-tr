---
title: "İleti eşleme makroları (ATL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 200d82c9d9b2ca0456ae5de4d6c937be69e212bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="message-map-macros-atl"></a>İleti eşleme makroları (ATL)
İleti eşlemeleri ve girişleri bu makroları tanımlayın.  
  
|||  
|-|-|  
|[ALT_MSG_MAP](#alt_msg_map)|Bir alternatif ileti eşlemesi başlangıcını işaretler.|  
|[BEGIN_MSG_MAP](#begin_msg_map)|Varsayılan ileti eşlemesi başlangıcını işaretler.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Alternatif iletisine zincirleri taban sınıf içinde eşleyin.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Alternatif iletisine zincirleri bir sınıfı veri üyesi eşleyin.|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Varsayılan ileti zincirleri taban sınıf içinde eşleyin.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Çalışma zamanında başka bir sınıf ileti eşlemesinde zincir oluşturur.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Sınıfı veri üyesi varsayılan ileti eşlemesinde zincir oluşturur.|  
|[COMMAND_CODE_HANDLER](#command_code_handler)|MAPS bir **WM_COMMAND** bildirim koduna göre bir işleyici işlevi ileti.|  
|[COMMAND_HANDLER](#command_handler)|MAPS bir **WM_COMMAND** bildirim kodu ve menü öğesi, denetim veya Hızlandırıcı tanıtıcısı dayalı bir işleyici işlevi ileti.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|MAPS bir **WM_COMMAND** menü öğesi, denetim veya Hızlandırıcı tanımlayıcısına göre bir işleyici işlevi ileti.|  
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|MAPS bir **WM_COMMAND** bildirim kodu ve denetim tanımlayıcıları bitişik bir dizi dayalı bir işleyici işlevi ileti.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|MAPS bir **WM_COMMAND** denetim tanımlayıcıları bitişik bir aralığı tabanlı bir işleyici işlevi ileti.|  
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|Bir boş ileti eşlemesi uygular.|  
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|Aksi takdirde işlenmemiş yansımış iletiler için bir varsayılan işleyici sağlar.|  
|[END_MSG_MAP](#end_msg_map)|İleti eşlemesi sonunu işaretler.|  
|[FORWARD_NOTIFICATIONS](#forward_notifications)|Üst pencere bildirim iletileri iletir.|  
|[MESSAGE_HANDLER](#message_handler)|Windows ileti işleyicisi işleve eşler.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Bitişik Windows iletileri bir işleyici işlevi eşler.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|MAPS bir **wm_notıfy** bildirim koduna göre bir işleyici işlevi ileti.|  
|[NOTIFY_HANDLER](#notify_handler)|MAPS bir **wm_notıfy** bildirim kodu ve denetim tanımlayıcısı dayalı bir işleyici işlevi ileti.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|MAPS bir **wm_notıfy** denetim tanımlayıcısına göre bir işleyici işlevi ileti.|  
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|MAPS bir **wm_notıfy** bildirim kodu ve denetim tanımlayıcıları bitişik bir dizi dayalı bir işleyici işlevi ileti.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|MAPS bir **wm_notıfy** denetim tanımlayıcıları bitişik bir aralığı tabanlı bir işleyici işlevi ileti.|  
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|Bildirim iletilerini geri bunları gönderilen penceresine yansıtır.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Yansıtılan bir eşler **WM_COMMAND** bildirim koduna göre bir işleyici işlevi ileti.|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Yansıtılan bir eşler **WM_COMMAND** bildirim kodu ve menü öğesi, denetim veya Hızlandırıcı tanıtıcısı dayalı bir işleyici işlevi ileti.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Yansıtılan bir eşler **WM_COMMAND** menü öğesi, denetim veya Hızlandırıcı tanımlayıcısına göre bir işleyici işlevi ileti.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Yansıtılan bir eşler **WM_COMMAND** bildirim kodu ve denetim tanımlayıcıları bitişik bir dizi dayalı bir işleyici işlevi ileti.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Yansıtılan bir eşler **WM_COMMAND** denetim tanımlayıcıları bitişik bir aralığı tabanlı bir işleyici işlevi ileti.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Yansıtılan bir eşler **wm_notıfy** bildirim koduna göre bir işleyici işlevi ileti.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Yansıtılan bir eşler **wm_notıfy** bildirim kodu ve denetim tanımlayıcısı dayalı bir işleyici işlevi ileti.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Yansıtılan bir eşler **wm_notıfy** denetim tanımlayıcısına göre bir işleyici işlevi ileti.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Yansıtılan bir eşler **wm_notıfy** bildirim kodu ve denetim tanımlayıcıları bitişik bir dizi dayalı bir işleyici işlevi ileti.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Yansıtılan bir eşler **wm_notıfy** denetim tanımlayıcıları bitişik bir aralığı tabanlı bir işleyici işlevi ileti.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="alt_msg_map"></a>ALT_MSG_MAP  
 Bir alternatif ileti eşlemesi başlangıcını işaretler.  
  
```
ALT_MSG_MAP(msgMapID)
```  
  
### <a name="parameters"></a>Parametreler  
 `msgMapID`  
 [in] İleti eşleme tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL her ileti eşlemesi bir sayıyla tanımlar. Varsayılan ileti eşlemesi (ile bildirilen `BEGIN_MSG_MAP` makrosu) 0 ile tanımlanır. Bir alternatif ileti eşlemesi tarafından tanımlanan `msgMapID`.  
  
 İleti eşlemeleri için bir pencere gönderilen iletileri işlemek için kullanılır. Örneğin, [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) ileti eşlemesi tanımlayıcısını içeren nesnesinde belirtmenize olanak tanır. [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc) uygun işleyiciyi işlevi veya başka bir ileti eşlemesi içerdiği pencere iletileri yönlendirmek için bu ileti eşlemesi kullanır. İşleyici işlevleri bildirme makroları listesi için bkz: [BEGIN_MSG_MAP](#begin_msg_map).  
  
 Her zaman bir ileti eşlemesi ile başlayan `BEGIN_MSG_MAP`. Ardından, sonraki alternatif ileti eşlemeleri bildirebilirsiniz.  
  
 [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemesi sonunu işaretler. Her zaman tek bir örneği yoktur `BEGIN_MSG_MAP` ve `END_MSG_MAP`.  
  
 İleti eşlemeleri ATL içinde kullanma hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek varsayılan ileti eşlemesi ve her bir işleyici işlevi içeren bir alternatif ileti eşlemesi gösterir:  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 Sonraki örnekte iki alternatif ileti eşlemeleri gösterir. Varsayılan ileti eşlemesi boştur.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   

##  <a name="begin_msg_map"></a>BEGIN_MSG_MAP  
 Varsayılan ileti eşlemesi başlangıcını işaretler.  
  
```
BEGIN_MSG_MAP(theClass)
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 [in] İleti eşleme içeren sınıfın adı.  
  
### <a name="remarks"></a>Açıklamalar  
 [CWindowImpl::WindowProc](cwindowimpl-class.md#windowproc) pencereye gönderilen iletileri işlemek için varsayılan ileti eşlemesi kullanır. İleti eşlemesi iletileri uygun işleyiciyi işlevi veya başka bir ileti eşlemesi yönlendirir.  

  
 Aşağıdaki makroları bir ileti için bir işleyici işlevi eşleyin. Bu işlev tanımlanmalıdır `theClass`.  
  
|Makrosu|Açıklama|  
|-----------|-----------------|  
|[MESSAGE_HANDLER](#message_handler)|Windows ileti işleyicisi işleve eşler.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Bitişik Windows iletileri bir işleyici işlevi eşler.|  
|[COMMAND_HANDLER](#command_handler)|MAPS bir **WM_COMMAND** bildirim kodu ve menü öğesi, denetim veya Hızlandırıcı tanıtıcısı dayalı bir işleyici işlevi ileti.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|MAPS bir **WM_COMMAND** menü öğesi, denetim veya Hızlandırıcı tanımlayıcısına göre bir işleyici işlevi ileti.|  
|[COMMAND_CODE_HANDLER](#command_handler)|MAPS bir **WM_COMMAND** bildirim koduna göre bir işleyici işlevi ileti.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Bitişik bir dizi eşlemeleri **WM_COMMAND** bir işleyici işlevi iletileri dayalı menü öğesi, denetim veya Hızlandırıcı tanıtıcısı.|  
|[NOTIFY_HANDLER](#notify_handler)|MAPS bir **wm_notıfy** bildirim kodu ve denetim tanımlayıcısı dayalı bir işleyici işlevi ileti.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|MAPS bir **wm_notıfy** denetim tanımlayıcısına göre bir işleyici işlevi ileti.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|MAPS bir **wm_notıfy** bildirim koduna göre bir işleyici işlevi ileti.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Bitişik bir dizi eşlemeleri **wm_notıfy** bir işleyici işlevi iletileri tabanlı denetim tanımlayıcısı.|  
  
 Aşağıdaki makroları başka bir ileti eşlemesi iletilerini doğrudan. Bu işlem "zincirleme." olarak adlandırılır  
  
|Makrosu|Açıklama|  
|-----------|-----------------|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Varsayılan ileti zincirleri taban sınıf içinde eşleyin.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Sınıfı veri üyesi varsayılan ileti eşlemesinde zincir oluşturur.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Alternatif iletisine zincirleri taban sınıf içinde eşleyin.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Alternatif iletisine zincirleri bir sınıfı veri üyesi eşleyin.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Çalışma zamanında başka bir sınıf varsayılan ileti eşlemesinde zincir oluşturur.|  
  
 Aşağıdaki makroları "yansıtılan" iletileri üst penceresinden doğrudan. Örneğin, bir denetim normalde bildirim iletileri için kendi üst penceresine işleme gönderir, ancak üst pencere iletisi denetimi yansıtabilirsiniz.  
  
|Makrosu|Açıklama|  
|-----------|-----------------|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Yansıtılan bir eşler **WM_COMMAND** bildirim kodu ve menü öğesi, denetim veya Hızlandırıcı tanıtıcısı dayalı bir işleyici işlevi ileti.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Yansıtılan bir eşler **WM_COMMAND** menü öğesi, denetim veya Hızlandırıcı tanımlayıcısına göre bir işleyici işlevi ileti.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Yansıtılan bir eşler **WM_COMMAND** bildirim koduna göre bir işleyici işlevi ileti.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Yansıtılan bir eşler **WM_COMMAND** denetim tanımlayıcıları bitişik bir aralığı tabanlı bir işleyici işlevi ileti.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Yansıtılan bir eşler **WM_COMMAND** bildirim kodu ve denetim tanımlayıcıları bitişik bir dizi dayalı bir işleyici işlevi ileti.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Yansıtılan bir eşler **wm_notıfy** bildirim kodu ve denetim tanımlayıcısı dayalı bir işleyici işlevi ileti.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Yansıtılan bir eşler **wm_notıfy** denetim tanımlayıcısına göre bir işleyici işlevi ileti.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Yansıtılan bir eşler **wm_notıfy** bildirim koduna göre bir işleyici işlevi ileti.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Yansıtılan bir eşler **wm_notıfy** denetim tanımlayıcıları bitişik bir aralığı tabanlı bir işleyici işlevi ileti.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Yansıtılan bir eşler **wm_notıfy** bildirim kodu ve denetim tanımlayıcıları bitişik bir dizi dayalı bir işleyici işlevi ileti.|  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]  
  
 Zaman bir `CMyExtWindow` nesnesini alır bir `WM_PAINT` ileti, ileti yönlendirilir `CMyExtWindow::OnPaint` gerçek işleme. Varsa `OnPaint` ileti gerektiren başka bir işleme, ileti gösterir sonra varsayılan ileti eşlemesinde için yönlendirilmesi `CMyBaseWindow`.  
  
 Varsayılan ileti eşlemesi ek olarak, diğer ileti eşlemesi ile tanımlayabilirsiniz [ALT_MSG_MAP](#alt_msg_map). Her zaman bir ileti eşlemesi ile başlayan `BEGIN_MSG_MAP`. Ardından, sonraki alternatif ileti eşlemeleri bildirebilirsiniz. Aşağıdaki örnek varsayılan ileti eşlemesi ve her bir işleyici işlevi içeren bir alternatif ileti eşlemesi gösterir:  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 Sonraki örnekte iki alternatif ileti eşlemeleri gösterir. Varsayılan ileti eşlemesi boştur.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
 [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemesi sonunu işaretler. Her zaman tek bir örneği yoktur `BEGIN_MSG_MAP` ve `END_MSG_MAP`.  
  
 İleti eşlemeleri ATL içinde kullanma hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="chain_msg_map_alt"></a>CHAIN_MSG_MAP_ALT  
 Bir giriş ileti eşlemesinde tanımlar.  
  
```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```  
  
### <a name="parameters"></a>Parametreler  
 `theChainClass`  
 [in] İleti eşleme içeren temel sınıfın adı.  
  
 `msgMapID`  
 [in] İleti eşleme tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `CHAIN_MSG_MAP_ALT`iletileri alternatif ileti eşlemesi için bir taban sınıf içinde yönlendirir. Bu alternatif ileti eşlemesi ile bildirilen gerekir [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Taban sınıf varsayılan ileti eşlemesi iletilerini yönlendirmek için (ile bildirilen [BEGIN_MSG_MAP](#begin_msg_map)), kullanmak `CHAIN_MSG_MAP`. Bir örnek için bkz: [CHAIN_MSG_MAP](#chain_msg_map).  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi ile başlayan `BEGIN_MSG_MAP`. Ardından sonraki alternatif ileti Eşlemleriyle bildirebilir `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemesi sonunu işaretler. Her ileti eşlemesi tek bir örneği olmalıdır `BEGIN_MSG_MAP` ve `END_MSG_MAP`.  
  
 İleti eşlemeleri ATL içinde kullanma hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="chain_msg_map_alt_member"></a>CHAIN_MSG_MAP_ALT_MEMBER  
 Bir giriş ileti eşlemesinde tanımlar.  
  
```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```  
  
### <a name="parameters"></a>Parametreler  
 `theChainMember`  
 [in] İleti eşleme içeren veri üyesi adı.  
  
 `msgMapID`  
 [in] İleti eşleme tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `CHAIN_MSG_MAP_ALT_MEMBER`bir alternatif ileti eşlemesi iletileri veri üyesi yönlendirir. Bu alternatif ileti eşlemesi ile bildirilen gerekir [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Veri üye varsayılan ileti eşlemesi iletilerini yönlendirmek için (ile bildirilen [BEGIN_MSG_MAP](#begin_msg_map)), kullanmak `CHAIN_MSG_MAP_MEMBER`. Bir örnek için bkz: [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member).  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi ile başlayan `BEGIN_MSG_MAP`. Ardından sonraki alternatif ileti Eşlemleriyle bildirebilir `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemesi sonunu işaretler. Her ileti eşlemesi tek bir örneği olmalıdır `BEGIN_MSG_MAP` ve `END_MSG_MAP`.  
  
 İleti eşlemeleri ATL içinde kullanma hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="chain_msg_map"></a>CHAIN_MSG_MAP  
 Bir giriş ileti eşlemesinde tanımlar.  
  
```
CHAIN_MSG_MAP(theChainClass)
```  
  
### <a name="parameters"></a>Parametreler  
 `theChainClass`  
 [in] İleti eşleme içeren temel sınıfın adı.  
  
### <a name="remarks"></a>Açıklamalar  
 `CHAIN_MSG_MAP`taban sınıf varsayılan ileti eşlemesi iletileri yönlendiren (ile bildirilen [BEGIN_MSG_MAP](#begin_msg_map)). Taban sınıf alternatif ileti eşlemesi iletilerini yönlendirmek için (ile bildirilen [ALT_MSG_MAP](#alt_msg_map)), kullanın [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt).  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi ile başlayan `BEGIN_MSG_MAP`. Ardından sonraki alternatif ileti Eşlemleriyle bildirebilir `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemesi sonunu işaretler. Her ileti eşlemesi tek bir örneği olmalıdır `BEGIN_MSG_MAP` ve `END_MSG_MAP`.  
  
 İleti eşlemeleri ATL içinde kullanma hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]  
  
 Bu örnekte aşağıdaki gösterilmektedir:  
  
-   Pencere yordamı kullanıyorsanız `CMyClass`ait varsayılan ileti eşlemesi ve `OnPaint` olmayan bir ileti, ileti yönlendirilir tanıtıcı mu `CMyBaseClass`'s işlemek için varsayılan ileti eşlemesi.  
  
-   Pencere yordamı ilk alternatif ileti eşlemesinde kullanıp kullanmadığını `CMyClass`, tüm iletileri yönlendirilir `CMyBaseClass`ait varsayılan ileti eşlemesi.  
  
-   Pencere yordamı kullanıyorsanız `CMyClass`kullanıcının ikinci bir alternatif ileti eşleme ve `OnChar` olmayan bir ileti, ileti belirtilen diğer ileti eşlemesinde yönlendirilir tanıtıcı mu `CMyBaseClass`. `CMyBaseClass`Bu ileti eşlemesi ile bildirilen `ALT_MSG_MAP(1)`.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="chain_msg_map_dynamic"></a>CHAIN_MSG_MAP_DYNAMIC  
 Bir giriş ileti eşlemesinde tanımlar.  
  
```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```  
  
### <a name="parameters"></a>Parametreler  
 *dynaChainID*  
 [in] Bir nesnenin ileti eşlemesi için benzersiz tanımlayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 `CHAIN_MSG_MAP_DYNAMIC`Çalışma zamanında, varsayılan ileti eşlemesi için başka bir nesneyi iletileri yönlendirir. Nesne ve kendi ileti eşlemesi ile ilişkili *dynaChainID*, aracılığıyla tanımlayan [CDynamicChain::SetChainEntry](cdynamicchain-class.md#setchainentry). Sınıfından türetilmelidir `CDynamicChain` kullanmak için `CHAIN_MSG_MAP_DYNAMIC`. Bir örnek için bkz: [CDynamicChain](../../atl/reference/cdynamicchain-class.md) genel bakış.  

  
> [!NOTE]
>  Her zaman bir ileti eşlemesi ile başlayan [BEGIN_MSG_MAP](#begin_msg_map). Ardından sonraki alternatif ileti Eşlemleriyle bildirebilir `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemesi sonunu işaretler. Her ileti eşlemesi tek bir örneği olmalıdır `BEGIN_MSG_MAP` ve `END_MSG_MAP`.  
  
 İleti eşlemeleri ATL içinde kullanma hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="chain_msg_map_member"></a>CHAIN_MSG_MAP_MEMBER  
 Bir giriş ileti eşlemesinde tanımlar.  
  
```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```  
  
### <a name="parameters"></a>Parametreler  
 `theChainMember`  
 [in] İleti eşleme içeren veri üyesi adı.  
  
### <a name="remarks"></a>Açıklamalar  
 `CHAIN_MSG_MAP_MEMBER`veri üye varsayılan ileti eşlemesi iletileri yönlendiren (ile bildirilen [BEGIN_MSG_MAP](#begin_msg_map)). Veri üye alternatif ileti eşlemesi iletilerini yönlendirmek için (ile bildirilen [ALT_MSG_MAP](#alt_msg_map)), kullanın [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member).  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi ile başlayan `BEGIN_MSG_MAP`. Ardından sonraki alternatif ileti Eşlemleriyle bildirebilir `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemesi sonunu işaretler. Her ileti eşlemesi tek bir örneği olmalıdır `BEGIN_MSG_MAP` ve `END_MSG_MAP`.  
  
 İleti eşlemeleri ATL içinde kullanma hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]  
  
 Bu örnekte aşağıdaki gösterilmektedir:  
  
-   Pencere yordamı kullanıyorsanız `CMyClass`ait varsayılan ileti eşlemesi ve `OnPaint` olmayan bir ileti, ileti yönlendirilir tanıtıcı mu `m_obj`'s işlemek için varsayılan ileti eşlemesi.  
  
-   Pencere yordamı ilk alternatif ileti eşlemesinde kullanıp kullanmadığını `CMyClass`, tüm iletileri yönlendirilir `m_obj`ait varsayılan ileti eşlemesi.  
  
-   Pencere yordamı kullanıyorsanız `CMyClass`kullanıcının ikinci bir alternatif ileti eşleme ve `OnChar` olmayan bir ileti, ileti için belirtilen diğer ileti haritasını yönlendirilmiş tanıtıcı mu `m_obj`. Sınıf `CMyContainedClass` bu ileti eşlemesi ile bildirilen `ALT_MSG_MAP(1)`.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="command_code_handler"></a>COMMAND_CODE_HANDLER  
 Benzer şekilde [COMMAND_HANDLER](#command_handler), ancak eşleyen bir [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) ileti tabanlı yalnızca bildirim kodu.  
  
```
COMMAND_CODE_HANDLER(code, func)
```  
  
### <a name="parameters"></a>Parametreler  
 `code`  
 [in] Bildirim kodu.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="command_handler"></a>COMMAND_HANDLER  
 Bir giriş ileti eşlemesinde tanımlar.  
  
```
COMMAND_HANDLER(id, code, func)
```    
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Menü öğesi, denetim veya Hızlandırıcı tanımlayıcısı.  
  
 `code`  
 [in] Bildirim kodu.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 `COMMAND_HANDLER`eşleşen bir [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) bildirim kodu ve denetim tanımlayıcısı göre belirtilen işleyici işlevi ileti. Örneğin:  
  
 [!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]  
  
 Belirtilen herhangi bir işlev bir `COMMAND_HANDLER` makrosu gibi tanımlanmalıdır:  
  
 `LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`  
  
 İleti eşleme kümeleri `bHandled` için **TRUE** önce `CommandHandler` olarak adlandırılır. Varsa `CommandHandler` tam ileti işlemiyor ayarlamanız gerekir `bHandled` için **FALSE** ileti gereken başka bir işleme belirtmek için.  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi ile başlayan [BEGIN_MSG_MAP](#begin_msg_map). Ardından sonraki alternatif ileti Eşlemleriyle bildirebilir [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemesi sonunu işaretler. Her ileti eşlemesi tek bir örneği olmalıdır `BEGIN_MSG_MAP` ve `END_MSG_MAP`.  
  
 Ek olarak `COMMAND_HANDLER`, kullanabileceğiniz [MESSAGE_HANDLER](#message_handler) eşlemek için bir **WM_COMMAND** İleti tanımlayıcısı veya kod dikkate almaksızın. Bu durumda, `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` tüm doğrudan **WM_COMMAND** iletileri için `OnHandlerFunction`.  
  
 İleti eşlemeleri ATL içinde kullanma hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="command_id_handler"></a>COMMAND_ID_HANDLER  
 Benzer şekilde [COMMAND_HANDLER](#command_handler), ancak eşleyen bir [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) ileti tabanlı menü öğesi, denetim veya Hızlandırıcı tanımlayıcının yalnızca.  
  
```
COMMAND_ID_HANDLER(id, func)
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Menü öğesi, denetim veya ileti gönderme Hızlandırıcı tanımlayıcısı.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="command_range_code_handler"></a>COMMAND_RANGE_CODE_HANDLER  
 Benzer şekilde [COMMAND_RANGE_HANDLER](#command_range_handler), ancak eşlemeleri [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) tek işleyici işlevi denetimleri aralığından belirli bildirim koduyla iletileri.  
  
```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```    
  
### <a name="parameters"></a>Parametreler  
 `idFirst`  
 [in] Denetim tanımlayıcıların bitişik aralığının başlangıcını işaretler.  
  
 `idLast`  
 [in] Denetim tanımlayıcıları bitişik bir dizi sonunu işaretler.  
  
 `code`  
 [in] Bildirim kodu.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu aralık menü öğesi, denetim ya da bu iletiyi göndermek Hızlandırıcı tanımlayıcının temel alır.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="command_range_handler"></a>COMMAND_RANGE_HANDLER  
 Benzer şekilde [COMMAND_HANDLER](#command_handler), ancak eşlemeleri [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) tek işleyici işlevi denetimleri aralığından iletileri.  
  
```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```    
  
### <a name="parameters"></a>Parametreler  
 `idFirst`  
 [in] Denetim tanımlayıcıların bitişik aralığının başlangıcını işaretler.  
  
 `idLast`  
 [in] Denetim tanımlayıcıları bitişik bir dizi sonunu işaretler.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu aralık menü öğesi, denetim ya da bu iletiyi göndermek Hızlandırıcı tanımlayıcının temel alır.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="declare_empty_msg_map"></a>DECLARE_EMPTY_MSG_MAP  
 Bir boş ileti eşlemesi bildirir.  
  
```
DECLARE_EMPTY_MSG_MAP()
```  
  
### <a name="remarks"></a>Açıklamalar  
 `DECLARE_EMPTY_MSG_MAP`Makrolar çağıran kolaylık makro [BEGIN_MSG_MAP](#begin_msg_map) ve [END_MSG_MAP](#end_msg_map) boş ileti eşlemesi oluşturmak için:  
  
 [!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]  
  
##  <a name="default_reflection_handler"></a>DEFAULT_REFLECTION_HANDLER  
 Yansımış iletileri alacak alt pencere (Denetim) için bir varsayılan işleyici sağlar; işleyicinin düzgün işlenmemiş iletileri geçer `DefWindowProc`.  
  
```
DEFAULT_REFLECTION_HANDLER()
```  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="end_msg_map"></a>END_MSG_MAP  
 İleti eşlemesi sonunu işaretler.  
  
```
END_MSG_MAP()
```  
  
### <a name="remarks"></a>Açıklamalar  
 Her zaman kullanmak [BEGIN_MSG_MAP](#begin_msg_map) makrosu ileti eşlemesi başlangıcını işaretler. Kullanım [ALT_MSG_MAP](#alt_msg_map) sonraki alternatif ileti eşlemeleri bildirmek için.  
  
 Her zaman tek bir örneği yoktur `BEGIN_MSG_MAP` ve `END_MSG_MAP`.  
  
 İleti eşlemeleri ATL içinde kullanma hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek varsayılan ileti eşlemesi ve her bir işleyici işlevi içeren bir alternatif ileti eşlemesi gösterir:  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 Sonraki örnekte iki alternatif ileti eşlemeleri gösterir. Varsayılan ileti eşlemesi boştur.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="forward_notifications"></a>FORWARD_NOTIFICATIONS  
 Üst pencere bildirim iletileri iletir.  
  
```
FORWARD_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu ileti eşlemesi bir parçası olarak belirtin.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="message_handler"></a>MESSAGE_HANDLER  
 Bir giriş ileti eşlemesinde tanımlar.  
  
```
MESSAGE_HANDLER( msg, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `msg`  
 [in] Windows ileti.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 `MESSAGE_HANDLER`Windows ileti belirtilen işleyici işlevi eşler.  
  
 Belirtilen herhangi bir işlev bir `MESSAGE_HANDLER` makrosu gibi tanımlanmalıdır:  
  
 `LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`  
  
 İleti eşleme kümeleri `bHandled` için **TRUE** önce `MessageHandler` olarak adlandırılır. Varsa `MessageHandler` tam ileti işlemiyor ayarlamanız gerekir `bHandled` için **FALSE** ileti gereken başka bir işleme belirtmek için.  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi ile başlayan [BEGIN_MSG_MAP](#begin_msg_map). Ardından sonraki alternatif ileti Eşlemleriyle bildirebilir [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemesi sonunu işaretler. Her ileti eşlemesi tek bir örneği olmalıdır `BEGIN_MSG_MAP` ve `END_MSG_MAP`.  
  
 Ek olarak `MESSAGE_HANDLER`, kullanabileceğiniz [COMMAND_HANDLER](#command_handler) ve [NOTIFY_HANDLER](#notify_handler) eşlemek için [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) ve [wm_notıfy](http://msdn.microsoft.com/library/windows/desktop/bb775583) , sırasıyla iletileri.  
  
 İleti eşlemeleri ATL içinde kullanma hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="message_range_handler"></a>MESSAGE_RANGE_HANDLER  
 Benzer şekilde [MESSAGE_HANDLER](#message_handler), ancak Windows aralığı iletileri bir tek işleyici işlevi eşlemeleri.  
  
```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```  
  
### <a name="parameters"></a>Parametreler  
 *msgFirst*  
 [in] İletilerin bitişik aralığının başlangıcını işaretler.  
  
 *msgLast*  
 [in] İletileri bitişik bir dizi sonunu işaretler.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="notify_code_handler"></a>NOTIFY_CODE_HANDLER  
 Benzer şekilde [NOTIFY_HANDLER](#notify_handler), ancak eşleyen bir [wm_notıfy](http://msdn.microsoft.com/library/windows/desktop/bb775583) ileti tabanlı yalnızca bildirim kodu.  
  
```
NOTIFY_CODE_HANDLER(cd, func)
```  
  
### <a name="parameters"></a>Parametreler  
 `cd`  
 [in] Bildirim kodu.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="notify_handler"></a>NOTIFY_HANDLER  
 Bir giriş ileti eşlemesinde tanımlar.  
  
```
NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] İleti gönderilirken denetim tanımlayıcısı.  
  
 `cd`  
 [in] Bildirim kodu.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 `NOTIFY_HANDLER`eşleşen bir [wm_notıfy](http://msdn.microsoft.com/library/windows/desktop/bb775583) bildirim kodu ve denetim tanımlayıcısı göre belirtilen işleyici işlevi ileti.  
  
 Belirtilen herhangi bir işlev bir `NOTIFY_HANDLER` makrosu gibi tanımlanmalıdır:  
  
 `LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`  
  
 İleti eşleme kümeleri `bHandled` için **TRUE** önce `NotifyHandler` olarak adlandırılır. Varsa `NotifyHandler` tam ileti işlemiyor ayarlamanız gerekir `bHandled` için **FALSE** ileti gereken başka bir işleme belirtmek için.  
  
> [!NOTE]
>  Her zaman bir ileti eşlemesi ile başlayan [BEGIN_MSG_MAP](#begin_msg_map). Ardından sonraki alternatif ileti Eşlemleriyle bildirebilir [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) makrosu ileti eşlemesi sonunu işaretler. Her ileti eşlemesi tek bir örneği olmalıdır `BEGIN_MSG_MAP` ve `END_MSG_MAP`.  
  
 Ek olarak `NOTIFY_HANDLER`, kullanabileceğiniz [MESSAGE_HANDLER](#message_handler) eşlemek için bir **wm_notıfy** İleti tanımlayıcısı veya kod dikkate almaksızın. Bu durumda, `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` tüm doğrudan **wm_notıfy** iletileri için `OnHandlerFunction`.  
  
 İleti eşlemeleri ATL içinde kullanma hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="notify_id_handler"></a>NOTIFY_ID_HANDLER  
 Benzer şekilde [NOTIFY_HANDLER](#notify_handler), ancak eşleyen bir [wm_notıfy](http://msdn.microsoft.com/library/windows/desktop/bb775583) ileti tabanlı yalnızca denetim tanımlayıcısı.  
  
```
NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] İleti gönderilirken denetim tanımlayıcısı.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="notify_range_code_handler"></a>NOTIFY_RANGE_CODE_HANDLER  
 Benzer şekilde [NOTIFY_RANGE_HANDLER](#notify_range_handler), ancak eşlemeleri [wm_notıfy](http://msdn.microsoft.com/library/windows/desktop/bb775583) tek işleyici işlevi denetimleri aralığından belirli bildirim koduyla iletileri.  
  
```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `idFirst`  
 [in] Denetim tanımlayıcıların bitişik aralığının başlangıcını işaretler.  
  
 `idLast`  
 [in] Denetim tanımlayıcıları bitişik bir dizi sonunu işaretler.  
  
 `cd`  
 [in] Bildirim kodu.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu aralık, ileti gönderme denetim tanımlayıcısını temel alır.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="notify_range_handler"></a>NOTIFY_RANGE_HANDLER  
 Benzer şekilde [NOTIFY_HANDLER](#notify_handler), ancak eşlemeleri [wm_notıfy](http://msdn.microsoft.com/library/windows/desktop/bb775583) tek işleyici işlevi denetimleri aralığından iletileri.  
  
```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `idFirst`  
 [in] Denetim tanımlayıcıların bitişik aralığının başlangıcını işaretler.  
  
 `idLast`  
 [in] Denetim tanımlayıcıları bitişik bir dizi sonunu işaretler.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu aralık, ileti gönderme denetim tanımlayıcısını temel alır.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="reflect_notifications"></a>REFLECT_NOTIFICATIONS  
 Bunları gönderilen geri alt pencere (Denetim) için bildirim iletilerini yansıtır.  
  
```
REFLECT_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu üst pencere ileti eşlemesi bir parçası olarak belirtin.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="reflected_command_code_handler"></a>REFLECTED_COMMAND_CODE_HANDLER  
 Benzer şekilde [COMMAND_CODE_HANDLER](#command_code_handler), ancak üst penceresinden yansıtılan komutları eşler.  
  
```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `code`  
 [in] Bildirim kodu.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
   
##  <a name="reflected_command_handler"></a>REFLECTED_COMMAND_HANDLER  
 Benzer şekilde [COMMAND_HANDLER](#command_handler), ancak üst penceresinden yansıtılan komutları eşler.  
  
```
REFLECTED_COMMAND_HANDLER( id, code, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Menü öğesi, denetim veya Hızlandırıcı tanımlayıcısı.  
  
 `code`  
 [in] Bildirim kodu.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_command_id_handler"></a>REFLECTED_COMMAND_ID_HANDLER  
 Benzer şekilde [COMMAND_ID_HANDLER](#command_id_handler), ancak üst penceresinden yansıtılan komutları eşler.  
  
```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Menü öğesi, denetim veya Hızlandırıcı tanımlayıcısı.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_command_range_code_handler"></a>REFLECTED_COMMAND_RANGE_CODE_HANDLER  
 Benzer şekilde [COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler), ancak üst penceresinden yansıtılan komutları eşler.  
  
```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `idFirst`  
 [in] Denetim tanımlayıcıların bitişik aralığının başlangıcını işaretler.  
  
 `idLast`  
 [in] Denetim tanımlayıcıları bitişik bir dizi sonunu işaretler.  
  
 `code`  
 [in] Bildirim kodu.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_command_range_handler"></a>REFLECTED_COMMAND_RANGE_HANDLER  
 Benzer şekilde [COMMAND_RANGE_HANDLER](#command_range_handler), ancak üst penceresinden yansıtılan komutları eşler.  
  
```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `idFirst`  
 [in] Denetim tanımlayıcıların bitişik aralığının başlangıcını işaretler.  
  
 `idLast`  
 [in] Denetim tanımlayıcıları bitişik bir dizi sonunu işaretler.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_notify_code_handler"></a>REFLECTED_NOTIFY_CODE_HANDLER  
 Benzer şekilde [NOTIFY_CODE_HANDLER](#notify_code_handler), ancak üst penceresinden yansıtılan bildirimleri eşler.  
  
```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `cd`  
 [in] Bildirim kodu.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_notify_handler"></a>REFLECTED_NOTIFY_HANDLER  
 Benzer şekilde [NOTIFY_HANDLER](#notify_handler), ancak üst penceresinden yansıtılan bildirimleri eşler.  
  
```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Menü öğesi, denetim veya Hızlandırıcı tanımlayıcısı.  
  
 `cd`  
 [in] Bildirim kodu.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_notify_id_handler"></a>REFLECTED_NOTIFY_ID_HANDLER  
 Benzer şekilde [NOTIFY_ID_HANDLER](#notify_id_handler), ancak üst penceresinden yansıtılan bildirimleri eşler.  
  
```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Menü öğesi, denetim veya Hızlandırıcı tanımlayıcısı.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  

##  <a name="reflected_notify_range_code_handler"></a>REFLECTED_NOTIFY_RANGE_CODE_HANDLER  
 Benzer şekilde [NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler), ancak üst penceresinden yansıtılan bildirimleri eşler.  
  
```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```    
  
### <a name="parameters"></a>Parametreler  
 `idFirst`  
 [in] Denetim tanımlayıcıların bitişik aralığının başlangıcını işaretler.  
  
 `idLast`  
 [in] Denetim tanımlayıcıları bitişik bir dizi sonunu işaretler.  
  
 `cd`  
 [in] Bildirim kodu.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h   
  
##  <a name="reflected_notify_range_handler"></a>REFLECTED_NOTIFY_RANGE_HANDLER  
 Benzer şekilde [NOTIFY_RANGE_HANDLER](#notify_range_handler), ancak üst penceresinden yansıtılan bildirimleri eşler.  
  
```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Parametreler  
 `idFirst`  
 [in] Denetim tanımlayıcıların bitişik aralığının başlangıcını işaretler.  
  
 `idLast`  
 [in] Denetim tanımlayıcıları bitişik bir dizi sonunu işaretler.  
  
 `func`  
 [in] İleti işleyicisi işlevin adı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
