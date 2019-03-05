---
title: Ccmduı sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 12d9ead736a84d89b04f7b68ed76da8ccea22d0c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302883"
---
# <a name="ccmdui-class"></a>Ccmduı sınıfı

Yalnızca kullanılan bir `ON_UPDATE_COMMAND_UI` işleyicisinde bir `CCmdTarget`-türetilmiş sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CCmdUI
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCmdUI::ContinueRouting](#continuerouting)|Aşağı zinciri işleyicileri geçerli ileti yönlendirme devam etmek için komut yönlendirme mekanizması söyler.|
|[CCmdUI::Enable](#enable)|Sağlar veya bu komut için kullanıcı arabirimi öğesi devre dışı bırakır.|
|[CCmdUI::SetCheck](#setcheck)|Bu komut için kullanıcı arabirimi öğesi onay durumunu ayarlar.|
|[CCmdUI::SetRadio](#setradio)|Gibi `SetCheck` üye işlevi, ancak radyo grupları üzerinde çalışır.|
|[CCmdUI::SetText](#settext)|Bu komut için kullanıcı arabirimi öğesi için metin ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CCmdUI::m_nID](#m_nid)|Kullanıcı arabirimi nesnesinin kimliği.|
|[CCmdUI::m_nIndex](#m_nindex)|Kullanıcı arabirimi nesnesi dizini.|
|[CCmdUI::m_pMenu](#m_pmenu)|Tarafından temsil edilen menü işaret `CCmdUI` nesne.|
|[CCmdUI::m_pOther](#m_pother)|Bildirim gönderilen pencere nesnesi işaret eder.|
|[CCmdUI::m_pSubMenu](#m_psubmenu)|Tarafından temsil edilen Kapsanan alt menüsünü işaret `CCmdUI` nesne.|

## <a name="remarks"></a>Açıklamalar

`CCmdUI` bir temel sınıfa sahip değil.

Olduğunda, uygulamanızın bir kullanıcı, her, etkin olarak görüntülenmesi gerekip gerekmediğini öğrenmek için menü öğesi gereksinimlerini veya devre dışı bir menüyü çeker. Menü komut hedefinin on_update_command_uı işleyici uygulayarak bu bilgileri sağlar. Her komut kullanıcı arabirimi nesneleri, uygulamanızdaki bir ileti eşleme girişi ve işlev prototipi her işleyicisi oluşturmak için Özellikler penceresini kullanın.

Menüyü çekildiğinde framework arar ve her on_update_command_uı işleyici çağırır, her bir işleyici çağırır `CCmdUI` üye işlevleri gibi `Enable` ve `Check`, ve framework uygun şekilde her bir menü öğesi görüntüler.

Bir menü öğesi bir denetim çubuğu düğme ya da diğer komut kullanıcı arabirimi nesnesi içindeki kod değişikliği yapmadan değiştirilebilir `ON_UPDATE_COMMAND_UI` işleyici.

Aşağıdaki tabloda özetlenmiştir etkisi `CCmdUI`kullanıcının olmayan üye işlevleri çeşitli komutu kullanıcı arabirimi öğeleri.

|Kullanıcı arabirimi öğesi|Etkinleştir|SetCheck|SetRadio|SetText|
|--------------------------|------------|--------------|--------------|-------------|
|Menü öğesi|Etkinleştirir veya devre dışı bırakır|Denetler veya temizler|Bir nokta kullanarak denetler|Metin ayarlar öğesi|
|Araç çubuğu düğmesi|Etkinleştirir veya devre dışı bırakır|Seçer, seçili olanları kaldırdığında, veya belirsiz|Aynı `SetCheck`|(Uygulanamaz)|
|Durum çubuğu bölmesi|Görünür veya gizli metni|Ayarlar açılır ya da normal kenarlık|Aynı `SetCheck`|Ayarlar bölmesinde metin|
|Normal bir düğme `CDialogBar`|Etkinleştirir veya devre dışı bırakır|Denetler veya onay kutusunu temizler|Aynı `SetCheck`|Metin Ayarlar düğmesi|
|Normal denetiminde `CDialogBar`|Etkinleştirir veya devre dışı bırakır|(Uygulanamaz)|(Uygulanamaz)|Pencere metni ayarlar|

Bu sınıf kullanımı hakkında daha fazla bilgi için bkz. [kullanıcı arabirimi nesnelerini güncelleştirme](../../mfc/how-to-update-user-interface-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CCmdUI`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="continuerouting"></a>  CCmdUI::ContinueRouting

Aşağı zinciri işleyicileri geçerli ileti yönlendirme devam etmek için komut yönlendirme mekanizması bildirmek için bu üye işlevini çağırın.

```
void ContinueRouting();
```

### <a name="remarks"></a>Açıklamalar

FALSE döndüren bir ON_COMMAND_EX işleyicisi ile birlikte kullanılması gereken bir Gelişmiş üye işlev budur. Daha fazla bilgi için [Teknik Not 6](../../mfc/tn006-message-maps.md).

##  <a name="enable"></a>  CCmdUI::Enable

Etkinleştirme veya devre dışı kullanıcı arabirimi öğesi bu komut için bu üye işlevini çağırın.

```
virtual void Enable(BOOL bOn = TRUE);
```

### <a name="parameters"></a>Parametreler

*İyi*<br/>
Öğeyi devre dışı bırakmak için FALSE etkinleştirmek için TRUE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]

##  <a name="m_nid"></a>  CCmdUI::m_nID

Menü öğesi, araç çubuğu düğmesini veya diğer kullanıcı arabirimi nesnesi tarafından temsil edilen kimliği `CCmdUI` nesne.

```
UINT m_nID;
```

##  <a name="m_nindex"></a>  CCmdUI::m_nIndex

Menü öğesi, araç çubuğu düğmesini veya diğer kullanıcı arabirimi nesnesi tarafından temsil edilen dizinini `CCmdUI` nesne.

```
UINT m_nIndex;
```

##  <a name="m_pmenu"></a>  CCmdUI::m_pMenu

İşaretçi (biri `CMenu` türü) tarafından temsil edilen menüsüne `CCmdUI` nesne.

```
CMenu* m_pMenu;
```

### <a name="remarks"></a>Açıklamalar

Bir menü değilse null değerini DÖNDÜRÜR.

##  <a name="m_psubmenu"></a>  CCmdUI::m_pSubMenu

İşaretçi (biri `CMenu` türü) Kapsanan alt menüsü tarafından temsil edilen `CCmdUI` nesne.

```
CMenu* m_pSubMenu;
```

### <a name="remarks"></a>Açıklamalar

Bir menü değilse null değerini DÖNDÜRÜR. Alt menü bir açılır pencere ise *m_nID* ilk açılan menü öğesi Kimliğini içerir. Daha fazla bilgi için [Teknik Not 21](../../mfc/tn021-command-and-message-routing.md).

##  <a name="m_pother"></a>  CCmdUI::m_pOther

İşaretçi (tür `CWnd`), bir aracı veya durum çubuğu gibi pencere nesnesi için bildirim gönderilir.

```
CWnd* m_pOther;
```

### <a name="remarks"></a>Açıklamalar

Öğe bir menü veya olmayan bir yoksa NULL `CWnd` nesne.

##  <a name="setcheck"></a>  CCmdUI::SetCheck

Bu komut için kullanıcı arabirimi öğesi için uygun denetim durumu ayarlamak için bu üye işlevini çağırın.

```
virtual void SetCheck(int nCheck = 1);
```

### <a name="parameters"></a>Parametreler

*Nbakım*<br/>
Ayarlanacak denetim durumu belirtir. 0, temizler, 1 denetler; ve 2 değilse, belirsiz ayarlar.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, menü öğeleri ve araç çubuğu düğmeleri için çalışır. Belirlenmemiş duruma yalnızca araç çubuğu düğmeleri için geçerlidir.

##  <a name="setradio"></a>  CCmdUI::SetRadio

Bu komut için kullanıcı arabirimi öğesi için uygun denetim durumu ayarlamak için bu üye işlevini çağırın.

```
virtual void SetRadio(BOOL bOn = TRUE);
```

### <a name="parameters"></a>Parametreler

*İyi*<br/>
Öğesini etkinleştirmek için TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi gibi çalışan `SetCheck`dışında radyo grubunun bir parçası görev yapan kullanıcı arabirimi öğeleri üzerinde çalışır. Gruptaki diğer öğeler kaldırılırsa, öğeleri Grup radyo davranışı korumak sürece otomatik değildir.

##  <a name="settext"></a>  CCmdUI::SetText

Bu komut için kullanıcı arabirimi öğesinin metnini ayarlamak için bu üye işlevini çağırın.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
Bir metin dizesi için bir işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)
