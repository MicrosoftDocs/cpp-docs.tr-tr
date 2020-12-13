---
description: 'Daha fazla bilgi edinin: CMessageMap sınıfı'
title: CMessageMap sınıfı
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
ms.openlocfilehash: 90ecdc101071b84362d328558ff2e74cb9bbeb6b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141446"
---
# <a name="cmessagemap-class"></a>CMessageMap sınıfı

Bu sınıf, bir nesnenin ileti eşlemelerinin başka bir nesne tarafından erişmesine izin verir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class ATL_NO_VTABLE CMessageMap
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMessageMap::P rocessWindowMessage](#processwindowmessage)|Türetilmiş sınıftaki bir ileti eşlemesine erişir `CMessageMap` .|

## <a name="remarks"></a>Açıklamalar

`CMessageMap` , bir nesnenin ileti eşlemelerine başka bir nesne tarafından erişilmesine izin veren soyut bir temel sınıftır. Bir nesnenin ileti haritalarını açığa çıkarmak için, sınıfının türevi olması gerekir `CMessageMap` .

ATL `CMessageMap` , içerilen Windows ve dinamik ileti eşleme zincirlemesini desteklemek için kullanır. Örneğin, bir [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) nesnesi içeren herhangi bir sınıf öğesinden türetilmelidir `CMessageMap` . Aşağıdaki kod alt [DIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) örneğinden alınmıştır. [CComControl](../../atl/reference/ccomcontrol-class.md)aracılığıyla `CAtlEdit` sınıfı otomatik olarak türetilir `CMessageMap` .

[!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]

İçerilen pencere, `m_EditCtrl` kapsayan sınıfta bir ileti eşlemesi kullanacaktır, `CAtlEdit` öğesinden türetilir `CMessageMap` .

İleti haritaları hakkında daha fazla bilgi için, "ATL pencere sınıfları" makalesindeki [Ileti haritaları](../../atl/message-maps-atl.md) bölümüne bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="cmessagemapprocesswindowmessage"></a><a name="processwindowmessage"></a> CMessageMap::P rocessWindowMessage

, Bir türetilmiş sınıfta *dwMsgMapID* tarafından tanımlanan ileti eşlemesine erişir `CMessageMap` .

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

*dwMsgMapID*<br/>
'ndaki İletiyi işleyecek ileti eşlemesinin tanımlayıcısı. [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile belirtilen varsayılan ileti eşlemesi 0 ile tanımlanır. [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)ile belirtilen alternatif bir ileti eşlemesi tarafından tanımlanır `msgMapID` .

### <a name="return-value"></a>Dönüş Değeri

İleti tam olarak işlenirse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bir [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) nesnesinin pencere yordamı veya ileti eşlemesine dinamik olarak zincirleme yapan bir nesne tarafından çağırılır.

## <a name="see-also"></a>Ayrıca bkz.

[Cdynamiczincirine sınıfı](../../atl/reference/cdynamicchain-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
