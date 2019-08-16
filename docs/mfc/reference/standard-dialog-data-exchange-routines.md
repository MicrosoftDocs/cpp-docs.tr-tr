---
title: Standart İletişim Kutusu Veri Değişimi Rutinleri
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data exchange routines
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
ms.openlocfilehash: 47586f9cff0fcbe2cd7bad31f3d93fed08190830
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511574"
---
# <a name="standard-dialog-data-exchange-routines"></a>Standart İletişim Kutusu Veri Değişimi Rutinleri

Bu konuda, ortak MFC iletişim denetimleri için kullanılan standart iletişim kutusu veri değişimi (DDX) yordamları listelenmektedir.

> [!NOTE]
>  Standart iletişim kutusu veri değişimi yordamları, afxdd_. h üstbilgi dosyasında tanımlanmıştır. Ancak, uygulamalar Afxwin. h 'yi içermelidir.

### <a name="ddx-functions"></a>DDX Işlevleri

|||
|-|-|
|[DDX_CBIndex](#ddx_cbindex)|Birleşik giriş kutusu denetiminin geçerli seçiminin dizinini başlatır veya alır.|
|[DDX_CBString](#ddx_cbstring)|Birleşik giriş kutusu denetiminin düzenleme alanının geçerli içeriğini başlatır veya alır.|
|[DDX_CBStringExact](#ddx_cbstringexact)|Birleşik giriş kutusu denetiminin düzenleme alanının geçerli içeriğini başlatır veya alır.|
|[DDX_Check](#ddx_check)|Bir onay kutusu denetiminin geçerli durumunu başlatır veya alır.|
|[DDX_Control](#ddx_control)|Bir iletişim kutusu içindeki belirli bir denetim alt sınıfları.|
|[DDX_DateTimeCtrl](#ddx_datetimectrl)|Tarih ve saat seçici denetiminin tarih ve/veya saat verilerini başlatır veya alır.|
|[DDX_IPAddress](#ddx_ipaddress)|Bir IP adresi denetiminin geçerli değerini başlatır veya alır.|
|[DDX_LBIndex](#ddx_lbindex)|Liste kutusu denetiminin geçerli seçiminin dizinini başlatır veya alır.|
|[DDX_LBString](#ddx_lbstring)|Liste kutusu denetimi içindeki geçerli seçimi başlatır veya alır.|
|[DDX_LBStringExact](#ddx_lbstringexact)|Liste kutusu denetimi içindeki geçerli seçimi başlatır veya alır.|
|[DDX_ManagedControl](#ddx_managedcontrol)|Denetimin kaynak KIMLIĞIYLE eşleşen bir .NET denetimi oluşturur.|
|[DDX_MonthCalCtrl](#ddx_monthcalctrl)|Aylık takvim denetiminin geçerli değerini başlatır veya alır.|
|[DDX_Radio](#ddx_radio)|Radyo denetim grubu içinde işaretlenmiş olan radyo denetiminin 0 tabanlı dizinini başlatır veya alır.|
|[DDX_Scroll](#ddx_scroll)|Bir kaydırma denetiminin kaydırma kutusunun geçerli konumunu başlatır veya alır.|
|[DDX_Slider](#ddx_slider)|Kaydırıcı denetiminin kaydırma kutusunun geçerli konumunu başlatır veya alır.|
|[DDX_Text](#ddx_text)|Bir düzenleme denetiminin geçerli değerini başlatır veya alır.|

##  <a name="ddx_cbindex"></a>  DDX_CBIndex

İşlevi bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir **int** veri üyesi içindeki bir Birleşik giriş kutusu denetimi arasında int verilerinin aktarılmasını yönetir. `DDX_CBIndex`

```
void AFXAPI DDX_CBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Denetim özelliğiyle ilişkili Birleşik giriş kutusu denetiminin kaynak KIMLIĞI.

*indeks*<br/>
İletişim kutusu, form görünümü veya veri alışverişi yapılan denetim görünümü nesnesinin üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, dizin geçerli Birleşik giriş kutusu seçiminin dizinine ayarlanır. `DDX_CBIndex` Hiçbir öğe seçilmezse, *Dizin* 0 olarak ayarlanır.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

##  <a name="ddx_cbstring"></a>DDX_CBString

İşlevi bir iletişim kutusu, form `CString` görünümü veya `CString` denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir veri üyesi içindeki bir Birleşik giriş kutusu denetiminin düzenleme denetimi arasında veri aktarımını yönetir. `DDX_CBString`

```
void AFXAPI DDX_CBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Denetim özelliğiyle ilişkili Birleşik giriş kutusu denetiminin kaynak KIMLIĞI.

*value*<br/>
İletişim kutusu, form görünümü veya veri alışverişi yapılan denetim görünümü nesnesinin üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, değer geçerli Birleşik giriş kutusu seçimine ayarlanır. `DDX_CBString` Hiçbir öğe seçilmezse, *değer* sıfır uzunluklu bir dizeye ayarlanır.

> [!NOTE]
>  Birleşik giriş kutusu bir açılan liste kutusu ise, değiştirilen değer 255 karakterle sınırlıdır.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

##  <a name="ddx_cbstringexact"></a>DDX_CBStringExact

İşlevi bir iletişim kutusu, form `CString` görünümü veya `CString` denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir veri üyesi içindeki bir Birleşik giriş kutusu denetiminin düzenleme denetimi arasında veri aktarımını yönetir. `DDX_CBStringExact`

```
void AFXAPI DDX_CBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Denetim özelliğiyle ilişkili Birleşik giriş kutusu denetiminin kaynak KIMLIĞI.

*value*<br/>
İletişim kutusu, form görünümü veya veri alışverişi yapılan denetim görünümü nesnesinin üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, değer geçerli Birleşik giriş kutusu seçimine ayarlanır. `DDX_CBStringExact` Hiçbir öğe seçilmezse, *değer* sıfır uzunluklu bir dizeye ayarlanır.

> [!NOTE]
>  Birleşik giriş kutusu bir açılan liste kutusu ise, değiştirilen değer 255 karakterle sınırlıdır.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

##  <a name="ddx_check"></a>DDX_Check

İşlevi, bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir **int** veri üyesi içindeki bir onay kutusu denetimi arasında int verilerinin aktarılmasını yönetir. `DDX_Check`

```
void AFXAPI DDX_Check(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Denetim özelliğiyle ilişkili onay kutusu denetiminin kaynak KIMLIĞI.

*value*<br/>
İletişim kutusu, form görünümü veya veri alışverişi yapılan denetim görünümü nesnesinin üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, değeri onay kutusu denetiminin geçerli durumu olarak ayarlanır. `DDX_Check` Olası durum değerlerinin listesi için, Windows SDK [BM_GETCHECK](/windows/win32/Controls/bm-getcheck) bakın.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

##  <a name="ddx_control"></a>DDX_Control

İşlevi, iletişim kutusu, form görünümü veya denetim görünümü nesnesinin nıdc tarafından belirtilen denetimin alt sınıfları. `DDX_Control`

```
void AFXAPI DDX_Control(
    CDataExchange* pDX,
    int nIDC,
    CWnd& rControl);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*Nıdc*<br/>
Alt sınıflandırılacak denetimin kaynak KIMLIĞI.

*rControl*<br/>
Belirtilen denetimle ilgili iletişim kutusu, form görünümü veya denetim görünümü nesnesinin üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

`DoDataExchange` İşlev çağrıldığında, *PDX* nesnesi Framework tarafından sağlanır. Bu nedenle `DDX_Control` , yalnızca `DoDataExchange`geçersiz kılmanın içinde çağrılmalıdır.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

##  <a name="ddx_datetimectrl"></a>DDX_DateTimeCtrl

İşlevi bir iletişim kutusu veya form görünümü nesnesindeki bir tarih ve saat seçici denetimi ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) arasında tarih ve/veya saat verilerinin aktarımını ve iletişim kutusu ya da formun bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya [copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) veri üyesini yönetir `DDX_DateTimeCtrl` nesneyi görüntüle.

```
void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,
    int nIDC,
    CTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar. Bu nesneyi silmeniz gerekmez.

*Nıdc*<br/>
Üye değişkeniyle ilişkili tarih ve saat seçici denetiminin kaynak KIMLIĞI.

*value*<br/>
İlk iki sürümde, veri alışverişi yapılan bir `CTime` veya `COleDateTime` üye değişkenine, iletişim kutusuna, Form görünümüne veya denetim görünümü nesnesine bir başvuru. Üçüncü sürümde, bir `CString` veri üyesi denetim görünümü nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, değer tarih ve saat seçici denetiminin geçerli durumu olarak ayarlanır veya değişim yönüne bağlı olarak denetim *değer*olarak ayarlanır. `DDX_DateTimeCtrl`

Yukarıdaki üçüncü sürümde, `DDX_DateTimeCtrl` `CString` veri aktarımını denetim görünümü nesnesinin bir tarih saat denetimi ve [CString](../../atl-mfc-shared/reference/cstringt-class.md) veri üyesi arasında yönetir. Dize, tarihleri ve saatleri biçimlendirmek için geçerli yerel ayarların kuralları kullanılarak biçimlendirilir.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="ddx_managedcontrol"></a>DDX_ManagedControl

Denetimin kaynak KIMLIĞIYLE eşleşen bir .NET denetimi oluşturur.

### <a name="syntax"></a>Sözdizimi

```
template <typename T>
void DDX_ManagedControl(
   CDataExchange* pDX,
   int nIDC,
   CWinFormsControl<T>& control );
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange sınıf](cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Denetim özelliğiyle ilişkili denetimin kaynak KIMLIĞI.

*control*<br/>
Bir [CWinFormsControl Class](cwinformscontrol-class.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

`DDX_ManagedControl`kaynak denetim KIMLIĞIYLE eşleşen bir denetim oluşturmak için [CWinFormsControl:: CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol) çağırır. `DDX_ManagedControl` [CDialog:: OnInitDialog](cdialog-class.md#oninitdialog)içindeki Kaynak kimliklerinden denetimler oluşturmak için kullanın. Veri değişimi için, Windows Forms denetimleriyle DDX/DDV işlevlerini kullanmanız gerekmez.

Daha fazla bilgi için [nasıl yapılır: Windows Forms](../../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)Ile ddx/ddv veri bağlamayı yapın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms. h

##  <a name="ddx_ipaddress"></a>DDX_IPAddress

`DDX_IPAddress` İşlevi bir IP adresi denetimi ve denetim görünümü nesnesinin bir veri üyesi arasında veri aktarımını yönetir.

```
void AFXAPI DDX_IPAddress(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Denetim özelliğiyle ilişkili IP adresi denetiminin kaynak KIMLIĞI.

*value*<br/>
IP adresi denetiminin dört alan değerini içeren DWORD başvurusu. Alanlar doldurulmuş veya aşağıdaki şekilde okundu.

|Alan|Alan değerini içeren bitler|
|-----------|-------------------------------------|
|3|0 ila 7|
|2|8 ila 15|
|1\.|16 ila 23|
|0|24 ila 31|

Değeri okumak için Win32 [IPM_GETADDRESS](/windows/win32/Controls/ipm-getaddress) kullanın veya değeri dolduracak şekilde [IPM_SETADDRESS](/windows/win32/Controls/ipm-setaddress) kullanın. Bu iletiler Windows SDK açıklanmaktadır.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, *değeri* IP adresi denetiminden okur veya Exchange yönüne bağlı olarak denetime değer yazılır. `DDX_IPAddress`

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

##  <a name="ddx_lbindex"></a>  DDX_LBIndex

İşlevi, bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir **int** veri üyesi içindeki bir liste kutusu denetimi arasında int verilerinin aktarılmasını yönetir. `DDX_LBIndex`

```
void AFXAPI DDX_LBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Denetim özelliğiyle ilişkili liste kutusu denetiminin kaynak KIMLIĞI.

*indeks*<br/>
İletişim kutusu, form görünümü veya veri alışverişi yapılan denetim görünümü nesnesinin üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, dizin geçerli liste kutusu seçiminin dizinine ayarlanır. `DDX_LBIndex` Hiçbir öğe seçilmezse, *Dizin* -1 olarak ayarlanır.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

##  <a name="ddx_lbstring"></a>DDX_LBString

İşlevi bir iletişim kutusu, form `CString` görünümü veya `CString` denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir veri üyesi olan bir liste kutusu denetimi arasında veri aktarımını yönetir. `DDX_LBString`

```
void AFXAPI DDX_LBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Denetim özelliğiyle ilişkili liste kutusu denetiminin kaynak KIMLIĞI.

*value*<br/>
İletişim kutusu, form görünümü veya veri alışverişi yapılan denetim görünümü nesnesinin üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

Bir liste kutusu denetimine veri aktarmak için çağrıldığında, ilk eşleşen değeri olan denetimdeki ilk öğe seçilir. `DDX_LBString` (Yalnızca bir ön ek yerine tüm öğeyi eşleştirmek için, [DDX_LBStringExact](#ddx_lbstringexact)kullanın.) Eşleşme yoksa, hiçbir öğe seçilmedi. Eşleştirme, büyük/küçük harfe duyarsızdır.

Bir liste kutusu denetiminden veri aktarmak için çağrıldığında, değer geçerli liste kutusu seçimine ayarlanır. `DDX_LBString` Hiçbir öğe seçilmezse, *değer* sıfır uzunluklu bir dizeye ayarlanır.

> [!NOTE]
>  Liste kutusu bir açılan liste kutusu ise, değiştirilen değer 255 karakterle sınırlıdır.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

##  <a name="ddx_lbstringexact"></a>DDX_LBStringExact

İşlevi bir iletişim kutusu, form `CString` görünümü veya `CString` denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir veri üyesi olan bir liste kutusu denetiminin düzenleme denetimi arasında veri aktarımını yönetir. `DDX_CBStringExact`

```
void AFXAPI DDX_LBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Denetim özelliğiyle ilişkili liste kutusu denetiminin kaynak KIMLIĞI.

*value*<br/>
İletişim kutusu, form görünümü veya veri alışverişi yapılan denetim görünümü nesnesinin üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

Bir liste kutusu denetimine veri aktarmak için çağrıldığında, değeri eşleşen denetimdeki ilk öğe seçilir. `DDX_LBStringExact` (Tüm öğe yerine yalnızca bir ön eki eşleştirmek için [DDX_LBString](#ddx_lbstring)kullanın.) Eşleşme yoksa, hiçbir öğe seçilmedi. Eşleştirme, büyük/küçük harfe duyarsızdır.

Bir liste kutusu denetiminden veri aktarmak için çağrıldığında, değer geçerli liste kutusu seçimine ayarlanır. `DDX_CBStringExact` Hiçbir öğe seçilmezse, *değer* sıfır uzunluklu bir dizeye ayarlanır.

> [!NOTE]
>  Liste kutusu bir açılan liste kutusu ise, değiştirilen değer 255 karakterle sınırlıdır.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

##  <a name="ddx_monthcalctrl"></a>DDX_MonthCalCtrl

İşlevi bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile bir ay Takvim denetimi ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) arasında tarih verilerinin aktarımını, iletişim kutusunun bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya [copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) veri üyesini yönetir, form `DDX_MonthCalCtrl` Görünüm veya denetim nesnesi.

```
void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,
    int nIDC,
    CTime& value);

void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar. Bu nesneyi silmeniz gerekmez.

*Nıdc*<br/>
Üye değişkeniyle ilişkili aylık takvim denetiminin kaynak KIMLIĞI.

*value*<br/>
Veri alışverişi yapılan `CTime` iletişim kutusu `COleDateTime` , form görünümü veya denetim görünümü nesnesinin veya üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Denetim yalnızca bir tarih değerini yönetir. Zaman nesnesi içindeki zaman alanları, denetim penceresinin oluşturulma zamanını yansıtacak şekilde ayarlanır veya ' a çağrı `CMonthCalCtrl::SetCurSel`ile denetimde ayarlanan zaman ayarlanır.

Çağrıldığında, değer aylık takvim denetiminin geçerli durumuna ayarlanır. `DDX_MonthCalCtrl`

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

##  <a name="ddx_radio"></a>DDX_Radio

İşlevi bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir **int** veri üyesi içindeki bir radyo denetim grubu arasında int verilerinin aktarımını yönetir. `DDX_Radio` **İnt** veri üyesinin değeri, Grup içindeki hangi radyo düğmesine göre belirlenir.

```
void AFXAPI DDX_Radio(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Gruptaki ilk radyo denetiminin kaynak KIMLIĞI.

*value*<br/>
İletişim kutusu, form görünümü veya veri alışverişi yapılan denetim görünümü nesnesinin üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, değeri radyo denetim grubunun geçerli durumuna ayarlanır. `DDX_Radio` Değer, işaretlenmiş olan radyo denetiminin 0 tabanlı bir dizini olarak ayarlanır veya hiçbir radyo denetimi denetlendiğinde-1 ' dir.

Örneğin, gruptaki ilk radyo düğmesinin işaretli olması durumunda (WS_GROUP stilinde düğme) **int** üyesinin değeri 0 ' dır ve bu şekilde devam eder.

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

##  <a name="ddx_scroll"></a>DDX_Scroll

İşlevi, bir iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin bir **int** veri üyesi içindeki bir kaydırma çubuğu denetimi arasında int verilerinin aktarılmasını yönetir. `DDX_Scroll`

```
void AFXAPI DDX_Scroll(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir `CDataExchange` nesne işaretçisi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Denetim özelliğiyle ilişkili kaydırma çubuğu denetiminin kaynak KIMLIĞI.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesinin, verilerin alınıp alındığı bir üye değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, değeri denetimin kaydırma kutusunun geçerli konumuna ayarlanır. `DDX_Scroll` Denetimin kaydırma kutusunun geçerli konumuyla ilişkili değerler hakkında daha fazla bilgi için, Windows SDK bkz. [GetScrollPos](/windows/win32/api/winuser/nf-winuser-getscrollpos) .

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

##  <a name="ddx_slider"></a>DDX_Slider

İşlevi, bir iletişim kutusu veya form görünümü içindeki bir kaydırıcı denetimi ve iletişim kutusu ya da form görünümü nesnesinin bir **int** veri üyesi arasında int verilerinin aktarılmasını yönetir. `DDX_Slider`

```
void AFXAPI DDX_Slider(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
Kaydırıcı denetiminin kaynak KIMLIĞI.

*value*<br/>
Değiş tokuş edilecek değere bir başvuru. Bu parametre kaydırıcı denetiminin geçerli konumunu tutar veya ayarlar.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, değer denetimin kaydırma kutusunun geçerli konumuna ayarlanır veya değişim yönüne bağlı olarak bu değer konumu alır. `DDX_Slider`

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Kaydırıcı denetimleri hakkında daha fazla bilgi için bkz. [CSliderCtrl kullanma](../../mfc/using-csliderctrl.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

##  <a name="ddx_text"></a>DDX_Text

`CString` [](../../atl-mfc-shared/reference/cstringt-class.md)İşlevi bir iletişim kutusu, form görünümü veya denetim görünümü ve CString verileri içindeki bir düzenleme denetimi arasında int, UINT, Long, DWORD,, float veya Double verilerinin aktarımını yönetir `DDX_Text` iletişim kutusu, form görünümü veya denetim görünümü nesnesinin üyesi.

```
void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    BYTE& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    short& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    int& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    UINT& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    long& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    CString& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    float& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    double& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    COleCurrency& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi. Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*Nıdc*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesindeki bir düzenleme denetiminin KIMLIĞI.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünümü nesnesi içindeki bir veri üyesine başvuru. *Değerin* veri türü, kullandığınız aşırı yüklenmiş sürümlere `DDX_Text` bağlıdır.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_. h

## <a name="see-also"></a>Ayrıca bkz.

[Standart İletişim Kutusu Veri Doğrulama Rutinleri](standard-dialog-data-validation-routines.md)<br/>
[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
[CWinFormsControl:: CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol)<br/>
[CDialog:: OnInitDialog](cdialog-class.md#oninitdialog)
