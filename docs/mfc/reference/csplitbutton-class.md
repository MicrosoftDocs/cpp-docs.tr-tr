---
description: 'Daha fazla bilgi edinin: CSplitButton sınıfı'
title: CSplitButton sınıfı
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
ms.openlocfilehash: e73273bbeb0d03dc5ca2a3a2e6daa1be05936280
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345127"
---
# <a name="csplitbutton-class"></a>CSplitButton sınıfı

`CSplitButton`Sınıfı bir bölünmüş düğme denetimini temsil eder. Bölünmüş düğme denetimi, bir Kullanıcı düğmenin ana kısmına tıkladığında varsayılan bir davranış gerçekleştirir ve bir Kullanıcı düğmenin aşağı açılan okuna tıkladığında bir açılan menü görüntüler.

## <a name="syntax"></a>Syntax

```
class CSplitButton : public CButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSplitButton:: CSplitButton](#csplitbutton)|Bir `CSplitButton` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSplitButton:: Create](#create)|Belirtilen stillerle bir bölünmüş düğme denetimi oluşturur ve geçerli `CSplitButton` nesneye ekler.|
|[CSplitButton:: SetDropDownMenu](#setdropdownmenu)|Kullanıcı geçerli bölünmüş düğme denetiminin aşağı açılan okuna tıkladığında görüntülenen açılan menüyü ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSplitButton:: OnDropDown](#ondropdown)|Bir Kullanıcı geçerli bölünmüş düğme denetiminin aşağı açılan okuna tıkladığında sistemin gönderdiği BCN_DROPDOWN bildirimini işler.|

## <a name="remarks"></a>Açıklamalar

`CSplitButton`Sınıfı [CButton](../../mfc/reference/cbutton-class.md) sınıfından türetilir. Bölünmüş düğme denetimi, stili BS_SPLITBUTTON olan bir düğme denetimidir. Kullanıcı açılır oka tıkladığında bir özel menü görüntüler. Daha fazla bilgi için bkz. [düğme stillerinde](/windows/win32/Controls/button-styles)BS_SPLITBUTTON ve BS_DEFSPLITBUTTON stilleri.

Aşağıdaki şekilde, bir sayfalayıcı denetimi ve (1) bölünmüş düğme denetimi içeren bir iletişim kutusu gösterilmektedir. (2) aşağı açılan oka zaten tıklandı ve (3) alt menüsü gösteriliyor.

![SplitButton ve sayfalayıcı denetimiyle iletişim kutusu.](../../mfc/reference/media/splitbutton_pager.png "SplitButton ve sayfalayıcı denetimiyle iletişim kutusu.")

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CSplitButton`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

Bu sınıf Windows Vista ve sonraki sürümlerde desteklenir.

Bu sınıf için ek gereksinimler, [Windows Vista ortak denetimleri Için derleme gereksinimleri](../../mfc/build-requirements-for-windows-vista-common-controls.md)bölümünde açıklanmaktadır.

## <a name="csplitbuttoncreate"></a><a name="create"></a> CSplitButton:: Create

Belirtilen stillerle bir bölünmüş düğme denetimi oluşturur ve geçerli `CSplitButton` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*\
'ndaki Denetime uygulanacak stillerin bit tabanlı birleşimi (veya). Daha fazla bilgi için bkz. [düğme stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles).

*Rect*\
'ndaki Denetimin konumunu ve boyutunu içeren bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*\
'ndaki Denetimin üst penceresi olan bir [CWnd](../../mfc/reference/cwnd-class.md) nesnesine null olmayan bir işaretçi.

*NID*\
'ndaki Denetimin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

## <a name="csplitbuttoncsplitbutton"></a><a name="csplitbutton"></a> CSplitButton:: CSplitButton

Bir `CSplitButton` nesnesi oluşturur. Oluşturucunun parametreleri, Kullanıcı bölünmüş düğme denetiminin aşağı açılan okuna tıkladığında görüntülenen bir alt menü belirler.

```
CSplitButton();

CSplitButton(
    UINT nMenuId,
    UINT nSubMenuId)
CSplitButton(CMenu* pMenu)
```

### <a name="parameters"></a>Parametreler

*nMenuId*\
'ndaki Menü çubuğunun kaynak KIMLIĞI.

*nSubMenuId*\
'ndaki Bir alt menünün kaynak KIMLIĞI.

*pMenu*\
'ndaki Bir alt menüyü belirten bir [CMenu](../../mfc/reference/cmenu-class.md) nesnesine yönelik işaretçi. Nesne `CSplitButton` `CMenu` kapsam dışına geçtiğinde nesne nesneyi ve ILIŞKILI HMENU 'yi siler `CSplitButton` .

### <a name="remarks"></a>Açıklamalar

