---
description: 'Daha fazla bilgi edinin: CDockState sınıfı'
title: CDockState sınıfı
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
ms.openlocfilehash: 4bdc17ec5a09b812609b8aa71e3f361603c1106f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184965"
---
# <a name="cdockstate-class"></a>CDockState sınıfı

`CObject`Kalıcı bellekte (bir dosya) bir veya daha fazla yerleştirme denetim çubuğunun durumunu yükleyen, kaldırmanın veya temizleyen serileştirilmiş bir sınıf.

## <a name="syntax"></a>Syntax

```
class CDockState : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDockState:: Clear](#clear)|Dock durum bilgilerini temizler.|
|[CDockState:: GetVersion](#getversion)|Depolanan çubuk durumunun sürüm numarasını alır.|
|[CDockState:: LoadState](#loadstate)|Kayıt defterinden veya listesinden durum bilgilerini alır. INı dosyası.|
|[CDockState:: Savemlak](#savestate)|Durum bilgilerini kayıt defterine veya ıNı dosyasına kaydeder.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDockState:: m_arrBarInfo](#m_arrbarinfo)|Her denetim çubuğu için bir giriş ile, depolanan yerleştirme durumu bilgilerine işaretçiler dizisi.|

## <a name="remarks"></a>Açıklamalar

Dock durumu çubuğun boyutunu ve konumunu ve yerleştirilmiş olup olmadığını içerir. Depolanan yerleştirme durumunu alırken `CDockState` çubuğun konumunu denetler ve çubuk geçerli ekran ayarlarıyla görünmüyorsa, `CDockState` çubuğun konumunu görünür olacak şekilde ölçeklendirir. Ana amacı, `CDockState` bir dizi denetim çubuğunun tamamının durumunu tutmak ve bu durumun, uygulamanın kayıt defterine kaydedilip yüklenebilsin. Bir nesnenin içeriğinin bir parçası olarak ıNı dosyası veya ikili biçimde `CArchive` .

Çubuk, bir araç çubuğu, durum çubuğu veya iletişim çubuğu dahil olmak üzere herhangi bir yerleştirilebilir denetim çubuğu olabilir. `CDockState` nesneler bir nesne aracılığıyla yazılır ve dosyadan veya dosyadan okur `CArchive` .

[CFrameWnd:: GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) , tüm çerçeve penceresinin nesnelerinin durum bilgilerini alır `CControlBar` ve `CDockState` nesneye koyar. Daha sonra `CDockState` [seri hale getirme](../../mfc/reference/cobject-class.md#serialize) veya [CDockState:: savu](#savestate)ile nesnenin içeriğini depolamaya yazabilirsiniz. Daha sonra çerçeve penceresindeki denetim çubuklarının durumunu geri yüklemek isterseniz, durumu `Serialize` ya da [CDockState:: LoadState](#loadstate)ile yükleyebilir ve ardından [CFrameWnd:: SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) kullanarak kaydedilen durumu çerçeve penceresinin denetim çubuklarına uygulayabilirsiniz.

Yerleştirme denetim çubukları hakkında daha fazla bilgi için bkz. makalelere [Denetim çubukları](../../mfc/control-bars.md), [araç çubukları: yerleştirme ve kayan](../../mfc/docking-and-floating-toolbars.md)ve [çerçeve pencereleri](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDockState`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxadv. h

## <a name="cdockstateclear"></a><a name="clear"></a> CDockState:: Clear

Nesnede depolanan tüm yerleştirme bilgilerini temizlemek için bu işlevi çağırın `CDockState` .

```cpp
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Bu, yalnızca çubuğun yerleştirilmiş olup olmadığını, ancak çubuğun boyutunu ve konumunu ve görünür olup olmadığını içerir.

## <a name="cdockstategetversion"></a><a name="getversion"></a> CDockState:: GetVersion

Depolanan çubuk durumunun sürüm numarasını almak için bu işlevi çağırın.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Dönüş Değeri

1 depolanan çubuk bilgileri geçerli çubuk durumundan eskiyse; 2 depolanan çubuk bilgileri, geçerli çubuk durumuyla aynıysa.

### <a name="remarks"></a>Açıklamalar

Sürüm desteği, düzeltilmiş bir çubuğun yeni kalıcı özellikler eklemesine olanak sağlar ve görüntünün önceki bir sürümü tarafından oluşturulan kalıcı durumu tespit edebilir ve yükleyebilir.

## <a name="cdockstateloadstate"></a><a name="loadstate"></a> CDockState:: LoadState

Kayıt defterinden veya ' den durum bilgilerini almak için bu işlevi çağırın. INı dosyası.

```cpp
void LoadState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
Başlatma dosyasındaki bir bölümün adını veya durum bilgilerinin depolandığı Windows kayıt defteri 'ndeki bir anahtarı belirten null-teminated dizesine işaret eder.

### <a name="remarks"></a>Açıklamalar

Profil adı, uygulamanın bölümüdür. INı dosyası veya çubukların durum bilgilerini içeren kayıt defteri. Denetim çubuğu durum bilgilerini kayıt defterine veya uygulamasına kaydedebilirsiniz. İle ıNı dosyası `SaveState` .

## <a name="cdockstatem_arrbarinfo"></a><a name="m_arrbarinfo"></a> CDockState:: m_arrBarInfo

`CPtrArray`Nesne içinde durum bilgilerini kaydeden her denetim çubuğu için depolanan denetim çubuğu bilgilerine işaretçiler dizisi olan bir nesne `CDockState` .

```
CPtrArray m_arrBarInfo;
```

## <a name="cdockstatesavestate"></a><a name="savestate"></a> CDockState:: Savemlak

Durum bilgilerini kayıt defterine veya kayıt defterine kaydetmek için bu işlevi çağırın. INı dosyası.

```cpp
void SaveState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
Başlatma dosyasındaki bir bölümün adını veya durum bilgilerinin depolandığı Windows kayıt defteri 'ndeki bir anahtarı belirten null-teminated dizesine işaret eder.

### <a name="remarks"></a>Açıklamalar

Profil adı, uygulamanın bölümüdür. INı dosyası veya denetim çubuğunun durum bilgilerini içeren kayıt defteri. `SaveState` Ayrıca geçerli ekran boyutunu kaydeder. Denetim çubuğu bilgilerini kayıt defterinden veya aracılığıyla alabilirsiniz. İle ıNı dosyası `LoadState` .

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
