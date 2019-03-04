---
title: CRuntimeClass yapısı
ms.date: 11/04/2016
f1_keywords:
- CRuntimeClass
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
ms.openlocfilehash: 92979a10c18d9759e0ecc9f0785e56a97c0f0642
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274303"
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass yapısı

Her sınıf için türetilen `CObject` ile ilişkili bir `CRuntimeClass` çalışma zamanında nesneyi veya onun temel sınıfından hakkında bilgi almak için kullanabileceğiniz yapısı.

## <a name="syntax"></a>Sözdizimi

```
struct CRuntimeClass
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRuntimeClass::CreateObject](#createobject)|Çalışma zamanı sırasında bir nesne oluşturur.|
|[CRuntimeClass::FromName](#fromname)|Tanıdık sınıf adını kullanarak çalışma zamanı sırasında bir nesne oluşturur.|
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|Belirtilen sınıftan türetilmiş sınıf varsa belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|Sınıf adı.|
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|Nesnenin bayt cinsinden boyutu.|
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|Bir işaretçi `CRuntimeClass` yapısı temel sınıf.|
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|Dinamik olarak nesneyi oluşturan işlevi işaretçisi.|
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|Döndürür `CRuntimeClass` (kullanılabilir olduğunda, dinamik olarak bağlı yalnızca) yapılandırın.|
|[CRuntimeClass::m_wSchema](#m_wschema)|Sınıfın şeması sayısı.|

## <a name="remarks"></a>Açıklamalar

`CRuntimeClass` bir yapı olduğunu ve bu nedenle bir temel sınıfa sahip değil.

Çalışma zamanında bir nesnenin sınıfını belirleme imkanı, ek türü işlev bağımsız değişkenleri denetimini gerektiğinde veya bir nesnenin sınıfını esas özel amaçlı kod yazmanız gerekir yararlıdır. Çalışma süresi sınıf bilgilerine doğrudan C++ dil tarafından desteklenmiyor.

`CRuntimeClass` bir işaretçi gibi ilgili C++ nesne hakkında bilgi verilmektedir `CRuntimeClass` temel sınıf ve ilgili sınıf ASCII sınıf adı. Bu yapı, tanıdık bir ad kullanarak ve ilgili sınıfı belirli bir sınıftan türetilen, belirleyen nesne türünü belirtme nesneleri, dinamik olarak oluşturmak için kullanılan çeşitli işlevleri de uygular.

Kullanma hakkında daha fazla bilgi için `CRuntimeClass`, makaleye göz atın [çalışma süresi sınıf bilgilerine erişme](../../mfc/accessing-run-time-class-information.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CRuntimeClass`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="createobject"></a>  CRuntimeClass::CreateObject

Belirtilen sınıf çalışma zamanı sırasında dinamik olarak oluşturmak için bu işlevi çağırın.

```
CObject* CreateObject();

static CObject* PASCAL CreateObject(LPCSTR lpszClassName);

static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>Parametreler

*lpszClassName*<br/>
Oluşturulacak sınıfı bilinen adı.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan nesne veya sınıf adı bulunamadı veya nesneyi oluşturmak için yeterli bellek yoksa NULL bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Türetilen sınıflar `CObject` çalışma zamanında belirtilen sınıfın bir nesnesi oluşturma özelliği olan dinamik oluşturma destekleyebilir. Örneğin, belge, Görünüm ve çerçeve sınıfları dinamik oluşturma desteklemelidir. Dinamik oluşturma hakkında daha fazla bilgi ve `CreateObject` üyesi bkz [CObject sınıfı](../../mfc/using-cobject.md) ve [CObject sınıfı: İşlevsellik düzeylerini belirtme](../../mfc/specifying-levels-of-functionality.md).

### <a name="example"></a>Örnek

  Örneğin bakın [IsDerivedFrom](#isderivedfrom).

##  <a name="fromname"></a>  CRuntimeClass::FromName

Almak için bu işlevi çağırın `CRuntimeClass` yapısı tanıdık adıyla ilişkili.

```
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);

static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>Parametreler

