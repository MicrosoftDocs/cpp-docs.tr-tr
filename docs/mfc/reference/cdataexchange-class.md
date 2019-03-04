---
title: CDataExchange Class
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
ms.openlocfilehash: 630bc41ee20aa7cf6f62cd320b15b8dca0d3fedf
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268401"
---
# <a name="cdataexchange-class"></a>CDataExchange Class

İletişim kutusu veri değişimi (DDX) ve Microsoft Foundation sınıfları tarafından kullanılan iletişim kutusu veri doğrulama (DDV) yordamlarını destekler.

## <a name="syntax"></a>Sözdizimi

```
class CDataExchange
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDataExchange::CDataExchange](#cdataexchange)|Oluşturur bir `CDataExchange` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDataExchange::Fail](#fail)|Doğrulama başarısız olduğunda çağrılır. Odağı önceki denetim sıfırlar ve bir özel durum oluşturur.|
|[CDataExchange::PrepareCtrl](#preparectrl)|Belirtilen denetim veri değişimi veya doğrulama için hazırlar. Nonedit denetimleri için kullanın.|
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|Belirtilen düzenleme denetiminin, veri değişimi veya doğrulama için hazırlar.|
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|Belirtilen OLE denetim veri değişimi veya doğrulama için hazırlar. Nonedit denetimleri için kullanın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|DDX ve DDV yönü için bayrak.|
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|Burada veri değişimi iletişim kutusu ya da pencere gerçekleşir.|

## <a name="remarks"></a>Açıklamalar

`CDataExchange` bir temel sınıfa sahip değil.

Bu sınıf, özel veri türleri veya denetimleri için veri değişimi rutinleri yazıyorsanız kullanın veya kendi veri doğrulama rutinleri yazıyorsanız. Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutuları](../../mfc/dialog-boxes.md).

A `CDataExchange` nesnesi DDX ve DDV gerçekleştirilecek yerleştirmek için gereken bağlam bilgilerini sağlar. Bayrağı *m_bSaveAndValidate* FALSE olduğunda DDX veri üyelerinden iletişim denetimlerin ilk değerleri doldurmak için kullanılır. Bayrağı *m_bSaveAndValidate* DDX veri üyeleri ve DDV veri değerleri doğrulaması için kullanıldığında halinde iletişim kutusu denetimleri geçerli değerlerini ayarlamak için kullanılan zaman true'dur. DDV doğrulama başarısız olursa DDV yordam giriş hatayı açıklayan bir ileti kutusu görüntüler. DDV yordamı ardından çağırın `Fail` odağı sorunlu denetime sıfırlama ve doğrulama işlemi durdurmak için bir özel durum.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDataExchange`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cdataexchange"></a>  CDataExchange::CDataExchange

Oluşturmak için bu üye işlevi çağrısı bir `CDataExchange` nesne.

```
CDataExchange(
    CWnd* pDlgWnd,
    BOOL bSaveAndValidate);
```

### <a name="parameters"></a>Parametreler

*pDlgWnd*<br/>
Denetimi içeren üst penceresine bir işaretçi. Genellikle bu, bir [CDialog](../../mfc/reference/cdialog-class.md)-türetilmiş bir nesneye.

