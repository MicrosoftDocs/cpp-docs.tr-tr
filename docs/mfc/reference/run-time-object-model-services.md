---
title: Çalışma Süresi Nesne Modeli Hizmetleri
ms.date: 03/27/2019
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
ms.openlocfilehash: f8b891467d91d0c945b6c59c90dbc49fd7cbcb30
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491583"
---
# <a name="run-time-object-model-services"></a>Çalışma Süresi Nesne Modeli Hizmetleri

[CObject](../../mfc/reference/cobject-class.md) ve [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) sınıfları, çalışma zamanı sınıf bilgilerine, serileştirme ve dinamik nesne oluşturmaya erişim de dahil olmak üzere çeşitli nesne hizmetlerini kapsülletir. Sınıfından türetilmiş tüm sınıflar `CObject` bu işlevi alır.

Çalışma zamanı sınıf bilgilerine erişim, bir nesnenin sınıfı hakkında çalışma zamanında bilgi belirlemenizi sağlar. Çalışma zamanında bir nesnenin sınıfını belirleme özelliği, işlev bağımsız değişkenlerinin ek tür denetimi yapmanız gerektiğinde ve bir nesnenin sınıfına göre özel amaçlı kod yazmanız gerektiğinde faydalıdır. Çalışma zamanı sınıf bilgileri doğrudan C++ dil tarafından desteklenmez.

Serileştirme, bir nesnenin içeriğini bir dosyaya veya dosyadan yazma veya okuma işlemidir. Uygulamanın çıktıktan sonra bile bir nesnenin içeriğini depolamak için serileştirme kullanabilirsiniz. Nesne daha sonra uygulama yeniden başlatıldığında dosyadan okunabilir. Bu tür veri nesneleri "persistent" olarak kabul edilir.

Dinamik nesne oluşturma, çalışma zamanında belirtilen sınıfın bir nesnesini oluşturmanıza olanak sağlar. Örneğin, Framework 'ün dinamik olarak oluşturulması gerektiğinden, belge, görünüm ve çerçeve nesneleri dinamik oluşturmayı desteklemelidir.

Aşağıdaki tabloda, çalışma zamanı sınıf bilgilerini, serileştirme ve dinamik oluşturmayı destekleyen MFC makroları listelenmektedir.

Bu çalışma zamanı nesne Hizmetleri ve serileştirme hakkında daha fazla bilgi için CObject sınıfı makalesine [bakın: Çalışma zamanı sınıf bilgilerine](../../mfc/accessing-run-time-class-information.md)erişme.

### <a name="run-time-object-model-services-macros"></a>Çalışma zamanı nesne modeli Hizmetleri makroları

