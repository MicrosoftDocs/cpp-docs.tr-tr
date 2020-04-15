---
title: Çalışma Süresi Nesne Modeli Hizmetleri
ms.date: 03/27/2019
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
ms.openlocfilehash: f1cefdad368ebcd006dcb4ecf653247147f36d03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372937"
---
# <a name="run-time-object-model-services"></a>Çalışma Süresi Nesne Modeli Hizmetleri

[CObject](../../mfc/reference/cobject-class.md) ve [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) sınıfları, çalışma zamanı sınıf bilgilerine erişim, serileştirme ve dinamik nesne oluşturma dahil olmak üzere çeşitli nesne hizmetlerini kapsüller. Bu işlevselliği `CObject` devralan tüm sınıflar.

Çalışma zamanı sınıf bilgilerine erişim, bir nesnenin sınıfı hakkındaki bilgileri çalışma zamanında belirlemenize olanak tanır. Çalışma zamanında bir nesnenin sınıfını belirleme yeteneği, işlev bağımsız değişkenlerinin fazladan tür denetimine ihtiyaç duyduğunuzda ve bir nesnenin sınıfına göre özel amaçlı kod yazmanız gerektiğinde yararlıdır. Çalışma zamanı sınıf bilgileri doğrudan C++ dili tarafından desteklenmez.

Serileştirme, bir nesnenin içeriğini bir dosyaya veya dosyadan yazma veya okuma işlemidir. Uygulama çıktıktan sonra bile nesnenin içeriğini depolamak için serileştirmeyi kullanabilirsiniz. Uygulama yeniden başlatıldığında nesne dosyadan okunabilir. Bu tür veri nesnelerinin "kalıcı" olduğu söylenir.

Dinamik nesne oluşturma, çalışma zamanında belirli bir sınıftan bir nesne oluşturmanıza olanak tanır. Örneğin, belge, görünüm ve çerçeve nesneleri dinamik oluşturmayı desteklemelidir, çünkü çerçevenin bunları dinamik olarak oluşturması gerekir.

Aşağıdaki tabloda çalışma zamanı sınıf bilgilerini, serileştirmeyi ve dinamik oluşturmayı destekleyen MFC makroları listelenir.

Bu çalışma zamanı nesne hizmetleri ve serileştirme hakkında daha fazla bilgi için [CObject Class: Run-Time Sınıf Bilgilerine Erişim](../../mfc/accessing-run-time-class-information.md)makalesine bakın.

### <a name="run-time-object-model-services-macros"></a>Çalışma Zamanı Nesne Modeli Hizmetleri Makroları

