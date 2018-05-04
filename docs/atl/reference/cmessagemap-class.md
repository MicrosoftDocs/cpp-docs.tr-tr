---
title: CMessageMap sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CMessageMap
- ATLWIN/ATL::CMessageMap
- ATLWIN/ATL::CMessageMap::ProcessWindowMessage
dev_langs:
- C++
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 187d9964da0929516207a67b0e3a769649fc375b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="cmessagemap-class"></a>CMessageMap sınıfı
Bu sınıf, başka bir nesne tarafından erişimi olacak şekilde bir nesnenin ileti eşlemeleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class ATL_NO_VTABLE CMessageMap
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMessageMap::ProcessWindowMessage](#processwindowmessage)|Erişen bir ileti eşlemesi `CMessageMap`-türetilmiş sınıf.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMessageMap` başka bir nesne tarafından erişilecek bir nesnenin ileti veren Özet temel sınıf eşlemeleri olur. İleti eşlemeleri kullanıma sunmak bir nesne için sırayla sınıfındaki öğesinden türetilmelidir `CMessageMap`.  
  
 ATL kullanan `CMessageMap` yer alan Destek windows ve dinamik ileti eşlemesi zincirleme. Örneğin, tüm sınıfı içeren bir [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) nesne öğesinden türetilmelidir `CMessageMap`. Aşağıdaki kod alınırlar [SUBEDIT](../../visual-cpp-samples.md) örnek. Aracılığıyla [CComControl](../../atl/reference/ccomcontrol-class.md), `CAtlEdit` sınıfı otomatik olarak türetilen `CMessageMap`.  
  
 [!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]  
  
 Çünkü kapsanan penceresi `m_EditCtrl`, ileti eşlemesi içeren sınıfında kullanacağı `CAtlEdit` türetilen `CMessageMap`.  
  
 İleti eşlemeleri hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md) makalesinde "ATL pencere sınıfları."  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="processwindowmessage"></a>  CMessageMap::ProcessWindowMessage  
 Tarafından tanımlanan ileti eşlemesi erişen `dwMsgMapID` içinde bir `CMessageMap`-türetilmiş sınıf.  
  
```
virtual BOOL ProcessWindowMessage(  
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult,
    DWORD dwMsgMapID) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 [in] İletiyi alan penceresine işleci.  
  
 `uMsg`  
 [in] Pencereyi gönderilen ileti.  
  
 `wParam`  
 [in] Ek ileti özgü bilgiler.  
  
 `lParam`  
 [in] Ek ileti özgü bilgiler.  
  
 `lResult`  
 [out] İleti işleme sonucu.  
  
 `dwMsgMapID`  
 [in] İleti işleme ileti eşlemesi tanımlayıcısı. Varsayılan ileti eşlemesi bildirilen ile [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), 0 ile tanımlanır. Bir alternatif ileti eşlemesi bildirilen ile [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), tarafından tanımlanan `msgMapID`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** ileti, tam olarak işlenmemişse **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Pencere yordam tarafından çağrılan bir [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) nesnesi veya bir nesne, dinamik olarak zincirleme için ileti eşlemesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicChain sınıfı](../../atl/reference/cdynamicchain-class.md)   
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
