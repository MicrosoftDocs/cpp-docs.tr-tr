---
title: Eşlemeleri Dağıtma
ms.date: 06/20/2018
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
ms.openlocfilehash: f1afa95d7c20d54f2015255a7e4e0d7ad9ae9c2b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856656"
---
# <a name="dispatch-maps"></a>Eşlemeleri Dağıtma

OLE Otomasyonu yöntemleri çağırmak ve uygulamalar arasında özelliklere erişmek için yollar sağlar. Bu istekleri göndermek için Microsoft Foundation Class Kitaplığı tarafından sağlanan mekanizma, nesne işlevlerinin ve özelliklerinin iç ve dış adlarını, özelliklerinin ve bunların kendilerine ait veri türlerini ve işlev bağımsız değişkenleri.

|Harita makrosunu dağıtma|Açıklama|
|-|-|
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|Bir dağıtım eşlemesinin, bir sınıfın yöntemlerini ve özelliklerini göstermek için kullanılacağını bildirir (sınıf bildiriminde kullanılması gerekir).|
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|Bir dağıtım eşlemesinin tanımını başlatır.|
|[END_DISPATCH_MAP](#end_dispatch_map)|Bir dağıtım eşlemesinin tanımını sonlandırır.|
|[DISP_FUNCTION](#disp_function)|Bir OLE Otomasyonu işlevi tanımlamak için bir dağıtım eşlemesinde kullanılır.|
|[DISP_PROPERTY](#disp_property)|OLE Otomasyonu özelliğini tanımlar.|
|[DISP_PROPERTY_EX](#disp_property_ex)|OLE Otomasyonu özelliğini tanımlar ve Get ve set işlevlerini adlandırır.|
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|Bildirimi olan bir OLE Otomasyonu özelliğini tanımlar.|
|[DISP_PROPERTY_PARAM](#disp_property_param)|Parametreleri alan ve Get ve set işlevlerini isimuygulayan bir OLE Otomasyonu özelliği tanımlar.|
|[DISP_DEFVALUE](#disp_defvalue)|Varolan bir özelliği bir nesnenin varsayılan değeri yapar.|

## <a name="declare_dispatch_map"></a>DECLARE_DISPATCH_MAP

Programınızdaki `CCmdTarget`türetilmiş bir sınıf OLE Otomasyonu destekliyorsa, bu sınıf kendi yöntemlerini ve özelliklerini sunmak için bir dağıtım eşlemesi sağlamalıdır.

```cpp
DECLARE_DISPATCH_MAP()
```

### <a name="remarks"></a>Açıklamalar

Sınıf bildirimindeki sonundaki DECLARE_DISPATCH_MAP makrosunu kullanın. Ardından içinde. Sınıf için üye işlevlerini tanımlayan CPP dosyası BEGIN_DISPATCH_MAP makrosunu kullanın. Ardından, sınıfınızın sunulan yöntemlerin ve özelliklerin her biri için makro girdilerini ekleyin (DISP_FUNCTION, DISP_PROPERTY vb.). Son olarak, END_DISPATCH_MAP makrosunu kullanın.

> [!NOTE]
> DECLARE_DISPATCH_MAP sonra herhangi bir üye bildirirseniz, bunlar için yeni bir erişim türü ( **genel**, **özel**veya **korumalı**) belirtmeniz gerekir.

Uygulama Sihirbazı ve kod sihirbazları, Otomasyon sınıfları oluşturmaya ve dağıtım haritalarını sürdürmesine yardımcı olur. Dağıtım haritaları hakkında daha fazla bilgi için bkz. [Automation Servers](../../mfc/automation-servers.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="begin_dispatch_map"></a>BEGIN_DISPATCH_MAP

Dağıtım haritaınızın tanımını bildirir.

```cpp
BEGIN_DISPATCH_MAP(theClass, baseClass)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Bu dağıtım eşlemesine sahip olan sınıfın adını belirtir.

*baseClass*<br/>
Sınıfın temel sınıf adını *belirtir.*

### <a name="remarks"></a>Açıklamalar

Sınıfınız için üye işlevlerini tanımlayan uygulama (. cpp) dosyasında, dağıtım haritasını BEGIN_DISPATCH_MAP makrosu ile başlatın, dağıtım işlevlerinizin ve özelliklerden her biri için makro girişleri ekleyin ve dağıtım haritasını END_DISPATCH_ ile doldurun Makroyu EŞLEYIN.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="end_dispatch_map"></a>END_DISPATCH_MAP

Dağıtım haritaınızın tanımını sonlandırır.

```cpp
END_DISPATCH_MAP()
```

### <a name="remarks"></a>Açıklamalar

BEGIN_DISPATCH_MAP ile birlikte kullanılması gerekir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="disp_function"></a>DISP_FUNCTION

Bir dağıtım haritasında OLE Otomasyonu işlevini tanımlar.

```cpp
DISP_FUNCTION(
    theClass,
    pszName,
    pfnMember,
    vtRetVal,
    vtsParams)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Sınıfın adı.

*pszName*<br/>
İşlevin dış adı.

*pfnMember*<br/>
Üye işlevinin adı.

*vtRetVal*<br/>
İşlevin dönüş türünü belirten bir değer.

*vtsParams*<br/>
İşlevin parametre listesini belirten bir veya daha fazla sabitin boşlukla ayrılmış listesi.

### <a name="remarks"></a>Açıklamalar

*VtRetVal* BAĞıMSıZ değişkeni VarType türünde. Bu bağımsız değişken için aşağıdaki olası değerler `VARENUM` numaralandırmasından alınır:

|Sembol|Dönüş türü|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

*VtsParams* bağımsız değişkeni, `VTS_*` sabitlerinden alınan değerlerin boşlukla ayrılmış bir listesidir. Boşluklarla (virgüller değil) ayrılmış bir veya daha fazla değer, işlevin parametre listesini belirtir. Örneğin,

[!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]

kısa bir tamsayı içeren bir liste ve ardından kısa bir tamsayıya yönelik işaretçiyi belirtir.

`VTS_` sabitleri ve anlamları aşağıdaki gibidir:

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
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*` veya `VARIANT&`|
|VTS_UNKNOWN|LPUNKNOWN|
|VTS_PI2|__kısa\*__|
|VTS_PI4|__uzun\*__|
|VTS_PR4|__kayan\*__|
|VTS_PR8|__Double\*__|
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

**Üstbilgi:** AfxDisp. h

## <a name="disp_property"></a>DISP_PROPERTY

Bir dağıtım haritasında OLE Otomasyonu özelliğini tanımlar.

```cpp
DISP_PROPERTY(
    theClass,
    pszName,
    memberName,
    vtPropType)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Sınıfın adı.

*pszName*<br/>
Özelliğin dış adı.

*memberName*<br/>
Özelliğin depolandığı üye değişkeninin adı.

*vtPropType*<br/>
Özelliğin türünü belirten bir değer.

### <a name="remarks"></a>Açıklamalar

*VtPropType* bağımsız değişkeni **VarType**türünde. Bu bağımsız değişken için olası değerler, VARENUM numaralandırmasından alınır:

|Sembol|Özellik türü|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

Bir dış istemci özelliğini değiştirdiğinde, *Üyei* değişiklikleri tarafından belirtilen üye değişkeninin değeri; değişiklik bildirimi yok.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="disp_property_ex"></a>DISP_PROPERTY_EX

Bir OLE Otomasyonu özelliği tanımlar ve bir dağıtım eşlemesindeki özelliğin değerini almak ve ayarlamak için kullanılan işlevleri adlandırın.

```cpp
DISP_PROPERTY_EX(
    theClass,
    pszName,
    memberGet,
    memberSet,
    vtPropType)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Sınıfın adı.

*pszName*<br/>
Özelliğin dış adı.

*memberGet*<br/>
Özelliği almak için kullanılan üye işlevinin adı.

*memberSet*<br/>
Özelliği ayarlamak için kullanılan üye işlevinin adı.

*vtPropType*<br/>
Özelliğin türünü belirten bir değer.

### <a name="remarks"></a>Açıklamalar

*MemberGet* ve *memberSet* Işlevlerinin, *vtPropType* bağımsız değişkeni tarafından belirlenen imzaları vardır. *MemberGet* işlevi bağımsız değişken almaz ve *vtPropType*tarafından belirtilen türde bir değer döndürür. *MemberSet* Işlevi, *vtPropType* tarafından belirtilen türde bir bağımsız değişken alır ve hiçbir şey döndürmez.

*VtPropType* BAĞıMSıZ değişkeni VarType türünde. Bu bağımsız değişken için olası değerler, VARENUM numaralandırmasından alınır. Bu değerlerin bir listesi için [DISP_FUNCTION](#disp_function) *vtRetVal* parametresinin açıklamalarını inceleyin. DISP_FUNCTION açıklamalarında listelenen VT_EMPTY, özellik veri türü olarak izin verilmediğini unutmayın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="disp_property_notify"></a>DISP_PROPERTY_NOTIFY

Bir dağıtım eşlemesinde bildirimi olan bir OLE Otomasyonu özelliği tanımlar.

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    szExternalName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Sınıfın adı.

*szExternalName*<br/>
Özelliğin dış adı.

*memberName*<br/>
Özelliğin depolandığı üye değişkeninin adı.

*pfnAfterSet*<br/>
*SzExternalName*için bildirim işlevinin adı.

*vtPropType*<br/>
Özelliğin türünü belirten bir değer.

### <a name="remarks"></a>Açıklamalar

DISP_PROPERTY ile tanımlanan özelliklerden farklı olarak, DISP_PROPERTY_NOTIFY ile tanımlanan bir özellik, özellik değiştirildiğinde *pfnAfterSet* tarafından belirtilen işlevi otomatik olarak çağırır.

*VtPropType* BAĞıMSıZ değişkeni VarType türünde. Bu bağımsız değişken için olası değerler, VARENUM numaralandırmasından alınır:

|Sembol|Özellik türü|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="disp_property_param"></a>DISP_PROPERTY_PARAM

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

*Sınıf*<br/>
Sınıfın adı.

*pszExternalName*<br/>
Özelliğin dış adı.

*pfnGet*<br/>
Özelliği almak için kullanılan üye işlevinin adı.

*pfnSet*<br/>
Özelliği ayarlamak için kullanılan üye işlevinin adı.

*vtPropType*<br/>
Özelliğin türünü belirten bir değer.

*vtsParams*<br/>
Her parametre için bir tane olmak üzere boşlukla ayrılmış `VTS_*` Variant parametre türleri dizesi.

### <a name="remarks"></a>Açıklamalar

DISP_PROPERTY_EX makrosunun aksine, bu makro özellik için bir parametre listesi belirtmenize olanak tanır. Bu, dizini oluşturulmuş veya parametreli olan özellikleri uygulamak için yararlıdır.

### <a name="example"></a>Örnek

Kullanıcının özelliğe erişirken belirli bir satır ve sütun istemesine izin veren get ve set üye işlevlerinin aşağıdaki bildirimini göz önünde bulundurun:

[!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]

Bunlar, denetim dağıtım eşlemesindeki şu DISP_PROPERTY_PARAM makroya karşılık gelir:

[!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]

Diğer bir örnek olarak, aşağıdaki get ve set üye işlevlerini göz önünde bulundurun:

[!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]

Bunlar, denetim dağıtım eşlemesindeki şu DISP_PROPERTY_PARAM makroya karşılık gelir:

[!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="disp_defvalue"></a>DISP_DEFVALUE

Varolan bir özelliği bir nesnenin varsayılan değeri yapar.

```cpp
DISP_DEFVALUE(theClass, pszName)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Sınıfın adı.

*pszName*<br/>
Nesnenin "değerini" temsil eden özelliğin dış adı.

### <a name="remarks"></a>Açıklamalar

Varsayılan bir değer kullanmak, Otomasyon nesnenizin Visual Basic uygulamalar için daha kolay programlama yapmasını sağlayabilir.

Nesnenizin "varsayılan değeri", bir nesne başvurusu bir özellik veya üye işlevi belirtmezse alınan veya ayarlanan özelliktir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
