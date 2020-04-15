---
title: Eşlemeleri Dağıtma
ms.date: 06/20/2018
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
ms.openlocfilehash: 59dd8c7a7b0b930ffdb68fd96410fd73aeb02e81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365748"
---
# <a name="dispatch-maps"></a>Eşlemeleri Dağıtma

OLE Automation, yöntemleri aramanın ve uygulamalar arasında özelliklere erişmenin yollarını sağlar. Bu istekleri göndermek için Microsoft Hazırlık Sınıfı Kitaplığı tarafından sağlanan mekanizma, nesne işlevlerinin ve özelliklerinin iç ve dış adlarının yanı sıra özelliklerin ve işlev bağımsız değişkenlerinin veri türlerini belirleyen "gönderme eşlemi"dir.

|Gönderme haritası makrosu|Açıklama|
|-|-|
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|Bir sınıfın yöntemlerini ve özelliklerini ortaya çıkarmak için bir sevk haritası kullanılacağını bildirir (sınıf bildiriminde kullanılmalıdır).|
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|Sevk haritasının tanımını başlatır.|
|[END_DISPATCH_MAP](#end_dispatch_map)|Sevk haritasının tanımını sona erdirer.|
|[DISP_FUNCTION](#disp_function)|Bir OLE otomasyon işlevini tanımlamak için bir sevkiyat haritasında kullanılır.|
|[DISP_PROPERTY](#disp_property)|Bir OLE otomasyon özelliği tanımlar.|
|[DISP_PROPERTY_EX](#disp_property_ex)|Bir OLE otomasyon özelliği tanımlar ve Al ve Ayarla işlevlerini adlandırır.|
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|Bildirimle bir OLE otomasyon özelliği tanımlar.|
|[DISP_PROPERTY_PARAM](#disp_property_param)|Parametreleri alan ve Al ve Ayarla işlevlerini isimleyen bir OLE otomasyon özelliği tanımlar.|
|[DISP_DEFVALUE](#disp_defvalue)|Varolan bir özelliği nesnenin varsayılan değeri yapar.|

## <a name="declare_dispatch_map"></a><a name="declare_dispatch_map"></a>DECLARE_DISPATCH_MAP

Programınızdaki `CCmdTarget`türetilmiş bir sınıf OLE Otomasyonunu destekliyorsa, bu sınıfın yöntemlerini ve özelliklerini ortaya çıkarmak için bir gönderme eşlemesi sağlaması gerekir.

```cpp
DECLARE_DISPATCH_MAP()
```

### <a name="remarks"></a>Açıklamalar

Sınıf bildirgenizin sonundaki DECLARE_DISPATCH_MAP makroyu kullanın. Sonra, içinde. Sınıfın üye işlevlerini tanımlayan CPP dosyası, BEGIN_DISPATCH_MAP makroyu kullanın. Ardından, sınıfınızın maruz kalan yöntemleri ve özelliklerinin her biri için makro girişleri (DISP_FUNCTION, DISP_PROPERTY vb.) ekleyin. Son olarak, END_DISPATCH_MAP makroyu kullanın.

> [!NOTE]
> DECLARE_DISPATCH_MAP sonra herhangi bir üye bildirirseniz, onlar için yeni bir erişim türü **(genel,** **özel**veya **korumalı)** belirtmeniz gerekir.

Uygulama Sihirbazı ve kod sihirbazları Otomasyon sınıfları oluşturmada ve gönderme eşlemlerini korumaya yardımcı olur. Gönderi meşinamaları hakkında daha fazla bilgi için [Otomasyon Sunucuları'na](../../mfc/automation-servers.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="begin_dispatch_map"></a><a name="begin_dispatch_map"></a>BEGIN_DISPATCH_MAP

Sevk haritanızın tanımını bildirir.

```cpp
BEGIN_DISPATCH_MAP(theClass, baseClass)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Bu gönderme haritasının sahibi sınıfın adını belirtir.

*Baseclass*<br/>
*Sınıfın*taban sınıf adını belirtir.

### <a name="remarks"></a>Açıklamalar

Sınıfınızın üye işlevlerini tanımlayan uygulama (.cpp) dosyasında, BEGIN_DISPATCH_MAP makrosuyla gönderim eşlemi başlatın, gönderim işlevlerinizin ve özelliklerinizin her biri için makro girişleri ekleyin ve END_DISPATCH_MAP makrosuyla gönderim eşlemi tamamlayın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="end_dispatch_map"></a><a name="end_dispatch_map"></a>END_DISPATCH_MAP

Gönderi müdürünün tanım

```cpp
END_DISPATCH_MAP()
```

### <a name="remarks"></a>Açıklamalar

BEGIN_DISPATCH_MAP ile birlikte kullanılmalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="disp_function"></a><a name="disp_function"></a>DISP_FUNCTION

Sevk haritasında Bir OLE otomasyon işlevini tanımlar.

```cpp
DISP_FUNCTION(
    theClass,
    pszName,
    pfnMember,
    vtRetVal,
    vtsParams)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Sınıfın adı.

*pszName*<br/>
Fonksiyonun dış adı.

*pfnÜye*<br/>
Üye işlevin adı.

*vtRetVal*<br/>
İşlevin dönüş türünü belirten bir değer.

*vtsParams*<br/>
İşlevin parametre listesini belirten bir veya daha fazla sabitin boşluktan ayrılmış listesi.

### <a name="remarks"></a>Açıklamalar

*vtRetVal* bağımsız değişkeni VARTYPE türündedir. Bu bağımsız değişken için aşağıdaki olası `VARENUM` değerler numaralandırmadan alınır:

|Sembol|Dönüş türü|
|------------|-----------------|
|Vt_empty|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|Vt_cy|CY|
|Vt_date|DATE|
|Vt_bstr|Bstr|
|Vt_dıspatch|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|Bool|
|VT_VARIANT|VARIANT|
|Vt_unknown|LPUNKNOWN|

*vtsParams* bağımsız `VTS_*` değişkeni, sabitlerden gelen değerlerin boşluktan ayrılmış bir listesidir. Boşluklarla ayrılan bu değerlerden biri veya birkaçı (virgül değil) işlevin parametre listesini belirtir. Örneğin,

[!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]

kısa bir tamsayı içeren bir liste ve ardından kısa bir tamsayı işaretçisi belirtir.

Sabitler `VTS_` ve anlamları aşağıdaki gibidir:

|Sembol|Parametre türü|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**long**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_CY|`const CY` veya `CY*`|
|VTS_DATE|DATE|
|VTS_BSTR|LPCSTR|
|VTS_DISPATCH|LPDISPATCH|
|VTS_SCODE|SCODE|
|VTS_BOOL|Bool|
|VTS_VARIANT|`const VARIANT*` veya `VARIANT&`|
|VTS_UNKNOWN|LPUNKNOWN|
|VTS_PI2|__Kısa\*__|
|VTS_PI4|__Uzun\*__|
|VTS_PR4|__float\*__|
|VTS_PR8|__double\*__|
|VTS_PCY|`CY*`|
|VTS_PDATE|`DATE*`|
|VTS_PBSTR|`BSTR*`|
|VTS_PDISPATCH|`LPDISPATCH*`|
|VTS_PSCODE|`SCODE*`|
|VTS_PBOOL|`BOOL*`|
|VTS_PVARIANT|`VARIANT*`|
|VTS_PUNKNOWN|`LPUNKNOWN*`|
|VTS_NONE|Parametre yok|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="disp_property"></a><a name="disp_property"></a>DISP_PROPERTY

Bir sevk haritasında Bir OLE otomasyon özelliği tanımlar.

```cpp
DISP_PROPERTY(
    theClass,
    pszName,
    memberName,
    vtPropType)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Sınıfın adı.

*pszName*<br/>
Özelliğin dış adı.

*üyeAdı*<br/>
Özelliğin depolandığı üye değişkenin adı.

*vtPropType*<br/>
Özelliğin türünü belirten bir değer.

### <a name="remarks"></a>Açıklamalar

*vtPropType* bağımsız değişkeni **VARTYPE**türündedir. Bu bağımsız değişken için olası değerler VARENUM numaralandırmasından alınır:

|Sembol|Özellik türü|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|Vt_cy|CY|
|Vt_date|DATE|
|Vt_bstr|`CString`|
|Vt_dıspatch|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|Bool|
|VT_VARIANT|VARIANT|
|Vt_unknown|LPUNKNOWN|

Harici bir istemci özelliği değiştirdiğinde, *üye Adı* tarafından belirtilen üye değişkenin değeri değişir; değişikliğin bildirimi yoktur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="disp_property_ex"></a><a name="disp_property_ex"></a>DISP_PROPERTY_EX

Bir OLE otomasyon özelliği tanımlar ve bir sevkiyat haritasında özelliğin değerini almak ve ayarlamak için kullanılan işlevleri adlandırır.

```cpp
DISP_PROPERTY_EX(
    theClass,
    pszName,
    memberGet,
    memberSet,
    vtPropType)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Sınıfın adı.

*pszName*<br/>
Özelliğin dış adı.

*üyeAl*<br/>
Özelliği almak için kullanılan üye işlevin adı.

*üyeSet*<br/>
Özelliği ayarlamak için kullanılan üye işlevin adı.

*vtPropType*<br/>
Özelliğin türünü belirten bir değer.

### <a name="remarks"></a>Açıklamalar

*memberGet* ve *memberSet* *işlevlerivtPropType* bağımsız değişkeni tarafından belirlenen imzalara sahiptir. *memberGet* işlevi hiçbir bağımsız değişken alır ve *vtPropType*tarafından belirtilen tür bir değer döndürür. *memberSet* işlevi *vtPropType* tarafından belirtilen türün bir bağımsız değişkenalır ve hiçbir şey döndürür.

*vtPropType* bağımsız değişkeni VARTYPE türündedir. Bu bağımsız değişken için olası değerler VARENUM numaralandırmasından alınır. Bu değerlerin listesi için, [DISP_FUNCTION'daki](#disp_function) *vtRetVal* parametresinin Açıklamaları'na bakın. DISP_FUNCTION açıklamalarında listelenen VT_EMPTY özellik veri türü olarak izin verilmeyeceğini unutmayın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="disp_property_notify"></a><a name="disp_property_notify"></a>DISP_PROPERTY_NOTIFY

Bir ole otomasyon özelliğini bir sevkiyat haritasında bildirimle tanımlar.

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    szExternalName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Sınıfın adı.

*szExternalName*<br/>
Özelliğin dış adı.

*üyeAdı*<br/>
Özelliğin depolandığı üye değişkenin adı.

*pfnAfterSet*<br/>
*szExternalName*için bildirim işlevinin adı.

*vtPropType*<br/>
Özelliğin türünü belirten bir değer.

### <a name="remarks"></a>Açıklamalar

DISP_PROPERTY tanımlanan özelliklerin aksine, DISP_PROPERTY_NOTIFY tanımlanan bir özellik, özellik değiştirildiğinde *pfnAfterSet* tarafından belirtilen işlevi otomatik olarak çağırır.

*vtPropType* bağımsız değişkeni VARTYPE türündedir. Bu bağımsız değişken için olası değerler VARENUM numaralandırmasından alınır:

|Sembol|Özellik türü|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|Vt_cy|CY|
|Vt_date|DATE|
|Vt_bstr|`CString`|
|Vt_dıspatch|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|Bool|
|VT_VARIANT|VARIANT|
|Vt_unknown|LPUNKNOWN|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="disp_property_param"></a><a name="disp_property_param"></a>DISP_PROPERTY_PARAM

Ayrı `Get` ve `Set` üye işlevlerle erişilen bir özelliği tanımlar.

```cpp
DISP_PROPERTY_PARAM(
    theClass,
    pszExternalName,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Sınıfın adı.

*pszExternalName*<br/>
Özelliğin dış adı.

*pfnGet*<br/>
Özelliği almak için kullanılan üye işlevin adı.

*pfnSet*<br/>
Özelliği ayarlamak için kullanılan üye işlevin adı.

*vtPropType*<br/>
Özelliğin türünü belirten bir değer.

*vtsParams*<br/>
Her parametre için `VTS_*` bir tane olan, uzaya ayrılmış varyant parametre türleri dizesi.

### <a name="remarks"></a>Açıklamalar

DISP_PROPERTY_EX makronun aksine, bu makro özellik için bir parametre listesi belirtmenize olanak tanır. Bu, dizinlenmiş veya parametrelendirilmiş özellikleri uygulamak için yararlıdır.

### <a name="example"></a>Örnek

Kullanıcının özelliğe erişirken belirli bir satır ve sütun istemesine izin veren üye işlevleri al ve ayarla aşağıdaki bildirimi ni göz önünde bulundurun:

[!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]

Bunlar, denetim sevkiyat haritasında aşağıdaki DISP_PROPERTY_PARAM makroya karşılık gelir:

[!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]

Başka bir örnek olarak, aşağıdaki al ve üye işlevleri ayarlamak düşünün:

[!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]

Bunlar, denetim sevkiyat haritasında aşağıdaki DISP_PROPERTY_PARAM makroya karşılık gelir:

[!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="disp_defvalue"></a><a name="disp_defvalue"></a>DISP_DEFVALUE

Varolan bir özelliği nesnenin varsayılan değeri yapar.

```cpp
DISP_DEFVALUE(theClass, pszName)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Sınıfın adı.

*pszName*<br/>
Nesnenin "değerini" temsil eden özelliğin dış adı.

### <a name="remarks"></a>Açıklamalar

Varsayılan bir değer kullanmak, Visual Basic uygulamaları için otomasyon nesnenizi programlamayı daha basit hale getirebilir.

Nesnenizin "varsayılan değeri", bir nesneye yapılan başvuru bir özellik veya üye işlev belirtilmediğinde alınan veya ayarlanan özelliktir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
