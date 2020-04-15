---
title: CRuntimeClass Yapısı
ms.date: 11/04/2016
f1_keywords:
- CRuntimeClass
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
ms.openlocfilehash: a58b9c97d5683423a0f81f6b5424f19f987943bf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318560"
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass Yapısı

Türetilen `CObject` her sınıf, `CRuntimeClass` çalışma zamanında bir nesne veya taban sınıfı hakkında bilgi edinmek için kullanabileceğiniz bir yapıyla ilişkilidir.

## <a name="syntax"></a>Sözdizimi

```
struct CRuntimeClass
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRuntimeClass::CreateObject](#createobject)|Çalışma süresi boyunca bir nesne oluşturur.|
|[CRuntimeClass::FromName](#fromname)|Tanıdık sınıf adını kullanarak çalışma sırasında bir nesne oluşturur.|
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|Sınıfın belirtilen sınıftan türetilip türetilip türetilenin ilerler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|Sınıfın adı.|
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|Baytlar'daki nesnenin boyutu.|
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|Taban sınıfın `CRuntimeClass` yapısına işaretçi.|
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|Nesneyi dinamik olarak oluşturan işleve işaretçi.|
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|Yapıyı `CRuntimeClass` döndürür (yalnızca dinamik olarak bağlandığında kullanılabilir).|
|[CRuntimeClass::m_wSchema](#m_wschema)|Sınıfın şema numarası.|

## <a name="remarks"></a>Açıklamalar

`CRuntimeClass`bir yapıdır ve bu nedenle bir taban sınıf yoktur.

Çalışma zamanında bir nesnenin sınıfını belirleme yeteneği, işlev bağımsız değişkenlerinin ek tür denetimi gerektiğinde veya bir nesnenin sınıfına dayalı özel amaçlı kod yazmanız gerektiğinde yararlıdır. Çalışma zamanı sınıf bilgileri doğrudan C++ dili tarafından desteklenmez.

`CRuntimeClass`taban sınıfın işaretçisi `CRuntimeClass` ve ilgili sınıfın ASCII sınıf adı gibi ilgili C++ nesnesi hakkında bilgi sağlar. Bu yapı ayrıca nesneleri dinamik olarak oluşturmak için kullanılabilecek çeşitli işlevler uygular, tanıdık bir ad kullanarak nesnenin türünü belirtir ve ilgili sınıfın belirli bir sınıftan türetilip türetilmediğini belirler.

Kullanma `CRuntimeClass`hakkında daha fazla bilgi için, [Çalışma Zamanı Sınıf Bilgilerine Erişen](../../mfc/accessing-run-time-class-information.md)makaleye bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CRuntimeClass`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="cruntimeclasscreateobject"></a><a name="createobject"></a>CRuntimeClass::CreateObject

Çalışma süresi boyunca belirtilen sınıfı dinamik olarak oluşturmak için bu işlevi çağırın.

```
CObject* CreateObject();

static CObject* PASCAL CreateObject(LPCSTR lpszClassName);

static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>Parametreler

*lpszClassName*<br/>
Oluşturulacak sınıfın tanıdık adı.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan nesneye işaretçi veya sınıf adı bulunamazsa veya nesneyi oluşturmak için yeterli bellek yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Türetilen `CObject` sınıflar, çalışma zamanında belirli bir sınıfın nesnesini oluşturma yeteneği olan dinamik oluşturmayı destekleyebilir. Belge, görünüm ve çerçeve sınıfları, örneğin, dinamik oluşturma desteklemelidir. Dinamik oluşturma ve `CreateObject` üye hakkında daha fazla bilgi için [CObject Sınıfı](../../mfc/using-cobject.md) ve [CObject Sınıfı: İşlevsellik Düzeylerini Belirtme](../../mfc/specifying-levels-of-functionality.md)bölümüne bakın.

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)için örneğe bakın.

## <a name="cruntimeclassfromname"></a><a name="fromname"></a>CRuntimeClass::FromName

Tanıdık adla ilişkili `CRuntimeClass` yapıyı almak için bu işlevi çağırın.

```
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);

static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>Parametreler

*lpszClassName*<br/>
Türetilen bir sınıfın tanıdık `CObject`adı.

### <a name="return-value"></a>Dönüş Değeri

`CRuntimeClass` *LpszClassName'de*geçirilen ada karşılık gelen bir nesneye işaretçi. Eşleşen bir sınıf adı bulunamadıysa işlev NULL döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]

