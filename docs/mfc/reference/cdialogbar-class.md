---
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
ms.openlocfilehash: af84c5239a9cb3cbddb1ab4f0230e5b1a3373573
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78883635"
---
# <a name="cdialogbar-class"></a>CDialogBar sınıfı

Bir denetim çubuğundaki Windows kalıcı olmayan iletişim kutusunun işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CDialogBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDialogBar:: CDialogBar](#cdialogbar)|`CDialogBar` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDialogBar:: Create](#create)|Bir Windows iletişim kutusu oluşturur ve onu `CDialogBar` nesnesine ekler.|

## <a name="remarks"></a>Açıklamalar

İletişim kutusu bir iletişim kutusuna benzer ve bu, kullanıcının aralarında sekme olarak kullanabileceğiniz standart Windows denetimlerini içerir. Diğer bir benzerliği, iletişim çubuğunu temsil eden bir iletişim kutusu şablonu oluşturmaktır.

Bir iletişim çubuğu oluşturma ve kullanma, `CFormView` nesnesi oluşturmaya ve kullanmaya benzer. İlk olarak, WS_CHILD stil içeren bir iletişim şablonu tanımlamak için [iletişim düzenleyicisini](../../windows/dialog-editor.md) kullanın ve başka stil kullanmayın. Şablon WS_VISIBLE stil içermemelidir. Uygulama kodunuzda `CDialogBar` nesnesini oluşturmak için oluşturucuyu çağırın, sonra iletişim kutusu penceresini oluşturmak ve `CDialogBar` nesnesine eklemek için `Create` çağırın.

`CDialogBar`hakkında daha fazla bilgi için bkz. [Iletişim çubukları](../../mfc/dialog-bars.md) ve [teknik notta 31](../../mfc/tn031-control-bars.md). denetim çubukları.

> [!NOTE]
>  Geçerli sürümde, bir `CDialogBar` nesnesi Windows Forms denetimleri barındıraamaz. Görseldeki C++Windows Forms denetimleri hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CDialogBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

##  <a name="cdialogbar"></a>CDialogBar:: CDialogBar

`CDialogBar` nesnesi oluşturur.

```
CDialogBar();
```

##  <a name="create"></a>CDialogBar:: Create

`lpszTemplateName` veya `nIDTemplate`tarafından belirtilen iletişim kutusu kaynak şablonunu yükler, iletişim çubuğu penceresini oluşturur, stilini ayarlar ve `CDialogBar` nesnesiyle ilişkilendirir.

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
Üst `CWnd` nesnesine yönelik bir işaretçi.

*lpszTemplateName*<br/>
`CDialogBar` nesnenin iletişim kutusu kaynak şablonunun adı için bir işaretçi.

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
`CDialogBar` nesnenin iletişim kutusu şablonunun kaynak KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

CBRS_TOP veya CBRS_BOTTOM hizalama stilini belirtirseniz, iletişim çubuğunun genişliği, çerçeve penceresinin ve yüksekliğinin *Nıdtemplate*tarafından belirtilen kaynağın bulunduğu yer olur. CBRS_LEFT veya CBRS_RIGHT hizalama stilini belirtirseniz, iletişim çubuğunun yüksekliği, çerçeve penceresinin ve genişliğinin *Nıdtemplate*tarafından belirtilen kaynağın bulunduğu yer olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFormView Sınıfı](../../mfc/reference/cformview-class.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)
