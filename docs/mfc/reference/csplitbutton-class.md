---
title: CSplitButton Sınıfı
ms.date: 11/19/2018
f1_keywords:
- CSplitButton
- AFXCMN/CSplitButton
- AFXCMN/CSplitButton::CSplitButton
- AFXCMN/CSplitButton::Create
- AFXCMN/CSplitButton::SetDropDownMenu
- AFXCMN/CSplitButton::OnDropDown
helpviewer_keywords:
- CSplitButton [MFC], CSplitButton
- CSplitButton [MFC], Create
- CSplitButton [MFC], SetDropDownMenu
- CSplitButton [MFC], OnDropDown
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
ms.openlocfilehash: 0b54324c3c5503182add15a3dd0a9ecd07c24b18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318110"
---
# <a name="csplitbutton-class"></a>CSplitButton Sınıfı

Sınıf `CSplitButton` bölünmüş düğme denetimini temsil eder. Bölünmüş düğme denetimi, bir kullanıcı düğmenin ana bölümünü tıklattığında varsayılan bir davranış gerçekleştirir ve kullanıcı düğmenin açılır okünü tıklattığında açılır menü görüntüler.

## <a name="syntax"></a>Sözdizimi

```
class CSplitButton : public CButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSplitButton::CSplitButton](#csplitbutton)|Bir `CSplitButton` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSplitButton::Oluştur](#create)|Belirtilen stilleri içeren bölünmüş düğme denetimi oluşturur ve `CSplitButton` geçerli nesneye bağlar.|
|[CSplitButton::SetDropDownMenü](#setdropdownmenu)|Kullanıcı geçerli bölünmüş düğme denetiminin açılır oka tıkladığında görüntülenen açılır menüyü ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CsplitButton::Ondropdown](#ondropdown)|Bir kullanıcı geçerli bölme düğmesi denetiminin açılır ok'una tıkladığında sistemin gönderdiği BCN_DROPDOWN bildirimi işler.|

## <a name="remarks"></a>Açıklamalar

Sınıf `CSplitButton` [CButton](../../mfc/reference/cbutton-class.md) sınıfından türetilmiştir. Bölme düğmesi denetimi, stili BS_SPLITBUTTON olan bir düğme denetimidir. Bir kullanıcı açılır oka tıkladığında özel bir menü görüntüler. Daha fazla bilgi için [Düğme Stilleri'ndeki](/windows/win32/Controls/button-styles)BS_SPLITBUTTON ve BS_DEFSPLITBUTTON stillerine bakın.

Aşağıdaki şekilde, çağrı cihazı denetimi ve (1) bölünmüş düğme denetimi içeren bir iletişim kutusu gösterilmiştir. (2) açılır ok zaten tıklandı ve (3) alt menüsü görüntülenir.

![Splitbutton ve çağrı cihazı denetimi ile iletişim kutusu.](../../mfc/reference/media/splitbutton_pager.png "Splitbutton ve çağrı cihazı denetimi ile iletişim kutusu.")

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cbutton](../../mfc/reference/cbutton-class.md)

`CSplitButton`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

Bu sınıf Windows Vista ve daha sonra desteklenir.

Bu sınıf için ek gereksinimler [Windows Vista Ortak Denetimleri için Yapı Gereksinimleri](../../mfc/build-requirements-for-windows-vista-common-controls.md)açıklanmıştır.

## <a name="csplitbuttoncreate"></a><a name="create"></a>CSplitButton::Oluştur

Belirtilen stilleri içeren bölünmüş düğme denetimi oluşturur ve `CSplitButton` geçerli nesneye bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Dwstyle*|[içinde] Denetime uygulanacak stillerin bitwise kombinasyonu (OR). Daha fazla bilgi için [Düğme Stilleri'ne](../../mfc/reference/styles-used-by-mfc.md#button-styles)bakın.|
|*Rect*|[içinde] Denetimin konumunu ve boyutunu içeren bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.|
|*pParentWnd*|[içinde] Denetimin ana penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine null olmayan bir işaretçi.|
|*Nıd*|[içinde] Kontrol kimliği.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="csplitbuttoncsplitbutton"></a><a name="csplitbutton"></a>CSplitButton::CSplitButton

Bir `CSplitButton` nesne inşa eder. Oluşturucunun parametreleri, kullanıcı bölünmüş düğme denetiminin açılır oka bastığında görüntülenen bir alt menü belirtir.

```
CSplitButton();

CSplitButton(
    UINT nMenuId,
    UINT nSubMenuId)
CSplitButton(CMenu* pMenu)
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*nMenuId*|[içinde] Menü çubuğunun kaynak kimliği.|
|*nSubMenuId*|[içinde] Alt menünün kaynak kimliği.|
|*pMenü*|[içinde] Bir alt menü belirten bir [CMenu](../../mfc/reference/cmenu-class.md) nesnesine işaretçi. Nesne `CSplitButton` kapsam dışına `CMenu` çıktığında `CSplitButton` nesneyi ve ilişkili HMENU'yi siler.|

### <a name="remarks"></a>Açıklamalar