|||
|-|-|
|[Declare_dynamıc](#declare_dynamic)|Çalışma zamanı sınıf bilgilerine erişimi sağlar (sınıf bildiriminde kullanılmalıdır).|
|[Declare_dyncreate](#declare_dyncreate)|Dinamik oluşturma ve çalışma zamanı sınıf bilgilerine erişim sağlar (sınıf bildiriminde kullanılmalıdır).|
|[Declare_serıal](#declare_serial)|Serileştirme ve çalışma zamanı sınıf bilgilerine erişim sağlar (sınıf bildiriminde kullanılmalıdır).|
|[ımplement_dynamıc](#implement_dynamic)|Çalışma zamanı sınıf bilgilerine erişimi sağlar (sınıf uygulamasında kullanılmalıdır).|
|[ımplement_dyncreate](#implement_dyncreate)|Dinamik oluşturma ve çalışma zamanı bilgilerine erişim sağlar (sınıf uygulamasında kullanılmalıdır).|
|[ımplement_serıal](#implement_serial)|Serileştirme ve çalışma zamanı sınıf bilgilerine erişime izin verir (sınıf uygulamasında kullanılmalıdır).|
|[RUNTIME_CLASS](#runtime_class)|Adlandırılmış `CRuntimeClass` sınıfa karşılık gelen yapıyı döndürür.|

OLE sık sık çalışma zamanında nesnelerin dinamik oluşturulmasını gerektirir. Örneğin, bir OLE sunucu uygulaması, istemciden gelen bir talebe yanıt olarak dinamik olarak OLE öğeleri oluşturabilmeli. Benzer şekilde, bir otomasyon sunucusu nun otomasyon istemcilerinden gelen isteklere yanıt olarak öğeler oluşturabilmesi gerekir.

Microsoft Hazırlık Sınıfı Kitaplığı, OLE'ye özgü iki makro sağlar.

### <a name="dynamic-creation-of-ole-objects"></a>OLE Nesnelerinin Dinamik Oluşturulması

|||
|-|-|
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|Ortak Denetimler kitaplığında belirtilen API'nin uygulanıp uygulanmadığını belirler.|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|Ortak Denetimler kitaplığında belirtilen API'nin uygulanıp uygulanmadığını belirler.|
|[DECLARE_OLECREATE](#declare_olecreate)|OLE otomasyonu ile nesnelerin oluşturulmasını sağlar.|
|[DECLARE_OLECTLTYPE](#declare_olectltype)|Denetim `GetUserTypeNameID` sınıfınızın `GetMiscStatus` ve üye işlevlerini bildirir.|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|OLE denetiminin özelliklerini görüntülemek için özellik sayfalarının bir listesini sağladığını bildirir.|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|Nesnelerin OLE sistemi tarafından oluşturulmasını sağlar.|
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|Denetim `GetUserTypeNameID` sınıfınızın `GetMiscStatus` ve üye işlevlerini uygular.|
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|Bu makro veya [IMPLEMENT_OLECREATE](#implement_olecreate) kullanan `DECLARE_OLECREATE`herhangi bir sınıf için uygulama dosyasında görünmesi gerekir. |

## <a name="afx_comctl32_if_exists"></a><a name="afx_comctl32_if_exists"></a>AFX_COMCTL32_IF_EXISTS

Ortak Denetimler kitaplığında belirtilen API'nin uygulanıp uygulanmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```
AFX_COMCTL32_IF_EXISTS(  proc );
```

### <a name="parameters"></a>Parametreler

*Yordam*<br/>
İşlev adını içeren geçersiz sonlandırılmış bir dize işaretçisi veya işlevin ordinal değerini belirtir. Bu parametre bir ordinal değerise, düşük sıralı sözcükte olmalıdır; yüksek sıralı sözcük sıfır olmalıdır. Bu parametre Unicode'da olmalıdır.

### <a name="remarks"></a>Açıklamalar

Ortak Denetimler kitaplığı *proc* tarafından belirtilen işlevi olup olmadığını belirlemek için bu makroyu kullanın [(GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)arama yerine.

### <a name="requirements"></a>Gereksinimler

afxcomctl32.h, afxcomctl32.inl

## <a name="afx_comctl32_if_exists2"></a><a name="afx_comctl32_if_exists2"></a>AFX_COMCTL32_IF_EXISTS2

Ortak Denetimler kitaplığı belirtilen API'yi uygulayıp uygulamadığını belirler [(bu, AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)Unicode sürümüdür).

### <a name="syntax"></a>Sözdizimi

```
AFX_COMCTL32_IF_EXISTS2( proc );
```

### <a name="parameters"></a>Parametreler

*Yordam*<br/>
İşlev adını içeren geçersiz sonlandırılmış bir dize işaretçisi veya işlevin ordinal değerini belirtir. Bu parametre bir ordinal değerise, düşük sıralı sözcükte olmalıdır; yüksek sıralı sözcük sıfır olmalıdır. Bu parametre Unicode'da olmalıdır.

### <a name="remarks"></a>Açıklamalar

Ortak Denetimler kitaplığı *proc* tarafından belirtilen işlevi olup olmadığını belirlemek için bu makroyu kullanın [(GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)arama yerine. Bu makro, AFX_COMCTL32_IF_EXISTS Unicode sürümüdür.

### <a name="requirements"></a>Gereksinimler

afxcomctl32.h, afxcomctl32.inl

## <a name="declare_dynamic"></a><a name="declare_dynamic"></a>Declare_dynamıc

Bir sınıftan türeyen nesnenin sınıfı yla ilgili çalışma zamanı `CObject`bilgilerine erişme özelliği ekler.

```
DECLARE_DYNAMIC(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

### <a name="remarks"></a>Açıklamalar

Sınıf için başlık (.h) modülüne DECLARE_DYNAMIC makroekleyin, ardından bu modülü bu sınıfın nesnelerine erişmesi gereken tüm .cpp modüllerine ekleyin.

DECLARE_ DYNAMIC ve IMPLEMENT_DYNAMIC makrolarını açıklandığı gibi kullanırsanız, çalışma zamanında `CObject::IsKindOf` nesnelerinizin sınıfını belirlemek için RUNTIME_CLASS makroyu ve işlevini kullanabilirsiniz.

DECLARE_DYNAMIC sınıf bildirimine dahil edilirse, IMPLEMENT_DYNAMIC sınıf uygulamasına dahil edilmelidir.

DECLARE_DYNAMIC makrosu hakkında daha fazla bilgi için [CObject Sınıf Konuları'na](../../mfc/using-cobject.md)bakın.

### <a name="example"></a>Örnek

[IMPLEMENT_DYNAMIC](#implement_dynamic)için örneğe bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="declare_dyncreate"></a><a name="declare_dyncreate"></a>Declare_dyncreate

Türetilmiş sınıfların nesnelerinin `CObject`çalışma zamanında dinamik olarak oluşturulmasını sağlar.

```
DECLARE_DYNCREATE(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

### <a name="remarks"></a>Açıklamalar

Çerçeve dinamik olarak yeni nesneler oluşturmak için bu yeteneği kullanır. Örneğin, yeni bir belge açtığınızda oluşturulan yeni görünüm. Çerçevenin bunları dinamik olarak oluşturması gerektiğinden, belge, görünüm ve çerçeve sınıfları dinamik oluşturmayı desteklemelidir.

Sınıf için .h modülüne DECLARE_DYNCREATE makroekleyin, ardından bu modülü bu sınıfın nesnelerine erişmesi gereken tüm .cpp modüllerine ekleyin.

DECLARE_DYNCREATE sınıf bildirimine dahil edilirse, IMPLEMENT_DYNCREATE sınıf uygulamasına dahil edilmelidir.

DECLARE_DYNCREATE makrosu hakkında daha fazla bilgi için [CObject Sınıf Konuları'na](../../mfc/using-cobject.md)bakın.

> [!NOTE]
> DECLARE_DYNCREATE makroDECLARE_DYNAMIC tüm işlevselliğini içerir.

### <a name="example"></a>Örnek

[IMPLEMENT_DYNCREATE](#implement_dyncreate)için örneğe bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="declare_olectltype"></a><a name="declare_olectltype"></a>DECLARE_OLECTLTYPE

Denetim `GetUserTypeNameID` sınıfınızın `GetMiscStatus` ve üye işlevlerini bildirir.

### <a name="syntax"></a>Sözdizimi

```
DECLARE_OLECTLTYPE( class_name )
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Kontrol sınıfının adı.

### <a name="remarks"></a>Açıklamalar

`GetUserTypeNameID`ve `GetMiscStatus` saf sanal işlevler, ilan `COleControl`edilir. Bu işlevler saf sanal olduğundan, denetim sınıfınızda geçersiz kılınmalıdır. DECLARE_OLECTLTYPE ek olarak, denetim sınıfı bildiriminize IMPLEMENT_OLECTLTYPE makroeklemeniz gerekir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxctl.h

## <a name="declare_proppageids"></a><a name="declare_proppageids"></a>DECLARE_PROPPAGEIDS

OLE denetiminin özelliklerini görüntülemek için özellik sayfalarının bir listesini sağladığını bildirir.

### <a name="syntax"></a>Sözdizimi

```
DECLARE_PROPPAGEIDS( class_name )
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Özellik sayfalarının sahibi denetim sınıfının adı.

### <a name="remarks"></a>Açıklamalar

Sınıf `DECLARE_PROPPAGEIDS` bildirgenizin sonundaki makroyu kullanın. Ardından, sınıfın üye işlevlerini tanımlayan .cpp dosyasında, `BEGIN_PROPPAGEIDS` denetiminizin özellik sayfalarının her biri için makro, makro girişleri ve özellik sayfası listesinin sonunu bildirmek için `END_PROPPAGEIDS` makroyu kullanın.

Özellik sayfaları hakkında daha fazla bilgi için [ActiveX Denetimleri: Özellik Sayfaları](../mfc-activex-controls-property-pages.md)makalesine bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxctl.h

## <a name="declare_serial"></a><a name="declare_serial"></a>Declare_serıal

Serihale getirilebilen türetilmiş `CObject`bir sınıf için gerekli C++ üstbilgi kodunu oluşturur.

```
DECLARE_SERIAL(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

### <a name="remarks"></a>Açıklamalar

Serileştirme, bir nesnenin içeriğini bir dosyaya ve dosyadan yazma veya okuma işlemidir.

DECLARE_SERIAL makroyu bir .h modülünde kullanın ve ardından bu modülü bu sınıfın nesnelerine erişmesi gereken tüm .cpp modüllerine ekleyin.

DECLARE_SERIAL sınıf bildirimine dahil edilirse, IMPLEMENT_SERIAL sınıf uygulamasına dahil edilmesi gerekir.

DECLARE_SERIAL makrosu DECLARE_DYNAMIC ve DECLARE_DYNCREATE tüm işlevselliğini içerir.

DECLARE_SERIAL ve IMPLEMENT_SERIAL makrolarını kullanan `CArchive` sınıflar için çıkarma işleciotomatik olarak dışa aktarma yapmak için AFX_API makroyu kullanabilirsiniz. Sınıf bildirimlerini (.h dosyasında bulunan) aşağıdaki kodla parantez e-

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

DECLARE_SERIAL makrosu hakkında daha fazla bilgi için [CObject Sınıf Konuları'na](../../mfc/using-cobject.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="implement_dynamic"></a><a name="implement_dynamic"></a>ımplement_dynamıc

Hiyerarşi içinde sınıf adı ve `CObject`konumuna çalışma zamanı erişimi olan dinamik türetilmiş sınıf için gerekli C++ kodunu oluşturur.

```
IMPLEMENT_DYNAMIC(class_name, base_class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

*base_class_name*<br/>
Taban sınıfın adı.

### <a name="remarks"></a>Açıklamalar

IMPLEMENT_DYNAMIC makroyu .cpp modülünde kullanın ve ardından ortaya çıkan nesne kodunu yalnızca bir kez bağlayın.

Daha fazla bilgi için [CObject Sınıf Konuları'na](../../mfc/using-cobject.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]

[!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="implement_dyncreate"></a><a name="implement_dyncreate"></a>ımplement_dyncreate

DECLARE_DYNCREATE makrosuyla `CObject`kullanıldığında, türetilmiş sınıfların nesnelerinin çalışma zamanında dinamik olarak oluşturulmasını sağlar.

```
IMPLEMENT_DYNCREATE(class_name, base_class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

*base_class_name*<br/>
Taban sınıfın gerçek adı.

### <a name="remarks"></a>Açıklamalar

Çerçeve, örneğin serileştirme sırasında diskten bir nesneyi okuduğunda dinamik olarak yeni nesneler oluşturmak için bu yeteneği kullanır. Sınıf uygulama dosyasına IMPLEMENT_DYNCREATE makroekleyin. Daha fazla bilgi için [CObject Sınıf Konuları'na](../../mfc/using-cobject.md)bakın.

DECLARE_DYNCREATE ve IMPLEMENT_DYNCREATE makrolarını kullanırsanız, çalışma zamanında nesnelerinizin `CObject::IsKindOf` sınıfını belirlemek için RUNTIME_CLASS makroyu ve üye işlevini kullanabilirsiniz.

DECLARE_DYNCREATE sınıf bildirimine dahil edilirse, IMPLEMENT_DYNCREATE sınıf uygulamasına dahil edilmelidir.

Bu makro tanımının sınıfınız için varsayılan oluşturucuyu çağıracağını unutmayın. Önemsiz olmayan bir oluşturucu sınıf tarafından açıkça uygulanıyorsa, varsayılan oluşturucuyu da açıkça uygulaması gerekir. Varsayılan oluşturucu, sınıfın özel **veya** **korumalı** üye bölümlerine eklenerek sınıf uygulaması dışından çağrılmasını engelleyebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]

[!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="implement_olecreate_flags"></a><a name="implement_olecreate_flags"></a>IMPLEMENT_OLECREATE_FLAGS

Bu makro veya [IMPLEMENT_OLECREATE](#implement_olecreate) DECLARE_OLECREATE kullanan herhangi bir sınıf için uygulama dosyasında görünmesi gerekir.

### <a name="syntax"></a>Sözdizimi

```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags,
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

*external_name*<br/>
Diğer uygulamalara maruz kalan nesne adı (tırnak işaretleriyle birlikte).

*Nflags*<br/>
Aşağıdaki bayraklardan birini veya birkaçını içerir:

- `afxRegInsertable`Denetimin OLE nesneleri için Nesne Ekle iletişim kutusunda görünmesini sağlar.
- `afxRegApartmentThreading`İş parçacığı modelini threadingModel=Apartment olarak ayarlar.
- `afxRegFreeThreading`Kayıt defterindeki iş parçacığı modelini ThreadingModel=Free olarak ayarlar.

İki bayrağı `afxRegApartmentThreading` `afxRegFreeThreading` birleştirip ThreadingModel=Her ikisini de ayarlayabilirsiniz. İş parçacığı modeli kaydı hakkında daha fazla bilgi için Windows SDK'da [InprocServer32'ye](/windows/win32/com/inprocserver32) bakın.

*l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8* Sınıfın CLSID bileşenleri.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> IMPLEMENT_OLECREATE_FLAGS kullanıyorsanız, *nFlags* parametresini kullanarak nesnenizin hangi iş parçacığı modelini desteklediğini belirtebilirsiniz. Yalnızca tek basma modelini desteklemek istiyorsanız, IMPLEMENT_OLECREATE kullanın.

Dış ad, diğer uygulamalara maruz kalan tanımlayıcıdır. İstemci uygulamaları, bir otomasyon sunucusundan bu sınıfın bir nesnesini istemek için dış adı kullanır.

OLE sınıfı kimliği nesne için benzersiz bir 128 bit tanımlayıcıdır. Sözdizimi açıklamasında *l*, *w1*, *w2*ve *b1* ile *b8* ile temsil edilen bir **uzun,** iki **WORD**s ve sekiz **BYTE**s'den oluşur. Uygulama Sihirbazı ve kod sihirbazları, gerektiğinde sizin için benzersiz OLE sınıfı iD'ler oluşturur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="implement_olectltype"></a><a name="implement_olectltype"></a>IMPLEMENT_OLECTLTYPE

Denetim `GetUserTypeNameID` sınıfınızın `GetMiscStatus` ve üye işlevlerini uygular.

### <a name="syntax"></a>Sözdizimi

```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Kontrol sınıfının adı.

*idsUserTypeName*<br/>
Denetimin dış adını içeren bir dize kaynak kimliği.

*dwOleMisc*<br/>
Bir veya daha fazla bayrak içeren numaralandırma. Bu numaralandırma hakkında daha fazla bilgi için Windows SDK'daki [OLEMISC'ye](/windows/win32/api/oleidl/ne-oleidl-olemisc) bakın.

### <a name="remarks"></a>Açıklamalar

IMPLEMENT_OLECTLTYPE ek olarak, denetim sınıfı bildiriminize DECLARE_OLECTLTYPE makroeklemeniz gerekir.

`GetUserTypeNameID` Üye işlev, denetim sınıfınızı tanımlayan kaynak dizesini döndürür. `GetMiscStatus`denetiminiz için OLEMISC bitlerini döndürür. Bu numaralandırma, denetiminizin çeşitli özelliklerini açıklayan bir ayar koleksiyonunu belirtir. OLEMISC ayarlarının tam açıklaması için Windows SDK'daki [OLEMISC'ye](/windows/win32/api/oleidl/ne-oleidl-olemisc) bakın.

> [!NOTE]
> ActiveX ControlWizard tarafından kullanılan varsayılan ayarlar şunlardır: OLEMISC_ACTIVATEWHENVISIBLE, OLEMISC_SETCLIENTSITEFIRST, OLEMISC_INSIDEOUT, OLEMISC_CANTLINKINSIDE ve OLEMISC_RECOMPOSEONRESIZE.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxctl.h

## <a name="implement_serial"></a><a name="implement_serial"></a>ımplement_serıal

Hiyerarşi içinde sınıf adı ve `CObject`konumuna çalışma zamanı erişimi olan dinamik türetilmiş sınıf için gerekli C++ kodunu oluşturur.

```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

*base_class_name*<br/>
Taban sınıfın adı.

*wSchema*<br/>
Önceki program sürümleri tarafından oluşturulan verileri tanımlamak ve işlemek için bir deserializing programı etkinleştirmek için arşivde kodlanacak bir UINT "sürüm numarası". Sınıf şema numarası -1 olmamalıdır.

### <a name="remarks"></a>Açıklamalar

IMPLEMENT_SERIAL makroyu .cpp modülünde kullanın; ardından ortaya çıkan nesne kodunu yalnızca bir kez bağlayın.

DECLARE_SERIAL ve IMPLEMENT_SERIAL makrolarını kullanan `CArchive` sınıflar için çıkarma işleciotomatik olarak dışa aktarma yapmak için AFX_API makroyu kullanabilirsiniz. Sınıf bildirimlerini (.h dosyasında bulunan) aşağıdaki kodla parantez e-

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

Daha fazla bilgi için [CObject Sınıf Konuları'na](../../mfc/using-cobject.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="runtime_class"></a><a name="runtime_class"></a>RUNTIME_CLASS

C++ sınıfının adından çalışma zamanı sınıf yapısını alır.

```
RUNTIME_CLASS(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı (tırnak işaretleriyle birlikte değil).

### <a name="remarks"></a>Açıklamalar

RUNTIME_CLASS, class_name tarafından belirtilen sınıf için bir [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) *yapısına*işaretçi döndürür. Yalnızca `CObject`DECLARE_DYNAMIC, DECLARE_DYNCREATE veya DECLARE_SERIAL ile bildirilen türetilmiş `CRuntimeClass` sınıflar işaretçileri bir yapıya döndürecek.

Daha fazla bilgi için [CObject Sınıf Konuları'na](../../mfc/using-cobject.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="declare_olecreate"></a><a name="declare_olecreate"></a>DECLARE_OLECREATE

OLE otomasyonu `CCmdTarget`aracılığıyla türemiş sınıfların nesnelerinin oluşturulmasını sağlar.

```
DECLARE_OLECREATE(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

### <a name="remarks"></a>Açıklamalar

Bu makro, diğer OLE özellikli uygulamaların bu tür nesneler oluşturmasını sağlar.

Sınıf için .h modülüne DECLARE_OLECREATE makroekleyin ve ardından bu modülü bu sınıfın nesnelerine erişmesi gereken tüm .cpp modüllerine ekleyin.

DECLARE_OLECREATE sınıf bildirimine dahil edilirse, IMPLEMENT_OLECREATE sınıf uygulamasına dahil edilmelidir. DECLARE_OLECREATE kullanan bir sınıf bildirimi de DECLARE_DYNCREATE veya DECLARE_SERIAL kullanmalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: afxdisp.h

## <a name="implement_olecreate"></a><a name="implement_olecreate"></a>IMPLEMENT_OLECREATE

Bu makro veya [IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags) kullanan `DECLARE_OLECREATE`herhangi bir sınıf için uygulama dosyasında görünmesi gerekir.

```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıfın gerçek adı.

*external_name*<br/>
Diğer uygulamalara maruz kalan nesne adı (tırnak işaretleriyle birlikte).

*l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8* Sınıfın CLSID bileşenleri.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> IMPLEMENT_OLECREATE kullanırsanız, varsayılan olarak yalnızca tek iş parçacığı modelini desteklersiniz. IMPLEMENT_OLECREATE_FLAGS kullanıyorsanız, *nFlags* parametresini kullanarak nesnenizin hangi iş parçacığı modelini desteklediğini belirtebilirsiniz.

Dış ad, diğer uygulamalara maruz kalan tanımlayıcıdır. İstemci uygulamaları, bir otomasyon sunucusundan bu sınıfın bir nesnesini istemek için dış adı kullanır.

OLE sınıfı kimliği nesne için benzersiz bir 128 bit tanımlayıcıdır. Sözdizimi açıklamasında *l*, *w1*, *w2*ve *b1* ile *b8* ile temsil edilen bir **uzun,** iki **WORD**s ve sekiz **BYTE**s'den oluşur. Uygulama Sihirbazı ve kod sihirbazları, gerektiğinde sizin için benzersiz OLE sınıfı iD'ler oluşturur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](mfc-macros-and-globals.md)<br/>
[MFC Ortak Denetimler Kitaplığını Yalıtma](../isolation-of-the-mfc-common-controls-library.md)<br/>
[CLSID Anahtar](/windows/win32/com/clsid-key-hklm)
