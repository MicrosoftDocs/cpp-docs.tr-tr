---
title: Çalışma Süresi Nesne Modeli Hizmetleri
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
ms.openlocfilehash: 45ad85e5b85674be957320ef6fdb7f5a81db6503
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304684"
---
# <a name="run-time-object-model-services"></a>Çalışma Süresi Nesne Modeli Hizmetleri

Sınıfları [CObject](../../mfc/reference/cobject-class.md) ve [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) çalışma süresi sınıf bilgilerine, seri hale getirme ve dinamik Nesne oluşturma dahil olmak üzere birçok nesne Hizmetleri kapsüller. Tüm sınıflar türetilen `CObject` bu işlevselliği devralır.

Çalışma süresi sınıf bilgilerine erişim, çalışma zamanında nesnenin sınıfına ilişkin bilgileri belirlemenize olanak sağlar. Çalışma zamanında bir nesnenin sınıfını belirleme imkanı ek tür denetimi işlev bağımsız değişkenlerinin ve bir nesne sınıfına göre özel amaçlı kod yazmanız gerekir, ihtiyacınız olduğunda yararlıdır. Çalışma süresi sınıf bilgilerine doğrudan C++ dil tarafından desteklenmiyor.

Seri hale getirme için veya bir nesnenin içeriğini okuma veya yazma dosyasından işlemidir. Serileştirme bile uygulama çıktıktan sonra bir nesnenin içeriğini depolamak için kullanabilirsiniz. Uygulama yeniden başlatıldığında nesne sonra dosyayı okuyabilir. Bu tür veri nesneleri "kalıcı" olduğu söylenir

Dinamik Nesne oluşturma, çalışma zamanında belirtilen sınıfın bir nesnesi oluşturmanıza olanak sağlar. Örneğin, belge, Görünüm ve çerçeve nesneleri framework dinamik olarak oluşturmak gerektiğinden, dinamik oluşturma desteklemelidir.

Aşağıdaki tablo, çalışma zamanı sınıf bilgileri, seri hale getirme ve dinamik oluşturma desteği MFC makrolarını listeler.

Bu çalışma zamanı nesne Hizmetleri ve seri hale getirme hakkında daha fazla bilgi için bkz [CObject sınıfı: Çalışma süresi sınıf bilgilerine erişme](../../mfc/accessing-run-time-class-information.md).

### <a name="run-time-object-model-services-macros"></a>Çalışma süresi nesne modeli Hizmetleri makroları

