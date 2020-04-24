---
title: CCmdUI Sınıfı
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
ms.openlocfilehash: 3e167d9e305481e05808f5e553222c10abbc88de
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752732"
---
# <a name="ccmdui-class"></a>CCmdUI Sınıfı

Yalnızca türetilmiş `ON_UPDATE_COMMAND_UI` bir `CCmdTarget`sınıfta ki bir işleyici içinde kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class CCmdUI
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CCmdUI::Devam Routing](#continuerouting)|Komut yönlendirme mekanizmasını, geçerli iletiyi işleyiciler zincirinden yönlendirmeye devam etmesini söyler.|
|[CCmdUI::Etkinleştir](#enable)|Bu komut için kullanıcı arabirimi öğesini etkinleştirir veya devre dışı kılabilir.|
|[CCmdUI::SetCheck](#setcheck)|Bu komut için kullanıcı arabirimi öğesinin denetim durumunu ayarlar.|
|[CCmdUI::SetRadio](#setradio)|`SetCheck` Üye işlev gibi, ancak radyo grupları üzerinde çalışır.|
|[CCmdUI::SetText](#settext)|Bu komut için kullanıcı arabirimi öğesiiçin metni ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CCmdUI::m_nID](#m_nid)|Kullanıcı arabirimi nesnesinin kimliği.|
|[CCmdUI::m_nIndex](#m_nindex)|Kullanıcı arabirimi nesnesinin dizin.|
|[CCmdUI::m_pMenu](#m_pmenu)|Nesne tarafından temsil edilen `CCmdUI` menüye işaret ediyor.|
|[CCmdUI::m_pOther](#m_pother)|Bildirimi gönderen pencere nesnesini işaret ediyor.|
|[CCmdUI::m_pSubMenu](#m_psubmenu)|Nesne tarafından temsil edilen içerdiği alt `CCmdUI` menüye işaret ediyor.|

## <a name="remarks"></a>Açıklamalar

`CCmdUI`taban sınıfa sahip değildir.

Uygulamanızın bir kullanıcısı bir menü çektiğinde, her menü öğesinin etkin veya devre dışı bırakılmış olarak görüntülenip görüntülenmemesi gerektiğini bilmesi gerekir. Bir menü komutunun hedefi, bir ON_UPDATE_COMMAND_UI işleyicisi uygulayarak bu bilgileri sağlar. Uygulamanızdaki komut kullanıcı arabirimi nesnelerinin her biri için, her işleyici için bir ileti eşlemi girişi ve işlev prototipi oluşturmak için [Sınıf Sihirbazı](mfc-class-wizard.md) veya **Özellikler** penceresini **(Sınıf Görünümünde)** kullanın.

Menü aşağı çekildiğinde, çerçeve arar ve her ON_UPDATE_COMMAND_UI işleyiciçağırır, `CCmdUI` her işleyici `Enable` `Check`gibi üye işlevleri çağırır ve , ve çerçeve sonra uygun her menü öğesi görüntüler.

Menü öğesi, `ON_UPDATE_COMMAND_UI` işleyici içindeki kodu değiştirmeden bir denetim çubuğu düğmesi veya başka bir komut kullanıcı arabirimi nesnesi ile değiştirilebilir.

Aşağıdaki tablo, 'üye `CCmdUI`işlevlerin çeşitli komut kullanıcı arabirimi öğeleri üzerindeki etkisini özetler.

|Kullanıcı Arabirimi Öğesi|Etkinleştirme|SetCheck|SetRadyo|SetText|
|--------------------------|------------|--------------|--------------|-------------|
|Menü öğesi|Etkinleştirir veya devre dışı|Çekler veya denetimleri geri al|Nokta kullanarak denetler|Madde metnini ayarlar|
|Araç çubuğu düğmesi|Etkinleştirir veya devre dışı|Seçer, seçer veya belirsiz|Aynı`SetCheck`|(Geçerli değildir)|
|Durum çubuğu bölmesi|Metni görünür veya görünmez yapar|Açılır veya normal kenarlık ayarlar|Aynı`SetCheck`|Bölme metnini ayarlar|
|Normal düğme`CDialogBar`|Etkinleştirir veya devre dışı|Onay kutusunu denetleme veya geri denetleme|Aynı`SetCheck`|Düğme metnini ayarlar|
|Normal kontrol`CDialogBar`|Etkinleştirir veya devre dışı|(Geçerli değildir)|(Geçerli değildir)|Pencere metnini ayarlar|

Bu sınıfın kullanımı hakkında daha fazla bilgi [için, Kullanıcı Arabirimi Nesneleri Nasıl Güncellenir](../../mfc/how-to-update-user-interface-objects.md)bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CCmdUI`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="ccmduicontinuerouting"></a><a name="continuerouting"></a>CCmdUI::Devam Routing

Komut yönlendirme mekanizmasına geçerli iletiyi işleyiciler zincirinden yönlendirmeye devam etmesini söylemek için bu üye işlevi arayın.

```cpp
void ContinueRouting();
```

### <a name="remarks"></a>Açıklamalar

Bu, FALSE döndüren bir ON_COMMAND_EX işleyicisi ile birlikte kullanılması gereken gelişmiş bir üye işlevdir. Daha fazla bilgi için [Teknik Not 6'ya](../../mfc/tn006-message-maps.md)bakın.

## <a name="ccmduienable"></a><a name="enable"></a>CCmdUI::Etkinleştir

Bu komutun kullanıcı arabirimi öğesini etkinleştirmek veya devre dışı etmek için bu üye işlevini çağırın.

```
virtual void Enable(BOOL bOn = TRUE);
```

### <a name="parameters"></a>Parametreler

*Bon*<br/>
DOĞRU öğeyi etkinleştirmek için, FALSE onu devre dışı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]

## <a name="ccmduim_nid"></a><a name="m_nid"></a>CCmdUI::m_nID

Menü öğesinin kimliği, araç çubuğu düğmesi veya nesne tarafından temsil `CCmdUI` edilen diğer kullanıcı arabirimi nesnesi.

```
UINT m_nID;
```

## <a name="ccmduim_nindex"></a><a name="m_nindex"></a>CCmdUI::m_nIndex

Menü öğesinin, araç çubuğu düğmesinin veya nesne tarafından temsil `CCmdUI` edilen diğer kullanıcı arabirimi nesnesinin dizini.

```
UINT m_nIndex;
```

## <a name="ccmduim_pmenu"></a><a name="m_pmenu"></a>CCmdUI::m_pMenu

Nesne tarafından `CMenu` temsil edilen menüye işaretçi (tür). `CCmdUI`

```
CMenu* m_pMenu;
```

### <a name="remarks"></a>Açıklamalar

Öğe menü değilse NULL.

## <a name="ccmduim_psubmenu"></a><a name="m_psubmenu"></a>CCmdUI::m_pSubMenu

Nesne tarafından `CMenu` temsil edilen içerdiği alt menüye işaretçi (tür). `CCmdUI`

```
CMenu* m_pSubMenu;
```

### <a name="remarks"></a>Açıklamalar

Öğe menü değilse NULL. Alt menü açılır pencereise, *m_nID* açılır menüdeki ilk öğenin kimliğini içerir. Daha fazla bilgi için [Teknik Not 21'e](../../mfc/tn021-command-and-message-routing.md)bakın.

## <a name="ccmduim_pother"></a><a name="m_pother"></a>CCmdUI::m_pOther

Bildirimi gönderen `CWnd`bir araç veya durum çubuğu gibi pencere nesnesine işaretçi (tür).

```
CWnd* m_pOther;
```

### <a name="remarks"></a>Açıklamalar

Öğe bir menü veya `CWnd` nesne olmayan bir öğeyse NULL.

## <a name="ccmduisetcheck"></a><a name="setcheck"></a>CCmdUI::SetCheck

Bu komutiçin kullanıcı arabirimi öğesini uygun denetim durumuna ayarlamak için bu üye işlevini çağırın.

```
virtual void SetCheck(int nCheck = 1);
```

### <a name="parameters"></a>Parametreler

*nCheck*<br/>
Ayarlanacak çek durumunu belirtir. 0 ise, çekleri unchecks; eğer 1, kontrol eder; ve eğer 2, belirsiz ayarlar.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev menü öğeleri ve araç çubuğu düğmeleri için çalışır. Belirsiz durum yalnızca araç çubuğu düğmeleri için geçerlidir.

## <a name="ccmduisetradio"></a><a name="setradio"></a>CCmdUI::SetRadio

Bu komutiçin kullanıcı arabirimi öğesini uygun denetim durumuna ayarlamak için bu üye işlevini çağırın.

```
virtual void SetRadio(BOOL bOn = TRUE);
```

### <a name="parameters"></a>Parametreler

*Bon*<br/>
Maddeyi etkinleştirmek için TRUE; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu üye `SetCheck`işlev, bir radyo grubunun parçası olarak hareket eden kullanıcı arabirimi öğeleri üzerinde çalışması dışında çalışır. Öğelerin kendileri radyo grubu davranışını korumadıkça, gruptaki diğer öğelerin denetimini açma otomatik değildir.

## <a name="ccmduisettext"></a><a name="settext"></a>CCmdUI::SetText

Bu komut için kullanıcı arabirimi öğesinin metnini ayarlamak için bu üye işlevini çağırın.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
Metin dizesine işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)
