---
description: 'Daha fazla bilgi edinin: CDialogBar sınıfı'
title: CDialogBar sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
helpviewer_keywords:
- CDialogBar [MFC], CDialogBar
- CDialogBar [MFC], Create
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
ms.openlocfilehash: 7feb31cd8152309557a398f5c8d0edb8d91c340e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185225"
---
# <a name="cdialogbar-class"></a>CDialogBar sınıfı

Bir denetim çubuğundaki Windows kalıcı olmayan iletişim kutusunun işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class CDialogBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDialogBar:: CDialogBar](#cdialogbar)|Bir `CDialogBar` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDialogBar:: Create](#create)|Bir Windows iletişim kutusu oluşturur ve bu çubuğu nesnesine ekler `CDialogBar` .|

## <a name="remarks"></a>Açıklamalar

İletişim kutusu bir iletişim kutusuna benzer ve bu, kullanıcının aralarında sekme olarak kullanabileceğiniz standart Windows denetimlerini içerir. Diğer bir benzerliği, iletişim çubuğunu temsil eden bir iletişim kutusu şablonu oluşturmaktır.

İletişim çubuğu oluşturma ve kullanma, bir nesne oluşturmaya ve kullanmaya benzer `CFormView` . İlk olarak, WS_CHILD stil içeren bir iletişim şablonu tanımlamak için [iletişim düzenleyicisini](../../windows/dialog-editor.md) kullanın ve başka stil kullanmayın. Şablon WS_VISIBLE stil içermemelidir. Uygulama kodunuzda, nesneyi oluşturmak için oluşturucuyu çağırın `CDialogBar` , ardından `Create` iletişim kutusu penceresi oluşturma ve nesneye iliştirme öğesini çağırın `CDialogBar` .

Hakkında daha fazla bilgi için `CDialogBar` bkz. [İletişim çubukları](../../mfc/dialog-bars.md) ve [teknik notta 31](../../mfc/tn031-control-bars.md). denetim çubukları.

> [!NOTE]
> Geçerli sürümde, bir `CDialogBar` nesne Windows Forms denetimleri barındıramaz. Visual C++ Windows Forms denetimleri hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CDialogBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

## <a name="cdialogbarcdialogbar"></a><a name="cdialogbar"></a> CDialogBar:: CDialogBar

Bir `CDialogBar` nesnesi oluşturur.

```
CDialogBar();
```

## <a name="cdialogbarcreate"></a><a name="create"></a> CDialogBar:: Create

Veya tarafından belirtilen iletişim kutusu kaynak şablonunu yükler `lpszTemplateName` `nIDTemplate` , iletişim çubuğu penceresini oluşturur, stilini ayarlar ve `CDialogBar` nesnesiyle ilişkilendirir.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID);

virtual BOOL Create(
    CWnd* pParentWnd,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Üst nesneye yönelik bir işaretçi `CWnd` .

*lpszTemplateName*<br/>
`CDialogBar`Nesnenin iletişim kutusu kaynak şablonunun adı için bir işaretçi.

*nStyle*<br/>
Araç çubuğu stili. Desteklenen ek araç çubuğu stilleri şunlardır:

- CBRS_TOP denetim çubuğu, çerçeve penceresinin en üstünde.

- CBRS_BOTTOM denetim çubuğu, çerçeve penceresinin en altında.

- Üst yeniden boyutlandırıldığında CBRS_NOALIGN denetim çubuğu yeniden konumlandırılmaz.

- CBRS_TOOLTIPS denetim çubuğu araç ipuçlarını görüntüler.

- CBRS_SIZE_DYNAMIC denetim çubuğu dinamiktir.

- CBRS_SIZE_FIXED denetim çubuğu düzeltildi.

- CBRS_FLOATING denetim çubuğu kayar.

- CBRS_FLYBY durum çubuğunda düğme hakkında bilgi görüntülenir.

- CBRS_HIDE_INPLACE denetim çubuğu kullanıcıya gösterilmez.

*NID*<br/>
İletişim çubuğunun denetim KIMLIĞI.

*Nıdtemplate*<br/>
`CDialogBar`Nesnenin iletişim kutusu şablonunun kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

CBRS_TOP veya CBRS_BOTTOM hizalama stilini belirtirseniz, iletişim çubuğunun genişliği, çerçeve penceresinin ve yüksekliğinin *Nıdtemplate* tarafından belirtilen kaynağın bulunduğu yer olur. CBRS_LEFT veya CBRS_RIGHT hizalama stilini belirtirseniz, iletişim çubuğunun yüksekliği, çerçeve penceresinin ve genişliğinin *Nıdtemplate* tarafından belirtilen kaynağın bulunduğu yer olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CControlBar sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFormView sınıfı](../../mfc/reference/cformview-class.md)<br/>
[CControlBar sınıfı](../../mfc/reference/ccontrolbar-class.md)
