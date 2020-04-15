---
title: Standart İletişim Kutusu Veri Değişimi Rutinleri
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data exchange routines
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
ms.openlocfilehash: 83d4a66cd3ec41008506b55f0b351fd9bcbc24b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372927"
---
# <a name="standard-dialog-data-exchange-routines"></a>Standart İletişim Kutusu Veri Değişimi Rutinleri

Bu konu, ortak MFC iletişim denetimleri için kullanılan standart iletişim veri alışverişi (DDX) yordamlarını listeler.

> [!NOTE]
> Standart iletişim veri alışverişi yordamları afxdd_.h. üstbilgi dosyasında tanımlanır. Ancak, uygulamalar afxwin.h içermelidir.

### <a name="ddx-functions"></a>DDX Fonksiyonları

|||
|-|-|
|[DDX_CBIndex](#ddx_cbindex)|Açılan kutu denetiminin geçerli seçiminin dizinini başolarak yanıtlar veya alır.|
|[DDX_CBString](#ddx_cbstring)|Açılan kutu denetiminin edinimi alanının geçerli içeriğini başolarak yanıtlar veya alır.|
|[DDX_CBStringExact](#ddx_cbstringexact)|Açılan kutu denetiminin edinimi alanının geçerli içeriğini başolarak yanıtlar veya alır.|
|[DDX_Check](#ddx_check)|Onay kutusu denetiminin geçerli durumunu başolarak karşılar veya alır.|
|[DDX_Control](#ddx_control)|Bir iletişim kutusu içinde verilen denetimi alt sınıflar.|
|[DDX_DateTimeCtrl](#ddx_datetimectrl)|Tarih ve saat seçici denetiminin tarih ve/veya saat verilerini ilk olarak alır veya alır.|
|[DDX_IPAddress](#ddx_ipaddress)|IP adresi denetiminin geçerli değerini başolarak karşılar veya alır.|
|[DDX_LBIndex](#ddx_lbindex)|Bir liste kutusu denetiminin geçerli seçiminin dizinini başolarak karşılar veya alır.|
|[DDX_LBString](#ddx_lbstring)|Liste kutusu denetiminde geçerli seçimi başlatma veya alma.|
|[DDX_LBStringExact](#ddx_lbstringexact)|Liste kutusu denetiminde geçerli seçimi başlatma veya alma.|
|[DDX_ManagedControl](#ddx_managedcontrol)|Denetimin kaynak kimliğiyle eşleşen bir .NET denetimi oluşturur.|
|[DDX_MonthCalCtrl](#ddx_monthcalctrl)|Bir aylık takvim denetiminin geçerli değerini başolarak karşılar veya alır.|
|[DDX_Radio](#ddx_radio)|Şu anda bir radyo denetim grubu içinde denetlenen radyo denetiminin 0 tabanlı dizinini başolarak karşılar veya alır.|
|[DDX_Scroll](#ddx_scroll)|Kaydırma denetiminin başparmağının geçerli konumunu başolarak alır veya alır.|
|[DDX_Slider](#ddx_slider)|Kaydırıcı denetiminin başparmağının geçerli konumunu başolarak alır veya alır.|
|[DDX_Text](#ddx_text)|Bir edit denetiminin geçerli değerini başolarak karşılar veya alır.|

## <a name="ddx_cbindex"></a><a name="ddx_cbindex"></a>DDX_CBIndex

İşlev, `DDX_CBIndex` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **int** veri üyesi bir açılan kutu denetimi arasında **int** veri aktarımını yönetir.

```cpp
void AFXAPI DDX_CBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliğiyle ilişkili açılan kutu denetiminin kaynak kimliği.

*Dizin*<br/>
İletişim kutusunun, form görünümünün veya verilerin değiş tokuş edildiği denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, `DDX_CBIndex` *dizin* geçerli açılan kutu seçiminin dizinine ayarlanır. Öğe seçili değilse, *dizin* 0 olarak ayarlanır.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_cbstring"></a><a name="ddx_cbstring"></a>DDX_CBString

İşlev, `DDX_CBString` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü `CString` veya denetim görünümü nesnesinin veri üyesindeki bir açılan kutu denetiminin denetimini yönetir. `CString`

```cpp
void AFXAPI DDX_CBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliğiyle ilişkili açılan kutu denetiminin kaynak kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin değiş tokuş edildiği denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, `DDX_CBString` *değer* geçerli açılan kutu seçimine ayarlanır. Öğe seçili değilse, *değer* sıfır uzunlukta bir dize olarak ayarlanır.

> [!NOTE]
> Açılan kutu açılır liste kutusuysa, değiştirilen değer 255 karakterle sınırlıdır.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_cbstringexact"></a><a name="ddx_cbstringexact"></a>DDX_CBStringExact

İşlev, `DDX_CBStringExact` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü `CString` veya denetim görünümü nesnesinin veri üyesindeki bir açılan kutu denetiminin denetimini yönetir. `CString`

```cpp
void AFXAPI DDX_CBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliğiyle ilişkili açılan kutu denetiminin kaynak kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin değiş tokuş edildiği denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, `DDX_CBStringExact` *değer* geçerli açılan kutu seçimine ayarlanır. Öğe seçili değilse, *değer* sıfır uzunlukta bir dize olarak ayarlanır.

> [!NOTE]
> Açılan kutu açılır liste kutusuysa, değiştirilen değer 255 karakterle sınırlıdır.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_check"></a><a name="ddx_check"></a>DDX_Check

İşlev, `DDX_Check` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **int** veri üyesindeki bir onay kutusu denetimi arasında **int** verilerinin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_Check(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliğiyle ilişkili onay kutusu denetiminin kaynak kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin değiş tokuş edildiği denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, `DDX_Check` *değer* onay kutusu denetiminin geçerli durumuna ayarlanır. Olası durum değerlerinin listesi için Windows SDK'daki [BM_GETCHECK](/windows/win32/Controls/bm-getcheck) bakın.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_control"></a><a name="ddx_control"></a>DDX_Control

İşlev, `DDX_Control` iletişim kutusunun, form görünümünün veya denetim görünümü nesnesinin *nIDC*tarafından belirtilen denetimini alt sınıflar.

```cpp
void AFXAPI DDX_Control(
    CDataExchange* pDX,
    int nIDC,
    CWnd& rControl);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*nIDC*<br/>
Alt sınıflanacak denetimin kaynak kimliği.

*rKontrol*<br/>
Belirtilen denetimle ilgili iletişim kutusu, form görünümü veya denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

*PDX* `DoDataExchange` nesnesi, işlev çağrıldığında çerçeve tarafından sağlanır. Bu `DDX_Control` nedenle, yalnızca geçersiz kılma `DoDataExchange`içinde çağrılmalıdır.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_datetimectrl"></a><a name="ddx_datetimectrl"></a>DDX_DateTimeCtrl

İşlev, `DDX_DateTimeCtrl` bir iletişim kutusu veya form görünümü nesnesi ile bir iletişim kutusu veya form görünümü nesnesi ve iletişim kutusunun veya form görünümü nesnesinin [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) veri üyesi arasında tarih ve saat seçici denetimi [(CDateTimeCtrl)](../../mfc/reference/cdatetimectrl-class.md)arasındaki tarih ve/veya saat verilerinin aktarılmasını yönetir.

```cpp
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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar. Bu nesneyi silmeniz gerekmez.

*nIDC*<br/>
Üye değişkenle ilişkili tarih ve saat seçici denetiminin kaynak kimliği.

*Değer*<br/>
İlk iki sürümde, bir `CTime` veya `COleDateTime` üye değişkene, iletişim kutusuna, form görünümüne veya verilerin değiş tokuş edildiği denetim görünümü nesnesine bir başvuru. Üçüncü sürümde, bir `CString` veri üyesi denetim görünümü nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, `DDX_DateTimeCtrl` *değer* tarih ve saat seçici denetiminin geçerli durumuna ayarlanır veya denetim, değişimin yönüne bağlı olarak *değer*olarak ayarlanır.

Yukarıdaki üçüncü sürümde, `DDX_DateTimeCtrl` bir tarih `CString` saati denetimi ile denetim görünümü nesnesinin [CString](../../atl-mfc-shared/reference/cstringt-class.md) veri üyesi arasındaki veri aktarımını yönetir. Dize, tarihleri ve saatleri biçimlendirmek için geçerli yerel in kuralları kullanılarak biçimlendirilir.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_managedcontrol"></a><a name="ddx_managedcontrol"></a>DDX_ManagedControl

Denetimin kaynak kimliğiyle eşleşen bir .NET denetimi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
void DDX_ManagedControl(
   CDataExchange* pDX,
   int nIDC,
   CWinFormsControl<T>& control );
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
[CDataExchange Sınıfı](cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliğiyle ilişkili denetimin kaynak kimliği.

*Denetim*<br/>
[CWinFormsControl Class](cwinformscontrol-class.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

`DDX_ManagedControl`[CWinFormsControl çağırır::Kaynak](cwinformscontrol-class.md#createmanagedcontrol) denetim kimliği eşleşen bir denetim oluşturmak için Yönetilen Kontrol oluşturun. CDialog'daki kaynak id'lerinden denetimler oluşturmak için `DDX_ManagedControl` [kullanın::OnInitDialog.](cdialog-class.md#oninitdialog) Veri alışverişi için Windows Forms denetimleri ile DDX/DDV işlevlerini kullanmanız gerekmez.

Daha fazla bilgi için [bkz: Windows Formlarıyla DDX/DDV Veri Bağlama yapın.](../../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms.h

## <a name="ddx_ipaddress"></a><a name="ddx_ipaddress"></a>DDX_IPAddress

İşlev, `DDX_IPAddress` ip adresi denetimi ile denetim görünümü nesnesinin veri üyesi arasındaki veri aktarımını yönetir.

```cpp
void AFXAPI DDX_IPAddress(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliğiyle ilişkili IP Adresi denetiminin kaynak kimliği.

*Değer*<br/>
IP Adresi denetiminin dört alan değerini içeren DWORD'ye bir başvuru. Alanlar doldurulur veya aşağıdaki gibi okunur.

|Alan|Alan değerini içeren bitler|
|-----------|-------------------------------------|
|3|0 ile 7 arasında|
|2|8 ile 15 arasında|
|1|16 ile 23 arası|
|0|24 ile 31 arası|

Değeri okumak için Win32 [IPM_GETADDRESS'nı](/windows/win32/Controls/ipm-getaddress) kullanın veya değeri doldurmak için [IPM_SETADDRESS](/windows/win32/Controls/ipm-setaddress) kullanın. Bu iletiler Windows SDK'da açıklanmıştır.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, `DDX_IPAddress` *değer* IP Adresi denetiminden okunur *veya* değer değişimin yönüne bağlı olarak denetime yazılır.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_lbindex"></a><a name="ddx_lbindex"></a>DDX_LBIndex

İşlev, `DDX_LBIndex` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **int** veri üyesi ndeki bir liste kutusu denetimi arasında **int** verilerinin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_LBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliğiyle ilişkili liste kutusu denetiminin kaynak kimliği.

*Dizin*<br/>
İletişim kutusunun, form görünümünün veya verilerin değiş tokuş edildiği denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, `DDX_LBIndex` *dizin* geçerli liste kutusu seçiminin dizinine ayarlanır. Öğe seçili değilse, *dizin* -1 olarak ayarlanır.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_lbstring"></a><a name="ddx_lbstring"></a>DDX_LBString

İşlev, `DDX_LBString` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü veya denetim görünümü nesnesinin `CString` `CString` veri üyesindeki liste kutusu denetimi arasında veri aktarımını yönetir.

```cpp
void AFXAPI DDX_LBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliğiyle ilişkili liste kutusu denetiminin kaynak kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin değiş tokuş edildiği denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Bir `DDX_LBString` liste kutusu denetimine veri aktarmak için çağrıldığında, başlangıç *değeri* eşleşen denetimdeki ilk öğe seçilir. (Yalnızca bir önek yerine tüm öğeyi eşleştirmek [için DDX_LBStringExact](#ddx_lbstringexact)kullanın.) Eşleşme yoksa, öğe seçilmez. Eşleştirme büyük/küçük harf duyarsız.

Liste `DDX_LBString` kutusu denetiminden veri aktarmak için çağrıldığında, *değer* geçerli liste kutusu seçimine ayarlanır. Öğe seçili değilse, *değer* sıfır uzunlukta bir dize olarak ayarlanır.

> [!NOTE]
> Liste kutusu açılır liste kutusuysa, değiştirilen değer 255 karakterle sınırlıdır.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_lbstringexact"></a><a name="ddx_lbstringexact"></a>DDX_LBStringExact

İşlev, `DDX_CBStringExact` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü `CString` veya denetim görünümü nesnesinin veri üyesindeki bir liste kutusu denetiminin denetimini yönetir. `CString`

```cpp
void AFXAPI DDX_LBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliğiyle ilişkili liste kutusu denetiminin kaynak kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin değiş tokuş edildiği denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Bir `DDX_LBStringExact` liste kutusu denetimine veri aktarmak için çağrıldığında, *değereşleşen* denetimdeki ilk öğe seçilir. (Maddenin tamamı yerine yalnızca bir önek için [DDX_LBString](#ddx_lbstring)kullanın.) Eşleşme yoksa, öğe seçilmez. Eşleştirme büyük/küçük harf duyarsız.

Liste `DDX_CBStringExact` kutusu denetiminden veri aktarmak için çağrıldığında, *değer* geçerli liste kutusu seçimine ayarlanır. Öğe seçili değilse, *değer* sıfır uzunlukta bir dize olarak ayarlanır.

> [!NOTE]
> Liste kutusu açılır liste kutusuysa, değiştirilen değer 255 karakterle sınırlıdır.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_monthcalctrl"></a><a name="ddx_monthcalctrl"></a>DDX_MonthCalCtrl

İşlev, `DDX_MonthCalCtrl` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ve iletişim kutusu, form görünümü veya denetim görünümü nesnesinin [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) veri üyesi nde bir ay takvim denetimi [(CMonthCalCtrl)](../../mfc/reference/cmonthcalctrl-class.md)arasındaki tarih verilerinin aktarılmasını yönetir.

```cpp
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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar. Bu nesneyi silmeniz gerekmez.

*nIDC*<br/>
Üye değişkenle ilişkili ay takvim denetiminin kaynak kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya denetim görünümü nesnesinin bir `CTime` veya `COleDateTime` üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Denetim yalnızca bir tarih değerini yönetir. Zaman nesnesindeki zaman alanları, denetim penceresinin oluşturma saatini veya denetimde bir çağrı yla `CMonthCalCtrl::SetCurSel`ayarlanan zamanı yansıtacak şekilde ayarlanır.

Çağrıldığında, `DDX_MonthCalCtrl` *değer* ay takvim denetiminin geçerli durumuna ayarlanır.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_radio"></a><a name="ddx_radio"></a>DDX_Radio

İşlev, `DDX_Radio` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **int** veri üyesindeki bir radyo denetim grubu arasında **int** verilerinin aktarılmasını yönetir. **Int** veri üyesinin değeri, grup içindeki radyo düğmesine göre belirlenir.

```cpp
void AFXAPI DDX_Radio(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Gruptaki ilk radyo denetiminin kaynak kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümünün veya verilerin değiş tokuş edildiği denetim görünümü nesnesinin üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, `DDX_Radio` *değer* radyo denetim grubunun geçerli durumuna ayarlanır. Değer, şu anda denetlenen radyo denetiminin 0 tabanlı dizini olarak veya radyo denetimi denetlenmezse -1 olarak ayarlanır.

Örneğin, gruptaki ilk radyo düğmesinin işaretlemi durumunda (WS_GROUP stiliolan düğme) **int** üyesinin değeri 0 ve benzeridir.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_scroll"></a><a name="ddx_scroll"></a>DDX_Scroll

İşlev, `DDX_Scroll` iletişim kutusu, form görünümü veya denetim görünümü nesnesi ile iletişim kutusu, form görünümü veya denetim görünümü nesnesinin **int** veri üyesi ndeki bir kaydırma çubuğu denetimi arasında **int** verilerinin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_Scroll(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
Bir `CDataExchange` nesneye işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Denetim özelliğiyle ilişkili kaydırma çubuğu denetiminin kaynak kimliği.

*Değer*<br/>
İletişim kutusunun, form görünümü veya denetim görünümü nesnesinin bir üye değişkenine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, `DDX_Scroll` *değer* denetimin başparmağının geçerli konumuna ayarlanır. Denetimin başparmağının geçerli konumuyla ilişkili değerler hakkında daha fazla bilgi için Windows SDK'daki [GetScrollPos'a](/windows/win32/api/winuser/nf-winuser-getscrollpos) bakın.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_slider"></a><a name="ddx_slider"></a>DDX_Slider

İşlev, `DDX_Slider` iletişim kutusuveya form görünümündeki kaydırıcı denetimi ile iletişim kutusu veya form görünümü nesnesinin **int** veri üyesi arasında **int** verilerinin aktarılmasını yönetir.

```cpp
void AFXAPI DDX_Slider(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
Kaydırıcı denetiminin kaynak kimliği.

*Değer*<br/>
Değiştirilecek değere bir başvuru. Bu parametre kaydırıcı denetiminin geçerli konumunu tutar veya ayarlar.

### <a name="remarks"></a>Açıklamalar

Çağrıldığında, `DDX_Slider` *değer* denetimin başparmağının geçerli konumuna ayarlanır veya değer değişimin yönüne bağlı olarak konumu alır.

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın. Kaydırıcı denetimleri hakkında daha fazla bilgi için [Bkz. CSliderCtrl'yi kullanma.](../../mfc/using-csliderctrl.md)

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="ddx_text"></a><a name="ddx_text"></a>DDX_Text

İşlev, `DDX_Text` iletişim kutusu, form görünümü veya denetim görünümündeki `CString`bir denetim denetimi ile iletişim kutusu, form görünümü veya denetim görünümü ndeki [CString](../../atl-mfc-shared/reference/cstringt-class.md) veri üyesi arasındaki **int,** **UINT,** **long,** DWORD, **float**float veya **çift** veri aktarımı, form görünümü veya denetim görünümü nesnesinin aktarılmasını yönetir.

```cpp
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

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi. Çerçeve, yönü de dahil olmak üzere veri alışverişi bağlamını oluşturmak için bu nesneyi sağlar.

*nIDC*<br/>
İletişim kutusunda, form görünümünde veya denetim görünümü nesnesinde bir denetimin kimliği.

*Değer*<br/>
İletişim kutusunda, form görünümünde veya denetim görünümü nesnesinde bir veri üyesine başvuru. Değerin veri *value* türü, aşırı yüklenen sürümlerinden `DDX_Text` hangisinin kullanıldığına bağlıdır.

### <a name="remarks"></a>Açıklamalar

DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdd_.h

## <a name="see-also"></a>Ayrıca bkz.

[Standart İletişim Veri Doğrulama Yordamları](standard-dialog-data-validation-routines.md)<br/>
[Makrolar ve Küreseller](mfc-macros-and-globals.md)<br/>
[CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol)<br/>
[CDialog::OnInitDialog](cdialog-class.md#oninitdialog)