*bSaveAndValidate*<br/>
TRUE ise, bu nesne verileri doğrular, sonra veri üyeleri denetimlerden yazar. FALSE ise, bu nesne üyelerinden verileri denetimlere taşıyın.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CDataExchange` nesne, pencerenin geçirmek için veri değişimi nesnede ek bilgi depolamak için kendiniz [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]

##  <a name="fail"></a>  CDataExchange::Fail

Framework, bir iletişim kutusu veri doğrulama (DDV) işlemi başarısız olduğunda bu üye işlevini çağırır.

```
void Fail();
```

### <a name="remarks"></a>Açıklamalar

`Fail` odak ve seçim (geri yüklemek için bir denetim varsa), doğrulama başarısız oldu denetime geri yükler. `Fail` ardından türünde bir özel durum oluşturduğunda [CUserException](../../mfc/reference/cuserexception-class.md) doğrulama işlemini durdurmak için. Özel durum görüntülenecek hatayı açıklayan bir ileti kutusu neden olur. DDV doğrulama başarısız olduktan sonra kullanıcı sorunlu denetiminde verileri yeniden girebilirsiniz.

Özel DDV rutinleri, implementors çağırabilir `Fail` gelen bir doğrulama başarısız olduğunda, yordamlar.

Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusu konuları](../../mfc/dialog-boxes.md).

##  <a name="m_bsaveandvalidate"></a>  CDataExchange::m_bSaveAndValidate

Bu bayrak, bir iletişim kutusu veri değişimi (DDX) işleminin yönünü belirtir.

```
BOOL m_bSaveAndValidate;
```

### <a name="remarks"></a>Açıklamalar

Bayrağı sıfır olmayan, `CDataExchange` nesne, kullanıcı denetimleri düzenledikten sonra verileri iletişim sınıf veri üyeleri için iletişim kutusu denetimleri taşımak için kullanılıyor. İletişim kutusu sınıfı veri üyelerini denetimlerden iletişim başlatmak için nesne kullanılıyorsa bayrağı sıfırdır.

Ayrıca iletişim verisi doğrulama (DDV) sırasında sıfır olmayan bir göstergedir.

Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusu konuları](../../mfc/dialog-boxes.md).

##  <a name="m_pdlgwnd"></a>  CDataExchange::m_pDlgWnd

Bir işaretçi içeren [CWnd](../../mfc/reference/cwnd-class.md) nesnesi için hangi iletişim kutusu veri değişimi (DDX) veya doğrulama (DDV) sürüyor yerleştir.

```
CWnd* m_pDlgWnd;
```

### <a name="remarks"></a>Açıklamalar

Genellikle bu nesne olduğu bir [CDialog](../../mfc/reference/cdialog-class.md) nesne. İmplementors özel DDX veya DDV rutinleri, bu işaretçi üzerinde çalıştıkları denetimleri içeren iletişim kutusu penceresine erişim sağlamak için kullanabilirsiniz.

Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusu konuları](../../mfc/dialog-boxes.md).

##  <a name="preparectrl"></a>  CDataExchange::PrepareCtrl

Framework'te iletişim kutusu veri değişimi (DDX) ve doğrulama (DDV) için belirtilen denetim hazırlamak için bu üye işlevini çağırır.

```
HWND PrepareCtrl(int nIDC);
```

### <a name="parameters"></a>Parametreler

*nIDC*<br/>
DDX veya DDV için hazırlıklı olmak için denetimin kimliği.

### <a name="return-value"></a>Dönüş Değeri

HWND denetimin DDX veya DDV için hazırlanıyor.

### <a name="remarks"></a>Açıklamalar

Kullanma [PrepareEditCtrl](#prepareeditctrl) düzenleme denetimlerinde; diğer tüm denetimler için bu üye işlevini kullanın.

Hazırlama oluşur, denetimin HWND depolayabilen `CDataExchange` sınıfı. Çerçeve odağı önceden odaklı denetimin DDX veya DDV bir arıza olması durumunda geri yüklemek için bu tutamacı kullanır.

Özel DDX veya DDV rutinleri, implementors çağırmalıdır `PrepareCtrl` , bunlar DDX aracılığıyla veri değişimi veya DDV aracılığıyla verileri doğrulamak için tüm düzen olmayan denetimler için.

Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusu konuları](../../mfc/dialog-boxes.md).

##  <a name="prepareeditctrl"></a>  CDataExchange::PrepareEditCtrl

Framework'te iletişim kutusu veri değişimi (DDX) ve doğrulama (DDV) için belirtilen düzenleme denetiminin hazırlamak için bu üye işlevini çağırır.

```
HWND PrepareEditCtrl(int nIDC);
```

### <a name="parameters"></a>Parametreler

*nIDC*<br/>
DDX veya DDV için hazırlanması düzenleme denetiminin kimliği.

### <a name="return-value"></a>Dönüş Değeri

HWND düzenleme denetiminin DDX veya DDV için hazırlanıyor.

### <a name="remarks"></a>Açıklamalar

Kullanım [PrepareCtrl](#preparectrl) bunun yerine tüm düzen olmayan denetimler için.

Hazırlama iki şey oluşur. İlk olarak, `PrepareEditCtrl` denetimin HWND içinde depolar `CDataExchange` sınıfı. Çerçeve odağı önceden odaklı denetimin DDX veya DDV bir arıza olması durumunda geri yüklemek için bu tutamacı kullanır. İkinci olarak, `PrepareEditCtrl` bir bayrak ayarlar `CDataExchange` göstermek için sınıf verisini değiştirilen veya doğrulanmış bir düzenleme denetimi olan denetim.

Özel DDX veya DDV rutinleri, implementors çağırmalıdır `PrepareEditCtrl` tüm kendisi için bunlar DDX aracılığıyla veri değişimi veya DDV aracılığıyla veri doğrulama denetimleri düzenlemek için.

Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusu konuları](../../mfc/dialog-boxes.md).

##  <a name="prepareolectrl"></a>  CDataExchange::PrepareOleCtrl

Framework'te iletişim kutusu veri değişimi (DDX) ve doğrulama (DDV) için belirtilen OLE denetim hazırlamak için bu üye işlevini çağırır.

```
COleControlSite* PrepareOleCtrl(int nIDC);
```

### <a name="parameters"></a>Parametreler

*nIDC*<br/>
DDX veya DDV için hazırlanması OLE denetiminin kimliği.

### <a name="return-value"></a>Dönüş Değeri

OLE denetim site için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kullanım [PrepareEditCtrl](#prepareeditctrl) yerine düzenleme denetimleri için veya [PrepareCtrl](#preparectrl) diğer tüm OLE olmayan denetimler için.

Özel DDX veya DDV rutinleri, implementors çağırmalıdır `PrepareOleCtrl` tüm OLE denetimleri için bunlar DDX aracılığıyla veri değişimi veya DDV aracılığıyla verileri doğrulamak için.

Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusu konuları](../../mfc/dialog-boxes.md).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek VIEWEX](../../visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)<br/>
[CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)
