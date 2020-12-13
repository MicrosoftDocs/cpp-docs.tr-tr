---
description: 'Daha fazla bilgi edinin: Cdynamiczincirle sınıfı'
title: Cdynamiczincirine sınıfı
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
ms.openlocfilehash: 5ada99b519900150afa2143fb1527245797fed98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141823"
---
# <a name="cdynamicchain-class"></a>Cdynamiczincirine sınıfı

Bu sınıf, İleti eşlemelerinin dinamik zincirlemesini destekleyen yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CDynamicChain
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cdynamiczincirine:: Cdynamiczinciri](#cdynamicchain)|Oluşturucu.|
|[Cdynamiczincirine:: ~ Cdynamiczinciri](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cdynamiczincirine:: Callzincirine](#callchain)|Bir Windows iletisini başka bir nesnenin ileti eşlemesine yönlendirir.|
|[Cdynamiczincirine:: RemoveChainEntry](#removechainentry)|Koleksiyondan bir ileti eşleme girişini kaldırır.|
|[Cdynamiczincirine:: SetChainEntry](#setchainentry)|Koleksiyona bir ileti eşleme girişi ekler veya var olan bir girişi değiştirir.|

## <a name="remarks"></a>Açıklamalar

`CDynamicChain` , çalışma zamanında, başka bir nesnenin ileti eşlemesine bir Windows iletisinin yönlendirilmesini sağlayan bir ileti haritaları koleksiyonunu yönetir.

İleti eşlemelerinin dinamik zincirleme desteği eklemek için aşağıdakileri yapın:

- Sınıfınızı ' dan türet `CDynamicChain` . İleti eşlemesinde, başka bir nesnenin varsayılan ileti eşlemesine zincirlenen [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) makrosunu belirtin.

- [CMessageMap](../../atl/reference/cmessagemap-class.md)'ten içine zincir eklemek istediğiniz her sınıfı türet. `CMessageMap` bir nesnenin ileti eşlemelerini diğer nesnelerle kullanıma almasına izin verir.

- `CDynamicChain::SetChainEntry`Hangi nesneye ve hangi ileti eşlemine zincir atamak istediğinizi belirlemek için çağırın.

Örneğin, sınıfınızın aşağıdaki gibi tanımlandığını varsayalım:

[!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]

İstemci daha sonra şunu çağırır `CMyWindow::SetChainEntry` :

[!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]

, `chainedObj` zincirleme nesnesidir ve öğesinden türetilen bir sınıfın örneğidir `CMessageMap` . Şimdi, `myCtl` veya tarafından işlenmeyen bir ileti alırsa `OnPaint` `OnSetFocus` , pencere yordamı iletiyi `chainedObj` varsayılan ileti eşlemesine yönlendirir.

İleti eşleme zinciri hakkında daha fazla bilgi için, "ATL pencere sınıfları" makalesindeki [Ileti haritaları](../../atl/message-maps-atl.md) bölümüne bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="cdynamicchaincallchain"></a><a name="callchain"></a> Cdynamiczincirine:: Callzincirine

Windows iletisini başka bir nesnenin ileti eşlemesine yönlendirir.

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
'ndaki Zincirlenmiş nesne ve ileti eşlemesiyle ilişkili benzersiz tanımlayıcı.

*lendiği*<br/>
'ndaki İletiyi alan pencerenin tutamacı.

*uMsg*<br/>
'ndaki Pencereye gönderilen ileti.

*wParam*<br/>
'ndaki İletiye özgü ek bilgiler.

*lParam*<br/>
'ndaki İletiye özgü ek bilgiler.

*lResult*<br/>
dışı İleti işlemenin sonucu.

### <a name="return-value"></a>Dönüş Değeri

İleti tam olarak işlendiyse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Çağrılacak pencere yordamı için `CallChain` ileti eşlemindeki [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) makrosunu belirtmeniz gerekir. Bir örnek için, [Cdynamiczincirine](../../atl/reference/cdynamicchain-class.md) genel bakış bölümüne bakın.

`CallChain`*dwChainID* değerini bir nesneyle ve ileti eşlemesiyle Ilişkilendirmek Için [SetChainEntry](#setchainentry) öğesine önceki bir çağrı gerektirir.

## <a name="cdynamicchaincdynamicchain"></a><a name="cdynamicchain"></a> Cdynamiczincirine:: Cdynamiczinciri

Oluşturucu.

```
CDynamicChain();
```

## <a name="cdynamicchaincdynamicchain"></a><a name="dtor"></a> Cdynamiczincirine:: ~ Cdynamiczinciri

Yok edicisi.

```
~CDynamicChain();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

## <a name="cdynamicchainremovechainentry"></a><a name="removechainentry"></a> Cdynamiczincirine:: RemoveChainEntry

Belirtilen ileti eşlemesini koleksiyondan kaldırır.

```
BOOL RemoveChainEntry(DWORD dwChainID);
```

### <a name="parameters"></a>Parametreler

*dwChainID*<br/>
'ndaki Zincirlenmiş nesne ve ileti eşlemesiyle ilişkili benzersiz tanımlayıcı. Bu değeri, ilk olarak [SetChainEntry](#setchainentry)çağrısıyla tanımlarsınız.

### <a name="return-value"></a>Dönüş Değeri

İleti eşlemesi koleksiyondan başarıyla kaldırıldıysa TRUE. Aksi takdirde, FALSE.

## <a name="cdynamicchainsetchainentry"></a><a name="setchainentry"></a> Cdynamiczincirine:: SetChainEntry

Belirtilen ileti eşlemesini koleksiyona ekler.

```
BOOL SetChainEntry(
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```

### <a name="parameters"></a>Parametreler

*dwChainID*<br/>
'ndaki Zincirlenmiş nesne ve ileti eşlemesiyle ilişkili benzersiz tanımlayıcı.

*Nesnesini*<br/>
'ndaki İleti eşlemini bildiren zincirleme nesnesine yönelik bir işaretçi. Bu nesne [CMessageMap](../../atl/reference/cmessagemap-class.md)öğesinden türetilmelidir.

*dwMsgMapID*<br/>
'ndaki Zincirleme nesnesindeki ileti eşlemesinin tanımlayıcısı. Varsayılan değer, [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile belirtilen varsayılan ileti haritasını belirleyen 0 ' dır. [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)ile belirtilen alternatif bir ileti eşlemesi belirtmek için pass `msgMapID` .

### <a name="return-value"></a>Dönüş Değeri

İleti eşlemesi koleksiyona başarıyla eklendiyse TRUE. Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

*DwChainID* değeri koleksiyonda zaten mevcutsa, ilişkili nesne ve ileti eşlemesi sırasıyla *pObject* ve *dwMsgMapID* ile değiştirilmiştir. Aksi takdirde, yeni bir giriş eklenir.

## <a name="see-also"></a>Ayrıca bkz.

[CWindowImpl sınıfı](../../atl/reference/cwindowimpl-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
