---
title: Gönderme eşlemeleri | Microsoft Docs
ms.custom: ''
ms.date: 06/20/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d22c94513e80c4f353de9e10588f219a2d3be92
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388077"
---
# <a name="dispatch-maps"></a>Eşlemeleri Dağıtma

OLE Otomasyonu nesnesi etkin yöntemlerini çağırmaya ve uygulamalar arasında özelliklerine erişmek için bir yol sağlar. Bu istekleri gönderme için Microsoft Foundation Class Kitaplığı tarafından sağlanan "nesne işlevleri ve özellikleri yanı sıra, Özellikler'in ve veri türleri, iç ve dış adları atayan dağıtım eşlemesi" mekanizmasıdır işlev bağımsız değişkenleri.

|Dağıtım eşlemesi makrosu|Açıklama|
|-|-|
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|Dağıtım eşlemesi bir sınıfın yöntemlerini ve özelliklerini (sınıf bildirimi içinde kullanılmalıdır) kullanıma sunmak için kullanılacak bildirir.|
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|Dağıtım eşlemesi tanımını başlatır.|
|[END_DISPATCH_MAP](#end_dispatch_map)|Dağıtım eşlemesi tanımını sonlandırır.|
|[DISP_FUNCTION](#disp_function)|Bir dağıtım haritasında, bir OLE Otomasyon işlevi tanımlamak için kullanılır.|
|[DISP_PROPERTY](#disp_property)|Bir OLE Otomasyon özelliği tanımlar.|
|[DISP_PROPERTY_EX](#disp_property_ex)|Bir OLE Otomasyon özelliği tanımlar ve Get ve Set işlevlerini adları.|
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|Bildirim ile bir OLE Otomasyon özelliği tanımlar.|
|[DISP_PROPERTY_PARAM](#disp_property_param)|Parametreler ve adları Get ve Set işlevlerini alır bir OLE Otomasyon özelliği tanımlar.|
|[DISP_DEFVALUE](#disp_defvalue)|Varolan bir özellik bir nesnenin varsayılan değerini getirir.|

## <a name="declare_dispatch_map"></a>  DECLARE_DISPATCH_MAP

Varsa bir `CCmdTarget`-OLE sınıfı yöntemleri ve özellikleri göstermek için bir dağıtım eşlemesi sağlamalısınız Otomasyonu, programınızı türetilen sınıfta destekler.

```cpp
DECLARE_DISPATCH_MAP()
```

### <a name="remarks"></a>Açıklamalar

Declare_dıspatch_map makrosu, sınıf bildiriminin sonuna kullanın. Ardından. Sınıfın üye işlevleri tanımlar CPP dosyasına begın_dıspatch_map makrosu kullanın. Ardından makrosu girişleri her sınıfınızın kullanıma sunulan yöntemleri ve özellikleri (dısp_functıon, dısp_property ve benzeri) içerir. Son olarak, end_dıspatch_map makrosu kullanın.

> [!NOTE]
> Declare_dıspatch_map sonra herhangi bir üye bildirirseniz, yeni bir erişim türü belirtmeniz gerekir ( **genel**, **özel**, veya **korumalı**) için bunları.

Uygulama Sihirbazı ve kod sihirbazları Otomasyon sınıfları oluşturma ve gönderme eşlemeleri Bakımı yardımcı olur. Eşlemeleri dağıtma hakkında daha fazla bilgi için bkz. [otomasyon sunucuları](../../mfc/automation-servers.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

## <a name="begin_dispatch_map"></a>  BEGIN_DISPATCH_MAP

Gönderme haritanızı tanımını bildirir.

```cpp
BEGIN_DISPATCH_MAP(theClass, baseClass)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Bu dağıtım eşlemesi sahip olan sınıfın adını belirtir.

*baseClass*<br/>
Temel sınıfın adını belirtir *sınıfın*.

### <a name="remarks"></a>Açıklamalar

Sınıfınız için üye işlevleri tanımlayan uygulama dosyasında (.cpp), dağıtım eşlemesi begın_dıspatch_map makrosu ile Başlat, her dağıtım işlevleri ve özellikleri için makro girişler ekleyin ve END_DISPATCH_ ile dağıtım eşlemesi tamamlayın Harita makrosu.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="end_dispatch_map"></a>  END_DISPATCH_MAP

Gönderme haritanızı tanımını sonlandırır.

```cpp
END_DISPATCH_MAP()
```

### <a name="remarks"></a>Açıklamalar

Begın_dıspatch_map ile birlikte kullanılması gerekir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="disp_function"></a>  DISP_FUNCTION

Bir OLE Otomasyon işlevi, bir dağıtım haritasında tanımlar.

```cpp
DISP_FUNCTION(
  theClass,
  pszName,
  pfnMember,
  vtRetVal,
  vtsParams)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Sınıfın adı.

*pszName*<br/>
İşlev dış adı.

*pfnMember*<br/>
Üye işlevinin adı.

*vtRetVal*<br/>
İşlevin dönüş türünü belirten bir değeri.

*vtsParams*<br/>
İşlevin parametre listesi belirten bir veya daha fazla sabitleri boşlukla ayrılmış listesi.

### <a name="remarks"></a>Açıklamalar

*VtRetVal* VARTYPE tür olmayan bağımsız değişken. Bu bağımsız değişkeni aşağıdaki değerlerden alınmıştır `VARENUM` sabit listesi:

|Sembol|Dönüş türü|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|TARİH|
|VT_BSTR|BSTR|
|GT; VT_DISPATCH &AMP;|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT BEKLENİYORDU|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

*VtsParams* bağımsız değişken değerlerini boşlukla ayrılmış bir listesi verilmiştir `VTS_*` sabitler. Bir veya daha fazla boşluk (virgül değil) ile ayırarak bu değerleri işlevin parametre listesi belirtir. Örneğin,

[!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]

kısa bir tamsayı olarak bir işaretçi tarafından izlenen bir kısa tamsayı içeren bir liste belirtir.

`VTS_` Sabitleri ve bunların anlamları şu şekildedir:

|Sembol|Parametre türü|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**long**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_CY|`const CY` veya `CY*`|
|VTS_DATE|TARİH|
|VTS_BSTR|LPCSTR|
|VTS_DISPATCH|LPDISPATCH|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*` veya `VARIANT&`|
|VTS_UNKNOWN|LPUNKNOWN|
|VTS_PI2|__kısa\*__|
|VTS_PI4|__uzun\*__|
|VTS_PR4|__kayan nokta\*__|
|VTS_PR8|__çift\*__|
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

**Başlık:** afxdisp.h

## <a name="disp_property"></a>  DISP_PROPERTY

Bir OLE Otomasyon özelliği, bir dağıtım haritasında tanımlar.

```cpp
DISP_PROPERTY(
  theClass,
  pszName,
  memberName,
  vtPropType)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Sınıfın adı.

*pszName*<br/>
Özelliğin dış adı.

*memberName*<br/>
Özellik depolandığı üye değişkeninin adı.

*vtPropType*<br/>
Özelliğin türü belirten bir değeri.

### <a name="remarks"></a>Açıklamalar

*VtPropType* bağımsız değişken türü ise **VARTYPE**. Bu bağımsız değişken için olası değerler VARENUM sabit listesinden alınmış alınır:

|Sembol|Özellik türü|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|TARİH|
|VT_BSTR|`CString`|
|GT; VT_DISPATCH &AMP;|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT BEKLENİYORDU|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

Özelliği tarafından belirtilen üye değişkeninin değeri değiştiğinde bir dış istemci *memberName* değiştirir; değişikliği bildirim yoktur.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="disp_property_ex"></a>  DISP_PROPERTY_EX

Bir OLE Otomasyon özelliği ve adı almak ve bir dağıtım haritasında özelliğin değerini ayarlamak için kullanılan işlevleri tanımlar.

```cpp
DISP_PROPERTY_EX(
  theClass,
  pszName,
  memberGet,
  memberSet,
  vtPropType)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Sınıfın adı.

*pszName*<br/>
Özelliğin dış adı.

*memberGet*<br/>
Özelliği almak için kullanılan bir üye işlevin adı.

*memberSet*<br/>
Özelliği ayarlamak için kullanılan bir üye işlevin adı.

*vtPropType*<br/>
Özelliğin türü belirten bir değeri.

### <a name="remarks"></a>Açıklamalar

*MemberGet* ve *memberSet* işlevlerde tarafından belirlenen imzaları *vtPropType* bağımsız değişken. *MemberGet* işlev hiçbir bağımsız değişkeni alır ve belirtilen türde bir değer döndürür *vtPropType*. *MemberSet* işlevi bağımsız değişken tarafından belirtilen türü alır *vtPropType* ve nothing döndürür.

*VtPropType* VARTYPE tür olmayan bağımsız değişken. Bu bağımsız değişken için olası değerler VARENUM sabit listesinden alınmış alınır. Açıklamalar için bu değerlerin listesi için bkz. *vtRetVal* parametresinde [dısp_functıon](#disp_function). Dısp_functıon Açıklamalar içinde listelenen VT_EMPTY, özellik veri türü izin verilmiyor unutmayın.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="disp_property_notify"></a>  DISP_PROPERTY_NOTIFY

Bir OLE Otomasyon özelliği ile bildirim gönderme eşlemesinde tanımlar.

```cpp
DISP_PROPERTY_NOTIFY(
  theClass,
  szExternalName,
  memberName,
  pfnAfterSet,
  vtPropType)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Sınıfın adı.

*szExternalName*<br/>
Özelliğin dış adı.

*memberName*<br/>
Özellik depolandığı üye değişkeninin adı.

*pfnAfterSet*<br/>
Bildirim işlevi adı *szExternalName*.

*vtPropType*<br/>
Özelliğin türü belirten bir değeri.

### <a name="remarks"></a>Açıklamalar

Dısp_property ile tanımlanan özelliklerin aksine, dısp_property_notıfy ile tanımlanmış bir özellik tarafından belirtilen işlev otomatik olarak çağırır *pfnAfterSet* özelliği değiştiği.

*VtPropType* VARTYPE tür olmayan bağımsız değişken. Bu bağımsız değişken için olası değerler VARENUM sabit listesinden alınmış alınır:

|Sembol|Özellik türü|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|TARİH|
|VT_BSTR|`CString`|
|GT; VT_DISPATCH &AMP;|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT BEKLENİYORDU|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="disp_property_param"></a>  DISP_PROPERTY_PARAM

Erişilen ayrı bir özelliğini tanımlar `Get` ve `Set` üye işlevleri.

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

*Sınıfın*<br/>
Sınıfın adı.

*pszExternalName*<br/>
Özelliğin dış adı.

*pfnGet*<br/>
Özelliği almak için kullanılan bir üye işlevin adı.

*pfnSet*<br/>
Özelliği ayarlamak için kullanılan bir üye işlevin adı.

*vtPropType*<br/>
Özelliğin türü belirten bir değeri.

*vtsParams*<br/>
Boşlukla ayrılmış bir dizi `VTS_*` değişken parametre türleri, her parametre için bir tane.

### <a name="remarks"></a>Açıklamalar

Dısp_property_ex makrosu Bu makroyu özelliğinin bir parametre listesini belirtmenizi sağlar. Bu dizine veya parametreli özellikleri uygulamak için kullanışlıdır.

### <a name="example"></a>Örnek

Get aşağıdaki bildirimini düşünün ve üye özelliğine erişirken bir özel satır ve sütun istemek kullanıcının olanak tanıyan işlevler ayarlayın:

[!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]

Bunlar aşağıdaki dısp_property_param makrosu denetim gönderme eşlemesindeki karşılık gelir:

[!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]

Başka bir örnek olarak aşağıdaki get göz önünde bulundurun ve üye işlevleri ayarlayın:

[!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]

Bunlar aşağıdaki dısp_property_param makrosu denetim gönderme eşlemesindeki karşılık gelir:

[!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="disp_defvalue"></a>  DISP_DEFVALUE

Varolan bir özellik bir nesnenin varsayılan değerini getirir.

```cpp
DISP_DEFVALUE(theClass, pszName)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Sınıfın adı.

*pszName*<br/>
Nesnenin "value" temsil eden özelliğin dış adı.

### <a name="remarks"></a>Açıklamalar

Varsayılan bir değer kullanarak Visual Basic uygulamaları için daha basit, Otomasyon nesnesi programlama yapabilirsiniz.

Nesne "varsayılan değer" olan veya bir özellik veya üye işlevi bir nesneye bir başvuru belirtmediğinde ayarlamak özelliğidir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
