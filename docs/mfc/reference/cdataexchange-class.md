---
title: CDataExchange Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDataExchange
- AFXWIN/CDataExchange
- AFXWIN/CDataExchange::CDataExchange
- AFXWIN/CDataExchange::Fail
- AFXWIN/CDataExchange::PrepareCtrl
- AFXWIN/CDataExchange::PrepareEditCtrl
- AFXWIN/CDataExchange::PrepareOleCtrl
- AFXWIN/CDataExchange::m_bSaveAndValidate
- AFXWIN/CDataExchange::m_pDlgWnd
helpviewer_keywords:
- CDataExchange [MFC], CDataExchange
- CDataExchange [MFC], Fail
- CDataExchange [MFC], PrepareCtrl
- CDataExchange [MFC], PrepareEditCtrl
- CDataExchange [MFC], PrepareOleCtrl
- CDataExchange [MFC], m_bSaveAndValidate
- CDataExchange [MFC], m_pDlgWnd
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
ms.openlocfilehash: 73319ad898bfebf4caf191954ebb3935bd4ebce9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321959"
---
# <a name="cdataexchange-class"></a>CDataExchange Sınıfı

Microsoft Foundation sınıfları tarafından kullanılan iletişim veri alışverişi (DDX) ve iletişim veri doğrulama (DDV) yordamlarını destekler.

## <a name="syntax"></a>Sözdizimi

```
class CDataExchange
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDataExchange::CDataExchange](#cdataexchange)|Bir `CDataExchange` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDataExchange::Fail](#fail)|Doğrulama başarısız olduğunda çağrılır. Önceki denetime odak sıfırlamave bir özel durum atar.|
|[CDataExchange::PrepareCtrl](#preparectrl)|Veri alışverişi veya doğrulama için belirtilen denetimi hazırlar. Nonedit denetimleri için kullanın.|
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|Veri alışverişi veya doğrulama için belirtilen edit denetimini hazırlar.|
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|Veri alışverişi veya doğrulama için belirtilen OLE denetimini hazırlar. Nonedit denetimleri için kullanın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|DDX ve DDV yönü için bayrak.|
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|Veri alışverişinin gerçekleştiği iletişim kutusu veya penceresi.|

## <a name="remarks"></a>Açıklamalar

`CDataExchange`taban sınıfa sahip değildir.

Özel veri türleri veya denetimler için veri alışverişi yordamları yazıyorsanız veya kendi veri doğrulama yordamlarınızı yazıyorsanız bu sınıfı kullanın. Kendi DDX ve DDV rutinlerinizi yazma hakkında daha fazla bilgi için [Teknik Not 26'ya](../../mfc/tn026-ddx-and-ddv-routines.md)bakın. DDX ve DDV'ye genel bir bakış için, [Bkz. İletişim Veri Alışverişi ve Doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [İletişim Kutuları.](../../mfc/dialog-boxes.md)

Bir `CDataExchange` nesne, DDX ve DDV'nin gerçekleşmesi için gereken bağlam bilgilerini sağlar. DDX, veri üyelerinden gelen iletişim denetimlerinin ilk değerlerini doldurmak için kullanıldığında *m_bSaveAndValidate* bayrak FALSE'dur. DDX, iletişim denetimlerinin geçerli değerlerini veri üyelerine ayarlamak için kullanıldığında ve DDV veri değerlerini doğrulamak için kullanıldığında m_bSaveAndValidate doğrudur. *m_bSaveAndValidate* DDV doğrulama başarısız olursa, DDV yordamı giriş hatasını açıklayan bir ileti kutusu görüntüler. DDV yordamı daha `Fail` sonra rahatsız edici denetime odak sıfırlamak ve doğrulama işlemini durdurmak için bir özel durum atmak için çağırır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDataExchange`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cdataexchangecdataexchange"></a><a name="cdataexchange"></a>CDataExchange::CDataExchange

Bir `CDataExchange` nesne oluşturmak için bu üye işlevi çağırın.

```
CDataExchange(
    CWnd* pDlgWnd,
    BOOL bSaveAndValidate);
```

### <a name="parameters"></a>Parametreler

*pDlgWnd*<br/>
Denetimi içeren ana pencereiçin bir işaretçi. Genellikle bu [CDialog](../../mfc/reference/cdialog-class.md)türetilmiş bir nesnedir.

*bSaveAndValidate*<br/>
TRUE ise, bu nesne verileri doğrular ve denetimlerden verileri üyelere yazar. FALSE ise, bu nesne verileri üyelerden denetimlere taşır.