|||
|-|-|
|[DECLARE_DYNAMIC](#declare_dynamic)|(Sınıf bildirimi içinde kullanılmalıdır) çalışma süresi sınıf bilgilerine erişim sağlar.|
|[DECLARE_DYNCREATE](#declare_dyncreate)|Dinamik oluşturma ve (sınıf bildirimi içinde kullanılmalıdır) çalışma süresi sınıf bilgilerine erişim sağlar.|
|[DECLARE_SERIAL](#declare_serial)|Serileştirme ve (sınıf bildirimi içinde kullanılmalıdır) çalışma süresi sınıf bilgilerine erişim sağlar.|
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|(Sınıfı uygulamasında kullanılmalıdır) çalışma süresi sınıf bilgilerine erişim sağlar.|
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|Dinamik oluşturma ve çalışma zamanı bilgilerini (sınıfı uygulamasında kullanılmalıdır) erişim sağlar.|
|[IMPLEMENT_SERIAL](#implement_serial)|Serileştirme ve çalışma süresi sınıf bilgilerine (sınıfı uygulamasında kullanılmalıdır) erişim verir.|
|[RUNTIME_CLASS](#runtime_class)|Döndürür `CRuntimeClass` adlandırılmış sınıf için karşılık gelen yapısı.|

OLE sık nesneler çalışma zamanında dinamik oluşturulmasını gerektirir. Örneğin, bir sunucu uygulaması OLE öğeleri isteğine yanıt olarak bir istemciden gelen dinamik olarak oluşturmak mümkün olması gerekir. Benzer şekilde, Otomasyon sunucusu Otomasyon istemcilerden gelen isteklere yanıt öğeleri oluşturmak mümkün olması gerekir.

Microsoft Foundation Class Kitaplığı için OLE iki makro belirli sağlar.

### <a name="dynamic-creation-of-ole-objects"></a>OLE nesne dinamik oluşturma

|||
|-|-|
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|Ortak Denetimler kitaplığını belirtilen API uygulayıp uygulamadığını belirler.|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|Ortak Denetimler kitaplığını belirtilen API uygulayıp uygulamadığını belirler.|
|[DECLARE_OLECREATE](#declare_olecreate)|Nesnelerinin OLE Otomasyon yoluyla oluşturulmasına olanak sağlar.|
|[DECLARE_OLECTLTYPE](#declare_olectltype)|Bildirir `GetUserTypeNameID` ve `GetMiscStatus` denetim sınıfınızın bir üye işlevleri.|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|OLE denetim özelliklerini görüntülemek için özellik sayfalarının bir listesini sağlar bildirir.|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|OLE sistem tarafından oluşturulacak nesneleri sağlar.|
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|Implements `GetUserTypeNameID` ve `GetMiscStatus` denetim sınıfınızın bir üye işlevleri.|
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|Ya da bu makroyu veya [ımplement_olecreate](#implement_olecreate) kullanan herhangi bir sınıf için uygulama dosyasında yer almalıdır `DECLARE_OLECREATE`. |

## <a name="afx_comctl32_if_exists"></a> AFX_COMCTL32_IF_EXISTS

Ortak Denetimler kitaplığını belirtilen API uygulayıp uygulamadığını belirler.

### <a name="syntax"></a>Sözdizimi

  ```
AFX_COMCTL32_IF_EXISTS(  proc );
```

### <a name="parameters"></a>Parametreler

*yordam*<br/>
İşlev adı içeren null ile sonlandırılmış bir dize işaretçisi veya işlev sıra değeri belirtir. Bu parametre bir sıra değeri ise, düşük düzey Word'de olmalıdır; dwpoint sıfır olmalıdır. Bu parametre, Unicode biçiminde olmalıdır.

### <a name="remarks"></a>Açıklamalar

Ortak Denetimler kitaplığı tarafından işlevi belirtilen olup olmadığını belirlemek için bu makroyu kullanın *proc* (çağırmak yerine [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress).

### <a name="requirements"></a>Gereksinimler

afxcomctl32.h, afxcomctl32.inl

## <a name="afx_comctl32_if_exists2"></a>  AFX_COMCTL32_IF_EXISTS2

Ortak Denetimler kitaplığını belirtilen API uygulayıp uygulamadığını belirler (Unicode sürümü budur [afx_comctl32_ıf_exısts](#afx_comctl32_if_exists)).

### <a name="syntax"></a>Sözdizimi

```
AFX_COMCTL32_IF_EXISTS2( proc );
```

### <a name="parameters"></a>Parametreler

*yordam*<br/>
İşlev adı içeren null ile sonlandırılmış bir dize işaretçisi veya işlev sıra değeri belirtir. Bu parametre bir sıra değeri ise, düşük düzey Word'de olmalıdır; dwpoint sıfır olmalıdır. Bu parametre, Unicode biçiminde olmalıdır.

### <a name="remarks"></a>Açıklamalar

Ortak Denetimler kitaplığı tarafından işlevi belirtilen olup olmadığını belirlemek için bu makroyu kullanın *proc* (çağırmak yerine [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress). Bu makro afx_comctl32_ıf_exısts Unicode sürümüdür.

### <a name="requirements"></a>Gereksinimler

afxcomctl32.h, afxcomctl32.inl

##  <a name="declare_dynamic"></a>  DECLARE_DYNAMIC

Bir nesnenin sınıfına ilişkin çalışma zamanı bilgileri bir sınıftan türetilirken erişme yeteneği ekler `CObject`.

```
DECLARE_DYNAMIC(class_name)
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Sınıf gerçek adıdır.

### <a name="remarks"></a>Açıklamalar

DECLARE_DYNAMIC makrosu için sınıf üstbilgi (.h) modülünü ekleyin ve ardından bu sınıfın nesneleri erişmesi gereken tüm .cpp modüllerin bu modülü dahil edildi.

Açıklandığı DECLARE_ dinamik ve ımplement_dynamıc makroları kullanın, ardından RUNTIME_CLASS makrosunu kullanabilirsiniz ve `CObject::IsKindOf` çalışma zamanında nesnelerinizin sınıfı belirlemek için işlevi.

DECLARE_DYNAMIC sınıf bildirimi içinde yer alıyorsa ımplement_dynamıc sınıfı uygulamasında eklenmesi gerekir.

DECLARE_DYNAMIC makrosu hakkında daha fazla bilgi için bkz. [CObject sınıfı konuları](../../mfc/using-cobject.md).

### <a name="example"></a>Örnek

Örneğin bakın [ımplement_dynamıc](#implement_dynamic).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="declare_dyncreate"></a>  DECLARE_DYNCREATE

Nesnelerin sağlayan `CObject`-türetilmiş sınıflar çalışma zamanında dinamik olarak oluşturulacak.

```
DECLARE_DYNCREATE(class_name)
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Sınıf gerçek adıdır.

### <a name="remarks"></a>Açıklamalar

Framework, yeni nesneler dinamik olarak oluşturmak için bu özelliği kullanır. Yeni bir belge açtığınızda oluşturduğunuz Örneğin, yeni görünüm. Dinamik olarak oluşturmak framework gerektiğinden belge, Görünüm ve çerçeve sınıfları dinamik oluşturma desteklemelidir.

DECLARE_DYNCREATE makrosu sınıfı için .h modülünü ekleyin ve ardından bu sınıfın nesneleri erişmesi gereken tüm .cpp modüllerin bu modülü dahil edildi.

DECLARE_DYNCREATE sınıf bildirimi içinde bulunan, IMPLEMENT_DYNCREATE sınıfı uygulamasında eklenmesi gerekir.

DECLARE_DYNCREATE makrosu hakkında daha fazla bilgi için bkz. [CObject sınıfı konuları](../../mfc/using-cobject.md).

> [!NOTE]
>  DECLARE_DYNCREATE makrosu DECLARE_DYNAMIC tüm işlevleri içerir.

### <a name="example"></a>Örnek

Örneğin bakın [IMPLEMENT_DYNCREATE](#implement_dyncreate).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

## <a name="declareolectltype"></a>DECLARE_OLECTLTYPE

Bildirir `GetUserTypeNameID` ve `GetMiscStatus` denetim sınıfınızın bir üye işlevleri.

### <a name="syntax"></a>Sözdizimi

```
DECLARE_OLECTLTYPE( class_name )
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Denetim sınıfı adı.

### <a name="remarks"></a>Açıklamalar

`GetUserTypeNameID` ve `GetMiscStatus` bildirilen saf sanal işlevler `COleControl`. Çünkü bu işlevleri saf sanal, bunlar denetim sınıfınızda geçersiz kılınmalıdır. DECLARE_OLECTLTYPE ek olarak, denetim sınıf bildiriminizin ımplement_olectltype makrosu eklemeniz gerekir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxctl.h

## <a name="declareproppageids"></a>DECLARE_PROPPAGEIDS

OLE denetim özelliklerini görüntülemek için özellik sayfalarının bir listesini sağlar bildirir.

### <a name="syntax"></a>Sözdizimi

```
DECLARE_PROPPAGEIDS( class_name )
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Özellik sayfaları sahibi denetim sınıfı adı.

### <a name="remarks"></a>Açıklamalar

Kullanım `DECLARE_PROPPAGEIDS` makrosu, sınıf bildiriminin sonuna. Ardından, sınıfın üye işlevleri tanımlar .cpp dosyasını kullanın `BEGIN_PROPPAGEIDS` makrosu, her denetimin özellik sayfaları, bir makro girişleri ve `END_PROPPAGEIDS` özellik sayfası listesinin sonuna bildirmek için makrosu.

Özellik sayfaları hakkında daha fazla bilgi için bkz [ActiveX denetimleri: Özellik sayfaları](../mfc-activex-controls-property-pages.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxctl.h

##  <a name="declare_serial"></a>  DECLARE_SERIAL

Gerekli C++ üstbilgi kod oluşturur bir `CObject`-türetilmiş bir seri hale getirilebilir bir sınıf.

```
DECLARE_SERIAL(class_name)
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Sınıf gerçek adıdır.

### <a name="remarks"></a>Açıklamalar

Seri hale getirme için ve bir nesnenin içeriğini okuma veya yazma dosyasından işlemidir.

Declare_serıal makrosu bir .h Modülü'nü kullanın ve bu sınıfın nesneleri erişmesi gereken tüm .cpp modüllerin, ardından bu modülü dahil edildi.

Declare_serıal sınıf bildirimi içinde yer alıyorsa ımplement_serıal sınıfı uygulamasında eklenmesi gerekir.

Declare_serıal makrosu DECLARE_DYNAMIC ve DECLARE_DYNCREATE tüm işlevleri içerir.

AFX_API makrosu otomatik olarak dışarı aktarmak için kullanabileceğiniz `CArchive` declare_serıal ve ımplement_serıal makroları sınıflar için ayıklama işleci. Köşeli ayraç (.h dosyası içinde bulunur), aşağıdaki kodla sınıf bildirimleri:

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

Declare_serıal makrosu hakkında daha fazla bilgi için bkz. [CObject sınıfı konuları](../../mfc/using-cobject.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="implement_dynamic"></a>  IMPLEMENT_DYNAMIC

C++ kodu için dinamik bir gerekli oluşturur `CObject`-türetilmiş sınıf çalışma zamanı erişimi olan sınıf adı ve konumu hiyerarşi içinde.

```
IMPLEMENT_DYNAMIC(class_name, base_class_name)
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Sınıf gerçek adıdır.

*BASE_CLASS_NAME*<br/>
Temel sınıfın adı.

### <a name="remarks"></a>Açıklamalar

Implement_dynamıc makrosu bir .cpp Modülü'nü kullanın ve elde edilen nesne kodu yalnızca bir kez bağlayın.

Daha fazla bilgi için [CObject sınıfı konuları](../../mfc/using-cobject.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]

[!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="implement_dyncreate"></a>  IMPLEMENT_DYNCREATE

Nesnelerin sağlayan `CObject`-türetilmiş sınıflar çalışma zamanında dinamik olarak oluşturulması zaman DECLARE_DYNCREATE makrosu ile kullanıldığında.

```
IMPLEMENT_DYNCREATE(class_name, base_class_name)
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Sınıf gerçek adıdır.

*BASE_CLASS_NAME*<br/>
Temel sınıfın gerçek adı.

### <a name="remarks"></a>Açıklamalar

Framework bu özelliği bir nesne seri hale getirme sırasında diskten okuduğunda yeni nesneler dinamik olarak örnek oluşturmak için kullanır. IMPLEMENT_DYNCREATE makrosu sınıf uygulama dosyasında ekleyin. Daha fazla bilgi için [CObject sınıfı konuları](../../mfc/using-cobject.md).

DECLARE_DYNCREATE ve IMPLEMENT_DYNCREATE makroları kullanın, ardından RUNTIME_CLASS makrosunu kullanabilirsiniz ve `CObject::IsKindOf` çalışma zamanında nesnelerinizin sınıfı belirlemek için üye işlevi.

DECLARE_DYNCREATE sınıf bildirimi içinde bulunan, IMPLEMENT_DYNCREATE sınıfı uygulamasında eklenmesi gerekir.

Bu Makro tanımında sınıfınız için varsayılan oluşturucuyu çağırır unutmayın. Önemsiz olmayan bir oluşturucu sınıfı tarafından açıkça uygulanmışsa de açıkça varsayılan oluşturucuyu de uygulamalıdır. Varsayılan Oluşturucu sınıfın eklenebilir **özel** veya **korumalı** gelen dışında sınıf uygulamasını çağırılmasını önlemek için üye bölümler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]

[!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

## <a name="implement_olecreate_flags"></a>  IMPLEMENT_OLECREATE_FLAGS

Ya da bu makroyu veya [ımplement_olecreate](#implement_olecreate) DECLARE_OLECREATE kullanan herhangi bir sınıf için uygulama dosyasında yer almalıdır.

### <a name="syntax"></a>Sözdizimi

```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags,
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Sınıf gerçek adıdır.

*external_name*<br/>
Diğer uygulamalar (tırnak işareti içine alınmış) maruz nesne adı.

*nFlags*<br/>
Bir veya daha fazla aşağıdaki bayraklar içerir:

   - `afxRegInsertable` OLE nesneleri için Nesne Ekle iletişim kutusunda görünmesini sağlar.
   - `afxRegApartmentThreading` İş parçacığı modeli ThreadingModel kayıt defterindeki ayarlar Grup =.
   - `afxRegFreeThreading` İş parçacığı modeli ThreadingModel kayıt defterindeki ayarlar ücretsiz =.

         You can combine the two flags `afxRegApartmentThreading` and `afxRegFreeThreading` to set ThreadingModel=Both. See [InprocServer32](/windows/desktop/com/inprocserver32) in the Windows SDK for more information on threading model registration.

*m*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4* , *b5*, *b6*, *b7*, *b8* sınıfın CLSID bileşenleri.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Implement_olecreate_flags kullanırsanız, nesnenizin desteklediği kullanarak hangi iş parçacığı modeli belirtebilirsiniz *nFlags* parametresi. Yalnızca tek treading modelini desteklemek istiyorsanız, ımplement_olecreate kullanın.

Dış adı, diğer uygulamalar için sunulan tanımlayıcısıdır. İstemci uygulamaları, bu sınıfın bir nesnesi bir Otomasyon sunucusundan istemek için dış adı kullanın.

OLE sınıf kimliği bir nesne için benzersiz 128-bit tanımlayıcısıdır. Biri oluşur **uzun**, iki **WORD**s ve sekiz **bayt**tarafından temsil edilen s *l*, *w1*, *w2*, ve *b1* aracılığıyla *b8* söz dizimi açıklaması. Uygulama Sihirbazı ve kod sihirbazları benzersiz OLE sınıf kimlikleri, gerektiği gibi oluşturun.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="implement_olecreate"></a> IMPLEMENT_OLECTLTYPE

Implements `GetUserTypeNameID` ve `GetMiscStatus` denetim sınıfınızın bir üye işlevleri.

### <a name="syntax"></a>Sözdizimi

```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Denetim sınıfı adı.

*idsUserTypeName*<br/>
Denetimin dış adını içeren bir dize kaynak kimliği.

*dwOleMisc*<br/>
Bir veya daha fazla bayrakları içeren bir sabit listesi. Bu sabit listesi hakkında daha fazla bilgi için bkz. [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) Windows SDK.

### <a name="remarks"></a>Açıklamalar

Implement_olectltype ek olarak, denetim sınıf bildiriminizin DECLARE_OLECTLTYPE makrosu eklemeniz gerekir.

`GetUserTypeNameID` Üye işlevi denetim sınıfınıza tanımlayan kaynak dizesi döndürür. `GetMiscStatus` OLEMISC bitlerin denetiminizin döndürür. Bu numaralandırma denetiminizin çeşitli özelliklerini açıklayan bir ayarlar koleksiyonu belirtir. OLEMISC ayarlarının tam bir açıklaması için bkz. [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) Windows SDK.

> [!NOTE]
>  ActiveX ControlWizard tarafından kullanılan varsayılan ayarlar şunlardır: OLEMISC_ACTIVATEWHENVISIBLE, OLEMISC_SETCLIENTSITEFIRST, OLEMISC_INSIDEOUT, OLEMISC_CANTLINKINSIDE ve OLEMISC_RECOMPOSEONRESIZE.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxctl.h

##  <a name="implement_serial"></a>  IMPLEMENT_SERIAL

C++ kodu için dinamik bir gerekli oluşturur `CObject`-türetilmiş sınıf çalışma zamanı erişimi olan sınıf adı ve konumu hiyerarşi içinde.

```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Sınıf gerçek adıdır.

*BASE_CLASS_NAME*<br/>
Temel sınıfın adı.

*wSchema*<br/>
"Tarafından oluşturulan verileri işlemek üzere seri durumdan çıkarılırken bir programı etkinleştirmek için Arşiv'de kodlanmış bir UINT sürüm numarası" önceki sürümleri program. Sınıf şema numarası -1 olmalıdır.

### <a name="remarks"></a>Açıklamalar

Implement_serıal makrosu .cpp modülünde kullanın. ardından ortaya çıkan nesne kodu yalnızca bir kez bağlayın.

AFX_API makrosu otomatik olarak dışarı aktarmak için kullanabileceğiniz `CArchive` declare_serıal ve ımplement_serıal makroları sınıflar için ayıklama işleci. Köşeli ayraç (.h dosyası içinde bulunur), aşağıdaki kodla sınıf bildirimleri:

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

Daha fazla bilgi için [CObject sınıfı konuları](../../mfc/using-cobject.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="runtime_class"></a>  RUNTIME_CLASS

Çalışma zamanı sınıf yapısını bir C++ sınıf adından alır.

```
RUNTIME_CLASS(class_name)
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
(Tırnak işaretleri arasına değil) sınıfın gerçek adı.

### <a name="remarks"></a>Açıklamalar

RUNTIME_CLASS bir işaretçi döndürür bir [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) tarafından belirtilen sınıf yapısını *$class_name*. Yalnızca `CObject`-DECLARE_DYNAMIC, DECLARE_DYNCREATE veya declare_serıal ile bildirilen türetilmiş sınıfların işaretçileri döndürür bir `CRuntimeClass` yapısı.

Daha fazla bilgi için [CObject sınıfı konuları](../../mfc/using-cobject.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="declare_olecreate"></a>  DECLARE_OLECREATE

Nesnelerin sağlayan `CCmdTarget`-türetilmiş sınıfları OLE Otomasyon yoluyla oluşturulacak.

```
DECLARE_OLECREATE(class_name)
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Sınıf gerçek adıdır.

### <a name="remarks"></a>Açıklamalar

Bu makro, bu tür nesneler oluşturmak diğer OLE özellikli uygulamalar sağlar.

Sınıfı için .h modülünde DECLARE_OLECREATE makrosu ekleyin ve bu sınıfın nesneleri erişmesi gereken tüm .cpp modüllerin, ardından bu modülü dahil edildi.

DECLARE_OLECREATE sınıf bildirimi içinde yer alıyorsa ımplement_olecreate sınıfı uygulamasında eklenmesi gerekir. DECLARE_OLECREATE kullanarak bir sınıf bildirimi ayrıca DECLARE_DYNCREATE veya declare_serıal kullanmanız gerekir.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi**: afxdisp.h

##  <a name="implement_olecreate"></a>  IMPLEMENT_OLECREATE

Ya da bu makroyu veya [ımplement_olecreate_flags](#implement_olecreate_flags) kullanan herhangi bir sınıf için uygulama dosyasında yer almalıdır `DECLARE_OLECREATE`.

```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Sınıf gerçek adıdır.

*external_name*<br/>
Diğer uygulamalar (tırnak işareti içine alınmış) maruz nesne adı.

*m*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4* , *b5*, *b6*, *b7*, *b8* sınıfın CLSID bileşenleri.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Varsayılan olarak, ımplement_olecreate kullanırsanız, yalnızca tek iş parçacığı modelini destekler. Implement_olecreate_flags kullanırsanız, nesnenizin desteklediği kullanarak hangi iş parçacığı modeli belirtebilirsiniz *nFlags* parametresi.

Dış adı, diğer uygulamalar için sunulan tanımlayıcısıdır. İstemci uygulamaları, bu sınıfın bir nesnesi bir Otomasyon sunucusundan istemek için dış adı kullanın.

OLE sınıf kimliği bir nesne için benzersiz 128-bit tanımlayıcısıdır. Biri oluşur **uzun**, iki **WORD**s ve sekiz **bayt**tarafından temsil edilen s *l*, *w1*, *w2*, ve *b1* aracılığıyla *b8* söz dizimi açıklaması. Uygulama Sihirbazı ve kod sihirbazları benzersiz OLE sınıf kimlikleri, gerektiği gibi oluşturun.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi**: afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](mfc-macros-and-globals.md)<br/>
[MFC Ortak Denetimler Kitaplığını Yalıtma](../isolation-of-the-mfc-common-controls-library.md)<br/>
[CLSID anahtarı](/windows/desktop/com/clsid-key-hklm)