*lpszClassName*<br/>
Türetilen bir sınıfın tam adını `CObject`.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CRuntimeClass` nesnesi, geçirilen gibi adına karşılık gelen *lpszClassName*. Eşleşen hiçbir sınıf adı bulunursa işlev NULL döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]

##  <a name="isderivedfrom"></a>  CRuntimeClass::IsDerivedFrom

Arama sınıfı belirtilen sınıf türetilir olmadığını belirlemek için bu işlevi çağırın *pBaseClass* parametresi.

```
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;
```

### <a name="parameters"></a>Parametreler

*pBaseClass*<br/>
Türetilen bir sınıfın tam adını `CObject`.

### <a name="return-value"></a>Dönüş Değeri

TRUE ise sınıfı arama `IsDerivedFrom` temelden türetilmiş sınıfının `CRuntimeClass` yapısı, bir parametre olarak belirtilen; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

İlişki "üyenin sınıfından türetilen sınıfların zincir oluşturan tüm dön taramasını tarafından" belirlenir. Bu işlev, yalnızca temel sınıf için eşleşme bulunursa FALSE döndürür.

> [!NOTE]
>  Kullanılacak `CRuntimeClass` yapısı, çalışma zamanı nesne bilgileri almak istediğiniz sınıfının uygulamasında ımplement_dynamıc, IMPLEMENT_DYNCREATE veya ımplement_serıal makrosu içermelidir.

Kullanma hakkında daha fazla bilgi için `CRuntimeClass`, makaleye göz atın [CObject sınıfı: Çalışma süresi sınıf bilgilerine erişme](../../mfc/accessing-run-time-class-information.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]

##  <a name="m_lpszclassname"></a>  CRuntimeClass::m_lpszClassName

ASCII sınıf adını içeren null ile sonlandırılmış bir dize.

### <a name="remarks"></a>Açıklamalar

Bu ad sınıfı kullanmanın bir örneğini oluşturmak için kullanılan `FromName` üye işlevi.

### <a name="example"></a>Örnek

  Örneğin bakın [IsDerivedFrom](#isderivedfrom).

##  <a name="m_nobjectsize"></a>  CRuntimeClass::m_nObjectSize

Nesnesinin bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Nesne veri üyeleri o noktaya ayrılan bellek varsa, bu bellek boyutu dahil değil.

### <a name="example"></a>Örnek

  Örneğin bakın [IsDerivedFrom](#isderivedfrom).

##  <a name="m_pbaseclass"></a>  CRuntimeClass::m_pBaseClass

Uygulamanızı MFC'ye, bu veri üyesi için bir işaretçi içeren `CRuntimeClass` yapısı temel sınıf.

### <a name="remarks"></a>Açıklamalar

Uygulamanızı MFC kitaplığına dinamik olarak olup [m_pfnGetBaseClass](#m_pfngetbaseclass).

### <a name="example"></a>Örnek

  Örneğin bakın [IsDerivedFrom](#isderivedfrom).

##  <a name="m_pfncreateobject"></a>  CRuntimeClass::m_pfnCreateObject

Sınıfınızın bir nesne oluşturur. varsayılan oluşturucu bir işlev işaretçisi.

### <a name="remarks"></a>Açıklamalar

This işaretçisi, yalnızca dinamik oluşturma sınıfı destekliyorsa, geçerlidir. Aksi halde, işlev NULL döndürür.

##  <a name="m_pfngetbaseclass"></a>  CRuntimeClass::m_pfnGetBaseClass

Uygulamanız paylaşılan DLL olarak MFC Kitaplığı kullanıyorsa, bu veri üyesi döndüren bir işleve işaret `CRuntimeClass` yapısı temel sınıf.

### <a name="remarks"></a>Açıklamalar

Uygulamanızı MFC kitaplığına statik değilse [m_pBaseClass](#m_pbaseclass).

### <a name="example"></a>Örnek

  Örneğin bakın [IsDerivedFrom](#isderivedfrom).

##  <a name="m_wschema"></a>  CRuntimeClass::m_wSchema

Şema numarasını (nonserializable sınıflar için -1).

### <a name="remarks"></a>Açıklamalar

Şema sayıları hakkında daha fazla bilgi için bkz. [ımplement_serıal](run-time-object-model-services.md#implement_serial) makrosu.

### <a name="example"></a>Örnek

  Örneğin bakın [IsDerivedFrom](#isderivedfrom).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObject::GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)<br/>
[CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)<br/>
[RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)<br/>
[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)<br/>
[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)<br/>
[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)
