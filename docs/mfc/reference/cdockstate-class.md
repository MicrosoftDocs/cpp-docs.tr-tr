---
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
ms.openlocfilehash: 56be735aa99cfebe4ec64ff76f53d28cc9b9779e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443608"
---
# <a name="cdockstate-class"></a>CDockState sınıfı

Seri hale getirilmiş bir `CObject` yükler, kaldırır veya bir veya daha fazla yerleştirme denetim durumunu temizler sınıfı çubuklarını kalıcı bellekte (bir dosya).

## <a name="syntax"></a>Sözdizimi

```
class CDockState : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDockState::Clear](#clear)|Dock durum bilgilerini temizler.|
|[CDockState::GetVersion](#getversion)|Depolanan sürüm numarasını alır. durum çubuğu.|
|[CDockState::LoadState](#loadstate)|Durum bilgilerini kayıt defterinden alır veya. INI dosyası.|
|[CDockState::SaveState](#savestate)|INI dosya ve kayıt defteri için durum bilgilerini kaydeder.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|Her denetim çubuğu için bir giriş olan durum bilgilerini dock saklı işaretçiler dizisi.|

## <a name="remarks"></a>Açıklamalar

Dock durumu, boyutunu ve konumunu çubuğu ve yerleştirilmiş olup olmadığını içerir. Ne zaman saklı alınırken izin ver dock durumu `CDockState` çubuğunun denetler konumu ve geçerli ekran ayarlarla çubuğu görünmüyorsa `CDockState` çubuğunun ölçeklendirir görünür olması getirin. Ana amacı, `CDockState` ya da kayıt defterindeki, uygulama yüklendi ve bir dizi denetim çubukları tüm durumu tutacak ve kaydedilmesi bu duruma izin vermek için. INI dosyası veya bir parçası olarak ikili biçimde bir `CArchive` nesnenin içeriğini.

Çubuk çubuğu, araç, durum çubuğu veya iletişim çubuğu gibi herhangi bir yerleştirilebilir denetimi olabilir. `CDockState` nesneleri yazılır ve okuma için veya bir dosyadan bir `CArchive` nesne.

[CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) tüm çerçeve penceresinin durumu bilgilerini alır `CControlBar` nesneleri ve içine yerleştirir `CDockState` nesne. Ardından içeriğini yazabileceğiniz `CDockState` ile depolama nesnesine [serileştirme](../../mfc/reference/cobject-class.md#serialize) veya [CDockState::SaveState](#savestate). Daha sonra Denetim çubukları çerçeve penceresindeki durumunu geri yüklemek istiyorsanız, durumuyla yükleyebilir `Serialize` veya [CDockState::LoadState](#loadstate), ardından [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) kaydedilen uygulamak için Çerçeve penceresinin denetim çubukları durumu.

Denetim çubukları yerleştirme daha fazla bilgi için makalelere göz atın [denetim çubukları](../../mfc/control-bars.md), [araç çubukları: yerleşen ve kayan](../../mfc/docking-and-floating-toolbars.md), ve [çerçeve Windows](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDockState`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxadv.h

##  <a name="clear"></a>  CDockState::Clear

İçinde depolanan tüm yerleştirme bilgilerini temizlemek için bu işlevi çağırın `CDockState` nesne.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Bu çubuk veya olmasın çubuğunun boyutunu ve konumunu yerleştirildiğini olup olmadığını ve yalnızca görünür olup olmadığını içerir.

##  <a name="getversion"></a>  CDockState::GetVersion

Depolanan sürüm numarasını almak için bu işlevi çağırın durum çubuğu.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Dönüş Değeri

1 ise saklı Çubuğu Bilgi çubuğu durumu; geçerli daha eski 2 ise saklı çubuğu bilgi aynıdır geçerli durum çubuğu.

### <a name="remarks"></a>Açıklamalar

Sürekli yeni özellikler ekleyebilir ve hala algılamak ve çubuk önceki bir sürümü tarafından oluşturulmuş durumunu sürekli yükleme için düzeltilmiş çubuğu sürüm desteği sağlar.

##  <a name="loadstate"></a>  CDockState::LoadState

Kayıt defterinden durum bilgilerini almak için bu işlevi çağırın veya. INI dosyası.

```
void LoadState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
Başlatma dosyası ya da durum bilgisi depolandığı Windows kayıt defteri anahtarında bir bölümün adını belirten bir null teminated dizeyi işaret eder.

### <a name="remarks"></a>Açıklamalar

Profil adı uygulamanın bölümüdür. INI dosyası veya çubukları durum bilgilerini içeren kayıt. Denetim çubuğu durum bilgilerini kayıt defterine Kaydet veya. INI dosyasıyla `SaveState`.

##  <a name="m_arrbarinfo"></a>  CDockState::m_arrBarInfo

A `CPtrArray` bir durum bilgilerini kaydetti her denetim çubuğu için depolanan denetim çubuğu bilgi işaretçiler dizisi nesnesini `CDockState` nesnesi.

```
CPtrArray m_arrBarInfo;
```

##  <a name="savestate"></a>  CDockState::SaveState

Durum bilgileri kayıt defterine kaydetmek için bu işlevi çağırın veya. INI dosyası.

```
void SaveState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
Başlatma dosyası ya da durum bilgisi depolandığı Windows kayıt defteri anahtarında bir bölümün adını belirten bir null teminated dizeyi işaret eder.

### <a name="remarks"></a>Açıklamalar

Profil adı uygulamanın bölümüdür. INI dosyası veya kayıt defteri içeren denetim çubuğunun durum bilgileri. `SaveState` Geçerli ekran boyutu de kaydeder. Denetim çubuğu bilgileri kayıt defterinden alabilir veya. INI dosyasıyla `LoadState`.

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

