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
ms.openlocfilehash: 663ee462bf03e76ab15cbac05790c89dcaf07dca
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884860"
---
# <a name="cmessagemap-class"></a>CMessageMap sınıfı
Bu sınıf, başka bir nesneye erişimi olacak şekilde bir nesnenin ileti eşlemeleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class ATL_NO_VTABLE CMessageMap
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMessageMap::ProcessWindowMessage](#processwindowmessage)|Bir ileti eşlemede erişen `CMessageMap`-türetilmiş sınıf.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMessageMap` başka bir nesne tarafından erişilecek bir nesnenin ileti sağlayan soyut bir temel sınıf eşler olur. Kendi ileti eşlemeleri kullanıma sunmak bir nesne için sırayla sınıfıyla öğesinden türetilmelidir `CMessageMap`.  
  
 ATL kullanan `CMessageMap` yer alan Destek windows ve dinamik ileti eşlemesi zincirleme. Örneğin, bir sınıf içeren bir [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) nesne öğesinden türetilmelidir `CMessageMap`. Aşağıdaki kod alınır [SUBEDIT](../../visual-cpp-samples.md) örnek. Aracılığıyla [CComControl](../../atl/reference/ccomcontrol-class.md), `CAtlEdit` otomatik olarak sınıf türetilir `CMessageMap`.  
  
 [!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]  
  
 Çünkü kapsanan pencerenin `m_EditCtrl`, ileti eşlemesi kapsayan sınıfta kullanacağı `CAtlEdit` türetildiği `CMessageMap`.  
  
 İleti eşlemeleri hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md) makaledeki "ATL pencere sınıflarına."  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="processwindowmessage"></a>  CMessageMap::ProcessWindowMessage  
 İleti eşlemesi tarafından tanımlanan erişen *dwMsgMapID* içinde bir `CMessageMap`-türetilmiş sınıf.  
  
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
 *hWnd*  
 [in] İletiyi alan pencereye tanıtıcısı.  
  
 *uMsg*  
 [in] Pencereye gönderilen ileti.  
  
 *wParam*  
 [in] İletiye özgü ek bilgiler.  
  
 *lParam*  
 [in] İletiye özgü ek bilgiler.  
  
 *lResult*  
 [out] İleti işleme sonucu.  
  
 *dwMsgMapID*  
 [in] İleti işleme ileti eşlemesi tanımlayıcısı. Varsayılan ileti eşlemesi ile bildirilmiş [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), 0 ile tanımlanır. Bir diğer ileti eşlemesi ile bildirilmiş [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), tarafından tanımlanan `msgMapID`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti tam olarak işlenen TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Pencere yordamı tarafından adlandırılan bir [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) nesnesi veya bir nesne, dinamik olarak zincirleme için ileti eşlemesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicChain sınıfı](../../atl/reference/cdynamicchain-class.md)   
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
