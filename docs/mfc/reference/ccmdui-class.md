---
description: 'Daha fazla bilgi edinin: CCmdUI sınıfı'
title: CCmdUI sınıfı
ms.date: 09/06/2019
f1_keywords:
- CCmdUI
- AFXWIN/CCmdUI
- AFXWIN/CCmdUI::ContinueRouting
- AFXWIN/CCmdUI::Enable
- AFXWIN/CCmdUI::SetCheck
- AFXWIN/CCmdUI::SetRadio
- AFXWIN/CCmdUI::SetText
- AFXWIN/CCmdUI::m_nID
- AFXWIN/CCmdUI::m_nIndex
- AFXWIN/CCmdUI::m_pMenu
- AFXWIN/CCmdUI::m_pOther
- AFXWIN/CCmdUI::m_pSubMenu
helpviewer_keywords:
- CCmdUI [MFC], ContinueRouting
- CCmdUI [MFC], Enable
- CCmdUI [MFC], SetCheck
- CCmdUI [MFC], SetRadio
- CCmdUI [MFC], SetText
- CCmdUI [MFC], m_nID
- CCmdUI [MFC], m_nIndex
- CCmdUI [MFC], m_pMenu
- CCmdUI [MFC], m_pOther
- CCmdUI [MFC], m_pSubMenu
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
ms.openlocfilehash: d868c0dc3c9915f5300f56e5bfa5f1971d4ec3ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132996"
---
# <a name="ccmdui-class"></a>CCmdUI sınıfı

Yalnızca `ON_UPDATE_COMMAND_UI` türetilmiş sınıftaki bir işleyici içinde kullanılır `CCmdTarget` .

## <a name="syntax"></a>Syntax

```
class CCmdUI
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCmdUI:: Devamsallama](#continuerouting)|Komut yönlendirme mekanizmasına, geçerli iletiyi işleyiciler zincirinin altına yönlendirmeye devam etmeyi söyler.|
|[CCmdUI:: Enable](#enable)|Bu komut için Kullanıcı arabirimi öğesini etkinleştirilir veya devre dışı bırakır.|
|[CCmdUI:: SetCheck](#setcheck)|Bu komut için Kullanıcı arabirimi öğesinin denetim durumunu ayarlar.|
|[CCmdUI:: SetRadio](#setradio)|`SetCheck`Üye işlevi gibi, ancak radyo grupları üzerinde çalışır.|
|[CCmdUI:: SetText](#settext)|Bu komut için Kullanıcı arabirimi öğesi metnini ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CCmdUI:: m_nID](#m_nid)|Kullanıcı arabirimi nesnesinin KIMLIĞI.|
|[CCmdUI:: m_nIndex](#m_nindex)|Kullanıcı arabirimi nesnesinin dizini.|
|[CCmdUI:: m_pMenu](#m_pmenu)|Nesnenin temsil ettiği menüyü işaret eder `CCmdUI` .|
|[CCmdUI:: m_pOther](#m_pother)|Bildirimi gönderen pencere nesnesine işaret eder.|
|[CCmdUI:: m_pSubMenu](#m_psubmenu)|Nesnenin temsil ettiği içerilen alt menüye işaret eder `CCmdUI` .|

## <a name="remarks"></a>Açıklamalar

`CCmdUI` taban sınıfına sahip değildir.

Uygulamanızın bir kullanıcısı bir menü aldığında, her menü öğesinin etkin veya devre dışı olarak görüntülenmesi gerekip gerekmediğini bilmeleri gerekir. Bir menü komutunun hedefi bir ON_UPDATE_COMMAND_UI işleyicisi uygulayarak bu bilgileri sağlar. Uygulamanızdaki her bir komut Kullanıcı arabirimi nesnesi için, her işleyici için bir ileti eşleme girişi ve işlev prototipi oluşturmak üzere [sınıf Sihirbazı](mfc-class-wizard.md) 'Nı veya **özellikler** penceresini ( **sınıf görünümü**) kullanın.

Menü çekileklendiğinde, çerçeve her bir ON_UPDATE_COMMAND_UI işleyicisini arar ve çağırır, her işleyici `CCmdUI` ve gibi üye işlevlerini çağırır `Enable` `Check` ve daha sonra her bir menü öğesini uygun şekilde görüntüler.

Bir menü öğesi, işleyici içindeki kodu değiştirmeden bir denetim çubuğu düğmesi veya diğer komut Kullanıcı arabirimi nesnesi ile değiştirilebilir `ON_UPDATE_COMMAND_UI` .

Aşağıdaki tabloda, efektin `CCmdUI` üye işlevlerinin çeşitli komut Kullanıcı Arabirimi öğelerine sahip olduğu özetlenmektedir.

|User-Interface öğesi|Etkinleştir|SetCheck|SetRadio|SetText|
|--------------------------|------------|--------------|--------------|-------------|
|Menü öğesi|Etkinleştirilir veya devre dışı bırakır|Denetimleri veya denetimleri geri al|Nokta kullanarak denetim|Öğe metnini ayarlar|
|Araç çubuğu düğmesi|Etkinleştirilir veya devre dışı bırakır|Seçer, seçimi kaldır veya belirsiz|Aynı `SetCheck`|(Uygulanamaz)|
|Durum çubuğu bölmesi|Metnin görünür veya görünmez olmasını sağlar|Açılır veya normal kenarlığı ayarlar|Aynı `SetCheck`|Bölme metnini ayarlar|
|İçindeki normal düğme `CDialogBar`|Etkinleştirilir veya devre dışı bırakır|Denetimler veya denetimleri kaldır onay kutusu|Aynı `SetCheck`|Düğme metnini ayarlar|
|İçindeki normal denetim `CDialogBar`|Etkinleştirilir veya devre dışı bırakır|(Uygulanamaz)|(Uygulanamaz)|Pencere metnini ayarlar|

Bu sınıfın kullanımı hakkında daha fazla bilgi için bkz. [User-Interface nesneleri güncelleştirme](../../mfc/how-to-update-user-interface-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CCmdUI`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="ccmduicontinuerouting"></a><a name="continuerouting"></a> CCmdUI:: Devamsallama

