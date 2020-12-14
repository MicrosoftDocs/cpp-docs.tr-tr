---
description: 'Daha fazla bilgi edinin: CDataExchange sınıfı'
title: CDataExchange sınıfı
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
ms.openlocfilehash: 36d11dc2b74142bd869b0e7b459d8bdb888b2cef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222183"
---
# <a name="cdataexchange-class"></a>CDataExchange sınıfı

, Microsoft Foundation sınıfları tarafından kullanılan iletişim kutusu veri değişimi (DDX) ve iletişim verileri doğrulama (DDV) yordamlarını destekler.

## <a name="syntax"></a>Syntax

```
class CDataExchange
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDataExchange:: CDataExchange](#cdataexchange)|Bir `CDataExchange` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDataExchange:: Fail](#fail)|Doğrulama başarısız olduğunda çağırılır. Odağı önceki denetime sıfırlar ve bir özel durum oluşturur.|
|[CDataExchange::P Repareci](#preparectrl)|Veri değişimi veya doğrulama için belirtilen denetimi hazırlar. Düzenleme olmayan denetimler için kullanın.|
|[CDataExchange::P repareEditCtrl](#prepareeditctrl)|Veri değişimi veya doğrulama için belirtilen düzenleme denetimini hazırlar.|
|[CDataExchange::P repareOleCtrl](#prepareolectrl)|Veri değişimi veya doğrulama için belirtilen OLE denetimini hazırlar. Düzenleme olmayan denetimler için kullanın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDataExchange:: m_bSaveAndValidate](#m_bsaveandvalidate)|DDX ve DDV yönlerinin yönü için bayrak.|
|[CDataExchange:: m_pDlgWnd](#m_pdlgwnd)|Veri değişimi 'nin gerçekleştiği iletişim kutusu veya pencere.|

## <a name="remarks"></a>Açıklamalar

`CDataExchange` taban sınıfına sahip değildir.

Özel veri türleri veya denetimler için veri değişim yordamları yazıyorsanız veya kendi veri doğrulama yordamlarınızı yazıyorsanız bu sınıfı kullanın. Kendi DDX ve DDV yordamlarınızı yazma hakkında daha fazla bilgi için bkz. [teknik notta 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV 'ye genel bakış için bkz. [Iletişim kutusu veri değişimi ve doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutuları](../../mfc/dialog-boxes.md).

Bir `CDataExchange` nesnesi, ddx ve DDV 'nin gerçekleşmesi için gereken bağlam bilgilerini sağlar. Veri üyelerinden iletişim kutusu denetimlerinin başlangıç değerlerini doldurmaya yönelik DDX kullanılırsa, bayrak *m_bSaveAndValidate* false 'tur. Bayrak *m_bSaveAndValidate* , iletişim kutusu denetimlerinin geçerli değerlerini veri üyelerine ayarlamak için ve veri değerlerini doğrulamak için DDV kullanıldığında true olur. DDV doğrulaması başarısız olursa, DDV yordamı giriş hatasını açıklayan bir ileti kutusu görüntüler. Ardından, DDV yordamı, `Fail` odağı sorunlu denetime sıfırlama ve doğrulama işlemini durdurmak için bir özel durum oluşturacak şekilde çağırır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDataExchange`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cdataexchangecdataexchange"></a><a name="cdataexchange"></a> CDataExchange:: CDataExchange

Bir nesne oluşturmak için bu üye işlevini çağırın `CDataExchange` .

```
CDataExchange(
    CWnd* pDlgWnd,
    BOOL bSaveAndValidate);
```

### <a name="parameters"></a>Parametreler

*pDlgWnd*<br/>
Denetimi içeren üst pencereye yönelik bir işaretçi. Genellikle bu bir [CDialog](../../mfc/reference/cdialog-class.md)-türetilmiş nesnesidir.

*bSaveAndValidate*<br/>
TRUE ise, bu nesne verileri doğrular ve ardından denetimlerden verileri üyelere yazar. FALSE ise, bu nesne verileri üyelerden denetimlere taşır.

### <a name="remarks"></a>Açıklamalar