### <a name="remarks"></a>Açıklamalar

Pencerenizin `CDataExchange` [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) üye işlevine geçmek için veri alışverişi nesnesinde fazladan bilgi depolamak için kendiniz bir nesne oluşturun.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]

## <a name="cdataexchangefail"></a><a name="fail"></a>CDataExchange::Fail

Bir iletişim veri doğrulama (DDV) işlemi başarısız olduğunda çerçeve bu üye işlevi çağırır.

```
void Fail();
```

### <a name="remarks"></a>Açıklamalar

`Fail`odağı ve seçimi doğrulama başarısız olan denetime geri yükler (geri yükleme denetimi varsa). `Fail`ardından doğrulama işlemini durdurmak için [CUserException](../../mfc/reference/cuserexception-class.md) türünden bir özel durum oluşturur. Özel durum, görüntülenecek hatayı açıklayan bir ileti kutusuna neden olur. DDV doğrulama başarısız olduktan sonra, kullanıcı rahatsız edici denetimverileri yeniden girebilirsiniz.

Özel DDV yordamlarının uygulayıcıları, `Fail` doğrulama başarısız olduğunda rutinlerinden arayabilirler.

Kendi DDX ve DDV rutinlerinizi yazma hakkında daha fazla bilgi için [Teknik Not 26'ya](../../mfc/tn026-ddx-and-ddv-routines.md)bakın. DDX ve DDV'ye genel bir bakış için, [Bkz. İletişim Veri Alışverişi ve Doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [İletişim Kutusu Konuları.](../../mfc/dialog-boxes.md)

## <a name="cdataexchangem_bsaveandvalidate"></a><a name="m_bsaveandvalidate"></a>CDataExchange::m_bSaveAndValidate

Bu bayrak, bir iletişim veri alışverişi (DDX) işleminin yönünü gösterir.

```
BOOL m_bSaveAndValidate;
```

### <a name="remarks"></a>Açıklamalar

`CDataExchange` Kullanıcı denetimleri yaptıktan sonra iletişim denetimlerinden iletişim sınıfı veri üyelerine veri taşımak için kullanılıyorsa, bayrak sıfır değildir. Nesne iletişim sınıfı veri üyelerinden iletişim denetimleri başlatmaiçin kullanılıyorsa, bayrak sıfırdır.

İletim veri doğrulaması (DDV) sırasında bayrak da sıfırdeğildir.

Kendi DDX ve DDV rutinlerinizi yazma hakkında daha fazla bilgi için [Teknik Not 26'ya](../../mfc/tn026-ddx-and-ddv-routines.md)bakın. DDX ve DDV'ye genel bir bakış için, [Bkz. İletişim Veri Alışverişi ve Doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [İletişim Kutusu Konuları.](../../mfc/dialog-boxes.md)

## <a name="cdataexchangem_pdlgwnd"></a><a name="m_pdlgwnd"></a>CDataExchange::m_pDlgWnd

[CWnd](../../mfc/reference/cwnd-class.md) nesnesine iletişim veri alışverişi (DDX) veya doğrulama (DDV) için bir işaretçi içerir.

```
CWnd* m_pDlgWnd;
```

### <a name="remarks"></a>Açıklamalar

Bu nesne genellikle bir [CDialog nesnesidir.](../../mfc/reference/cdialog-class.md) Özel DDX veya DDV yordamlarının uygulayıcıları, üzerinde çalıştıkları denetimleri içeren iletişim penceresine erişmek için bu işaretçiyi kullanabilir.

Kendi DDX ve DDV rutinlerinizi yazma hakkında daha fazla bilgi için [Teknik Not 26'ya](../../mfc/tn026-ddx-and-ddv-routines.md)bakın. DDX ve DDV'ye genel bir bakış için, [Bkz. İletişim Veri Alışverişi ve Doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [İletişim Kutusu Konuları.](../../mfc/dialog-boxes.md)

## <a name="cdataexchangepreparectrl"></a><a name="preparectrl"></a>CDataExchange::PrepareCtrl

Çerçeve, iletişim veri alışverişi (DDX) ve doğrulama (DDV) için belirtilen denetimi hazırlamak için bu üye işlevi çağırır.

```
HWND PrepareCtrl(int nIDC);
```

### <a name="parameters"></a>Parametreler

*nIDC*<br/>
DDX veya DDV için hazırlanacak denetimin kimliği.

### <a name="return-value"></a>Dönüş Değeri

Kontrolün HWND'si DDX veya DDV için hazırlanıyor.

### <a name="remarks"></a>Açıklamalar

Denetimleri yerine [PrepareEditCtrl'i](#prepareeditctrl) kullanın; diğer tüm denetimler için bu üye işlevi kullanın.

Hazırlık, kontrolün HWND'sinin sınıfta `CDataExchange` depolanmasından oluşur. Çerçeve, bir DDX veya DDV hatası durumunda odağı daha önce odaklanmış denetime geri yüklemek için bu tutamacı kullanır.

Özel DDX veya DDV yordamlarının uygulayıcıları, DDX üzerinden veri alışverişi yaptıkları veya DDV üzerinden veri doğrulama yaptıkları tüm edit olmayan denetimleri çağırmalıdır. `PrepareCtrl`

Kendi DDX ve DDV rutinlerinizi yazma hakkında daha fazla bilgi için [Teknik Not 26'ya](../../mfc/tn026-ddx-and-ddv-routines.md)bakın. DDX ve DDV'ye genel bir bakış için, [Bkz. İletişim Veri Alışverişi ve Doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [İletişim Kutusu Konuları.](../../mfc/dialog-boxes.md)

## <a name="cdataexchangeprepareeditctrl"></a><a name="prepareeditctrl"></a>CDataExchange::PrepareEditCtrl

Çerçeve, iletişim veri alışverişi (DDX) ve doğrulama (DDV) için belirtilen edit denetimini hazırlamak için bu üye işlevi çağırır.

```
HWND PrepareEditCtrl(int nIDC);
```

### <a name="parameters"></a>Parametreler

*nIDC*<br/>
DDX veya DDV için hazırlanacak edit denetiminin kimliği.

### <a name="return-value"></a>Dönüş Değeri

DDX veya DDV için hazırlanan edit denetiminin HWND'si.

### <a name="remarks"></a>Açıklamalar

Tüm olmayan denetimler için [PrepareCtrl'ı](#preparectrl) kullanın.

Hazırlık iki şeyden oluşur. İlk `PrepareEditCtrl` olarak, denetimin HWND'sini sınıfta saklar. `CDataExchange` Çerçeve, bir DDX veya DDV hatası durumunda odağı daha önce odaklanmış denetime geri yüklemek için bu tutamacı kullanır. İkinci `PrepareEditCtrl` olarak, verileri `CDataExchange` değiştirilen veya doğrulanan denetimin bir denetim denetimi olduğunu belirtmek için sınıfta bir bayrak ayarlar.

Özel DDX veya DDV yordamlarının uygulayıcıları, DDX üzerinden veri alışverişi yaptıkları veya DDV üzerinden verileri doğruladıkları tüm edit denetimlerini çağırmalıdır. `PrepareEditCtrl`

Kendi DDX ve DDV rutinlerinizi yazma hakkında daha fazla bilgi için [Teknik Not 26'ya](../../mfc/tn026-ddx-and-ddv-routines.md)bakın. DDX ve DDV'ye genel bir bakış için, [Bkz. İletişim Veri Alışverişi ve Doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [İletişim Kutusu Konuları.](../../mfc/dialog-boxes.md)

## <a name="cdataexchangeprepareolectrl"></a><a name="prepareolectrl"></a>CDataExchange::PrepareOleCtrl

Çerçeve, iletişim veri alışverişi (DDX) ve doğrulama (DDV) için belirtilen OLE denetimini hazırlamak için bu üye işlevi çağırır.

```
COleControlSite* PrepareOleCtrl(int nIDC);
```

### <a name="parameters"></a>Parametreler

*nIDC*<br/>
DDX veya DDV için hazırlanacak OLE denetiminin kimliği.

### <a name="return-value"></a>Dönüş Değeri

OLE denetim sitesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bunun [yerine](#prepareeditctrl) denetimleri veya Diğer OLE olmayan tüm denetimler için [PrepareCtrl'yi](#preparectrl) kullanın.

Özel DDX veya DDV yordamlarının uygulayıcıları, DDX üzerinden veri alışverişi yaptıkları veya DDV üzerinden verileri doğruladıkları tüm OLE denetimlerini aramalıdır. `PrepareOleCtrl`

Kendi DDX ve DDV rutinlerinizi yazma hakkında daha fazla bilgi için [Teknik Not 26'ya](../../mfc/tn026-ddx-and-ddv-routines.md)bakın. DDX ve DDV'ye genel bir bakış için, [Bkz. İletişim Veri Alışverişi ve Doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [İletişim Kutusu Konuları.](../../mfc/dialog-boxes.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)<br/>
[CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)