Komut yönlendirme mekanizmasına, geçerli iletiyi işleyici zincirinde aşağı yönlendirmeye devam etmek için bu üye işlevi çağırın.

```cpp
void ContinueRouting();
```

### <a name="remarks"></a>Açıklamalar

Bu, FALSE döndüren bir ON_COMMAND_EX işleyicisiyle birlikte kullanılması gereken gelişmiş bir üye işlevdir. Daha fazla bilgi için bkz. [teknik notta 6](../../mfc/tn006-message-maps.md).

## <a name="ccmduienable"></a><a name="enable"></a> CCmdUI:: Enable

Bu komut için Kullanıcı arabirimi öğesini etkinleştirmek veya devre dışı bırakmak için bu üye işlevini çağırın.

```
virtual void Enable(BOOL bOn = TRUE);
```

### <a name="parameters"></a>Parametreler

*Um*<br/>
Öğeyi etkinleştirmek için TRUE, devre dışı bırakmak için FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]

## <a name="ccmduim_nid"></a><a name="m_nid"></a> CCmdUI:: m_nID

Nesne tarafından temsil edilen menü öğesi, araç çubuğu düğmesi veya diğer kullanıcı arabirimi nesnesi KIMLIĞI `CCmdUI` .

```
UINT m_nID;
```

## <a name="ccmduim_nindex"></a><a name="m_nindex"></a> CCmdUI:: m_nIndex

Menü öğesi, araç çubuğu düğmesi veya nesne tarafından temsil edilen diğer kullanıcı arabirimi nesnesi dizini `CCmdUI` .

```
UINT m_nIndex;
```

## <a name="ccmduim_pmenu"></a><a name="m_pmenu"></a> CCmdUI:: m_pMenu

`CMenu`Nesne tarafından temsil edilen menüye işaretçi (türü) `CCmdUI` .

```
CMenu* m_pMenu;
```

### <a name="remarks"></a>Açıklamalar

Öğe bir menü değilse NULL.

## <a name="ccmduim_psubmenu"></a><a name="m_psubmenu"></a> CCmdUI:: m_pSubMenu

`CMenu`Nesnenin temsil ettiği içerilen alt menüye işaretçi (türü) `CCmdUI` .

```
CMenu* m_pSubMenu;
```

### <a name="remarks"></a>Açıklamalar

Öğe bir menü değilse NULL. Alt menü bir açılır pencere ise, *m_nID* açılır menüdeki Ilk öğenin kimliğini içerir. Daha fazla bilgi için bkz. [teknik notta 21](../../mfc/tn021-command-and-message-routing.md).

## <a name="ccmduim_pother"></a><a name="m_pother"></a> CCmdUI:: m_pOther

`CWnd`Bildirimi gönderen bir araç veya durum çubuğu gibi pencere nesnesine işaretçi (türü).

```
CWnd* m_pOther;
```

### <a name="remarks"></a>Açıklamalar

Öğe bir menü veya nesne olmayan bir menü ise NULL `CWnd` .

## <a name="ccmduisetcheck"></a><a name="setcheck"></a> CCmdUI:: SetCheck

Bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlamak için bu üye işlevi çağırın.

```
virtual void SetCheck(int nCheck = 1);
```

### <a name="parameters"></a>Parametreler

*Nhatayla*<br/>
Ayarlanacak denetim durumunu belirtir. 0 ise, denetimleri kaldırır; 1 ise, denetimler; 2 ise, belirsiz olarak ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, menü öğeleri ve araç çubuğu düğmeleri için çalışır. Belirsiz durum yalnızca araç çubuğu düğmeleri için geçerlidir.

## <a name="ccmduisetradio"></a><a name="setradio"></a> CCmdUI:: SetRadio

Bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlamak için bu üye işlevi çağırın.

```
virtual void SetRadio(BOOL bOn = TRUE);
```

### <a name="parameters"></a>Parametreler

*Um*<br/>
Öğeyi etkinleştirmek için TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi gibi çalışır `SetCheck` , ancak radyo grubunun bir parçası olarak davranan Kullanıcı arabirimi öğelerinde çalışır. Öğelerin kendisi radyo grubu davranışını korumadığı takdirde gruptaki diğer öğelerin işaretlenmesi otomatik değildir.

## <a name="ccmduisettext"></a><a name="settext"></a> CCmdUI:: SetText

Bu komut için Kullanıcı arabirimi öğesinin metnini ayarlamak için bu üye işlevini çağırın.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
Bir metin dizesinin işaretçisi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)
