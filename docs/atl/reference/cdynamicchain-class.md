---
title: CDynamicChain Sınıfı
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
ms.openlocfilehash: 4a72b3b4308ed83dfdc4a2895a04d1fe9a177ce5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327027"
---
# <a name="cdynamicchain-class"></a>CDynamicChain Sınıfı

Bu sınıf, ileti haritalarının dinamik zincirlemesini destekleyen yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CDynamicChain
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CdynamicChain::CdynamicChain](#cdynamicchain)|Oluşturucu.|
|[CdynamicChain::~CdynamicChain](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CdynamicChain::CallChain](#callchain)|Windows iletisini başka bir nesnenin ileti haritasına yönlendirir.|
|[CdynamicChain::RemoveChainEntry](#removechainentry)|Koleksiyondan bir ileti eşlemi girişini kaldırır.|
|[CdynamicChain::SetChainEntry](#setchainentry)|Koleksiyona ileti eşlemi girişi ekler veya varolan bir girişi değiştirir.|

## <a name="remarks"></a>Açıklamalar

`CDynamicChain`bir Windows iletisinin çalışma zamanında başka bir nesnenin ileti haritasına yönlendirilmesine olanak tanıyan ileti eşlemleri koleksiyonunu yönetir.

İleti eşlemlerinin dinamik zincirleme desteği eklemek için aşağıdakileri yapın:

- `CDynamicChain`Sınıfınızı. İleti eşlemi'nde, CHAIN_MSG_MAP_DYNAMIC [makroyu](message-map-macros-atl.md#chain_msg_map_dynamic) başka bir nesnenin varsayılan ileti haritasına zincirlemek için belirtin.

- [CMessageMap'ten](../../atl/reference/cmessagemap-class.md)zincirlemek istediğiniz her sınıfı türetin. `CMessageMap`bir nesnenin ileti eşlemlerini diğer nesnelere maruz bırakmasını sağlar.

- Hangi `CDynamicChain::SetChainEntry` nesneye ve hangi ileti haritasına zincirlemek istediğinizi belirlemek için arayın.

Örneğin, sınıfınızın aşağıdaki gibi tanımlandığını varsayalım:

[!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]

İstemci `CMyWindow::SetChainEntry`daha sonra çağırır:

[!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]

nerede `chainedObj` zincirlenmiş nesne dir ve bir sınıf `CMessageMap`örneğitilmiştir. Şimdi, `myCtl` tarafından işlenmemiş bir ileti `OnPaint` `OnSetFocus`alıyorsa veya pencere yordamı iletiyi `chainedObj`'varsayılan ileti eşlenine yönlendirir.

İleti eşlem zinciri hakkında daha fazla bilgi için "ATL Pencere Sınıfları" makalesinde [İleti Haritaları'na](../../atl/message-maps-atl.md) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="cdynamicchaincallchain"></a><a name="callchain"></a>CdynamicChain::CallChain

Windows iletisini başka bir nesnenin ileti haritasına yönlendirir.

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
[içinde] Zincirlenmiş nesne ve ileti haritasıyla ilişkili benzersiz tanımlayıcı.

*Hwnd*<br/>
[içinde] İletiyi alan pencerenin tutamacı.

*uMsg*<br/>
[içinde] Pencereye gönderilen ileti.

*Wparam*<br/>
[içinde] İletiye özgü ek bilgiler.

*Lparam*<br/>
[içinde] İletiye özgü ek bilgiler.

*lResult*<br/>
[çıkış] İleti işleme sonucu.

### <a name="return-value"></a>Dönüş Değeri

İleti tam olarak işlenirse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Pencere yordamı nın `CallChain`çağrıda alabilmesi için, ileti haritanızda [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) makroyu belirtmeniz gerekir. Örneğin, [CDynamicChain](../../atl/reference/cdynamicchain-class.md) genel görünümüne bakın.

`CallChain`*dwChainID* değerini bir nesne ve ileti eşlemi ile ilişkilendirmek için [SetChainEntry'e](#setchainentry) önceki bir çağrı gerektirir.

## <a name="cdynamicchaincdynamicchain"></a><a name="cdynamicchain"></a>CdynamicChain::CdynamicChain

Oluşturucu.

```
CDynamicChain();
```

## <a name="cdynamicchaincdynamicchain"></a><a name="dtor"></a>CdynamicChain::~CdynamicChain

Yıkıcı.

```
~CDynamicChain();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest sağlar.

## <a name="cdynamicchainremovechainentry"></a><a name="removechainentry"></a>CdynamicChain::RemoveChainEntry

Belirtilen ileti eşlemi koleksiyondan kaldırır.

```
BOOL RemoveChainEntry(DWORD dwChainID);
```

### <a name="parameters"></a>Parametreler

*dwChainID*<br/>
[içinde] Zincirlenmiş nesne ve ileti haritasıyla ilişkili benzersiz tanımlayıcı. Bu değeri başlangıçta [SetChainEntry'e](#setchainentry)yapılan bir çağrı yla tanımlarsınız.

### <a name="return-value"></a>Dönüş Değeri

İleti eşlemi koleksiyondan başarıyla kaldırılırsa DOĞRU. Aksi takdirde, YANLIŞ.

## <a name="cdynamicchainsetchainentry"></a><a name="setchainentry"></a>CdynamicChain::SetChainEntry

Belirtilen ileti eşlemi koleksiyona ekler.

```
BOOL SetChainEntry(
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```

### <a name="parameters"></a>Parametreler

*dwChainID*<br/>
[içinde] Zincirlenmiş nesne ve ileti haritasıyla ilişkili benzersiz tanımlayıcı.

*Pobject*<br/>
[içinde] İleti eşlesini bildiren zincirlenmiş nesneye işaretçi. Bu nesne [CMessageMap](../../atl/reference/cmessagemap-class.md)türetilmelidir.

*dwMsgMapID*<br/>
[içinde] Zincirlenmiş nesnedeki ileti haritasının tanımlayıcısı. Varsayılan değer, [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile bildirilen varsayılan ileti eşleğini tanımlayan 0'dır. [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)ile bildirilen alternatif bir ileti `msgMapID`haritası belirtmek için , geç .

### <a name="return-value"></a>Dönüş Değeri

İleti eşlemi koleksiyona başarıyla eklenirse DOĞRU. Aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

*DwChainID* değeri koleksiyonda zaten varsa, ilişkili nesne ve ileti eşlemi sırasıyla *pObject* ve *dwMsgMapID*ile değiştirilir. Aksi takdirde, yeni bir giriş eklenir.

## <a name="see-also"></a>Ayrıca bkz.

[CWindowImpl Sınıfı](../../atl/reference/cwindowimpl-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