Bir Split Button denetimi oluşturmak ve nesneye iliştirmek için [CSplitButton:: Create](#create) metodunu kullanın `CSplitButton` .

## <a name="csplitbuttonondropdown"></a><a name="ondropdown"></a> CSplitButton:: OnDropDown

Bir Kullanıcı geçerli bölünmüş düğme denetiminin aşağı açılan okuna tıkladığında sistemin gönderdiği BCN_DROPDOWN bildirimini işler.

```
afx_msg void OnDropDown(
    NMHDR* pNMHDR,
    LRESULT* pResult);
```

### <a name="parameters"></a>Parametreler

*pNMHDR*\
'ndaki [BCN_DROPDOWN](/windows/win32/Controls/bcn-dropdown) bildirimiyle ilgili bilgiler Içeren bir [nmhdr](/windows/win32/api/richedit/ns-richedit-nmhdr) yapısına yönelik işaretçi.

*pResult*\
dışı (Kullanılmıyor; değer döndürülmedi.) [BCN_DROPDOWN](/windows/win32/Controls/bcn-dropdown) bildiriminin dönüş değeri.

### <a name="remarks"></a>Açıklamalar

Kullanıcı bölünmüş düğme denetimindeki aşağı açılan oka tıkladığında, sistem yöntemin işleyeceği bir BCN_DROPDOWN bildirim iletisi gönderir `OnDropDown` . Ancak, `CSplitButton` nesne BCN_DROPDOWN bildirimini bölünmüş düğme denetimini içeren denetime iletmez. Sonuç olarak, kapsayan denetim bildirime yanıt olarak özel bir eylemi desteklemez.

İçeren denetimin desteklediği özel bir eylem uygulamak için, bir nesne yerine BS_SPLITBUTTON stili olan bir [CButton](../../mfc/reference/cbutton-class.md) nesnesi kullanın `CSplitButton` . Ardından nesnedeki BCN_DROPDOWN bildirimi için bir işleyici uygulayın `CButton` . Daha fazla bilgi için bkz. [düğme stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles).

Bölünmüş düğme denetiminin kendisi tarafından desteklenen özel bir eylem uygulamak için [ileti yansıması](../../mfc/tn062-message-reflection-for-windows-controls.md)' nı kullanın. Sınıfından kendi sınıfınızı türetebilir `CSplitButton` ve örneğin, CMySplitButton gibi adlandırın. Sonra BCN_DROPDOWN bildirimi işlemek için aşağıdaki ileti haritasını uygulamanıza ekleyin:

```
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)
END_MESSAGE_MAP()
```

## <a name="csplitbuttonsetdropdownmenu"></a><a name="setdropdownmenu"></a> CSplitButton:: SetDropDownMenu

Kullanıcı geçerli bölünmüş düğme denetiminin aşağı açılan okuna tıkladığında görüntülenen açılan menüyü ayarlar.

```cpp
void SetDropDownMenu(
    UINT nMenuId,
    UINT nSubMenuId);

void SetDropDownMenu(CMenu* pMenu);
```

### <a name="parameters"></a>Parametreler

*nMenuId*\
'ndaki Menü çubuğunun kaynak KIMLIĞI.

*nSubMenuId*\
'ndaki Bir alt menünün kaynak KIMLIĞI.

*pMenu*\
'ndaki Bir alt menüyü belirten bir [CMenu](../../mfc/reference/cmenu-class.md) nesnesine yönelik işaretçi. Nesne `CSplitButton` `CMenu` kapsam dışına geçtiğinde nesne nesneyi ve ILIŞKILI HMENU 'yi siler `CSplitButton` .

### <a name="remarks"></a>Açıklamalar

*Nmenuid* parametresi, menü çubuğu öğelerinin yatay bir listesi olan bir menü çubuğunu tanımlar. *Nsubmenuid* parametresi, her menü çubuğu öğesiyle ilişkili menü öğelerinin açılan listesi olan bir alt menüyü tanımlayan sıfır tabanlı bir dizin numarasıdır. Örneğin, tipik bir uygulamanın menü çubuğu öğelerini, "dosya" "" Düzenle "ve" yardım "içeren bir menüsü vardır. "Dosya" menü çubuğu öğesi menü öğelerini içeren bir alt menüye sahiptir, "Aç", "Close" ve "Exit". Bölünmüş düğme denetiminin aşağı açılan okuna tıklandığında, denetim menü çubuğunu değil, belirtilen alt menüyü görüntüler.

Aşağıdaki şekilde, bir sayfalayıcı denetimi ve (1) bölünmüş düğme denetimi içeren bir iletişim kutusu gösterilmektedir. (2) aşağı açılan oka zaten tıklandı ve (3) alt menüsü gösteriliyor.

![SplitButton ve sayfalayıcı denetimiyle iletişim kutusu.](../../mfc/reference/media/splitbutton_pager.png "SplitButton ve sayfalayıcı denetimiyle iletişim kutusu.")

### <a name="example"></a>Örnek

Aşağıdaki kod örnekteki ilk ifadede [CSplitButton:: SetDropDownMenu](#setdropdownmenu) yöntemi gösterilmektedir. Menü çubuğu KIMLIĞI IDR_MENU1 otomatik olarak adlandırılan Visual Studio kaynak Düzenleyicisi ile menüyü oluşturduk. Sıfır olan *Nsubmenuid* parametresi, menü çubuğunun tek alt menüsüne başvurur.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CSplitButton sınıfı](../../mfc/reference/csplitbutton-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CButton sınıfı](../../mfc/reference/cbutton-class.md)
