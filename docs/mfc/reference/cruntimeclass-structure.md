---
description: 'Daha fazla bilgi edinin: CRuntimeClass yapısı'
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
ms.openlocfilehash: e02732ec595026f028ad4b8f9bd3d8898a40cbc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342923"
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass yapısı

Öğesinden türetilen her bir sınıf `CObject` , `CRuntimeClass` çalışma zamanında bir nesne veya temel sınıfı hakkında bilgi almak için kullanabileceğiniz bir yapıyla ilişkilendirilir.

## <a name="syntax"></a>Syntax

```
struct CRuntimeClass
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRuntimeClass:: CreateObject](#createobject)|Çalışma zamanında bir nesne oluşturur.|
|[CRuntimeClass:: FromName](#fromname)|Bilinen sınıf adını kullanarak çalışma zamanında bir nesne oluşturur.|
|[CRuntimeClass:: IsDerivedFrom](#isderivedfrom)|Sınıfın belirtilen sınıftan türetilmediğini belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CRuntimeClass:: m_lpszClassName](#m_lpszclassname)|Sınıfın adı.|
|[CRuntimeClass:: m_nObjectSize](#m_nobjectsize)|Nesnenin bayt cinsinden boyutu.|
|[CRuntimeClass:: m_pBaseClass](#m_pbaseclass)|`CRuntimeClass`Taban sınıfının yapısına yönelik bir işaretçi.|
|[CRuntimeClass:: m_pfnCreateObject](#m_pfncreateobject)|Nesneyi dinamik olarak oluşturan işleve yönelik bir işaretçi.|
|[CRuntimeClass:: m_pfnGetBaseClass](#m_pfngetbaseclass)|Yapıyı döndürür `CRuntimeClass` (yalnızca dinamik olarak bağlı olduğunda kullanılabilir).|
|[CRuntimeClass:: m_wSchema](#m_wschema)|Sınıfın şema numarası.|

## <a name="remarks"></a>Açıklamalar

`CRuntimeClass` bir yapısıdır ve bu nedenle temel bir sınıfa sahip değildir.

Çalışma zamanında bir nesnenin sınıfını belirleme özelliği, işlev bağımsız değişkenlerinin ek tür denetlemesi gerektiğinde veya bir nesnenin sınıfına göre özel amaçlı kod yazmanız gerektiğinde faydalıdır. Çalışma zamanı sınıf bilgileri doğrudan C++ dili tarafından desteklenmez.

`CRuntimeClass` ilgili C++ nesnesi hakkında, `CRuntimeClass` temel sınıfın bir işaretçisi ve ilgili SıNıFıN ASCII sınıf adı gibi bilgiler sağlar. Bu yapı ayrıca nesneleri dinamik olarak oluşturmak, tanıdık bir ad kullanarak nesne türünü belirtmek ve ilgili sınıfın belirli bir sınıftan türetilmiş olup olmadığını belirlemek için kullanılabilecek çeşitli işlevleri uygular.

Kullanma hakkında daha fazla bilgi için `CRuntimeClass` [Run-Time sınıfı bilgilerine erişme](../../mfc/accessing-run-time-class-information.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CRuntimeClass`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="cruntimeclasscreateobject"></a><a name="createobject"></a> CRuntimeClass:: CreateObject

Çalışma zamanında belirtilen sınıfı dinamik olarak oluşturmak için bu işlevi çağırın.

```
CObject* CreateObject();

static CObject* PASCAL CreateObject(LPCSTR lpszClassName);

static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>Parametreler

*lpszClassName*<br/>
Oluşturulacak sınıfın tanıdık adı.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan nesneye yönelik bir işaretçi veya sınıf adı bulunamazsa veya nesne oluşturmak için yeterli bellek yoksa NULL.

### <a name="remarks"></a>Açıklamalar

' Dan türetilmiş sınıflar `CObject` , çalışma zamanında belirli bir sınıfın bir nesnesini oluşturma özelliği olan dinamik oluşturmayı destekleyebilir. Örneğin, belge, görünüm ve çerçeve sınıfları dinamik oluşturmayı desteklemelidir. Dinamik oluşturma ve üye hakkında daha fazla bilgi için `CreateObject` bkz. [CObject Class](../../mfc/using-cobject.md) and [CObject sınıfı: işlev düzeylerini belirtme](../../mfc/specifying-levels-of-functionality.md).

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)örneğine bakın.

## <a name="cruntimeclassfromname"></a><a name="fromname"></a> CRuntimeClass:: FromName

Tanıdık adla ilişkili yapıyı almak için bu işlevi çağırın `CRuntimeClass` .

```
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);

static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>Parametreler

