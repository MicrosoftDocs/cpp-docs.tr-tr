---
description: 'Daha fazla bilgi edinin: Özellik sayfaları (MFC)'
title: Özellik Sayfaları (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- property page data transfer functions in MFC
- property pages [MFC], global MFC functions
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
ms.openlocfilehash: fa395272ba74c6b3900d5a1500d4cf47ade4e535
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218972"
---
# <a name="property-pages-mfc"></a>Özellik Sayfaları (MFC)

Özellik sayfaları, iletişim kutusu veri değişimi (DDX) temelinde bir veri eşleme mekanizmasını destekleyerek, görüntüleme ve düzenlemeyle ilgili OLE denetimi özelliklerinin geçerli değerlerini özelleştirilebilir, grafik bir arabirim halinde görüntüler.

Bu veri eşleme mekanizması, özellik sayfası denetimlerini OLE denetiminin bireysel özelliklerine eşler. Denetim özelliğinin değeri, özellik sayfası denetiminin durumunu veya içeriğini yansıtır. Özellik sayfası denetimleri ve özellikleri arasındaki eşleme, özellik sayfasının üye işlevindeki **ddp_** işlev çağrıları tarafından belirtilir `DoDataExchange` . Aşağıda, denetiminizin Özellik sayfası kullanılarak girilen Exchange verilerinin **ddp_** işlevlerinin bir listesi verilmiştir:

### <a name="property-page-data-transfer"></a>Özellik sayfası Veri Aktarımı

|Ad|Açıklama|
|-|-|
|[DDP_CBIndex](#ddp_cbindex)|Bir açılan kutuda seçilen dizenin dizinini denetimin özelliği ile bağlantılandırır.|
|[DDP_CBString](#ddp_cbstring)|Bir açılan kutudaki Seçili dizeyi denetimin özelliği ile bağlar. Seçilen dize, özelliğin değeri ile aynı harfle başlayabilir, ancak tamamen eşleşmesi gerekmez.|
|[DDP_CBStringExact](#ddp_cbstringexact)|Bir açılan kutudaki Seçili dizeyi denetimin özelliği ile bağlar. Seçilen dize ve özelliğin dize değeri tam olarak eşleşmelidir.|
|[DDP_Check](#ddp_check)|Denetimin özelliği olan denetimin özellik sayfasındaki onay kutusunu bağlar.|
|[DDP_LBIndex](#ddp_lbindex)|Bir liste kutusunda seçili dizenin dizinini denetimin özelliği ile bağlantılandırır.|
|[DDP_LBString](#ddp_lbstring)|Bir liste kutusunda seçili dizeyi denetimin özelliği ile bağlar. Seçilen dize, özelliğin değeri ile aynı harfle başlayabilir, ancak tam olarak eşleşmesi gerekmez.|
|[DDP_LBStringExact](#ddp_lbstringexact)|Bir liste kutusunda seçili dizeyi denetimin özelliği ile bağlar. Seçilen dize ve özelliğin dize değeri tam olarak eşleşmelidir.|
|[DDP_PostProcessing](#ddp_postprocessing)|Denetiinizden özellik değerlerinin aktarımını sonlandırır.|
|[DDP_Radio](#ddp_radio)|Denetimin özellik sayfasındaki bir radyo düğmesi grubunu denetimin özelliği ile bağlar.|
|[DDP_Text](#ddp_text)|Denetimin özellik sayfasında denetimin özelliği ile bir denetimi bağlar. Bu işlev,,, BSTR ve gibi birçok farklı özellik türünü işler **`double`** **`short`** **`long`** .|

İşlev ve özellik sayfaları hakkında daha fazla bilgi için `DoDataExchange` , [ActiveX denetimleri: Özellik sayfaları](../../mfc/mfc-activex-controls-property-pages.md)makalesine bakın.

Bir OLE denetimi için özellik sayfaları oluşturmak ve yönetmek için kullanılan makroların listesi aşağıda verilmiştir:

### <a name="property-pages"></a>Özellik Sayfaları

|Ad|Açıklama|
|-|-|
|[BEGIN_PROPPAGEIDS](#begin_proppageids)|Özellik sayfası kimliklerinin listesini başlatır.|
|[END_PROPPAGEIDS](#end_proppageids)|Özellik sayfası kimliklerinin listesini sonlandırır.|
|[PROPPAGEıD](#proppageid)|Denetim sınıfının özellik sayfasını bildirir.|

## <a name="ddp_cbindex"></a><a name="ddp_cbindex"></a> DDP_CBIndex

`DoDataExchange`Bir Integer özelliğinin değerini, özellik sayfasındaki Birleşik giriş kutusunda bulunan geçerli seçimin diziniyle eşleştirmek için özellik sayfanızın işlevinde bu işlevi çağırın.

```cpp
void AFXAPI DDP_CBIndex(
    CDataExchange* pDX,
    int id,
    int& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir nesne işaretçisi `CDataExchange` . Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*id*<br/>
*PszPropName* tarafından belirtilen denetim özelliği ile ilişkili Birleşik giriş kutusu DENETIMININ kaynak kimliği.

*üyesidir*<br/>
*Kimliğe* ve *pszPropName* tarafından belirtilen özelliğe göre belirtilen özellik sayfası denetimiyle ilişkili üye değişkeni.

*pszPropName*<br/>
*Kimliğe* göre belirtilen Birleşik giriş kutusu denetimiyle değiş tokuş edilecek denetim özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, karşılık gelen `DDX_CBIndex` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="ddp_cbstring"></a><a name="ddp_cbstring"></a> DDP_CBString

`DoDataExchange`Bir dize özelliğinin değerini özellik sayfasındaki Birleşik giriş kutusunda bulunan geçerli seçimle eşleştirmek için özellik sayfanızın işlevinde bu işlevi çağırın.

```cpp
void AFXAPI DDP_CBString(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir nesne işaretçisi `CDataExchange` . Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*id*<br/>
*PszPropName* tarafından belirtilen denetim özelliği ile ilişkili Birleşik giriş kutusu DENETIMININ kaynak kimliği.

*üyesidir*<br/>
*Kimliğe* ve *pszPropName* tarafından belirtilen özelliğe göre belirtilen özellik sayfası denetimiyle ilişkili üye değişkeni.

*pszPropName*<br/>
*Kimliğe* göre belirtilen Birleşik giriş kutusu dizesiyle birlikte değiş tokuş edilecek denetim özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, karşılık gelen `DDX_CBString` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="ddp_cbstringexact"></a><a name="ddp_cbstringexact"></a> DDP_CBStringExact

`DoDataExchange`Özellik sayfasındaki Birleşik giriş kutusunda bulunan geçerli seçimle tam olarak eşleşen bir dize özelliğinin değerini eşleştirmek için özellik sayfanızın işlevinde bu işlevi çağırın.

```cpp
void AFXAPI DDP_CBStringExact(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir nesne işaretçisi `CDataExchange` . Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*id*<br/>
*PszPropName* tarafından belirtilen denetim özelliği ile ilişkili Birleşik giriş kutusu DENETIMININ kaynak kimliği.

*üyesidir*<br/>
*Kimliğe* ve *pszPropName* tarafından belirtilen özelliğe göre belirtilen özellik sayfası denetimiyle ilişkili üye değişkeni.

*pszPropName*<br/>
*Kimliğe* göre belirtilen Birleşik giriş kutusu dizesiyle birlikte değiş tokuş edilecek denetim özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, karşılık gelen `DDX_CBStringExact` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="ddp_check"></a><a name="ddp_check"></a> DDP_Check

`DoDataExchange`Özelliğin değerini ilişkili özellik sayfası onay kutusu denetimiyle senkronize etmek için özellik sayfanızın işlevinde bu işlevi çağırın.

```cpp
void AFXAPI DDP_Check(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir nesne işaretçisi `CDataExchange` . Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*id*<br/>
*PszPropName* tarafından belirtilen denetim özelliği ile ilişkili onay kutusu DENETIMININ kaynak kimliği.

*üyesidir*<br/>
*Kimliğe* ve *pszPropName* tarafından belirtilen özelliğe göre belirtilen özellik sayfası denetimiyle ilişkili üye değişkeni.

*pszPropName*<br/>
*Kimliğe* göre belirtilen onay kutusu denetimiyle değiş tokuş edilecek denetim özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, karşılık gelen `DDX_Check` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="ddp_lbindex"></a><a name="ddp_lbindex"></a> DDP_LBIndex

`DoDataExchange`Bir Integer özelliğinin değerini, özellik sayfasındaki bir liste kutusunda geçerli seçimin diziniyle eşleştirmek için özellik sayfanızın işlevinde bu işlevi çağırın.

```cpp
void AFXAPI DDP_LBIndex(
    CDataExchange* pDX,
    int id,
    int& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir nesne işaretçisi `CDataExchange` . Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*id*<br/>
*PszPropName* tarafından belirtilen denetim özelliği ile ilişkili liste kutusu DENETIMININ kaynak kimliği.

*üyesidir*<br/>
*Kimliğe* ve *pszPropName* tarafından belirtilen özelliğe göre belirtilen özellik sayfası denetimiyle ilişkili üye değişkeni.

*pszPropName*<br/>
*Kimliğe* göre belirtilen liste kutusu dizesiyle birlikte değiş tokuş edilecek denetim özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, karşılık gelen `DDX_LBIndex` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="ddp_lbstring"></a><a name="ddp_lbstring"></a> DDP_LBString

`DoDataExchange`Bir dize özelliğinin değerini, özellik sayfasındaki bir liste kutusunda bulunan geçerli seçimle eşleştirmek için özellik sayfanızın işlevinde bu işlevi çağırın.

```cpp
void AFXAPI DDP_LBString(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir nesne işaretçisi `CDataExchange` . Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*id*<br/>
*PszPropName* tarafından belirtilen denetim özelliği ile ilişkili liste kutusu DENETIMININ kaynak kimliği.

*üyesidir*<br/>
*Kimliğe* ve *pszPropName* tarafından belirtilen özelliğe göre belirtilen özellik sayfası denetimiyle ilişkili üye değişkeni.

*pszPropName*<br/>
*Kimliğe* göre belirtilen liste kutusu dizesiyle birlikte değiş tokuş edilecek denetim özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, karşılık gelen `DDX_LBString` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="ddp_lbstringexact"></a><a name="ddp_lbstringexact"></a> DDP_LBStringExact

`DoDataExchange`Özellik sayfasındaki bir liste kutusunda bulunan geçerli seçimle tam olarak eşleşen bir dize özelliğinin değerini eşleştirmek için özellik sayfanızın işlevinde bu işlevi çağırın.

```cpp
void AFXAPI DDP_LBStringExact(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir nesne işaretçisi `CDataExchange` . Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*id*<br/>
*PszPropName* tarafından belirtilen denetim özelliği ile ilişkili liste kutusu DENETIMININ kaynak kimliği.

*üyesidir*<br/>
*Kimliğe* ve *pszPropName* tarafından belirtilen özelliğe göre belirtilen özellik sayfası denetimiyle ilişkili üye değişkeni.

*pszPropName*<br/>
*Kimliğe* göre belirtilen liste kutusu dizesiyle birlikte değiş tokuş edilecek denetim özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, karşılık gelen `DDX_LBStringExact` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="ddp_postprocessing"></a><a name="ddp_postprocessing"></a> DDP_PostProcessing

Özellik değerleri, özellik değerleri `DoDataExchange` kaydedilirken denetim sayfasından denetimi aktarmak için özellik sayfasının işlevinde bu işlevi çağırın.

```cpp
void AFXAPI DDP_PostProcessing(CDataExchange * pDX);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir nesne işaretçisi `CDataExchange` . Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm veri değişimi işlevleri tamamlandıktan sonra çağrılmalıdır. Örneğin:

[!code-cpp[NVC_MFCAxCtl#15](../../mfc/reference/codesnippet/cpp/property-pages-mfc_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="ddp_radio"></a><a name="ddp_radio"></a> DDP_Radio

`DoPropExchange`Özelliğin değerini ilişkili özellik sayfası radyo düğmesi denetimiyle eşleştirmek için, denetimin işlevinde bu işlevi çağırın.

```cpp
void AFXAPI DDP_Radio(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir nesne işaretçisi `CDataExchange` . Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*id*<br/>
*PszPropName* tarafından belirtilen denetim özelliğiyle ilişkili radyo düğmesi DENETIMININ kaynak kimliği.

*üyesidir*<br/>
*Kimliğe* ve *pszPropName* tarafından belirtilen özelliğe göre belirtilen özellik sayfası denetimiyle ilişkili üye değişkeni.

*pszPropName*<br/>
*Kimliğe* göre belirtilen radyo düğmesi denetimiyle değiş tokuş edilecek denetim özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, karşılık gelen `DDX_Radio` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="ddp_text"></a><a name="ddp_text"></a> DDP_Text

`DoDataExchange`Özelliğin değerini ilişkili özellik sayfası denetimiyle eşleştirmek için denetiminizin işlevinde bu işlevi çağırın.

```cpp
void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    BYTE & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    UINT & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    long & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    DWORD & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    float & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    double & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    CString & member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
Bir nesne işaretçisi `CDataExchange` . Framework, yönü dahil olmak üzere veri değişim bağlamını oluşturmak için bu nesneyi sağlar.

*id*<br/>
*PszPropName* tarafından belirtilen denetim özelliği ile ilişkili DENETIMIN kaynak kimliği.

*üyesidir*<br/>
*Kimliğe* ve *pszPropName* tarafından belirtilen özelliğe göre belirtilen özellik sayfası denetimiyle ilişkili üye değişkeni.

*pszPropName*<br/>
*Kimliğe* göre belirtilen denetimle değiştirilen denetim özelliğinin özellik adı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, karşılık gelen `DDX_Text` işlev çağrısından önce çağrılmalıdır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="begin_proppageids"></a><a name="begin_proppageids"></a> BEGIN_PROPPAGEIDS

Denetimin özellik sayfası kimlikleri listesinin tanımını başlatır.

```
BEGIN_PROPPAGEIDS(class_name,  count)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Özellik sayfaları belirtime denetim sınıfının adı.

*biriktirme*<br/>
Denetim sınıfı tarafından kullanılan özellik sayfası sayısı.

### <a name="remarks"></a>Açıklamalar

Sınıfınız için üye işlevleri tanımlayan uygulama (. cpp) dosyasında, özellik sayfası listesini BEGIN_PROPPAGEIDS makrosu ile başlatın, sonra özellik sayfalarınızın her biri için makro girişleri ekleyin ve özellik sayfası listesini END_PROPPAGEIDS makroyla doldurun.

Özellik sayfaları hakkında daha fazla bilgi için, [ActiveX denetimleri: Özellik sayfaları](../../mfc/mfc-activex-controls-property-pages.md)makalesine bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="end_proppageids"></a><a name="end_proppageids"></a> END_PROPPAGEIDS

Özellik sayfası KIMLIK listenizin tanımını sonlandırır.

```
END_PROPPAGEIDS(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Özellik sayfasının sahibi olan denetim sınıfının adı.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="proppageid"></a><a name="proppageid"></a> PROPPAGEıD

OLE denetiminiz tarafından kullanılmak üzere bir özellik sayfası ekler.

```
PROPPAGEID(clsid)
```

### <a name="parameters"></a>Parametreler

*in*<br/>
Özellik sayfasının benzersiz sınıf KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Tüm PROPPAGEıD makroları, denetimin uygulama dosyasında BEGIN_PROPPAGEIDS ve END_PROPPAGEIDS makroları arasına yerleştirilmelidir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
