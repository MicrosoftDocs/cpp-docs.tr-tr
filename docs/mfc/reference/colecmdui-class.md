---
title: COleCmdUI Sınıfı
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
ms.openlocfilehash: 1b7a6b21a3ad778b4a5ca345b1aaf42875810e4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376275"
---
# <a name="colecmdui-class"></a>COleCmdUI Sınıfı

MFC'nin uygulamanızın yönlendirilmiş özellikleriyle `IOleCommandTarget`ilgili kullanıcı arabirimi nesnelerinin durumunu güncelleştirmesi için bir yöntem uygular.

## <a name="syntax"></a>Sözdizimi

```
class COleCmdUI : public CCmdUI
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleCmdUI::COleCmdUI](#colecmdui)|Bir `COleCmdUI` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleCmdUI::Etkinleştir](#enable)|Enable komut bayrağını ayarlar veya temizler.|
|[COleCmdUI::SetCheck](#setcheck)|Açık/kapalı geçiş komutunun durumunu ayarlar.|
|[COleCmdUI::SetText](#settext)|Bir komut için bir metin adı veya durum dizesi döndürür.|

## <a name="remarks"></a>Açıklamalar

DocObjects için etkinleştirilen olmayan bir uygulamada, kullanıcı uygulamada bir menü görüntülediğinde, MFC UPDATE_COMMAND_UI notasyonları işler. Her bildirime, belirli bir komutun durumunu yansıtacak şekilde manipüle edilebilen bir [CCmdUI](../../mfc/reference/ccmdui-class.md) nesnesi verilir. Ancak, uygulamanız DocObjects için etkinleştirildiğinde, MFC bildirimleri `COleCmdUI` UPDATE_OLE_COMMAND_UI işler ve nesneler atar.

`COleCmdUI`Bir DocObject'in kapsayıcısının kullanıcı arabiriminden (FileNew, Open, Print vb.) kaynaklanan komutları almasına ve bir kapsayıcının DocObject'in kullanıcı arabiriminden kaynaklanan komutları almasına izin verir. `IDispatch` Aynı komutları göndermek için kullanılabilse de, `IOleCommandTarget` genellikle bağımsız değişkenler olmadan standart bir komut kümesine dayandığından ve hiçbir tür bilgisi söz konusu olmadığından sorgulamak ve yürütmek için daha basit bir yol sağlar. `COleCmdUI`DocObject kullanıcı arabirimi komutlarının diğer özelliklerini etkinleştirmek, güncelleştirmek ve ayarlamak için kullanılabilir. Komutu çağırmak istediğinizde [COleServerDoc'u arayın::OnExecOleCmd.](../../mfc/reference/coleserverdoc-class.md#onexecolecmd)

DocObjects hakkında daha fazla bilgi için CDocObjectServer ve [CDocObjectServerItem'e](../../mfc/reference/cdocobjectserveritem-class.md)bakın. [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Ccmduı](../../mfc/reference/ccmdui-class.md)

`COleCmdUI`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdocobj.h

## <a name="colecmduicolecmdui"></a><a name="colecmdui"></a>COleCmdUI::COleCmdUI

Belirli bir `COleCmdUI` kullanıcı arabirimi komutuyla ilişkili bir nesne oluşur.

```
COleCmdUI(
    OLECMD* rgCmds,
    ULONG cCmds,
    const GUID* m_pGroup);
```

### <a name="parameters"></a>Parametreler

*rgCmds*<br/>
Verilen GUID ile ilişkili desteklenen komutların listesi. Yapı `OLECMD` komutları komut bayraklarıyla ilişkilendirer.

*cCmds*<br/>
*rgCmds*komutsayısı .

*pGroup*<br/>
Bir komut kümesini tanımlayan bir GUID işaretçisi.

### <a name="remarks"></a>Açıklamalar

Nesne, `COleCmdUI` menü öğeleri veya denetim çubuğu düğmeleri gibi DocObject kullanıcı arabirimi nesnelerini güncelleştirmek için programlı bir arabirim sağlar. Kullanıcı arabirimi nesneleri nesne aracılığıyla `COleCmdUI` etkinleştirilebilir, devre dışı tutulabilir, denetlenebilir ve/veya temizlenebilir.

## <a name="colecmduienable"></a><a name="enable"></a>COleCmdUI::Etkinleştir

Nesnenin `COleCmdUI` komut bayrağını OLECOMDF_ENABLED ayarlamak için bu işlevi çağırın, bu da arabirime komutun kullanılabilir ve etkin olduğunu söyler veya komut bayrağını temizleyin.

```
virtual void Enable(BOOL bOn);
```

### <a name="parameters"></a>Parametreler

*Bon*<br/>
Nesneyle ilişkili komutun `COleCmdUI` etkin mi yoksa devre dışı mı olması gerektiğini gösterir. Sıfır sızkomutu sağlar; 0 komutu devre dışı kılabilir.

## <a name="colecmduisetcheck"></a><a name="setcheck"></a>COleCmdUI::SetCheck

Açık/kapalı geçiş komutunun durumunu ayarlamak için bu işlevi çağırın.

```
virtual void SetCheck(int nCheck);
```

### <a name="parameters"></a>Parametreler

*nCheck*<br/>
Açık/kapalı geçiş komutu ayarlamak için durumu belirleyen bir değer. Değerler şunlardır:

|Değer|Açıklama|
|-----------|-----------------|
|**1**|Komutu bağlı olarak ayarlar.|
|**2**|Komutu belirsiz olarak ayarlar; bu komutun özniteliği ilgili seçimde hem on hem de kapalı durumlarda olduğundan durum belirlenemez.|
|başka bir değer|Komutu kapatmaya ayarlar.|

## <a name="colecmduisettext"></a><a name="settext"></a>COleCmdUI::SetText

Bir komut için bir metin adı veya durum dizedönmek için bu işlevi arayın.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
Komutla kullanılacak metne işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdUI Sınıfı](../../mfc/reference/ccmdui-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
