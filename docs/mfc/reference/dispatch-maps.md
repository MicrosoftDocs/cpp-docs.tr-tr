---
title: Eşlemeleri dağıtma | Microsoft Docs
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
ms.openlocfilehash: 107dba503c11d3810f75dcd4ee6e6f5af47008fc
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122986"
---
# <a name="dispatch-maps"></a>Eşlemeleri Dağıtma

OLE Otomasyon yöntemlerini çağırmaya ve uygulamalar arasında özelliklere erişmek için yöntemler sağlar. Bu istekleri gönderme için Microsoft Foundation Class Kitaplığı tarafından sağlanan "nesne işlevler ve Özellikler yanı sıra, Özellikler'in ve veri türleri iç ve dış adlarını atar gönderme harita" mekanizmadır işlev bağımsız değişkenleri.

|Dağıtım eşlemi makrosu|Açıklama|
|-|-|
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|Gönderme eşleme sınıf yöntemleri ve özellikleri (sınıfı bildiriminde kullanılmalıdır) kullanıma sunmak için kullanılacak bildirir.|
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|Gönderme harita tanımını başlatır.|
|[END_DISPATCH_MAP](#end_dispatch_map)|Gönderme harita tanımını sona erer.|
|[DISP_FUNCTION](#disp_function)|OLE Otomasyon işlevi tanımlamak için bir gönderme eşleminde kullanılır.|
|[DISP_PROPERTY](#disp_property)|OLE Otomasyon özelliği tanımlar.|
|[DISP_PROPERTY_EX](#disp_property_ex)|OLE Otomasyon özelliğini tanımlar ve Get ve Set işlevleri adları.|
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|Bir bildirim OLE Otomasyon özelliğiyle tanımlar.|
|[DISP_PROPERTY_PARAM](#disp_property_param)|Parametreleri ve adları alma ve ayarlama işlevleri alır OLE Otomasyon özelliği tanımlar.|
|[DISP_DEFVALUE](#disp_defvalue)|Mevcut bir özellik bir nesnenin varsayılan değer kılar.|

## <a name="declare_dispatch_map"></a>  DECLARE_DISPATCH_MAP

Varsa bir `CCmdTarget`-programınızı türetilen sınıfta OLE sınıfı yöntemleri ve özellikleri kullanıma sunmak için bir gönderme harita sağlamalısınız Otomasyon destekler.

```cpp
DECLARE_DISPATCH_MAP()
```

### <a name="remarks"></a>Açıklamalar

Declare_dıspatch_map makrosu sınıf bildiriminin sonundaki kullanın. Ardından. Sınıf üyesi işlevleri tanımlar CPP dosyası begın_dıspatch_map makrosu kullanın. Ardından makrosu girişleri her sınıfınızın sunulan yöntemleri ve özellikleri (dısp_functıon, dısp_property ve benzeri) içerir. Son olarak, end_dıspatch_map makrosu kullanın.

> [!NOTE]
> Declare_dıspatch_map sonra herhangi bir üye bildirirseniz, yeni bir erişim türü belirtmeniz gerekir ( **ortak**, **özel**, veya **korumalı**) onlar için.

Uygulama Sihirbazı'nı ve kod sihirbazları Otomasyon sınıfları oluşturma ve gönderme eşlemeleri korumada yardımcı. Eşlemeleri dağıtma hakkında daha fazla bilgi için bkz: [otomasyon sunucuları](../../mfc/automation-servers.md).

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

*Sınıfın*  
Bu dağıtım eşlemine sahip sınıfın adını belirtir.

*baseClass*  
Temel sınıfın adını belirtir. *sınıfın*.

### <a name="remarks"></a>Açıklamalar

Sınıfınız için üye işlevleri tanımlar uygulaması (.cpp) dosyasında, gönderme eşlemesi ile begın_dıspatch_map makrosu başlatın, makrosu girişleri her gönderme işlevleri ve özellikleri ekleyin ve END_DISPATCH_ gönderme Haritası tamamlayın Harita makrosu.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="end_dispatch_map"></a>  END_DISPATCH_MAP

Gönderme haritanızı tanımını sona erer.

```cpp
END_DISPATCH_MAP()
```

### <a name="remarks"></a>Açıklamalar

Begın_dıspatch_map ile birlikte kullanılması gerekir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="disp_function"></a>  DISP_FUNCTION

OLE Otomasyon işlevi bir gönderme eşleminde tanımlar.

```cpp
DISP_FUNCTION(
  theClass,
  pszName,
  pfnMember,
  vtRetVal,
  vtsParams)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*  
Sınıfın adı.

*pszName*  
Dış işlev adı.

*pfnMember*  
Üye işlevi adı.

*vtRetVal*  
İşlevin dönüş türünü belirten bir değer.

*vtsParams*  
İşlev parametre listesi belirterek bir veya daha fazla sabitleri boşlukla ayrılmış listesi.

### <a name="remarks"></a>Açıklamalar

*VtRetVal* VARTYPE tür bağımsız değişkeni aşağıdaki gibidir. Bu bağımsız değişken için aşağıdaki olası değerler alındığı `VARENUM` numaralandırma:

|Simgesi|Dönüş türü|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|TARİH|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

*VtsParams* değişken değeri boşlukla ayrılmış bir liste değerleri `VTS_*` sabitleri. Bir veya daha fazla (değil virgüller) boşluklarla ayrılmış bu değerleri işlev parametre listesi belirtir. Örneğin,

[!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]

kısa bir tamsayıya bir işaretçi tarafından izlenen kısa bir tamsayı içeren bir listesini belirtir.

`VTS_` Sabitleri ve anlamlarını aşağıdaki gibidir:

|Simgesi|Parametre türü|
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
|VTS_NONE|Hiçbir parametre|

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="disp_property"></a>  DISP_PROPERTY

OLE Otomasyon özelliği gönderme eşlemesinde tanımlar.

```cpp
DISP_PROPERTY(
  theClass,
  pszName,
  memberName,
  vtPropType)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*  
Sınıfın adı.

*pszName*  
Dış özelliğin adı.

*memberName*  
Özellik depolandığı üye değişkeni adı.

*vtPropType*  
Özelliğin türünü belirten bir değer.

### <a name="remarks"></a>Açıklamalar

*VtPropType* bağımsız değişken türü ise **VARTYPE**. Bu bağımsız değişken için olası değerler VARENUM numaralandırma içinden alınır:

|Simgesi|Özellik türü|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|TARİH|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

Bir dış istemcinin özelliği tarafından belirtilen üye değişkeninin değeri değiştiğinde *memberName* değiştirir; değişikliği bildirim yoktur.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="disp_property_ex"></a>  DISP_PROPERTY_EX

OLE Otomasyon özelliği ve adını alma ve gönderme eşlemesinde özelliğin değerini ayarlamak için kullanılan işlevleri tanımlar.

```cpp
DISP_PROPERTY_EX(
  theClass,
  pszName,
  memberGet,
  memberSet,
  vtPropType)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*  
Sınıfın adı.

*pszName*  
Dış özelliğin adı.

*memberGet*  
Özellik get için kullanılan üye işlevinin adı.

*memberSet*  
Özelliği ayarlamak için kullanılan üye işlevinin adı.

*vtPropType*  
Özelliğin türünü belirten bir değer.

### <a name="remarks"></a>Açıklamalar

*MemberGet* ve *memberSet* işlevler tarafından belirlenen imzaları sahip *vtPropType* bağımsız değişkeni. *MemberGet* işlevi bağımsız değişken almayan ve tarafından belirtilen türde bir değer döndürür *vtPropType*. *MemberSet* işlev tarafından belirtilen türünde bir bağımsız değişken alır *vtPropType* ve hiçbir şey döndürür.

*VtPropType* VARTYPE tür bağımsız değişkeni aşağıdaki gibidir. Bu bağımsız değişken için olası değerler VARENUM numaralandırma içinden alınır. Açıklamalar için bu değerleri listesi için bkz: *vtRetVal* parametresinde [dısp_functıon](#disp_function). Dısp_functıon Açıklamalar içinde listelenen VT_EMPTY özellik veri türüne izin verilmiyor unutmayın.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="disp_property_notify"></a>  DISP_PROPERTY_NOTIFY

OLE Otomasyon özelliği bildirim gönderme eşlemesinde tanımlar.

```cpp
DISP_PROPERTY_NOTIFY(
  theClass,
  szExternalName,
  memberName,
  pfnAfterSet,
  vtPropType)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*  
Sınıfın adı.

*szExternalName*  
Dış özelliğin adı.

*memberName*  
Özellik depolandığı üye değişkeni adı.

*pfnAfterSet*  
Bildirim işlevi adını *szExternalName*.

*vtPropType*  
Özelliğin türünü belirten bir değer.

### <a name="remarks"></a>Açıklamalar

Dısp_property ile tanımlanan özellikleri dısp_property_notıfy ile tanımlanmış bir özelliği tarafından belirtilen işlevin otomatik olarak çağırır *pfnAfterSet* özelliği değiştiği.

*VtPropType* VARTYPE tür bağımsız değişkeni aşağıdaki gibidir. Bu bağımsız değişken için olası değerler VARENUM numaralandırma içinden alınır:

|Simgesi|Özellik türü|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|TARİH|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="disp_property_param"></a>  DISP_PROPERTY_PARAM

Ayrı erişilen bir özelliğini tanımlar `Get` ve `Set` üye işlevleri.

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

*Sınıfın*  
Sınıfın adı.

*pszExternalName*  
Dış özelliğin adı.

*pfnGet*  
Özellik get için kullanılan üye işlevinin adı.

*pfnSet*  
Özelliği ayarlamak için kullanılan üye işlevinin adı.

*vtPropType*  
Özelliğin türünü belirten bir değer.

*vtsParams*  
Boşlukla ayrılmış bir dizi `VTS_*` değişken parametre türleri, her parametre için bir tane.

### <a name="remarks"></a>Açıklamalar

Dısp_property_ex makrosu bu makrosu özelliğinin bir parametre listesini belirtmenize olanak tanır. Bu dizini ya da parametreli özellikleri uygulamak için kullanışlıdır.

### <a name="example"></a>Örnek

Get aşağıdaki bildirimi göz önünde bulundurun ve belirli satır ve sütun özelliğine erişirken isteği kullanıcıya izin işlevler üyesi ayarlayın:

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

Mevcut bir özellik bir nesnenin varsayılan değer kılar.

```cpp
DISP_DEFVALUE(theClass, pszName)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*  
Sınıfın adı.

*pszName*  
Nesnenin "değeri" temsil eden özellik dış adıdır.

### <a name="remarks"></a>Açıklamalar

Varsayılan bir değer kullanarak Visual Basic uygulamalar için daha basit, Otomasyon nesnesi programlama yapabilirsiniz.

"Varsayılan değer" nesnenizin olan veya bir nesneye başvuru özelliği veya üye fonksiyonu belirtmediğinde kümesi özelliğidir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)  
