---
title: "CDynamicChain sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
dev_langs: C++
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e66984fc7a7be45ea80dc894fcf0d11cc8febd45
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicchain-class"></a>CDynamicChain sınıfı
Bu sınıf ileti eşlemeleri dinamik zincirleme destekleyen yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CDynamicChain
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDynamicChain::CDynamicChain](#cdynamicchain)|Oluşturucu.|  
|[CDynamicChain:: ~ CDynamicChain](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDynamicChain::CallChain](#callchain)|Windows ileti başka bir nesnenin ileti eşlemesi için yönlendirir.|  
|[CDynamicChain::RemoveChainEntry](#removechainentry)|İleti eşleme girişi koleksiyondan kaldırır.|  
|[CDynamicChain::SetChainEntry](#setchainentry)|İleti eşleme girişi koleksiyona ekler veya varolan bir girişi değiştirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDynamicChain`ileti eşlemeleri, başka bir nesnenin ileti eşlemesi için çalışma zamanında yönlendirilecek Windows ileti etkinleştirme koleksiyonunu yönetir.  
  
 İleti eşlemeleri dinamik zincirleme için destek eklemek için aşağıdakileri yapın:  
  
-   Sınıfından türetilen `CDynamicChain`. İleti eşlemesinde belirtin [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) başka bir nesnenin varsayılan ileti eşlemesi zinciri makrosuna.  
  
-   Gelen zincir istediğiniz her bir sınıf türetin [CMessageMap](../../atl/reference/cmessagemap-class.md). `CMessageMap`kendi ileti eşlemeleri diğer nesnelere kullanıma sunmak bir nesne sağlar.  
  
-   Çağrı `CDynamicChain::SetChainEntry` zinciri nesne ve ileti eşlemek istediğiniz tanımlamak için.  
  
 Örneğin, sınıfınıza aşağıdaki gibi tanımlanır varsayın:  
  
 [!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]  
  
 İstemci ardından çağırır `CMyWindow::SetChainEntry`:  
  
 [!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]  
  
 Burada `chainedObj` zincirleme nesnesi ve türetilmiş bir sınıf örneği `CMessageMap`. Şimdi ise `myCtl` tarafından işlenmemiş bir ileti alır `OnPaint` veya `OnSetFocus`, pencere yordamı iletiye yönlendirir `chainedObj`ait varsayılan ileti eşlemesi.  
  
 İleti eşleme zincir hakkında daha fazla bilgi için bkz: [ileti eşlemeleri](../../atl/message-maps-atl.md) makalesinde "ATL pencere sınıfları."  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="callchain"></a>CDynamicChain::CallChain  
 Windows ileti başka bir nesnenin ileti eşlemesi için yönlendirir.  
  
```
BOOL CallChain(  
    DWORD dwChainID,
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwChainID`  
 [in] Zincirleme nesne ve kendi ileti eşlemesi ile ilişkili benzersiz tanımlayıcısı.  
  
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
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** ileti, tam olarak işlenen; Aksi takdirde **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Pencere yordamı çağırma için `CallChain`, belirtmeniz gerekir [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) makro ileti eşlemesi içinde. Bir örnek için bkz: [CDynamicChain](../../atl/reference/cdynamicchain-class.md) genel bakış.  
  
 `CallChain`Önceki çağrısı gerektirir [SetChainEntry](#setchainentry) ilişkilendirilecek `dwChainID` bir nesne ve kendi ileti eşlemesi ile değer.  
  
##  <a name="cdynamicchain"></a>CDynamicChain::CDynamicChain  
 Oluşturucu.  
  
```
CDynamicChain();
```  
  
##  <a name="dtor"></a>CDynamicChain:: ~ CDynamicChain  
 Yok Edicisi.  
  
```
~CDynamicChain();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="removechainentry"></a>CDynamicChain::RemoveChainEntry  
 Belirtilen ileti eşlemesi koleksiyondan kaldırır.  
  
```
BOOL RemoveChainEntry(DWORD dwChainID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwChainID`  
 [in] Zincirleme nesne ve kendi ileti eşlemesi ile ilişkili benzersiz tanımlayıcısı. İlk olarak bu değer için bir çağrı aracılığıyla tanımladığınız [SetChainEntry](#setchainentry).  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** ileti eşlemesi başarıyla koleksiyondan kaldırılırsa. Aksi takdirde, **FALSE**.  
  
##  <a name="setchainentry"></a>CDynamicChain::SetChainEntry  
 Belirtilen ileti eşlemesi koleksiyona ekler.  
  
```
BOOL SetChainEntry(  
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwChainID`  
 [in] Zincirleme nesne ve kendi ileti eşlemesi ile ilişkili benzersiz tanımlayıcısı.  
  
 `pObject`  
 [in] İleti eşlemesi bildirme zincirleme nesnesine bir işaretçi. Bu nesne öğesinden türetilmelidir [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] İleti eşlemesi zincirleme nesnesindeki tanımlayıcısı. Varsayılan değer ile bildirilen varsayılan ileti eşlemesi tanımlayan 0'dır [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Bir alternatif ileti eşlemesi belirtmek için bildirilen ile [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), geçirmek `msgMapID`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** ileti eşlemesi koleksiyonuna başarıyla eklenirse. Aksi takdirde, **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `dwChainID` değeri koleksiyonda zaten var, ilişkili nesne ve ileti eşlemesi değiştirilir `pObject` ve `dwMsgMapID`sırasıyla. Aksi takdirde, yeni bir giriş eklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWindowImpl sınıfı](../../atl/reference/cwindowimpl-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