*lpszClassName*<br/>
Öğesinden türetilen bir sınıfın tanıdık adı `CObject` .

### <a name="return-value"></a>Dönüş Değeri

`CRuntimeClass` *LpszClassName* içinde geçirilmiş şekilde ada karşılık gelen bir nesne işaretçisi. İşlev, eşleşen sınıf adı bulunmazsa NULL değerini döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]

## <a name="cruntimeclassisderivedfrom"></a><a name="isderivedfrom"></a> CRuntimeClass:: IsDerivedFrom

Çağırma sınıfının *Pbaseclass* parametresinde belirtilen sınıftan türetilmediğini öğrenmek için bu işlevi çağırın.

```
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;
```

### <a name="parameters"></a>Parametreler

*pBaseClass*<br/>
Öğesinden türetilen bir sınıfın tanıdık adı `CObject` .

### <a name="return-value"></a>Dönüş Değeri

Eğer çağırma sınıfı, `IsDerivedFrom` yapısı parametre olarak verilen temel sınıftan TÜRETILDIYSE true, `CRuntimeClass` aksı durumda false.

### <a name="remarks"></a>Açıklamalar

İlişki, üyenin sınıfından türetilmiş sınıfların zincirinden en üste kadar olan "yürüme" tarafından belirlenir. Bu işlev yalnızca temel sınıf için eşleşme bulunmazsa FALSE döndürür.

> [!NOTE]
> Yapıyı kullanmak için `CRuntimeClass` , çalışma zamanı nesne bilgilerini almak istediğiniz sınıfın uygulamasına IMPLEMENT_DYNAMIC, IMPLEMENT_DYNCREATE veya IMPLEMENT_SERIAL makrosunu dahil etmeniz gerekir.

Kullanma hakkında daha fazla bilgi için `CRuntimeClass` , [CObject sınıfı: Run-Time sınıf bilgilerine erişme](../../mfc/accessing-run-time-class-information.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]

## <a name="cruntimeclassm_lpszclassname"></a><a name="m_lpszclassname"></a> CRuntimeClass:: m_lpszClassName

ASCII sınıf adını içeren, null ile sonlandırılmış bir dize.

### <a name="remarks"></a>Açıklamalar

Bu ad, üye işlevi kullanılarak sınıfın bir örneğini oluşturmak için kullanılabilir `FromName` .

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)örneğine bakın.

## <a name="cruntimeclassm_nobjectsize"></a><a name="m_nobjectsize"></a> CRuntimeClass:: m_nObjectSize

Nesnenin bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Nesnede, ayrılan belleği işaret eden veri üyeleri varsa, bu belleğin boyutu dahil edilmez.

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)örneğine bakın.

## <a name="cruntimeclassm_pbaseclass"></a><a name="m_pbaseclass"></a> CRuntimeClass:: m_pBaseClass

Uygulamanız MFC 'ye statik olarak bağlanıyorsa, bu veri üyesi temel sınıfın yapısına yönelik bir işaretçi içerir `CRuntimeClass` .

### <a name="remarks"></a>Açıklamalar

Uygulamanız MFC kitaplığına dinamik olarak bağlanıyorsa, bkz. [m_pfnGetBaseClass](#m_pfngetbaseclass).

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)örneğine bakın.

## <a name="cruntimeclassm_pfncreateobject"></a><a name="m_pfncreateobject"></a> CRuntimeClass:: m_pfnCreateObject

Sınıfınızın bir nesnesini oluşturan varsayılan oluşturucuya yönelik bir işlev işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu işaretçi yalnızca sınıf dinamik oluşturmayı destekliyorsa geçerlidir; Aksi takdirde, işlev NULL değerini döndürür.

## <a name="cruntimeclassm_pfngetbaseclass"></a><a name="m_pfngetbaseclass"></a> CRuntimeClass:: m_pfnGetBaseClass

Uygulamanız MFC kitaplığını paylaşılan bir DLL olarak kullanıyorsa, bu veri üyesi temel sınıfın yapısını döndüren bir işleve işaret eder `CRuntimeClass` .

### <a name="remarks"></a>Açıklamalar

Uygulamanız MFC kitaplığına statik olarak bağlanıyorsa, bkz. [m_pBaseClass](#m_pbaseclass).

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)örneğine bakın.

## <a name="cruntimeclassm_wschema"></a><a name="m_wschema"></a> CRuntimeClass:: m_wSchema

Şema numarası (seri hale getirilebilir olmayan sınıflar için-1).

### <a name="remarks"></a>Açıklamalar

Şema numaraları hakkında daha fazla bilgi için [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makroya bakın.

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObject:: GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)<br/>
[CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)<br/>
[RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)<br/>
[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)<br/>
[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)<br/>
[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)
