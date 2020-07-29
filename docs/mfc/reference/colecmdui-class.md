---
title: Cotacmduı sınıfı
ms.date: 07/24/2020
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
ms.openlocfilehash: c21d9b504656e6bba5ca693e57958743bb1b8309
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233216"
---
# <a name="colecmdui-class"></a>Cotacmduı sınıfı

, MFC 'nin uygulamanızın odaklı özellikleriyle ilgili Kullanıcı arabirimi nesnelerinin durumunu güncelleştirmesine yönelik bir yöntem uygular `IOleCommandTarget` .

## <a name="syntax"></a>Sözdizimi

```cpp
class COleCmdUI : public CCmdUI
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cotacmduı:: Cotacmduı](#colecmdui)|Bir `COleCmdUI` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotacmduı:: Enable](#enable)|Etkinleştir komut bayrağını ayarlar veya temizler.|
|[Cotacmduı:: SetCheck](#setcheck)|Bir açık/kapalı iki durumlu komutun durumunu ayarlar.|
|[Cotacmduı:: SetText](#settext)|Bir komut için bir metin adı veya durum dizesi döndürür.|

## <a name="remarks"></a>Açıklamalar

DocObjects için etkinleştirilmemiş bir uygulamada, Kullanıcı uygulamada bir menüyü görüntülediğinde, MFC UPDATE_COMMAND_UI bildirimler işler. Her bildirime, belirli bir komutun durumunu yansıtacak şekilde işlenebilen bir [CCmdUI](../../mfc/reference/ccmdui-class.md) nesnesi verilir. Ancak, uygulamanız DocObjects için etkinleştirildiğinde, MFC UPDATE_OLE_COMMAND_UI bildirimleri işler ve `COleCmdUI` nesneleri atar.

`COleCmdUI`bir DocObject 'in kapsayıcının Kullanıcı arabirimindeki (FileNew, Open, Print, vb.) olan komutları almasına izin verir ve bir kapsayıcının, DocObject 'in Kullanıcı arabirimindeki komutları almasına izin verir. Aynı komutları dağıtmak için de kullanılabilse de, `IDispatch` `IOleCommandTarget` genellikle bağımsız değişkenler olmadan standart bir komut kümesini kullandığından sorgu ve yürütme için daha basit bir yol sağlar ve hiçbir tür bilgisi dahil değildir. `COleCmdUI`DocObject Kullanıcı arabirimi komutlarının diğer özelliklerini etkinleştirmek, güncelleştirmek ve ayarlamak için kullanılabilir. Komutu çağırmak istediğinizde [Copaserverdoc:: Onexecotacmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd)' yi çağırın.

DocObjects hakkında daha fazla bilgi için bkz. [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) and [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CCmdUI](../../mfc/reference/ccmdui-class.md)

`COleCmdUI`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdocob. h

## <a name="colecmduicolecmdui"></a><a name="colecmdui"></a>Cotacmduı:: Cotacmduı

Belirli bir `COleCmdUI` Kullanıcı arabirimi komutuyla ilişkili bir nesne oluşturur.

```cpp
COleCmdUI(
    OLECMD* rgCmds,
    ULONG cCmds,
    const GUID* m_pGroup);
```

### <a name="parameters"></a>Parametreler

*rgCmds*<br/>
Verilen GUID ile ilişkili desteklenen komutların listesi. `OLECMD`Yapı komutları komut bayraklarıyla ilişkilendirir.

*cCmds*<br/>
*RgCmds*içindeki komut sayısı.

*pGroup*<br/>
Bir komut kümesini tanımlayan GUID için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`COleCmdUI`Nesnesi, menü öğeleri veya denetim çubuğu düğmeleri gibi DocObject Kullanıcı arabirimi nesnelerini güncelleştirmek için programlı bir arabirim sağlar. Kullanıcı arabirimi nesneleri, nesne aracılığıyla etkinleştirilebilir, devre dışı bırakılabilir, denetlenebilir ve/veya temizlenir `COleCmdUI` .

## <a name="colecmduienable"></a><a name="enable"></a>Cotacmduı:: Enable

Bu işlevi çağırın, bu, `COleCmdUI` arabirime komutun kullanılabilir ve etkin olduğunu, ya da komut bayrağını temizlemesini söyleyen OLECOMDF_ENABLED.

```cpp
virtual void Enable(BOOL bOn);
```

### <a name="parameters"></a>Parametreler

*Um*<br/>
Nesneyle ilişkili komutun `COleCmdUI` etkinleştirilip etkinleştirilmeyeceğini veya devre dışı bırakılacağını belirtir. Sıfır dışında komut etkinleştirilir; 0 komutu devre dışı bırakır.

## <a name="colecmduisetcheck"></a><a name="setcheck"></a>Cotacmduı:: SetCheck

Bir açık/kapalı iki durumlu komutun durumunu ayarlamak için bu işlevi çağırın.

```cpp
virtual void SetCheck(int nCheck);
```

### <a name="parameters"></a>Parametreler

*Nhatayla*<br/>
Bir açık/kapalı geçiş komutu ayarlanacak durumu belirleyen bir değer. Değerler şunlardır:

|Değer|Açıklama|
|-----------|-----------------|
|**1**|Komutunu açık olarak ayarlar.|
|**2**|Komutu belirsiz olarak ayarlar. Bu komutun özniteliği ilgili seçimde hem açık hem de kapalı durumunda olduğundan durum belirlenemiyor.|
|diğer herhangi bir değer|Komutu kapalı olarak ayarlar.|

## <a name="colecmduisettext"></a><a name="settext"></a>Cotacmduı:: SetText

Bir komut için bir metin adı veya durum dizesi döndürmek üzere bu işlevi çağırın.

```cpp
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
Komutuyla kullanılacak metne yönelik bir işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdUI sınıfı](../../mfc/reference/ccmdui-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