[CSplitButton kullanın::Bölünmüş](#create) düğme denetimi oluşturmak ve `CSplitButton` nesneye takmak için yöntem oluşturun.

## <a name="csplitbuttonondropdown"></a><a name="ondropdown"></a>CsplitButton::Ondropdown

Bir kullanıcı geçerli bölme düğmesi denetiminin açılır ok'una tıkladığında sistemin gönderdiği BCN_DROPDOWN bildirimi işler.

```
afx_msg void OnDropDown(
    NMHDR* pNMHDR,
    LRESULT* pResult);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pNMHDR*|[içinde] [BCN_DROPDOWN](/windows/win32/Controls/bcn-dropdown) bildirimi hakkında bilgi içeren bir [NMHDR](/windows/win32/api/richedit/ns-richedit-nmhdr) yapısıiçin işaretçi.|
|*pResult*|[çıkış] (Kullanılmaz; hiçbir değer döndürülür.) [BCN_DROPDOWN](/windows/win32/Controls/bcn-dropdown) bildiriminin iade değeri.|

### <a name="remarks"></a>Açıklamalar

Kullanıcı bölünmüş düğme denetiminde açılır oka tıkladığında, sistem yöntemin işlediği `OnDropDown` bir BCN_DROPDOWN bildirim iletisi gönderir. Ancak, `CSplitButton` nesne BCN_DROPDOWN bildirimini bölme düğmesi denetimini içeren denetime iletmez. Sonuç olarak, içeren denetim bildirime yanıt olarak özel bir eylemi destekleyemez.

İçerdirme denetiminin desteklediği özel bir eylemi uygulamak için, `CSplitButton` nesne yerine BS_SPLITBUTTON stili olan bir [CButton](../../mfc/reference/cbutton-class.md) nesnesi kullanın. Ardından, nesnedeki bildirimBCN_DROPDOWN için `CButton` bir işleyici uygulayın. Daha fazla bilgi için [Düğme Stilleri'ne](../../mfc/reference/styles-used-by-mfc.md#button-styles)bakın.

Bölme düğmesi denetiminin kendisinin desteklediği özel bir eylem uygulamak için [ileti yansımasını](../../mfc/tn062-message-reflection-for-windows-controls.md)kullanın. `CSplitButton` Sınıftan kendi sınıfınızı türetin ve adını, örneğin CMySplitButton. Ardından, BCN_DROPDOWN bildirimini işlemek için uygulamanıza aşağıdaki ileti eşlemi ekleyin:

```
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)
END_MESSAGE_MAP()
```

## <a name="csplitbuttonsetdropdownmenu"></a><a name="setdropdownmenu"></a>CSplitButton::SetDropDownMenü

Kullanıcı geçerli bölünmüş düğme denetiminin açılır oka tıkladığında görüntülenen açılır menüyü ayarlar.

```
void SetDropDownMenu(
    UINT nMenuId,
    UINT nSubMenuId);

void SetDropDownMenu(CMenu* pMenu);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*nMenuId*|[içinde] Menü çubuğunun kaynak kimliği.|
|*nSubMenuId*|[içinde] Alt menünün kaynak kimliği.|
|*pMenü*|[içinde] Alt menüyü belirten bir [CMenu](../../mfc/reference/cmenu-class.md) nesnesine işaretçi. Nesne `CSplitButton` kapsam dışına `CMenu` çıktığında `CSplitButton` nesneyi ve ilişkili HMENU'yi siler.|

### <a name="remarks"></a>Açıklamalar

*nMenuId* parametresi, menü çubuğu öğelerinin yatay bir listesi olan bir menü çubuğunu tanımlar. *nSubMenuId* parametresi, her menü çubuğu öğesiyle ilişkili menü öğelerinin açılır listesi olan bir alt menüyü tanımlayan sıfır tabanlı bir dizin numarasıdır. Örneğin, tipik bir uygulamanın menü çubuğu öğelerini içeren bir menüsü vardır, "Dosya", "Edit" ve "Yardım" "Dosya" menü çubuğu öğesi, "Aç", "Kapat" ve "Çıkış" menü öğelerini içeren bir alt menüye sahiptir. Bölme düğmesinin açılır ok tıklatıldığında, denetim menü çubuğunu değil, belirtilen alt menüyü görüntüler.

Aşağıdaki şekilde, çağrı cihazı denetimi ve (1) bölünmüş düğme denetimi içeren bir iletişim kutusu gösterilmiştir. (2) açılır ok zaten tıklandı ve (3) alt menüsü görüntülenir.

![Splitbutton ve çağrı cihazı denetimi ile iletişim kutusu.](../../mfc/reference/media/splitbutton_pager.png "Splitbutton ve çağrı cihazı denetimi ile iletişim kutusu.")

### <a name="example"></a>Örnek

Aşağıdaki kod örneğindeki ilk ifade [CSplitButton::SetDropDownMenu](#setdropdownmenu) yöntemini gösterir. Menüyü Visual Studio kaynak editörüyle oluşturduk, bu menü otomatik olarak menü çubuğu kimliği, IDR_MENU1. Sıfır olan *nSubMenuId* parametresi, menü çubuğunun tek alt menüsünü ifade eder.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CSplitButton Sınıfı](../../mfc/reference/csplitbutton-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CButton Sınıfı](../../mfc/reference/cbutton-class.md)
