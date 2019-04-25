---
title: Colecmduı sınıfı
ms.date: 09/12/2018
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
helpviewer_keywords:
- COleCmdUI [MFC], COleCmdUI
- COleCmdUI [MFC], Enable
- COleCmdUI [MFC], SetCheck
- COleCmdUI [MFC], SetText
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
ms.openlocfilehash: 5dc4e9504805146a9eff0f5ab937868226e4516e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148516"
---
# <a name="colecmdui-class"></a>Colecmduı sınıfı

Uygulayan bir yöntem için kullanıcı arabirimi nesnelerinin durumunu güncelleştirmek MFC ilgili `IOleCommandTarget`-uygulamanızın özelliklerini temelli.

## <a name="syntax"></a>Sözdizimi

```
class COleCmdUI : public CCmdUI
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleCmdUI::COleCmdUI](#colecmdui)|Oluşturur bir `COleCmdUI` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleCmdUI::Enable](#enable)|Etkin komut bayrağını kaldırır veya ayarlar.|
|[COleCmdUI::SetCheck](#setcheck)|Bir açma/kapatma geçiş durumunu ayarlar komutu.|
|[COleCmdUI::SetText](#settext)|Bir komut için metin adı ya da durum dizesi döndürür.|

## <a name="remarks"></a>Açıklamalar

Bir MFC uygulamasında menüsü kullanıcı görünümleri UPDATE_COMMAND_UI bildirimleri işlerken bir uygulamada, DocObjects için etkin değil. Her bir bildirim verilen bir [Ccmduı](../../mfc/reference/ccmdui-class.md) nesnesini belirli bir komut durumunu yansıtacak şekilde yönetilebilir. Ancak, uygulamanız için DocObjects etkinleştirildiğinde, MFC UPDATE_OLE_COMMAND_UI bildirimleri işler ve atar `COleCmdUI` nesneleri.

`COleCmdUI` DocObject kapsayıcısının kullanıcı arabiriminde (örneğin, dosya yeni, açık, yazdırma ve benzeri) kaynaklanan komutları almak üzere, ve kapsayıcı DocObject'ın kullanıcı arabiriminde kaynaklanan komutları almasına olanak sağlar. Ancak `IDispatch` aynı komutları gönderme için kullanılabilecek `IOleCommandTarget` sorgulamak ve komutları, bağımsız değişken olmadan genellikle standart bir dizi kullanır ve hiçbir tür bilgileri söz konusu olduğundan yürütmek için daha basit bir yol sağlar. `COleCmdUI` etkinleştirme, güncelleştirme ve DocObject kullanıcı arabirimi komutları diğer özelliklerini ayarlamak için kullanılabilir. Çağırmak istediğinizde, çağrı [COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd).

DocObjects hakkında daha fazla bilgi için bkz: [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) ve [Cdocobjectserverıtem](../../mfc/reference/cdocobjectserveritem-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Ccmduı](../../mfc/reference/ccmdui-class.md)

`COleCmdUI`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdocobj.h

##  <a name="colecmdui"></a>  COleCmdUI::COleCmdUI

Oluşturur bir `COleCmdUI` belirli kullanıcı arabirimi komut ile ilişkili nesne.

```
COleCmdUI(
    OLECMD* rgCmds,
    ULONG cCmds,
    const GUID* m_pGroup);
```

### <a name="parameters"></a>Parametreler

*rgCmds*<br/>
Verilen GUID ile ilişkili desteklenen komutların listesi. `OLECMD` Yapı komutları komut bayrakları ile ilişkilendirir.

*cCmds*<br/>
Komutlarında sayısı *rgCmds*.

*pGroup*<br/>
Bir komut kümesini tanımlayan bir GUID için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`COleCmdUI` Nesnesi DocObject menü öğeleri ya da denetim çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerini güncelleştirme için bir programlama arabirimi sağlar. Kullanıcı arabirimi nesneleri etkin, devre dışı, kullanıma ve/veya aracılığıyla temizlenmiş `COleCmdUI` nesne.

##  <a name="enable"></a>  COleCmdUI::Enable

Komut bayrağını ayarlamak için bu işlevi çağırın `COleCmdUI` arabirimi komuttur sağlandığını ve etkinleştirildiğini belirten, OLECOMDF_ENABLED veya komut bayrağını temizlemek için nesne.

```
virtual void Enable(BOOL bOn);
```

### <a name="parameters"></a>Parametreler

*İyi*<br/>
Komut ile ilişkili olup olmadığını gösteren `COleCmdUI` nesne etkinleştirilecek veya devre dışı. NonZero komut etkinleştirir; 0 komutu devre dışı bırakır.

##  <a name="setcheck"></a>  COleCmdUI::SetCheck

Bir açma/kapatma geçiş durumunu ayarlamak için bu işlevi çağırın komutu.

```
virtual void SetCheck(int nCheck);
```

### <a name="parameters"></a>Parametreler

*Nbakım*<br/>
Bir açma/kapatma getirin durumuna belirleyen bir değer komutu. Değerler şunlardır:

|Değer|Açıklama|
|-----------|-----------------|
|**1**|Komutu, açık olarak ayarlar.|
|**2**|Komut için belirsiz ayarlar; Bu komutun öznitelik hem şirket hem de ilgili seçimi durumlarda devre dışı olduğundan durumu belirlenemiyor.|
|başka bir değer|Komutu, OFF olarak ayarlar.|

##  <a name="settext"></a>  COleCmdUI::SetText

Bir komut için metin adı ya da durum dize döndürmek için bu işlevi çağırın.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
Komutu ile kullanılacak metin işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdUI Sınıfı](../../mfc/reference/ccmdui-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