|||
|-|-|
|[DECLARE_DYNAMIC](#declare_dynamic)|Çalışma zamanı sınıf bilgilerine erişimi (sınıf bildiriminde kullanılması gerekir) sağlar.|
|[DECLARE_DYNCREATE](#declare_dyncreate)|Dinamik oluşturma ve çalışma zamanı sınıf bilgilerine erişimi (sınıf bildiriminde kullanılması gerekir) sağlar.|
|[DECLARE_SERIAL](#declare_serial)|Serileştirme ve çalışma zamanı sınıf bilgilerine erişimi (sınıf bildiriminde kullanılması gerekir) sağlar.|
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|Çalışma zamanı sınıf bilgilerine erişimi (sınıf uygulamasında kullanılması gerekir) sağlar.|
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|Dinamik oluşturma ve çalışma zamanı bilgilerine erişimi (sınıf uygulamasında kullanılması gerekir) sağlar.|
|[IMPLEMENT_SERIAL](#implement_serial)|Serileştirme ve çalışma zamanı sınıf bilgilerine erişime izin verir (sınıf uygulamasında kullanılması gerekir).|
|[RUNTIME_CLASS](#runtime_class)|Adlandırılmış sınıfa karşılık gelen yapıyıdöndürür.`CRuntimeClass`|

OLE genellikle çalışma zamanında nesnelerin dinamik olarak oluşturulmasını gerektirir. Örneğin, bir OLE sunucu uygulamasının bir istemciden gelen bir isteğe yanıt olarak OLE öğeleri oluşturabiliyor olması gerekir. Benzer şekilde, bir Otomasyon sunucusunun Otomasyon istemcilerinden gelen isteklere yanıt olarak öğe oluşturabiliyor olması gerekir.

Microsoft Foundation Class Kitaplığı OLE 'e özgü iki makro sağlar.

### <a name="dynamic-creation-of-ole-objects"></a>OLE nesnelerinin dinamik olarak oluşturulması

|||
|-|-|
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|Ortak denetimler kitaplığının belirtilen API 'YI uygulayıp uygulamadığını belirler.|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|Ortak denetimler kitaplığının belirtilen API 'YI uygulayıp uygulamadığını belirler.|
|[DECLARE_OLECREATE](#declare_olecreate)|OLE Otomasyonu aracılığıyla nesnelerin oluşturulmasını sağlar.|
|[DECLARE_OLECTLTYPE](#declare_olectltype)|Denetim sınıfınızın `GetMiscStatus` ve üye işlevlerini bildirir. `GetUserTypeNameID`|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|OLE denetiminin özelliklerini görüntüleyen özellik sayfalarının bir listesini sağladığını bildirir.|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|OLE sistemi tarafından oluşturulan nesneleri sağlar.|
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|Denetim sınıfınızın `GetMiscStatus` ve üye işlevlerini uygular. `GetUserTypeNameID`|
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|Bu makro veya [IMPLEMENT_OLECREATE](#implement_olecreate) , tarafından kullanılan `DECLARE_OLECREATE`herhangi bir sınıf için uygulama dosyasında görünmelidir. |

## <a name="afx_comctl32_if_exists"></a>AFX_COMCTL32_IF_EXISTS

Ortak denetimler kitaplığının belirtilen API 'YI uygulayıp uygulamadığını belirler.

### <a name="syntax"></a>Sözdizimi

```
AFX_COMCTL32_IF_EXISTS(  proc );
```

### <a name="parameters"></a>Parametreler

*proc*<br/>
İşlev adını içeren, null ile sonlandırılmış bir dize işaretçisi veya işlevin sıra değerini belirtir. Bu parametre bir sıralı değer ise, düşük sıralı sözcükte olmalıdır; yüksek sıralı sözcük sıfır olmalıdır. Bu parametre Unicode biçiminde olmalıdır.

### <a name="remarks"></a>Açıklamalar

Ortak denetimlerin işlem tarafından belirtilen işlevi ( [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)çağırmak yerine) kitaplık olarak belirtmediğini öğrenmek için bu makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

afxcomctl32. h, afxcomctl32. inl

## <a name="afx_comctl32_if_exists2"></a>AFX_COMCTL32_IF_EXISTS2

Ortak denetimler kitaplığının belirtilen API 'YI uygulayıp uygulamadığını belirler (Bu, [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)'in Unicode sürümüdür).

### <a name="syntax"></a>Sözdizimi

```
AFX_COMCTL32_IF_EXISTS2( proc );
```

### <a name="parameters"></a>Parametreler

*proc*<br/>
İşlev adını içeren, null ile sonlandırılmış bir dize işaretçisi veya işlevin sıra değerini belirtir. Bu parametre bir sıralı değer ise, düşük sıralı sözcükte olmalıdır; yüksek sıralı sözcük sıfır olmalıdır. Bu parametre Unicode biçiminde olmalıdır.

### <a name="remarks"></a>Açıklamalar

Ortak denetimlerin işlem tarafından belirtilen işlevi ( [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)çağırmak yerine) kitaplık olarak belirtmediğini öğrenmek için bu makroyu kullanın. Bu makro, AFX_COMCTL32_IF_EXISTS 'in Unicode sürümüdür.

### <a name="requirements"></a>Gereksinimler

afxcomctl32. h, afxcomctl32. inl

##  <a name="declare_dynamic"></a>DECLARE_DYNAMIC

Öğesinden `CObject`bir sınıf türetirken nesnenin sınıfı hakkında çalışma zamanı bilgilerine erişme özelliği ekler.

```
DECLARE_DYNAMIC(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

### <a name="remarks"></a>Açıklamalar

Sınıfın üst bilgi (. h) modülüne DECLARE_DYNAMIC makrosunu ekleyin ve bu modülün bu sınıfın nesnelerine erişmesi gereken tüm. cpp modüllerine dahil edin.

Açıklandığı gibi declare_ DYNAMIC ve IMPLEMENT_DYNAMIC makrolarını kullanıyorsanız, çalışma zamanında nesnelerinizin sınıfını belirleyebilmek için RUNTIME_CLASS makrosunu ve `CObject::IsKindOf` işlevini kullanabilirsiniz.

DECLARE_DYNAMIC sınıf bildiriminde yer alıyorsa, IMPLEMENT_DYNAMIC sınıf uygulamasına dahil olmalıdır.

DECLARE_DYNAMIC makrosu hakkında daha fazla bilgi için bkz. [CObject sınıfı konuları](../../mfc/using-cobject.md).

### <a name="example"></a>Örnek

[IMPLEMENT_DYNAMIC](#implement_dynamic)için örneğe bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="declare_dyncreate"></a>DECLARE_DYNCREATE

Türetilmiş sınıfların nesnelerinin `CObject`çalışma zamanında dinamik olarak oluşturulmasını sağlar.

```
DECLARE_DYNCREATE(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

### <a name="remarks"></a>Açıklamalar

Framework, dinamik olarak yeni nesneler oluşturmak için bu özelliği kullanır. Örneğin, yeni bir belge açtığınızda oluşturulan yeni görünüm. Framework 'ün dinamik olarak oluşturulması gerektiğinden, belge, görünüm ve çerçeve sınıfları dinamik oluşturmayı desteklemelidir.

Sınıfına ait. h modülüne DECLARE_DYNCREATE makrosunu ekleyin ve bu modülün bu sınıfın nesnelerine erişmesi gereken tüm. cpp modüllerine dahil edin.

DECLARE_DYNCREATE sınıf bildiriminde yer alıyorsa, IMPLEMENT_DYNCREATE sınıf uygulamasına dahil olmalıdır.

DECLARE_DYNCREATE makrosu hakkında daha fazla bilgi için bkz. [CObject sınıfı konuları](../../mfc/using-cobject.md).

> [!NOTE]
>  DECLARE_DYNCREATE makrosu tüm DECLARE_DYNAMIC işlevlerini içerir.

### <a name="example"></a>Örnek

[IMPLEMENT_DYNCREATE](#implement_dyncreate)için örneğe bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="declare_olectltype"></a>DECLARE_OLECTLTYPE

Denetim sınıfınızın `GetMiscStatus` ve üye işlevlerini bildirir. `GetUserTypeNameID`

### <a name="syntax"></a>Sözdizimi

```
DECLARE_OLECTLTYPE( class_name )
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Denetim sınıfının adı.

### <a name="remarks"></a>Açıklamalar

`GetUserTypeNameID`ve `GetMiscStatus` , içinde `COleControl`belirtilen saf sanal işlevlerdir. Bu işlevler saf sanal olduğundan, denetim sınıfınıza geçersiz kılınmalıdır. DECLARE_OLECTLTYPE ' a ek olarak, IMPLEMENT_OLECTLTYPE makrosunu denetim sınıfı bildiriye eklemeniz gerekir.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxctl. h

## <a name="declare_proppageids"></a>DECLARE_PROPPAGEIDS

OLE denetiminin özelliklerini görüntüleyen özellik sayfalarının bir listesini sağladığını bildirir.

### <a name="syntax"></a>Sözdizimi

```
DECLARE_PROPPAGEIDS( class_name )
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Özellik sayfalarına sahip olan denetim sınıfının adı.

### <a name="remarks"></a>Açıklamalar

Sınıf bildirimindeki sonundaki makroyu kullanın. `DECLARE_PROPPAGEIDS` Ardından, sınıfının üye işlevlerini tanımlayan. cpp dosyasında, denetimin özellik sayfalarının her biri için makro, `BEGIN_PROPPAGEIDS` makro girişleri `END_PROPPAGEIDS` ve özellik sayfası listesinin sonunu bildirmek için makro kullanın.

Özellik sayfaları hakkında daha fazla bilgi için bkz [. ActiveX denetimleri: Özellik sayfaları](../mfc-activex-controls-property-pages.md).

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxctl. h

##  <a name="declare_serial"></a>DECLARE_SERIAL

Seri hale C++ getirilebilecek bir `CObject`türetilmiş sınıf için gereken üst bilgi kodunu üretir.

```
DECLARE_SERIAL(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

### <a name="remarks"></a>Açıklamalar

Serileştirme, bir dosyanın içeriğini bir dosyadan veya dosyadan yazma veya okuma işlemidir.

DECLARE_SERIAL makrosunu bir. h modülünde kullanın ve bu modülün bu sınıfın nesnelerine erişmesi gereken tüm. cpp modüllerine dahil edin.

DECLARE_SERIAL sınıf bildiriminde yer alıyorsa, IMPLEMENT_SERIAL sınıf uygulamasına dahil olmalıdır.

DECLARE_SERIAL makrosu, DECLARE_DYNAMIC ve DECLARE_DYNCREATE 'in tüm işlevlerini içerir.

AFX_API makrosunu, DECLARE_SERIAL ve IMPLEMENT_SERIAL makrolarını kullanan sınıfların `CArchive` ayıklama işlecini otomatik olarak dışarı aktarmak için kullanabilirsiniz. Sınıf bildirimlerini (. h dosyasında bulunur) aşağıdaki kodla ayraç içine girin:

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

DECLARE_SERIAL makrosu hakkında daha fazla bilgi için bkz. [CObject sınıfı konuları](../../mfc/using-cobject.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="implement_dynamic"></a>IMPLEMENT_DYNAMIC

Sınıf adına C++ ve hiyerarşideki konuma çalışma zamanı `CObject`erişimi olan dinamik türetilmiş bir sınıf için gereken kodu üretir.

```
IMPLEMENT_DYNAMIC(class_name, base_class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

*base_class_name*<br/>
Temel sınıfın adı.

### <a name="remarks"></a>Açıklamalar

IMPLEMENT_DYNAMIC makrosunu bir. cpp modülünde kullanın ve ardından elde edilen nesne kodunu yalnızca bir kez bağlayın.

Daha fazla bilgi için bkz. [CObject sınıfı konuları](../../mfc/using-cobject.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]

[!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE

Türetilmiş sınıfların nesnelerinin `CObject`, DECLARE_DYNCREATE makrosu ile birlikte kullanıldığında çalışma zamanında dinamik olarak oluşturulmasını sağlar.

```
IMPLEMENT_DYNCREATE(class_name, base_class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

*base_class_name*<br/>
Taban sınıfının gerçek adı.

### <a name="remarks"></a>Açıklamalar

Framework, serileştirme sırasında diskten bir nesne okurken, örneğin, dinamik olarak yeni nesneler oluşturmak için bu özelliği kullanır. Sınıf uygulama dosyasına IMPLEMENT_DYNCREATE makrosunu ekleyin. Daha fazla bilgi için bkz. [CObject sınıfı konuları](../../mfc/using-cobject.md).

DECLARE_DYNCREATE ve IMPLEMENT_DYNCREATE makrolarını kullanıyorsanız, çalışma zamanında nesnelerinizin sınıfını belirleyebilmek için RUNTIME_CLASS makrosunu ve `CObject::IsKindOf` member işlevini kullanabilirsiniz.

DECLARE_DYNCREATE sınıf bildiriminde yer alıyorsa, IMPLEMENT_DYNCREATE sınıf uygulamasına dahil olmalıdır.

Bu makro tanımının sınıfınız için varsayılan oluşturucuyu çağıracağına unutmayın. Basit olmayan bir Oluşturucu sınıf tarafından açıkça uygulanırsa, ayrıca varsayılan oluşturucuyu de açıkça uygulamalıdır. Varsayılan Oluşturucu sınıfın **özel** veya **korumalı** üye bölümlerine, sınıf uygulamasının dışından çağrılmasına engel olmak için eklenebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]

[!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="implement_olecreate_flags"></a>IMPLEMENT_OLECREATE_FLAGS

Bu makro ya da [IMPLEMENT_OLECREATE](#implement_olecreate) , DECLARE_OLECREATE kullanan herhangi bir sınıf için uygulama dosyasında görünmelidir.

### <a name="syntax"></a>Sözdizimi

```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags,
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

*external_name*<br/>
Diğer uygulamalara sunulan nesne adı (tırnak işaretleri içine alınmıştır).

*nFlags*<br/>
Aşağıdaki bayraklardan birini veya daha fazlasını içerir:

   - `afxRegInsertable`OLE nesneleri için nesne Ekle iletişim kutusunda denetimin görünmesine izin verir.
   - `afxRegApartmentThreading`Kayıt defterindeki iş parçacığı modelini ThreadingModel = Apartment olarak ayarlar.
   - `afxRegFreeThreading`Kayıt defterindeki iş parçacığı modelini ThreadingModel = ücretsiz olarak ayarlar.

         You can combine the two flags `afxRegApartmentThreading` and `afxRegFreeThreading` to set ThreadingModel=Both. See [InprocServer32](/windows/win32/com/inprocserver32) in the Windows SDK for more information on threading model registration.

*l*, *W1*, *W2*, *B1*, *B2*, *B3*, *B4*, *B5*, *B6*, *B7*, , sınıfın CLSID 'si.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  IMPLEMENT_OLECREATE_FLAGS kullanıyorsanız, *nFlags* parametresini kullanarak nesnenizin hangi iş parçacığı modelini desteklediğini belirtebilirsiniz. Yalnızca tek-Tokuma modelini desteklemek istiyorsanız, IMPLEMENT_OLECREATE kullanın.

Dış ad, diğer uygulamalara sunulan tanıtıcıdır. İstemci uygulamaları, bir Otomasyon sunucusundan bu sınıftan bir nesne istemek için dış adı kullanır.

OLE sınıf KIMLIĞI, nesnesi için benzersiz bir 128 bitlik tanımlayıcıdır. Söz dizimi açıklamasında *l*, *W1*, *W2*ve *B1* - *B8* Ile gösterildiği gibi bir **Long**, iki **sözcükten**ve sekiz **baytlık**bir hata oluşur. Uygulama Sihirbazı ve kod sihirbazları, gerektiğinde sizin için benzersiz OLE sınıfı kimlikleri oluşturur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="implement_olectltype"></a>IMPLEMENT_OLECTLTYPE

Denetim sınıfınızın `GetMiscStatus` ve üye işlevlerini uygular. `GetUserTypeNameID`

### <a name="syntax"></a>Sözdizimi

```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Denetim sınıfının adı.

*idsUserTypeName*<br/>
Denetimin dış adını içeren bir dizenin kaynak KIMLIĞI.

*Dwotamisc*<br/>
Bir veya daha fazla bayrak içeren bir sabit listesi. Bu numaralandırma hakkında daha fazla bilgi için Windows SDK [Olemisc](/windows/win32/api/oleidl/ne-oleidl-olemisc) bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

IMPLEMENT_OLECTLTYPE ' a ek olarak, DECLARE_OLECTLTYPE makrosunu denetim sınıfı bildiriye eklemeniz gerekir.

Üye `GetUserTypeNameID` işlevi, denetim sınıfınızı tanımlayan kaynak dizesini döndürür. `GetMiscStatus`denetiminiz için OLEMISC bit döndürür. Bu numaralandırma, denetiminizin çeşitli özelliklerini açıklayan ayarların bir koleksiyonunu belirtir. OLEMISC ayarlarının tam açıklaması için bkz. Windows SDK [olemisc](/windows/win32/api/oleidl/ne-oleidl-olemisc) .

> [!NOTE]
>  ActiveX ControlWizard tarafından kullanılan varsayılan ayarlar şunlardır: OLEMISC_ACTIVATEWHENVISIBLE, OLEMISC_SETCLIENTSITEFIRST, OLEMISC_INSIDEOUT, OLEMISC_CANTLINKINSIDE ve OLEMISC_RECOMPOSEONRESIZE.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxctl. h

##  <a name="implement_serial"></a>IMPLEMENT_SERIAL

Sınıf adına C++ ve hiyerarşideki konuma çalışma zamanı `CObject`erişimi olan dinamik türetilmiş bir sınıf için gereken kodu üretir.

```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

*base_class_name*<br/>
Temel sınıfın adı.

*wSchema*<br/>
Seri durumdan çıkarma programının önceki program sürümleri tarafından oluşturulan verileri belirleyip işlemesini sağlamak için arşivde kodlanacak bir UINT "sürüm numarası". Sınıf şeması numarası-1 olmalıdır.

### <a name="remarks"></a>Açıklamalar

. Cpp modülünde IMPLEMENT_SERIAL makrosunu kullanın; ardından elde edilen nesne kodunu yalnızca bir kez bağlayın.

AFX_API makrosunu, DECLARE_SERIAL ve IMPLEMENT_SERIAL makrolarını kullanan sınıfların `CArchive` ayıklama işlecini otomatik olarak dışarı aktarmak için kullanabilirsiniz. Sınıf bildirimlerini (. h dosyasında bulunur) aşağıdaki kodla ayraç içine girin:

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

Daha fazla bilgi için [CObject sınıfı konularına](../../mfc/using-cobject.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="runtime_class"></a>RUNTIME_CLASS

Bir C++ sınıf adından çalışma zamanı sınıf yapısını alır.

```
RUNTIME_CLASS(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı (tırnak işaretleri içine alınmaz).

### <a name="remarks"></a>Açıklamalar

RUNTIME_CLASS, *class_name*tarafından belirtilen sınıf Için [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına yönelik bir işaretçi döndürür. Yalnızca `CObject`DECLARE_DYNAMIC, DECLARE_DYNCREATE veya DECLARE_SERIAL ile belirtilen türetilmiş sınıflar bir `CRuntimeClass` yapıya işaretçiler döndürür.

Daha fazla bilgi için bkz. [CObject sınıfı konuları](../../mfc/using-cobject.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="declare_olecreate"></a>DECLARE_OLECREATE

Türetilmiş sınıfların nesnelerinin `CCmdTarget`OLE Otomasyonu aracılığıyla oluşturulmasını sağlar.

```
DECLARE_OLECREATE(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

### <a name="remarks"></a>Açıklamalar

Bu makro, OLE özellikli diğer uygulamaların bu türden nesneler oluşturmasına olanak sağlar.

Sınıfına ait. h modülüne DECLARE_OLECREATE makrosunu ekleyin ve bu modülün bu sınıfın nesnelerine erişmesi gereken tüm. cpp modüllerine dahil edin.

DECLARE_OLECREATE sınıf bildiriminde yer alıyorsa, IMPLEMENT_OLECREATE sınıf uygulamasına dahil olmalıdır. DECLARE_OLECREATE kullanan bir sınıf bildirimi Ayrıca DECLARE_DYNCREATE veya DECLARE_SERIAL kullanmalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: AfxDisp. h

##  <a name="implement_olecreate"></a>IMPLEMENT_OLECREATE

Bu makro veya [IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags) , tarafından kullanılan `DECLARE_OLECREATE`herhangi bir sınıf için uygulama dosyasında görünmelidir.

```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

*external_name*<br/>
Diğer uygulamalara sunulan nesne adı (tırnak işaretleri içine alınmıştır).

*l*, *W1*, *W2*, *B1*, *B2*, *B3*, *B4*, *B5*, *B6*, *B7*, , sınıfın CLSID 'si.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  IMPLEMENT_OLECREATE kullanıyorsanız, varsayılan olarak yalnızca tek iş parçacığı modelini destekleyebilirsiniz. IMPLEMENT_OLECREATE_FLAGS kullanıyorsanız, *nFlags* parametresini kullanarak nesnenizin hangi iş parçacığı modelini desteklediğini belirtebilirsiniz.

Dış ad, diğer uygulamalara sunulan tanıtıcıdır. İstemci uygulamaları, bir Otomasyon sunucusundan bu sınıftan bir nesne istemek için dış adı kullanır.

OLE sınıf KIMLIĞI, nesnesi için benzersiz bir 128 bitlik tanımlayıcıdır. Söz dizimi açıklamasında *l*, *W1*, *W2*ve *B1* - *B8* Ile gösterildiği gibi bir **Long**, iki **sözcükten**ve sekiz **baytlık**bir hata oluşur. Uygulama Sihirbazı ve kod sihirbazları, gerektiğinde sizin için benzersiz OLE sınıfı kimlikleri oluşturur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: AfxDisp. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
[MFC Ortak Denetimler Kitaplığını Yalıtma](../isolation-of-the-mfc-common-controls-library.md)<br/>
[CLSID anahtarı](/windows/win32/com/clsid-key-hklm)
