---
title: CMultiPageDHtmlDialog Sınıfı
ms.date: 03/27/2019
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
ms.openlocfilehash: 89e4830c3b5c6cb663ca2d2935adaaae3f356958
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319661"
---
# <a name="cmultipagedhtmldialog-class"></a>CMultiPageDHtmlDialog Sınıfı

Çok sayfalı iletişim kutusu, birden çok HTML sayfasını sırayla görüntüler ve her sayfadaki olayları işler.

## <a name="syntax"></a>Sözdizimi

```
class CMultiPageDHtmlDialog : public CDHtmlDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|Çok sayfalı (sihirbaz stili) DHTML iletişim nesnesi oluşturuyor.|
|[CMultiPageDHtmlDialog::~CMultiPageDHtmlDialog](#_dtorcmultipagedhtmldialog)|Çok sayfalı bir DHTML iletişim nesnesi yok eder.|

## <a name="remarks"></a>Açıklamalar

Bunu yapmak için mekanizma, her sayfa için gömülü olay eşlemlerini içeren bir [DHTML ve URL olay haritasıdır.](dhtml-event-maps.md)

## <a name="example"></a>Örnek

Bu çok sayfalı iletişim kutusu, basit sihirbaz benzeri işlevselliği tanımlayan üç HTML kaynağı varsayar. İlk sayfada **Bir Sonraki** düğmesi, ikincisi Bir Öncev ve **İleri** düğmesi ve üçüncü bir **Prev** düğmesi vardır. **Prev** Düğmelerden birine basıldığında, bir işleyici işlevi UYGUN yeni sayfayı yüklemek için [CDHtmlDialog'u çağırır::LoadFromResource.](../../mfc/reference/cdhtmldialog-class.md#loadfromresource)

Sınıf bildiriminin ilgili bölümleri (CMyMultiPageDlg.h'de):

[!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]

Sınıf uygulamasının ilgili bölümleri (CMyMultipageDlg.cpp'de):

[!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CDHtmlSinkHandlerBase2`

`CDHtmlSinkHandlerBase1`

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`CDHtmlSinkHandler`

[Cwnd](../../mfc/reference/cwnd-class.md)

`CDHtmlEventSink`

[Cdialog](../../mfc/reference/cdialog-class.md)

[Cdhtmldialog](../../mfc/reference/cdhtmldialog-class.md)

`CMultiPageDHtmlDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdhtml.h

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="cmultipagedhtmldialog"></a>CMultiPageDHtmlDialog::CMultiPageDHtmlDialog

Çok sayfalı (sihirbaz stili) DHTML iletişim nesnesi oluşturuyor.

```
CMultiPageDHtmlDialog(
    LPCTSTR lpszTemplateName,
    LPCTSTR szHtmlResID = NULL,
    CWnd* pParentWnd = NULL);

CMultiPageDHtmlDialog(
    UINT nIDTemplate,
    UINT nHtmlResID = 0,
    CWnd* pParentWnd = NULL);

CMultiPageDHtmlDialog();
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
İletişim kutusu şablon kaynağının adı olan null-sonlandırılan dize.

*szHtmlResID*<br/>
HTML kaynağının adı olan null-sonlandırılan dize.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip penceresi nesnesine [(CWnd](../../mfc/reference/cwnd-class.md)türünden) işaretçi. NULL ise, iletişim nesnesinin üst penceresi ana uygulama penceresine ayarlanır.

*nIDTemplate*<br/>
İletişim kutusu şablonkaynağının kimlik numarasını içerir.

*nHtmlResID*<br/>
BIR HTML kaynağının kimlik numarasını içerir.

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="_dtorcmultipagedhtmldialog"></a>CMultiPageDHtmlDialog::~CMultiPageDHtmlDialog

Çok sayfalı bir DHTML iletişim nesnesi yok eder.

```
virtual ~CMultiPageDHtmlDialog();
```

## <a name="see-also"></a>Ayrıca bkz.

[CDHtmlDialog Sınıfı](../../mfc/reference/cdhtmldialog-class.md)
