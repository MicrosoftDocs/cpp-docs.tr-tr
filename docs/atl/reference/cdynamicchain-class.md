---
title: CDynamicChain sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
ms.openlocfilehash: 57bbd009bbcbe0ea3352ab27c5d6fbb630b7d050
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668019"
---
# <a name="cdynamicchain-class"></a>CDynamicChain sınıfı

Bu sınıf ileti eşlemeleri dinamik zincirleme destekleyen yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CDynamicChain
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDynamicChain::CDynamicChain](#cdynamicchain)|Oluşturucu.|
|[CDynamicChain:: ~ CDynamicChain](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDynamicChain::CallChain](#callchain)|Windows ileti başka bir nesnenin ileti eşlemesi yönlendirir.|
|[CDynamicChain::RemoveChainEntry](#removechainentry)|İleti eşleme girişi koleksiyondan kaldırır.|
|[CDynamicChain::SetChainEntry](#setchainentry)|Koleksiyona bir ileti eşleme girişi ekler veya varolan bir girişi değiştirir.|

## <a name="remarks"></a>Açıklamalar

`CDynamicChain` ileti eşlemeleri, bir Windows ileti için ileti eşlemesi başka bir nesnenin çalışma zamanında yönlendirilebilir etkinleştirme koleksiyonunu yönetir.

Dinamik zincirleme ileti haritaları için destek eklemek için aşağıdakileri yapın:

- Öğesinden, bir sınıf türetin `CDynamicChain`. İleti eşlemede belirtin [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) başka bir nesnenin varsayılan ileti eşlemesi zincirdeki makrosu.

- Gelen zincir şeklinde istediğiniz her bir sınıf türetin [CMessageMap](../../atl/reference/cmessagemap-class.md). `CMessageMap` diğer nesnelere kendi ileti eşlemeleri kullanıma sunmak bir nesne sağlar.

- Çağrı `CDynamicChain::SetChainEntry` zinciri nesne ve ileti eşlemek istediğiniz tanımlamak için.

Örneğin, sınıfınıza şu şekilde tanımlanır varsayalım:

[!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]

Ardından istemci çağrıları `CMyWindow::SetChainEntry`:

[!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]

Burada `chainedObj` zincirleme nesnesi ve bir türetilen bir sınıf örneğini `CMessageMap`. Şimdi ise `myCtl` tarafından işlenmemiş bir ileti alır `OnPaint` veya `OnSetFocus`, pencere yordamını iletiye yönlendirir `chainedObj`ait varsayılan ileti eşlemesi.

İleti eşleme zincirleme hakkında daha fazla bilgi için bkz. [ileti eşlemeleri](../../atl/message-maps-atl.md) makaledeki "ATL pencere sınıflarına."

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

##  <a name="callchain"></a>  CDynamicChain::CallChain

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

*dwChainID*<br/>
[in] Zincirleme nesne ve onun ileti eşlemesi ile ilişkilendirilmiş benzersiz tanımlayıcısı.

*hWnd*<br/>
[in] İletiyi alan pencereye tanıtıcısı.

*uMsg*<br/>
[in] Pencereye gönderilen ileti.

*wParam*<br/>
[in] İletiye özgü ek bilgiler.

*lParam*<br/>
[in] İletiye özgü ek bilgiler.

*lResult*<br/>
[out] İleti işleme sonucu.

### <a name="return-value"></a>Dönüş Değeri

İleti tam olarak işlendiği TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Pencere yordamı çağırmak için `CallChain`, belirtmelisiniz [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) makro, ileti eşlemesi. Bir örnek için bkz. [CDynamicChain](../../atl/reference/cdynamicchain-class.md) genel bakış.

`CallChain` önceki bir çağrı gerektirir [SetChainEntry](#setchainentry) ilişkilendirilecek *dwChainID* değeri bir nesne ve onun ileti eşlemesi.

##  <a name="cdynamicchain"></a>  CDynamicChain::CDynamicChain

Oluşturucu.

```
CDynamicChain();
```

##  <a name="dtor"></a>  CDynamicChain:: ~ CDynamicChain

Yıkıcı.

```
~CDynamicChain();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

##  <a name="removechainentry"></a>  CDynamicChain::RemoveChainEntry

Belirtilen ileti eşlemesi koleksiyondan kaldırır.

```
BOOL RemoveChainEntry(DWORD dwChainID);
```

### <a name="parameters"></a>Parametreler

*dwChainID*<br/>
[in] Zincirleme nesne ve onun ileti eşlemesi ile ilişkilendirilmiş benzersiz tanımlayıcısı. İlk olarak bu değer yapılan bir çağrıyla tanımladığınız [SetChainEntry](#setchainentry).

### <a name="return-value"></a>Dönüş Değeri

İleti eşlemesi başarıyla koleksiyondan kaldırılırsa TRUE. Aksi takdirde FALSE.

##  <a name="setchainentry"></a>  CDynamicChain::SetChainEntry

Belirtilen ileti eşlemesi koleksiyona ekler.

```
BOOL SetChainEntry(
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```

### <a name="parameters"></a>Parametreler

*dwChainID*<br/>
[in] Zincirleme nesne ve onun ileti eşlemesi ile ilişkilendirilmiş benzersiz tanımlayıcısı.

*pObject*<br/>
[in] İleti eşlemesi bildirme zincirleme nesnesine bir işaretçi. Bu nesne öğesinden türetilmelidir [CMessageMap](../../atl/reference/cmessagemap-class.md).

*dwMsgMapID*<br/>
[in] İleti eşlemede zincirleme nesne tanımlayıcısı. Varsayılan değer ile bildirilen varsayılan ileti eşlemesi tanımlayan 0 ' dır [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Bir diğer ileti eşlemesi belirtmek için bildirilen [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), geçmesi `msgMapID`.

### <a name="return-value"></a>Dönüş Değeri

İleti eşlemesi koleksiyona başarıyla eklenirse TRUE. Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Varsa *dwChainID* değeri zaten koleksiyonda var., ileti eşlemesi ve ilişkili nesne değiştirilir *pObject* ve *dwMsgMapID*sırasıyla. Aksi takdirde, yeni bir giriş eklenir.

## <a name="see-also"></a>Ayrıca Bkz.

[CWindowImpl Sınıfı](../../atl/reference/cwindowimpl-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