## <a name="cruntimeclassisderivedfrom"></a><a name="isderivedfrom"></a>CRuntimeClass::IsDerivedFrom

Arama sınıfının *pBaseClass* parametresinde belirtilen sınıftan türetilip türetilmeyaradığını belirlemek için bu işlevi arayın.

```
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;
```

### <a name="parameters"></a>Parametreler

*pBaseClass*<br/>
Türetilen bir sınıfın tanıdık `CObject`adı.

### <a name="return-value"></a>Dönüş Değeri

Sınıf `IsDerivedFrom` `CRuntimeClass` çağrısı, yapısı parametre olarak verilen taban sınıftan türetilmişse DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

İlişki, üyenin sınıfından türemiş sınıflar zincirine kadar "yürüme" ile belirlenir. Bu işlev yalnızca taban sınıf için eşleşme bulunamazsa FALSE döndürür.

> [!NOTE]
> Yapıyı `CRuntimeClass` kullanmak için, çalışma zamanı nesnesi bilgilerini almak istediğiniz sınıfın uygulanmasına IMPLEMENT_DYNAMIC, IMPLEMENT_DYNCREATE veya IMPLEMENT_SERIAL makroyu eklemeniz gerekir.

Kullanma `CRuntimeClass`hakkında daha fazla bilgi için [CObject Class: Run-Time Sınıf Bilgilerine Erişim](../../mfc/accessing-run-time-class-information.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]

## <a name="cruntimeclassm_lpszclassname"></a><a name="m_lpszclassname"></a>CRuntimeClass::m_lpszClassName

ASCII sınıf adını içeren null-sonlandırılan dize.

### <a name="remarks"></a>Açıklamalar

Bu `FromName` ad, üye işlevi kullanarak sınıfın bir örneğini oluşturmak için kullanılabilir.

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)için örneğe bakın.

## <a name="cruntimeclassm_nobjectsize"></a><a name="m_nobjectsize"></a>CRuntimeClass::m_nObjectSize

Nesnenin boyutu, baytlar halinde.

### <a name="remarks"></a>Açıklamalar

Nesne, ayrılan belleğe işaret eden veri üyelerine sahipse, bu belleğin boyutu dahil edilmez.

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)için örneğe bakın.

## <a name="cruntimeclassm_pbaseclass"></a><a name="m_pbaseclass"></a>CRuntimeClass::m_pBaseClass

Uygulamanız Statik olarak MFC'ye bağlanırsa, bu `CRuntimeClass` veri üyesi taban sınıfın yapısına bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Uygulamanız MFC kitaplığına dinamik olarak bağlanacaksa, [bkz. m_pfnGetBaseClass.](#m_pfngetbaseclass)

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)için örneğe bakın.

## <a name="cruntimeclassm_pfncreateobject"></a><a name="m_pfncreateobject"></a>CRuntimeClass::m_pfnCreateObject

Sınıfınızın bir nesnesini oluşturan varsayılan oluşturucuya bir işlev işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu işaretçi yalnızca sınıf dinamik oluşturmayı destekliyorsa geçerlidir; aksi takdirde, işlev NULL döndürür.

## <a name="cruntimeclassm_pfngetbaseclass"></a><a name="m_pfngetbaseclass"></a>CRuntimeClass::m_pfnGetBaseClass

Uygulamanız MFC kitaplığını paylaşılan bir DLL olarak kullanıyorsa, bu `CRuntimeClass` veri üyesi taban sınıfın yapısını döndüren bir işleve işaret eder.

### <a name="remarks"></a>Açıklamalar

Uygulamanız Statik olarak MFC kitaplığına bağlanacaksa, bkz. [m_pBaseClass.](#m_pbaseclass)

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)için örneğe bakın.

## <a name="cruntimeclassm_wschema"></a><a name="m_wschema"></a>CRuntimeClass::m_wSchema

Şema numarası ( seri olmayan sınıflar için -1).

### <a name="remarks"></a>Açıklamalar

Şema numaraları hakkında daha fazla bilgi için [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makroya bakın.

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObject::GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)<br/>
[Cobject::Iskindof](../../mfc/reference/cobject-class.md#iskindof)<br/>
[RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)<br/>
[ımplement_dynamıc](run-time-object-model-services.md#implement_dynamic)<br/>
[ımplement_dyncreate](run-time-object-model-services.md#implement_dyncreate)<br/>
[ımplement_serıal](run-time-object-model-services.md#implement_serial)
