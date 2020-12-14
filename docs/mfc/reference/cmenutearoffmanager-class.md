---
description: 'Daha fazla bilgi edinin: CMenuTearOffManager sınıfı'
title: CMenuTearOffManager sınıfı
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
ms.openlocfilehash: b80f2e935f8d1dd47bf19a11522e4556b35490b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336642"
---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager sınıfı

Koparmayı yönetme menülerini yönetir. Bir yırma menüsü menü çubuğundaki bir menü olur. Kullanıcı, menü çubuğundan bir yırma menüsünü kaldırarak, koparma menüsünün kayan olmasına neden olabilir.

   Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```
class CMenuTearOffManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMenuTearOffManager:: CMenuTearOffManager](#cmenutearoffmanager)|Bir `CMenuTearOffManager` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMenuTearOffManager:: Build](#build)||
|[CMenuTearOffManager:: GetRegPath](#getregpath)||
|[CMenuTearOffManager:: Initialize](#initialize)|Bir `CMenuTearOffManager` nesnesi başlatır.|
|[CMenuTearOffManager:: ısdynamicıd](#isdynamicid)||
|[CMenuTearOffManager::P arin](#parse)||
|[CMenuTearOffManager:: Reset](#reset)||
|[CMenuTearOffManager:: Setınuse](#setinuse)||
|[CMenuTearOffManager:: SetupTearOffMenus](#setuptearoffmenus)||

## <a name="remarks"></a>Açıklamalar

Uygulamanızda koparma menülerini kullanmak için bir nesneniz olması gerekir `CMenuTearOffManager` . Çoğu durumda, doğrudan bir nesne oluşturmaz veya başlatmayacaktır `CMenuTearOffManager` . Bu, [CWinAppEx:: EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) işlevini çağırdığınızda sizin için işlenir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, yöntemini çağırarak bir nesnenin nasıl oluşturulup başlatılacağını gösterir `CMenuTearOffManager` `CWinAppEX::EnableTearOffMenus` . Bu kod parçacığı, [sözcük paneli örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMenuTearOffManager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmenutearoffmanager. h

## <a name="cmenutearoffmanagerbuild"></a><a name="build"></a> CMenuTearOffManager:: Build

```cpp
void Build(
    UINT uiTearOffBarID,
    CString& strText);
```

### <a name="parameters"></a>Parametreler

'ndaki *Uitearoffbarıd*<br/>

'ndaki *strText*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmenutearoffmanagercmenutearoffmanager"></a><a name="cmenutearoffmanager"></a> CMenuTearOffManager:: CMenuTearOffManager

Bir [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) nesnesi oluşturur.

```
CMenuTearOffManager();
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda, `CMenuTearOffManager` el ile oluşturmamalıdır. `CMenuTearOffManager` [CWinAppEx:: EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)' i çağırdığınızda uygulamanızın çerçevesi nesnesini oluşturur.

## <a name="cmenutearoffmanagergetregpath"></a><a name="getregpath"></a> CMenuTearOffManager:: GetRegPath

```
LPCTSTR GetRegPath() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmenutearoffmanagerinitialize"></a><a name="initialize"></a> CMenuTearOffManager:: Initialize

Bir [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) nesnesi başlatır.

```
BOOL Initialize(
    LPCTSTR lpszRegEntry,
    UINT uiTearOffMenuFirst,
    UINT uiTearOffMenuLast);
```

### <a name="parameters"></a>Parametreler

*lpszRegEntry*<br/>
'ndaki Kayıt defteri girdisinin yolunu içeren bir dize. Uygulamalarınız, bu kayıt defteri girişinde koparma çubuklarının ayarlarını depolar.

*İlk önce uııtearoffmenu*<br/>
'ndaki Bir yırma menüsünün ilk menü KIMLIĞI.

*uiTearOffMenuLast*<br/>
'ndaki Bir yırma menüsünün son menü KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*Uııtemaroffmenuöğesinden önce* *Uııtemaroffmenulast* öğesine ait menü kimliklerinin aralığı sürekli bir Aralık olmalıdır. Aralık, uygulamada aynı anda görünebilen çıkarma menülerinin sayısını tanımlar.

## <a name="cmenutearoffmanagerisdynamicid"></a><a name="isdynamicid"></a> CMenuTearOffManager:: ısdynamicıd

```
BOOL IsDynamicID(UINT uiID) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *Uııd*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmenutearoffmanagerparse"></a><a name="parse"></a> CMenuTearOffManager::P arin

```
UINT Parse(CString& str);
```

### <a name="parameters"></a>Parametreler

'ndaki *Str*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmenutearoffmanagerreset"></a><a name="reset"></a> CMenuTearOffManager:: Reset

```cpp
void Reset(HMENU hmenu);
```

### <a name="parameters"></a>Parametreler

'ndaki *HMENU*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmenutearoffmanagersetinuse"></a><a name="setinuse"></a> CMenuTearOffManager:: Setınuse

```cpp
void SetInUse(
    UINT uiCmdId,
    BOOL bUse = TRUE);
```

### <a name="parameters"></a>Parametreler

'ndaki *Uıımıdıd*<br/>

'ndaki *buse*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmenutearoffmanagersetuptearoffmenus"></a><a name="setuptearoffmenus"></a> CMenuTearOffManager:: SetupTearOffMenus

```cpp
void SetupTearOffMenus(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

'ndaki *HMENU*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)