`CDataExchange`Pencerenin [CWnd::D oDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) üye işlevine iletmek için veri değişimi nesnesinde ek bilgi depolamak üzere bir nesne oluşturun.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]

## <a name="cdataexchangefail"></a><a name="fail"></a> CDataExchange:: Fail

Bir iletişim kutusu veri doğrulama (DDV) işlemi başarısız olduğunda Framework bu üye işlevini çağırır.

```cpp
void Fail();
```

### <a name="remarks"></a>Açıklamalar

`Fail` odağı ve seçimini doğrulama başarısız olan denetime (geri yüklenecek bir denetim varsa) geri yükler. `Fail` ardından, doğrulama işlemini durdurmak için [CUserException](../../mfc/reference/cuserexception-class.md) türünde bir özel durum oluşturur. Bu özel durum, hatayı açıklayan bir ileti kutusunun görüntülenmesine neden olur. DDV doğrulaması başarısız olduktan sonra, Kullanıcı sorunlu denetime verileri yeniden ekleyebilir.

Özel DDV yordamlarının uygulayıcılar, `Fail` bir doğrulama başarısız olduğunda kendi yordamlarından çağırabilir.

Kendi DDX ve DDV yordamlarınızı yazma hakkında daha fazla bilgi için bkz. [teknik notta 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV 'ye genel bakış için bkz. [iletişim kutusu veri değişimi ve doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusu konuları](../../mfc/dialog-boxes.md).

## <a name="cdataexchangem_bsaveandvalidate"></a><a name="m_bsaveandvalidate"></a> CDataExchange:: m_bSaveAndValidate

Bu bayrak bir iletişim kutusu veri değişimi (DDX) işleminin yönünü gösterir.

```
BOOL m_bSaveAndValidate;
```

### <a name="remarks"></a>Açıklamalar

`CDataExchange`Kullanıcı denetimleri düzenledikten sonra iletişim kutusu denetimlerinden verileri iletişim sınıfı veri üyelerine taşımak için kullanılan bayrak sıfır değildir. Nesne, iletişim kutusu-sınıf veri üyelerinden iletişim kutusu denetimlerini başlatmak için kullanılıyorsa, bayrak sıfırdır.

Bayrak, iletişim kutusu veri doğrulaması (DDV) sırasında da sıfır dışında.

Kendi DDX ve DDV yordamlarınızı yazma hakkında daha fazla bilgi için bkz. [teknik notta 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV 'ye genel bakış için bkz. [iletişim kutusu veri değişimi ve doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusu konuları](../../mfc/dialog-boxes.md).

## <a name="cdataexchangem_pdlgwnd"></a><a name="m_pdlgwnd"></a> CDataExchange:: m_pDlgWnd

İletişim kutusu veri değişimi (DDX) veya doğrulama (DDV) için bir [CWnd](../../mfc/reference/cwnd-class.md) nesnesine yönelik bir işaretçi içerir.

```
CWnd* m_pDlgWnd;
```

### <a name="remarks"></a>Açıklamalar

Bu nesne genellikle bir [CDialog](../../mfc/reference/cdialog-class.md) nesnesidir. Özel DDX veya DDV yordamlarının uygulayıcılar bu işaretçiyi, üzerinde çalıştıkları denetimleri içeren iletişim penceresine erişim sağlamak için kullanabilir.

Kendi DDX ve DDV yordamlarınızı yazma hakkında daha fazla bilgi için bkz. [teknik notta 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV 'ye genel bakış için bkz. [iletişim kutusu veri değişimi ve doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusu konuları](../../mfc/dialog-boxes.md).

## <a name="cdataexchangepreparectrl"></a><a name="preparectrl"></a> CDataExchange::P Repareci

Çerçeve, iletişim kutusu veri değişimi (DDX) ve doğrulaması (DDV) için belirtilen denetimi hazırlamak üzere bu üye işlevini çağırır.

```
HWND PrepareCtrl(int nIDC);
```

### <a name="parameters"></a>Parametreler

*Nıdc*<br/>
DDX veya DDV için hazırlanmakta olan denetimin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Denetimin, DDX veya DDV için hazırlanmakta olan HWND.

### <a name="remarks"></a>Açıklamalar

Düzenleme denetimleri için bunun yerine [PrepareEditCtrl](#prepareeditctrl) kullanın; diğer tüm denetimler için bu üye işlevini kullanın.

Hazırlık, denetimin HWND 'sini sınıfında depolamayı içerir `CDataExchange` . Framework, bir DDX veya DDV arızası durumunda odağı daha önce odaklanmış denetime geri yüklemek için bu tanıtıcıyı kullanır.

Özel DDX veya DDV yordamlarının uygulayıcılar `PrepareCtrl` , VERILERI ddx veya ddv aracılığıyla verileri doğrularken, düzenleme olmayan tüm denetimleri için çağırmalıdır.

Kendi DDX ve DDV yordamlarınızı yazma hakkında daha fazla bilgi için bkz. [teknik notta 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV 'ye genel bakış için bkz. [iletişim kutusu veri değişimi ve doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusu konuları](../../mfc/dialog-boxes.md).

## <a name="cdataexchangeprepareeditctrl"></a><a name="prepareeditctrl"></a> CDataExchange::P repareEditCtrl

Çerçeve, iletişim kutusu veri değişimi (DDX) ve doğrulaması (DDV) için belirtilen düzenleme denetimini hazırlamak üzere bu üye işlevini çağırır.

```
HWND PrepareEditCtrl(int nIDC);
```

### <a name="parameters"></a>Parametreler

*Nıdc*<br/>
DDX veya DDV için hazırlanmakta olan düzenleme denetiminin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Düzenleme denetiminin, DDX veya DDV için hazırlanmakta olan HWND.

### <a name="remarks"></a>Açıklamalar

Tüm düzenleme olmayan denetimler için yerine [hazırlık eci](#preparectrl) kullanın.

Hazırlık iki işlemlerden oluşur. İlk olarak, `PrepareEditCtrl` DENETIMIN HWND 'sini `CDataExchange` sınıfında depolar. Framework, bir DDX veya DDV arızası durumunda odağı daha önce odaklanmış denetime geri yüklemek için bu tanıtıcıyı kullanır. İkinci olarak, `PrepareEditCtrl` `CDataExchange` verileri değiştirilen veya doğrulanan denetimin bir düzenleme denetimi olduğunu göstermek için sınıfında bir bayrak ayarlar.

Özel DDX veya DDV yordamlarının uygulayıcılar `PrepareEditCtrl` , veri alışverişi yapan ve ddv aracılığıyla verileri doğrulayan tüm düzenleme denetimlerini çağırmalıdır.

Kendi DDX ve DDV yordamlarınızı yazma hakkında daha fazla bilgi için bkz. [teknik notta 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV 'ye genel bakış için bkz. [iletişim kutusu veri değişimi ve doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusu konuları](../../mfc/dialog-boxes.md).

## <a name="cdataexchangeprepareolectrl"></a><a name="prepareolectrl"></a> CDataExchange::P repareOleCtrl

Çerçeve, iletişim kutusu veri değişimi (DDX) ve doğrulaması (DDV) için belirtilen OLE denetimini hazırlamak üzere bu üye işlevini çağırır.

```
COleControlSite* PrepareOleCtrl(int nIDC);
```

### <a name="parameters"></a>Parametreler

*Nıdc*<br/>
DDX veya DDV için hazırlanmaya yönelik OLE denetiminin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

OLE denetim sitesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Düzenleme denetimleri için veya diğer tüm OLE dışı denetimler için bir ön [hazırlık](#preparectrl) Için [PrepareEditCtrl](#prepareeditctrl) kullanın.

Özel DDX veya DDV yordamlarının Uygulayıcı, `PrepareOleCtrl` VERILERI ddx veya ddv aracılığıyla doğrulamak için veri değiş tokuş ettikleri tüm OLE denetimlerini çağırmalıdır.

Kendi DDX ve DDV yordamlarınızı yazma hakkında daha fazla bilgi için bkz. [teknik notta 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV 'ye genel bakış için bkz. [iletişim kutusu veri değişimi ve doğrulama](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusu konuları](../../mfc/dialog-boxes.md).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd::D oDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)<br/>
[CWnd:: UpdateData](../../mfc/reference/cwnd-class.md#updatedata)
