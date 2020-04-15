---
title: CMenuTearOffManager Sınıfı
ms.date: 10/18/2018
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
ms.openlocfilehash: f41937179dc055213f3af093e107bcb08c8a8fcc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369971"
---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager Sınıfı

Yırtılma menülerini yönetir. Yırtılma menüsü menü çubuğunda bir menüdür. Kullanıcı, yırtılma menüsünü menü çubuğundan kaldırarak yırtılma menüsünün yüzdürülmesine neden olabilir.

   Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMenuTearOffManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CmenutearOffManager::CmenutearoffManager](#cmenutearoffmanager)|Bir `CMenuTearOffManager` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CmenuTearOffManager::Yapı](#build)||
|[CmenuTearOffManager::GetRegPath](#getregpath)||
|[CMenuTearOffManager::Initialize](#initialize)|Bir `CMenuTearOffManager` nesneyi başharfe alar.|
|[CmenuTearOffManager::IsdynamicID](#isdynamicid)||
|[CMenuTearOffManager::Parse](#parse)||
|[CMenuTearOffManager::Sıfırlama](#reset)||
|[CmenuTearOffManager::Setinuse](#setinuse)||
|[CMenuTearOffManager::SetupTearOffMenüler](#setuptearoffmenus)||

## <a name="remarks"></a>Açıklamalar

Uygulamanızda yırtılma menülerini kullanabilmek için bir `CMenuTearOffManager` nesneniz olmalıdır. Çoğu durumda, doğrudan bir `CMenuTearOffManager` nesne oluşturmaz veya başlatmazsınız. [Bu, CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) işlevini aradiğinizde sizin için işlenir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, yöntemi çağırarak bir `CMenuTearOffManager` nesnenin nasıl `CWinAppEX::EnableTearOffMenus` oluşturup başharflere alınır gösteriş gösterir. Bu kod parçacığı Word Pad [örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CMenuTearOffManager`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmenutearoffmanager.h

## <a name="cmenutearoffmanagerbuild"></a><a name="build"></a>CmenuTearOffManager::Yapı

```
void Build(
    UINT uiTearOffBarID,
    CString& strText);
```

### <a name="parameters"></a>Parametreler

[içinde] *uiTearOffBarID*<br/>

[içinde] *strText*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmenutearoffmanagercmenutearoffmanager"></a><a name="cmenutearoffmanager"></a>CmenutearOffManager::CmenutearoffManager

[Bir CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) nesnesi oluşturuyor.

```
CMenuTearOffManager();
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda, el ile `CMenuTearOffManager` oluşturmamalısınız. `CMenuTearOffManager` [CWinAppEx::EnableTearOffMenus'i](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)aradiğinizde uygulamanızın çerçevesi nesneyi oluşturur.

## <a name="cmenutearoffmanagergetregpath"></a><a name="getregpath"></a>CmenuTearOffManager::GetRegPath

```
LPCTSTR GetRegPath() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmenutearoffmanagerinitialize"></a><a name="initialize"></a>CMenuTearOffManager::Initialize

[Bir CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) nesnesi başharflerine.

```
BOOL Initialize(
    LPCTSTR lpszRegEntry,
    UINT uiTearOffMenuFirst,
    UINT uiTearOffMenuLast);
```

### <a name="parameters"></a>Parametreler

*lpszRegEntry*<br/>
[içinde] Kayıt defteri girişinin yolunu içeren bir dize. Uygulamalarınız bu kayıt defteri girişinde yırtılma çubuklarının ayarlarını depolar.

*uiTearOffMenuFirst*<br/>
[içinde] Yırtılma menüsünün ilk menü kimliği.

*uiTearOffMenuSon*<br/>
[içinde] Yırtılma menüsünün son menü kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*uiTearOffMenuFirst'den* *uiTearOffMenuLast'a* kadar menü dislerinin aralıkları sürekli bir aralık olmalıdır. Aralık, uygulamada aynı anda görünebilen yırtılma menülerinin sayısını tanımlar.

## <a name="cmenutearoffmanagerisdynamicid"></a><a name="isdynamicid"></a>CmenuTearOffManager::IsdynamicID

```
BOOL IsDynamicID(UINT uiID) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *uiID*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmenutearoffmanagerparse"></a><a name="parse"></a>CMenuTearOffManager::Parse

```
UINT Parse(CString& str);
```

### <a name="parameters"></a>Parametreler

[içinde] *str*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmenutearoffmanagerreset"></a><a name="reset"></a>CMenuTearOffManager::Sıfırlama

```
void Reset(HMENU hmenu);
```

### <a name="parameters"></a>Parametreler

[içinde] *hmenu*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmenutearoffmanagersetinuse"></a><a name="setinuse"></a>CmenuTearOffManager::Setinuse

```
void SetInUse(
    UINT uiCmdId,
    BOOL bUse = TRUE);
```

### <a name="parameters"></a>Parametreler

[içinde] *uiCmdId*<br/>

[içinde] *bKullan*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmenutearoffmanagersetuptearoffmenus"></a><a name="setuptearoffmenus"></a>CMenuTearOffManager::SetupTearOffMenüler

```
void SetupTearOffMenus(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

[içinde] *hMenü*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)
