---
title: CDockState Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
ms.openlocfilehash: 1c76bcda6465ca86b8da4778d3653cb23001b78b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375561"
---
# <a name="cdockstate-class"></a>CDockState Sınıfı

Kalıcı bellekteki (dosya) bir veya daha fazla yerleştirme denetim çubuklarını yükleyen, boşaltan veya temizleyen serileştirilmiş `CObject` bir sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CDockState : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDockState::Açık](#clear)|Dock durumu bilgilerini temizler.|
|[CDockState::GetVersion](#getversion)|Depolanan çubuk durumunun sürüm numarasını alır.|
|[CDockState::LoadState](#loadstate)|Kayıt defterinden durum bilgilerini alır veya . INI dosyası.|
|[CDockState::SaveState](#savestate)|Durum bilgilerini kayıt defterine veya INI dosyasına kaydeder.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|Her denetim çubuğu için bir girişiçeren depolanan dock durumu bilgilerine işaretçiler dizisi.|

## <a name="remarks"></a>Açıklamalar

Dock durumu, çubuğun boyutunu ve konumunu ve kenetlenip kenetlenmediğini içerir. Depolanan dock durumunu alırken, `CDockState` çubuğun konumunu denetler ve çubuk geçerli ekran ayarlarıyla görünmüyorsa, `CDockState` çubuğun konumunu görünür olacak şekilde ölçeklendirin. Temel amacı `CDockState` denetim çubukları bir dizi tüm devlet tutmak ve bu devlet kaydedilebilir ve kayıt defterine yüklenmesi için izin vermektir, uygulamanın . INI dosyası veya nesnenin içeriğinin `CArchive` bir parçası olarak ikili formda.

Çubuk, araç çubuğu, durum çubuğu veya iletişim çubuğu da dahil olmak üzere herhangi bir takılabilir denetim çubuğu olabilir. `CDockState`nesneler bir `CArchive` nesne üzerinden bir dosyaya yazılır ve okunur.

[CFrameWnd::GetDockState,](../../mfc/reference/cframewnd-class.md#getdockstate) çerçeve penceresinin tüm `CControlBar` nesnelerinin durum bilgilerini alır ve `CDockState` nesneye koyar. Daha sonra [Serialize](../../mfc/reference/cobject-class.md#serialize) veya `CDockState` CDockState ile depolama nesnenin içeriğini [yazabilirsiniz:SaveState](#savestate). Daha sonra çerçeve penceresindeki denetim çubuklarının durumunu geri yüklemek istiyorsanız, `Serialize` durumu veya CDockState ile yükleyebilirsiniz::LoadState, ardından kaydedilen durumu çerçeve penceresinin denetim çubuklarına uygulamak için [CFrameWnd::SetDockState'i](../../mfc/reference/cframewnd-class.md#setdockstate) kullanın. [CDockState::LoadState](#loadstate)

Yerleştirme denetim çubukları hakkında daha fazla bilgi için, [makaleleri Denetim Çubukları,](../../mfc/control-bars.md) [Araç Çubukları: Yerleştirme ve Kayan](../../mfc/docking-and-floating-toolbars.md)ve [Çerçeve Windows](../../mfc/frame-windows.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CDockState`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxadv.h

## <a name="cdockstateclear"></a><a name="clear"></a>CDockState::Açık

`CDockState` Nesnede depolanan tüm yerleştirme bilgilerini temizlemek için bu işlevi arayın.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Bu yalnızca çubuğun kenetlenip kenetlenmediğini değil, çubuğun boyutunu ve konumunu ve görünür olup olmadığını da içerir.

## <a name="cdockstategetversion"></a><a name="getversion"></a>CDockState::GetVersion

Depolanan çubuk durumunun sürüm numarasını almak için bu işlevi arayın.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Dönüş Değeri

Saklanan çubuk bilgileri geçerli çubuk durumundan daha eskiyse 1; 2 saklanan çubuk bilgileri geçerli çubuk durumuyla aynıysa.

### <a name="remarks"></a>Açıklamalar

Sürüm desteği, yeni kalıcı özellikler eklemek ve çubuğun önceki bir sürümü tarafından oluşturulan kalıcı durumu algılamak ve yüklemek için gözden geçirilmiş bir çubuk sağlar.

## <a name="cdockstateloadstate"></a><a name="loadstate"></a>CDockState::LoadState

Kayıt defterinden durum bilgilerini almak için bu işlevi arayın veya . INI dosyası.

```
void LoadState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
Başlatma dosyasındaki bir bölümün adını veya durum bilgilerinin depolandığı Windows kayıt defterindeki bir anahtarı belirten boş bir dize yi işaret ediyor.

### <a name="remarks"></a>Açıklamalar

Profil adı, uygulamanın . INI dosyası veya çubukların durum bilgilerini içeren kayıt defteri. Denetim çubuğu durum bilgilerini kayıt defterine kaydedebilirsiniz veya . INI dosyası `SaveState`ile .

## <a name="cdockstatem_arrbarinfo"></a><a name="m_arrbarinfo"></a>CDockState::m_arrBarInfo

Nesnedeki durum bilgilerini kaydeden her denetim çubuğu için depolanan denetim çubuğu bilgilerine işaretçi dizisi olan bir `CPtrArray` nesne. `CDockState`

```
CPtrArray m_arrBarInfo;
```

## <a name="cdockstatesavestate"></a><a name="savestate"></a>CDockState::SaveState

Durum bilgilerini kayıt defterine kaydetmek için bu işlevi arayın veya . INI dosyası.

```
void SaveState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
Başlatma dosyasındaki bir bölümün adını veya durum bilgilerinin depolandığı Windows kayıt defterindeki bir anahtarı belirten boş bir dize yi işaret ediyor.

### <a name="remarks"></a>Açıklamalar

Profil adı, uygulamanın . INI dosyası veya denetim çubuğunun durum bilgilerini içeren kayıt defteri. `SaveState`ayrıca geçerli ekran boyutunu kaydeder. Denetim çubuğu bilgilerini kayıt defterinden veya . INI dosyası `LoadState`ile .

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
