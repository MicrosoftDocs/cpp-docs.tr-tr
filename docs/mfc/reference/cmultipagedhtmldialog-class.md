---
description: 'Daha fazla bilgi edinin: CMultiPageDHtmlDialog sınıfı'
title: CMultiPageDHtmlDialog sınıfı
ms.date: 03/27/2019
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
ms.openlocfilehash: 1f7f8c2081687c71a98e427bb5396cfa47a73deb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331529"
---
# <a name="cmultipagedhtmldialog-class"></a>CMultiPageDHtmlDialog sınıfı

Çok sayfalı iletişim kutusu, birden fazla HTML sayfasını ardışık olarak görüntüler ve her sayfadaki olayları işler.

## <a name="syntax"></a>Syntax

```
class CMultiPageDHtmlDialog : public CDHtmlDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMultiPageDHtmlDialog:: CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|Çok sayfalı (Sihirbaz stili) DHTML iletişim kutusu nesnesi oluşturur.|
|[CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog](#_dtorcmultipagedhtmldialog)|Çok sayfalı DHTML iletişim kutusu nesnesini yok eder.|

## <a name="remarks"></a>Açıklamalar

Bunu yapma mekanizması, her sayfa için katıştırılmış olay haritaları içeren bir [DHTML ve URL olay eşlemedir](dhtml-event-maps.md).

## <a name="example"></a>Örnek

Bu çok sayfalı iletişim kutusunda, sihirbaz benzeri basit işlevleri tanımlayan üç HTML kaynağı varsayılır. İlk sayfada bir **sonraki** düğme, Ikinci bir **önceki** ve **sonraki** düğmesi ve üçüncü bir **önceki** düğme bulunur. Düğmelerden birine basıldığında bir işleyici işlevi, uygun yeni sayfayı yüklemek için [CDHtmlDialog:: LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) öğesini çağırır.

Sınıf bildiriminin ilgili kısımları (CMyMultiPageDlg. h içinde):

[!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]

Sınıf uygulamasının ilgili kısımları (CMyMultipageDlg. cpp):

[!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDHtmlSinkHandlerBase2`

`CDHtmlSinkHandlerBase1`

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDHtmlSinkHandler`

[CWnd](../../mfc/reference/cwnd-class.md)

`CDHtmlEventSink`

[CDialog](../../mfc/reference/cdialog-class.md)

[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)

`CMultiPageDHtmlDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdhtml. h

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="cmultipagedhtmldialog"></a> CMultiPageDHtmlDialog:: CMultiPageDHtmlDialog

Çok sayfalı (Sihirbaz stili) DHTML iletişim kutusu nesnesi oluşturur.

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
Bir iletişim kutusu şablon kaynağının adı olan null ile sonlandırılmış dize.

*Szhtmlresd*<br/>
Bir HTML kaynağının adı olan null ile sonlandırılmış dize.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip pencere nesnesine ( [CWnd](../../mfc/reference/cwnd-class.md)türü) yönelik bir işaretçi. NULL ise, iletişim kutusu nesnesinin ana penceresi ana uygulama penceresine ayarlanır.

*Nıdtemplate*<br/>
Bir iletişim kutusu şablon kaynağının KIMLIK numarasını içerir.

*Nhtmlresd*<br/>
Bir HTML kaynağının KIMLIK numarasını içerir.

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="_dtorcmultipagedhtmldialog"></a> CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog

Çok sayfalı DHTML iletişim kutusu nesnesini yok eder.

```
virtual ~CMultiPageDHtmlDialog();
```

## <a name="see-also"></a>Ayrıca bkz.

[CDHtmlDialog sınıfı](../../mfc/reference/cdhtmldialog-class.md)
