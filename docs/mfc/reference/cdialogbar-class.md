---
title: CDialogBar Sınıfı
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
ms.openlocfilehash: cf9a2658807959108b3bb0af672d4c1835b58bc5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375671"
---
# <a name="cdialogbar-class"></a>CDialogBar Sınıfı

Denetim çubuğundaki Windows moduz iletişim kutusunun işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CDialogBar : public CControlBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDialogBar::CDialogBar](#cdialogbar)|Bir `CDialogBar` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDialogBar::Oluştur](#create)|Bir Windows iletişim çubuğu oluşturur ve `CDialogBar` nesneye bağlar.|

## <a name="remarks"></a>Açıklamalar

İletişim çubuğu, kullanıcının arasında sektirebileceği standart Windows denetimleri içerdiği bir iletişim kutusunu andırır. Başka bir benzerlik, iletişim çubuğunu temsil edecek bir iletişim şablonu oluşturmanızdır.

İletişim çubuğu oluşturmak ve kullanmak, nesne `CFormView` oluşturmaya ve kullanmaya benzer. İlk olarak, stil WS_CHILD ve başka bir stil içeren bir iletişim şablonu tanımlamak için [iletişim düzenleyicisini](../../windows/dialog-editor.md) kullanın. Şablon, stil WS_VISIBLE olmamalıdır. Uygulama kodunuzda, `CDialogBar` nesneyi oluşturmak için oluşturucuyu çağırın, ardından iletişim çubuğu penceresi oluşturmak için arayın `Create` ve `CDialogBar` nesneye takın.

Daha fazla `CDialogBar`bilgi için, makaleye bakın [Dialog Barlar](../../mfc/dialog-bars.md) ve [Teknik Not 31](../../mfc/tn031-control-bars.md), Denetim Çubukları.

> [!NOTE]
> Geçerli sürümde, `CDialogBar` bir nesne Windows Forms denetimlerini barındıramaz. Visual C++'daki Windows Forms denetimleri hakkında daha fazla bilgi [için](../../dotnet/using-a-windows-form-user-control-in-mfc.md)bkz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Ccontrolbar](../../mfc/reference/ccontrolbar-class.md)

`CDialogBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext.h

## <a name="cdialogbarcdialogbar"></a><a name="cdialogbar"></a>CDialogBar::CDialogBar

Bir `CDialogBar` nesne inşa eder.

```
CDialogBar();
```

## <a name="cdialogbarcreate"></a><a name="create"></a>CDialogBar::Oluştur

İletişim kutusu kaynak şablonunu yükler `lpszTemplateName` `nIDTemplate`veya iletişim çubuğu penceresini oluşturur, stilini ayarlar ve `CDialogBar` nesneyle ilişkilendirer.

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
Ana `CWnd` nesneye işaretçi.

*lpszTemplateName*<br/>
`CDialogBar` Nesnenin iletişim kutusu kaynak şablonunun adına bir işaretçi.

*nStyle*<br/>
Araç çubuğu stili. Desteklenen ek araç çubuğu stilleri şunlardır:

- CBRS_TOP Denetim çubuğu çerçeve penceresinin en üstündedir.

- CBRS_BOTTOM Denetim çubuğu çerçeve penceresinin alt kısmındadır.

- CBRS_NOALIGN Denetim çubuğu, üst öğe yeniden boyutlandırıldığında yeniden konumlandırılmez.

- CBRS_TOOLTIPS Denetim çubuğu araç ipuçlarını görüntüler.

- CBRS_SIZE_DYNAMIC Kontrol çubuğu dinamiktir.

- CBRS_SIZE_FIXED Kontrol çubuğu sabittir.

- CBRS_FLOATING Kontrol çubuğu yüzer.

- CBRS_FLYBY Durum çubuğu düğme yle ilgili bilgileri görüntüler.

- CBRS_HIDE_INPLACE Denetim çubuğu kullanıcıya görüntülenmez.

*Nıd*<br/>
İletişim çubuğunun denetim kimliği.

*nIDTemplate*<br/>
Nesnenin iletişim `CDialogBar` kutusu şablonunun kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

CBRS_TOP veya CBRS_BOTTOM hizalama stilini belirtirseniz, iletişim çubuğunun genişliği çerçeve penceresinin genişliğidir ve yüksekliği *nIDTemplate*tarafından belirtilen kaynaktır. CBRS_LEFT veya CBRS_RIGHT hizalama stilini belirtirseniz, iletişim çubuğunun yüksekliği çerçeve penceresinin yüksekliğidir ve genişliği *nIDTemplate*tarafından belirtilen kaynaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFormView Sınıfı](../../mfc/reference/cformview-class.md)<br/>
[CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)
