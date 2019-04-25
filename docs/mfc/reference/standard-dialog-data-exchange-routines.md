---
title: Standart İletişim Kutusu Veri Değişimi Rutinleri
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data exchange routines
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
ms.openlocfilehash: 05eaa86133bb55cfbf62ec68f81e7ca7d9ab169b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310012"
---
# <a name="standard-dialog-data-exchange-routines"></a>Standart İletişim Kutusu Veri Değişimi Rutinleri

Bu konu, genel MFC iletişim kutusu denetimleri için kullanılan standart iletişim kutusu veri değişimi (DDX) rutinleri listeler.

> [!NOTE]
>  Standart iletişim kutusu veri değişimi rutinleri üstbilgi dosyası afxdd_.h içinde tanımlanır. Ancak, uygulamaları afxwin.h içermelidir.

### <a name="ddx-functions"></a>DDX işlevleri

|||
|-|-|
|[DDX_CBIndex](#ddx_cbindex)|Başlatır veya birleşik giriş kutusu denetimi oluşan geçerli seçimi dizinini alır.|
|[DDX_CBString](#ddx_cbstring)|Başlatır veya birleşik giriş kutusu denetimi Düzenle alanının geçerli içeriğini alır.|
|[DDX_CBStringExact](#ddx_cbstringexact)|Başlatır veya birleşik giriş kutusu denetimi Düzenle alanının geçerli içeriğini alır.|
|[DDX_Check](#ddx_check)|Başlatır veya onay kutusu denetimi geçerli durumunu alır.|
|[DDX_Control](#ddx_control)|Alt sınıfların bir iletişim kutusu içinde belirli bir denetim.|
|[DDX_DateTimeCtrl](#ddx_datetimectrl)|Başlatır veya tarih ve/veya saat verileri bir tarih ve saat seçici denetimi değerini alır.|
|[DDX_IPAddress](#ddx_ipaddress)|Başlatır veya bir IP adresi denetimi geçerli değerini alır.|
|[DDX_LBIndex](#ddx_lbindex)|Başlatır veya bir liste kutusu denetimini oluşan geçerli seçimi dizinini alır.|
|[DDX_LBString](#ddx_lbstring)|Geçerli seçimi içinde bir liste kutusu denetimini alır veya belirler başlatır.|
|[DDX_LBStringExact](#ddx_lbstringexact)|Geçerli seçimi içinde bir liste kutusu denetimini alır veya belirler başlatır.|
|[DDX_ManagedControl](#ddx_managedcontrol)|Denetimin kaynak kimliğiyle eşleşen bir .NET denetimi oluşturur|
|[DDX_MonthCalCtrl](#ddx_monthcalctrl)|Başlatır veya bir ay takvimi geçerli değerini alır.|
|[DDX_Radio](#ddx_radio)|Başlatır veya şu anda bir radyo denetimi grubu içinde kullanıma radyo denetimi 0 tabanlı dizinini alır.|
|[DDX_Scroll](#ddx_scroll)|Başlatır veya kaydırma denetim thumb geçerli konumunu alır.|
|[DDX_Slider](#ddx_slider)|Başlatır veya bir kaydırıcı denetiminin thumb geçerli konumunu alır.|
|[DDX_Text](#ddx_text)|Başlatır veya bir düzenleme denetimi geçerli değerini alır.|

##  <a name="ddx_cbindex"></a>  DDX_CBIndex

`DDX_CBIndex` İşlevi aktarımını yöneten **int** arasında bir iletişim kutusu, birleşik giriş kutusu denetiminde veri görünümü veya denetim görünüm nesnesi oluşturur ve bir **int** iletişim kutusu, form görünümü veya denetim veri üyesi Görünüm nesnesi.

```
void AFXAPI DDX_CBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliği ile ilişkili birleşik giriş kutusu denetimi kaynak kimliği.

*Dizin*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeninin bir başvuru.

### <a name="remarks"></a>Açıklamalar

Zaman `DDX_CBIndex` çağrıldığında *dizin* birleşik giriş kutusu seçilen dizinine ayarlanır. Hiçbir öğe seçili değilse *dizin* 0 olarak ayarlayın.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddx_cbstring"></a>  DDX_CBString

`DDX_CBString` İşlevi aktarımını yöneten `CString` verileri arasında bir iletişim kutusu, birleşik giriş kutusu denetiminde düzenleme denetimi form görünümü veya denetim görünüm nesnesi ve bir `CString` iletişim kutusu, form görünümü veya denetim view nesnesinin veri üyesi.

```
void AFXAPI DDX_CBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliği ile ilişkili birleşik giriş kutusu denetimi kaynak kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeninin bir başvuru.

### <a name="remarks"></a>Açıklamalar

Zaman `DDX_CBString` çağrıldığında *değer* geçerli birleşik giriş kutusu seçimi ayarlanır. Hiçbir öğe seçili değilse *değer* sıfır uzunluklu bir dizeye ayarlayın.

> [!NOTE]
>  Birleşik giriş kutusundaki açılır liste kutusu ise, değiştirilen değer 255 karakterle sınırlıdır.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddx_cbstringexact"></a>  DDX_CBStringExact

`DDX_CBStringExact` İşlevi aktarımını yöneten `CString` verileri arasında bir iletişim kutusu, birleşik giriş kutusu denetiminde düzenleme denetimi form görünümü veya denetim görünüm nesnesi ve bir `CString` iletişim kutusu, form görünümü veya denetim view nesnesinin veri üyesi.

```
void AFXAPI DDX_CBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliği ile ilişkili birleşik giriş kutusu denetimi kaynak kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeninin bir başvuru.

### <a name="remarks"></a>Açıklamalar

Zaman `DDX_CBStringExact` çağrıldığında *değer* geçerli birleşik giriş kutusu seçimi ayarlanır. Hiçbir öğe seçili değilse *değer* sıfır uzunluklu bir dizeye ayarlayın.

> [!NOTE]
>  Birleşik giriş kutusundaki açılır liste kutusu ise, değiştirilen değer 255 karakterle sınırlıdır.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddx_check"></a>  DDX_Check

`DDX_Check` İşlevi aktarımını yöneten **int** arasında bir iletişim kutusu bir onay kutusu denetiminde veri form görünümü veya denetim görünüm nesnesi ve bir **int** iletişim kutusu, form görünümü veya denetim veri üyesi Görünüm nesnesi.

```
void AFXAPI DDX_Check(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliği ile ilişkilendirilmiş onay kutusu denetimi kaynak kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeninin bir başvuru.

### <a name="remarks"></a>Açıklamalar

Zaman `DDX_Check` çağrıldığında *değer* onay kutusu denetimi geçerli durumuna ayarlanır. Olası durum değerleri listesi için bkz. [BM_GETCHECK](/windows/desktop/Controls/bm-getcheck) Windows SDK.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddx_control"></a>  DDX_Control

`DDX_Control` Alt sınıflar tarafından belirtilen denetim, işlev *nIDC*, iletişim kutusu, form görünümü veya denetim görünüm nesnesi.

```
void AFXAPI DDX_Control(
    CDataExchange* pDX,
    int nIDC,
    CWnd& rControl);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne.

*nIDC*<br/>
Kaynak Kimliği sınıflandırılacak denetimi.

*rControl*<br/>
İletişim kutusu, form görünümü veya belirtilen denetimle ilişkili denetim view nesnesinin üye değişkeninin bir başvuru.

### <a name="remarks"></a>Açıklamalar

*PDX* nesne framework tarafından sağlanan zaman `DoDataExchange` işlevi çağrılır. Bu nedenle, `DDX_Control` yalnızca kılacağınızı çağrılmalıdır `DoDataExchange`.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddx_datetimectrl"></a>  DDX_DateTimeCtrl

`DDX_DateTimeCtrl` İşlevi bir tarih ve Saat Seçici denetimini arasında tarih ve/veya saat veri aktarımını yönetir ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) bir iletişim kutusu veya form Görünüm nesnesi ve ya da bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) iletişim kutusu veya form view nesnesinin veri üyesi.

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
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar. Bu nesne silmeniz gerekmez.

*nIDC*<br/>
Üye değişkeni ile ilişkili tarih ve Saat Seçici denetimini kaynak kimliği.

*value*<br/>
İlk iki sürümlerinde, bir başvuru bir `CTime` veya `COleDateTime` üye değişkeni, iletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi. Üçüncü sürümünde, bir başvuru bir `CString` veri üyesi denetim görünüm nesnesi.

### <a name="remarks"></a>Açıklamalar

Zaman `DDX_DateTimeCtrl` çağrılır, *değeri* geçerli ayarlanmış tarih ve saat seçici denetimi veya denetim durumunu ayarlanır *değeri*exchange yönüne bağlı olarak.

Yukarıdaki üçüncü sürümünde `DDX_DateTimeCtrl` aktarımını yöneten `CString` verileri arasında bir tarih saat denetimi ve bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) denetim view nesnesinin veri üyesi. Dize, tarihleri ve saatleri biçimlendirme için geçerli yerel ayarın kuralları kullanılarak biçimlendirilir.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

## <a name="ddx_managedcontrol"></a>  DDX_ManagedControl

Denetimin kaynak kimliğiyle eşleşen bir .NET denetimi oluşturur

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
Bir işaretçi bir [CDataExchange sınıfı](cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetimin Denetim özelliği ile ilişkili kaynak kimliği.

*control*<br/>
Bir başvuru bir [CWinFormsControl sınıfı](cwinformscontrol-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

`DDX_ManagedControl` çağrıları [CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol) kaynak denetimi kimlikle eşleşen bir denetim oluşturmak için Kullanım `DDX_ManagedControl` kaynak kimlikleri denetimleri oluşturmak için [CDialog::OnInitDialog](cdialog-class.md#oninitdialog). Veri değişimi için Windows Forms denetimleri ile DDX/DDV işlevler kullanın gerekmez.

Daha fazla bilgi için [nasıl yapılır: Windows Forms ile DDX/DDV veri bağlaması yapma](../../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h

##  <a name="ddx_ipaddress"></a>  Ddx_ıpaddress

`DDX_IPAddress` İşlevi, bir IP adresi denetimini ve denetim view nesnesinin veri üyesi arasında veri aktarımını yönetir.

```
void AFXAPI DDX_IPAddress(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliği ile ilişkili IP adresi denetimi kaynak kimliği.

*value*<br/>
IP adresi denetimi dört alan değerini içeren DWORD başvuru. Alan dolu veya şu şekilde okuyun.

|Alan|Alan değeri içeren BITS|
|-----------|-------------------------------------|
|3|0 ile 7 arasındaki|
|2|8 ile 15|
|1.|16-23|
|0|24 ile 31|

Win32 kullanın [IPM_GETADDRESS](/windows/desktop/Controls/ipm-getaddress) değeri okunamıyor veya bunları kullanmanızı [IPM_SETADDRESS](/windows/desktop/Controls/ipm-setaddress) değeri doldurmak için. Bu iletiler, Windows SDK'yı açıklanmıştır.

### <a name="remarks"></a>Açıklamalar

Zaman `DDX_IPAddress` çağrılır, *değer* ya da IP adresi denetiminden okuyun veya *değer* exchange birini yöne bağlı olarak denetlemek için yazılır.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddx_lbindex"></a>  DDX_LBIndex

`DDX_LBIndex` İşlevi aktarımını yöneten **int** verileri arasında bir iletişim kutusunda, liste kutusu denetimi form görünümü veya denetim görünüm nesnesi ve bir **int** iletişim kutusu, form görünümü veya denetim veri üyesi Görünüm nesnesi.

```
void AFXAPI DDX_LBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliği ile ilişkilendirilen liste kutusu denetimini kaynak kimliği.

*Dizin*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeninin bir başvuru.

### <a name="remarks"></a>Açıklamalar

Zaman `DDX_LBIndex` çağrıldığında *dizin* geçerli liste kutusu seçenekleri dizinine ayarlanır. Hiçbir öğe seçili değilse *dizin* -1 olarak ayarlanır.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddx_lbstring"></a>  DDX_LBString

`DDX_LBString` İşlevi aktarımını yöneten `CString` verileri arasında bir iletişim kutusunda, liste kutusu denetimi form görünümü veya denetim görünüm nesnesi ve bir `CString` iletişim kutusu, form görünümü veya denetim view nesnesinin veri üyesi.

```
void AFXAPI DDX_LBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliği ile ilişkilendirilen liste kutusu denetimini kaynak kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeninin bir başvuru.

### <a name="remarks"></a>Açıklamalar

Zaman `DDX_LBString` liste kutusu denetimi, ilk öğesi denetiminde olan başlangıcıyla eşleşir veri aktarmak için çağrılan *değer* seçilir. (Öğenin tamamı yerine yalnızca bir ön eki eşleşmesi için kullanın [DDX_LBStringExact](#ddx_lbstringexact).) Herhangi bir eşleşme varsa, hiçbir öğe seçili. Eşleştirme büyük küçük harfe duyarlıdır.

Zaman `DDX_LBString` bir liste kutusu denetimi ile veri aktarmayı adlı *değer* geçerli liste kutusu seçenekleri ayarlayın. Hiçbir öğe seçili değilse *değer* sıfır uzunluklu bir dizeye ayarlayın.

> [!NOTE]
>  Aşağı açılan liste kutusu liste kutusunun ise değiştirilen değer 255 karakterle sınırlıdır.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddx_lbstringexact"></a>  DDX_LBStringExact

`DDX_CBStringExact` İşlevi aktarımını yöneten `CString` verileri arasında bir iletişim kutusunda, bir liste kutusu denetimini düzenleme denetimi form görünümü veya denetim görünüm nesnesi ve bir `CString` iletişim kutusu, form görünümü veya denetim view nesnesinin veri üyesi.

```
void AFXAPI DDX_LBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliği ile ilişkilendirilen liste kutusu denetimini kaynak kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeninin bir başvuru.

### <a name="remarks"></a>Açıklamalar

Zaman `DDX_LBStringExact` liste kutusu denetimi, denetimin eşleşen listedeki ilk öğe için veri aktarımı için çağrılan *değer* seçilir. (Öğenin tamamı yerine yalnızca bir ön eki eşleşmesi için kullanın [DDX_LBString](#ddx_lbstring).) Herhangi bir eşleşme varsa, hiçbir öğe seçili. Eşleştirme büyük küçük harfe duyarlıdır.

Zaman `DDX_CBStringExact` bir liste kutusu denetimi ile veri aktarmayı adlı *değer* geçerli liste kutusu seçenekleri ayarlayın. Hiçbir öğe seçili değilse *değer* sıfır uzunluklu bir dizeye ayarlayın.

> [!NOTE]
>  Aşağı açılan liste kutusu liste kutusunun ise değiştirilen değer 255 karakterle sınırlıdır.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddx_monthcalctrl"></a>  DDX_MonthCalCtrl

`DDX_MonthCalCtrl` İşlevi bir ay takvimi arasında tarih veri aktarımını yönetir ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) bir iletişim kutusu, form görünümü veya denetim görünüm nesnesi ve ya da bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) iletişim kutusu, form görünümü veya denetim view nesnesinin veri üyesi.

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
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar. Bu nesne silmeniz gerekmez.

*nIDC*<br/>
Aylık takvim denetiminin kaynak Kimliğini üye değişkeni ile ilişkili.

*value*<br/>
Bir başvuru bir `CTime` veya `COleDateTime` üye değişkeni iletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Denetim, yalnızca bir tarih değeri yönetir. Zaman zaman nesnesindeki oluşturulma zamanı denetimi pencerenin yansıtacak şekilde kümesi veya her zaman çağrısıyla denetimde ayarlanmış alanlar `CMonthCalCtrl::SetCurSel`.

Zaman `DDX_MonthCalCtrl` çağrıldığında *değer* aylık takvim denetiminin geçerli durumuna ayarlanır.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddx_radio"></a>  DDX_Radio

`DDX_Radio` İşlevi aktarımını yöneten **int** arasında bir iletişim kutusu, radyo denetimi grubunda veri form görünümü veya denetim görünüm nesnesi ve bir **int** iletişim kutusu, form görünümü veya denetim veri üyesi Görünüm nesnesi. Değerini **int** veri üyesi göre hangi radyo düğmesi grubundaki seçili belirlenir.

```
void AFXAPI DDX_Radio(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Gruptaki ilk radyo denetimi kaynak kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeninin bir başvuru.

### <a name="remarks"></a>Açıklamalar

Zaman `DDX_Radio` çağrıldığında *değer* radyo denetimi grubunun geçerli duruma ayarlayın. Değer bir 0 tabanlı bir dizin şu anda kullanıma radyo denetimi ayarlanır veya radyo denetim yok, -1 denetlenir.

Örneğin, ilk radyo düğmesi grubunda durumda (WS_GROUP stili düğme) değerini işaretli **int** üyesi olan 0 ve benzeri.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddx_scroll"></a>  DDX_Scroll

`DDX_Scroll` İşlevi aktarımını yöneten **int** verileri arasında bir iletişim kutusunda bir kaydırma çubuğu denetimi form görünümü veya denetim görünüm nesnesi ve bir **int** iletişim kutusu, form görünümü veya denetim veri üyesi Görünüm nesnesi.

```
void AFXAPI DDX_Scroll(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliği ile ilişkili kaydırma çubuğu denetimi kaynak kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim üye değişkeni başvuru ile veri değişimi nesne görüntüleyin.

### <a name="remarks"></a>Açıklamalar

Zaman `DDX_Scroll` çağrıldığında *değer* thumb denetiminin geçerli konumu için ayarlanır. Thumb denetiminin geçerli konumu ile ilişkili değerler hakkında daha fazla bilgi için bkz. [GetScrollPos](/windows/desktop/api/winuser/nf-winuser-getscrollpos) Windows SDK.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddx_slider"></a>  DDX_Slider

`DDX_Slider` İşlevi aktarımını yöneten **int** verileri arasında bir iletişim kutusu veya form görünümünde bir kaydırıcı denetimi ve bir **int** iletişim kutusu veya form view nesnesinin veri üyesi.

```
void AFXAPI DDX_Slider(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Kaydırıcı denetimi kaynak kimliği.

*value*<br/>
Değiştirilecek değerine bir başvuru. Bu parametre, tutan veya kaydırıcı denetiminin geçerli konumu ayarlar.

### <a name="remarks"></a>Açıklamalar

Zaman `DDX_Slider` çağrıldığında *değer* denetimin thumb geçerli konuma ayarlanır veya exchange birini yöne bağlı olarak konumu ' değerini alır.

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Kaydırıcı denetimleri hakkında daha fazla bilgi için bkz. [CSliderCtrl kullanma](../../mfc/using-csliderctrl.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

##  <a name="ddx_text"></a>  DDX_Text

`DDX_Text` İşlevi aktarımını yöneten **int**, **UINT**, **uzun**, DWORD, `CString`, **float**, veya **çift** verileri arasında bir iletişim kutusunda, bir düzenleme denetimi form görünümü veya denetim görünümü ve bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) iletişim kutusu, form görünümü veya denetim view nesnesinin veri üyesi.

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
Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.

*nIDC*<br/>
Bir düzenleme denetimi iletişim kutusu, form görünümü veya denetim view nesnesinin kimliği.

*value*<br/>
İletişim kutusu, form görünümü veya denetim view nesnesinin veri üyesine başvuru. Veri türü *değer* bağımlı olduğu aşırı yüklenmiş sürümlerinin `DDX_Text` kullanırsınız.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdd_.h

## <a name="see-also"></a>Ayrıca bkz.

[Standart İletişim Kutusu Veri Doğrulama Rutinleri](standard-dialog-data-validation-routines.md)<br/>
[Makroları ve genel öğeleri](mfc-macros-and-globals.md)<br/>
[CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol)<br/>
[CDialog::OnInitDialog](cdialog-class.md#oninitdialog)
