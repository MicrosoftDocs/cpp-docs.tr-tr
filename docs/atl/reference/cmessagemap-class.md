---
title: CMessageMap Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMessageMap
- ATLWIN/ATL::CMessageMap
- ATLWIN/ATL::CMessageMap::ProcessWindowMessage
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
ms.openlocfilehash: a822f36d6b6fd49301d8240324e27f0ad9ce52e7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326718"
---
# <a name="cmessagemap-class"></a>CMessageMap Sınıfı

Bu sınıf, bir nesnenin ileti eşlemlerinin başka bir nesne tarafından erişmesine izin verir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class ATL_NO_VTABLE CMessageMap
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMessageMap::ProcessWindowMessage](#processwindowmessage)|Türetilmiş sınıftaki `CMessageMap`bir ileti haritasına erişir.|

## <a name="remarks"></a>Açıklamalar

`CMessageMap`bir nesnenin ileti haritalarının başka bir nesne tarafından erişmesine izin veren soyut bir taban sınıftır. Bir nesnenin ileti eşlemlerini ortaya çıkarabilmesi için `CMessageMap`sınıfının.'dan türemesi gerekir.

ATL, `CMessageMap` içerdiği pencereleri ve dinamik ileti eşlemi zincirlemesini desteklemek için kullanır. Örneğin, [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) nesnesi içeren herhangi `CMessageMap`bir sınıf. Aşağıdaki kod [SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) örneğinden alınır. [CComControl](../../atl/reference/ccomcontrol-class.md)aracılığıyla, `CAtlEdit` sınıf otomatik olarak. `CMessageMap`

[!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]

Çünkü bulunan pencere, `m_EditCtrl`içeren sınıfta bir ileti eşlemi kullanır, `CAtlEdit` `CMessageMap`türetilmiştir.

İleti haritaları hakkında daha fazla bilgi için "ATL Pencere Sınıfları" makalesindeki [İleti Haritaları'na](../../atl/message-maps-atl.md) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="cmessagemapprocesswindowmessage"></a><a name="processwindowmessage"></a>CMessageMap::ProcessWindowMessage

türetilmiş bir sınıfta *dwMsgMapID* `CMessageMap`tarafından tanımlanan ileti haritasına erişir.

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

*dwMsgMapID*<br/>
[içinde] İletiyi işleyecek ileti haritasının tanımlayıcısı. [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile bildirilen varsayılan ileti eşlemi 0 ile tanımlanır. [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)ile bildirilen alternatif bir ileti `msgMapID`haritası tanımlanır.

### <a name="return-value"></a>Dönüş Değeri

İleti tam olarak işlenirse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

[CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) nesnesinin veya ileti eşlemi'ne dinamik olarak zincirleme bir nesnenin pencere yordamı tarafından çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[CDynamicChain Sınıfı](../../atl/reference/cdynamicchain-class.md)<br/>
[Begın_msg_map](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
