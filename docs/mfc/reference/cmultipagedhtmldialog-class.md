---
title: CMultiPageDHtmlDialog sınıfı
ms.date: 03/27/2019
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
ms.openlocfilehash: 404b1b8bb1c96c2b244a6cfaee7f2f2c77800f31
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366907"
---
# <a name="cmultipagedhtmldialog-class"></a>CMultiPageDHtmlDialog sınıfı

Birden çok sayfa iletişim birden çok HTML sayfasını sıralı olarak görüntüler ve her sayfadaki olayları işler.

## <a name="syntax"></a>Sözdizimi

```
class CMultiPageDHtmlDialog : public CDHtmlDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|Birden çok sayfa (Sihirbazı stili) DHTML iletişim nesnesi oluşturur.|
|[CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog](#_dtorcmultipagedhtmldialog)|Bir çok sayfalı DHTML iletişim nesnesini yok eder.|

## <a name="remarks"></a>Açıklamalar

Bunu yapmak için bir mekanizma bir [DHTML ve URL olay eşlemesi](dhtml-event-maps.md), her sayfa için olay eşlemeleri içeren katıştırılmış.

## <a name="example"></a>Örnek

Bu çok sayfalı iletişim basit Sihirbazı benzeri işlevsellik tanımlayan üç HTML kaynak varsayar. İlk sayfanın bir **sonraki** düğme, ikinci bir **önceki** ve **sonraki** düğmesi ve üçüncü bir **önceki** düğmesi. Düğmelerden birine basıldığında işleyici işlevi çağıran [CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) uygun yeni sayfa yüklenemiyor.

Sınıf bildiriminde (CMyMultiPageDlg.h) ilgili bölümleri:

[!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]

Sınıf uygulamasında (CMyMultipageDlg.cpp) ilgili bölümleri:

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

**Başlık:** afxdhtml.h

##  <a name="cmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog::CMultiPageDHtmlDialog

Birden çok sayfa (Sihirbazı stili) DHTML iletişim nesnesi oluşturur.

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
Bir iletişim kutusu şablonu kaynak adı null ile sonlandırılmış bir dize.

*szHtmlResID*<br/>
Bir HTML kaynak adı null ile sonlandırılmış bir dize.

*pParentWnd*<br/>
Üst veya sahibi pencere nesnesi için bir işaretçi (tür [CWnd](../../mfc/reference/cwnd-class.md)) ait olduğu iletişim nesnesi. NULL ise, ana uygulama penceresini iletişim nesnenin üst penceresine ayarlanır.

*nIDTemplate*<br/>
Bir iletişim kutusu şablon kaynağı kimliği numarasını içerir.

*nHtmlResID*<br/>
Bir HTML kaynağının kimliği numarasını içerir.

##  <a name="_dtorcmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog

Bir çok sayfalı DHTML iletişim nesnesini yok eder.

```
virtual ~CMultiPageDHtmlDialog();
```

## <a name="see-also"></a>Ayrıca bkz.

[CDHtmlDialog Sınıfı](../../mfc/reference/cdhtmldialog-class.md)
