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
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421445"
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass yapısı

`CObject` türetilen her bir sınıf, çalışma zamanında bir nesne veya temel sınıfı hakkında bilgi almak için kullanabileceğiniz bir `CRuntimeClass` yapısıyla ilişkilendirilir.

## <a name="syntax"></a>Sözdizimi

```
struct CRuntimeClass
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRuntimeClass:: CreateObject](#createobject)|Çalışma zamanında bir nesne oluşturur.|
|[CRuntimeClass:: FromName](#fromname)|Bilinen sınıf adını kullanarak çalışma zamanında bir nesne oluşturur.|
|[CRuntimeClass:: IsDerivedFrom](#isderivedfrom)|Sınıfın belirtilen sınıftan türetilmediğini belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CRuntimeClass:: m_lpszClassName](#m_lpszclassname)|Sınıfın adı.|
|[CRuntimeClass:: m_nObjectSize](#m_nobjectsize)|Nesnenin bayt cinsinden boyutu.|
|[CRuntimeClass:: m_pBaseClass](#m_pbaseclass)|Taban sınıfının `CRuntimeClass` yapısına yönelik bir işaretçi.|
|[CRuntimeClass:: m_pfnCreateObject](#m_pfncreateobject)|Nesneyi dinamik olarak oluşturan işleve yönelik bir işaretçi.|
|[CRuntimeClass:: m_pfnGetBaseClass](#m_pfngetbaseclass)|`CRuntimeClass` yapısını döndürür (yalnızca dinamik olarak bağlı olduğunda kullanılabilir).|
|[CRuntimeClass:: m_wSchema](#m_wschema)|Sınıfın şema numarası.|

## <a name="remarks"></a>Açıklamalar

`CRuntimeClass` bir yapıdır ve bu nedenle temel bir sınıfa sahip değildir.

Çalışma zamanında bir nesnenin sınıfını belirleme özelliği, işlev bağımsız değişkenlerinin ek tür denetlemesi gerektiğinde veya bir nesnenin sınıfına göre özel amaçlı kod yazmanız gerektiğinde faydalıdır. Çalışma zamanı sınıf bilgileri doğrudan C++ dil tarafından desteklenmez.

`CRuntimeClass`, temel sınıfın `CRuntimeClass` işaretçisi C++ ve ılgılı sınıfın ASCII sınıf adı gibi ilgili nesne hakkında bilgi sağlar. Bu yapı ayrıca nesneleri dinamik olarak oluşturmak, tanıdık bir ad kullanarak nesne türünü belirtmek ve ilgili sınıfın belirli bir sınıftan türetilmiş olup olmadığını belirlemek için kullanılabilecek çeşitli işlevleri uygular.

`CRuntimeClass`kullanma hakkında daha fazla bilgi için bkz. [çalışma zamanı sınıf bilgilerine erişme](../../mfc/accessing-run-time-class-information.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CRuntimeClass`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="createobject"></a>CRuntimeClass:: CreateObject

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

`CObject` türetilen sınıflar, çalışma zamanında belirli bir sınıfın bir nesnesini oluşturma özelliği olan dinamik oluşturmayı destekleyebilir. Örneğin, belge, görünüm ve çerçeve sınıfları dinamik oluşturmayı desteklemelidir. Dinamik oluşturma ve `CreateObject` üye hakkında daha fazla bilgi için bkz. [CObject Class](../../mfc/using-cobject.md) ve [CObject sınıfı: işlev düzeylerini belirtme](../../mfc/specifying-levels-of-functionality.md).

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)örneğine bakın.

##  <a name="fromname"></a>CRuntimeClass:: FromName

Tanıdık adla ilişkili `CRuntimeClass` yapısını almak için bu işlevi çağırın.

```
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);

static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>Parametreler

*lpszClassName*<br/>
`CObject`türetilen bir sınıfın tanıdık adı.

### <a name="return-value"></a>Dönüş Değeri

`CRuntimeClass` nesnesine bir işaretçi, *lpszClassName*içinde geçirilmiş şekilde ada karşılık gelir. İşlev, eşleşen sınıf adı bulunmazsa NULL değerini döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]

##  <a name="isderivedfrom"></a>CRuntimeClass:: IsDerivedFrom

Çağırma sınıfının *Pbaseclass* parametresinde belirtilen sınıftan türetilmediğini öğrenmek için bu işlevi çağırın.

```
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;
```

### <a name="parameters"></a>Parametreler

*pBaseClass*<br/>
`CObject`türetilen bir sınıfın tanıdık adı.

### <a name="return-value"></a>Dönüş Değeri

`IsDerivedFrom` çağıran sınıf, `CRuntimeClass` yapısı parametre olarak verilen temel sınıftan türetildiyse TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

İlişki, üyenin sınıfından türetilmiş sınıfların zincirinden en üste kadar olan "yürüme" tarafından belirlenir. Bu işlev yalnızca temel sınıf için eşleşme bulunmazsa FALSE döndürür.

> [!NOTE]
>  `CRuntimeClass` yapısını kullanmak için, çalışma zamanı nesne bilgilerini almak istediğiniz sınıfın uygulamasına IMPLEMENT_DYNAMIC, IMPLEMENT_DYNCREATE veya IMPLEMENT_SERIAL makrosunu dahil etmeniz gerekir.

`CRuntimeClass`kullanma hakkında daha fazla bilgi için [CObject sınıfı: çalışma zamanı sınıf bilgilerine erişme](../../mfc/accessing-run-time-class-information.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]

##  <a name="m_lpszclassname"></a>CRuntimeClass:: m_lpszClassName

ASCII sınıf adını içeren, null ile sonlandırılmış bir dize.

### <a name="remarks"></a>Açıklamalar

Bu ad, `FromName` member işlevi kullanılarak sınıfın bir örneğini oluşturmak için kullanılabilir.

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)örneğine bakın.

##  <a name="m_nobjectsize"></a>CRuntimeClass:: m_nObjectSize

Nesnenin bayt cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Nesnede, ayrılan belleği işaret eden veri üyeleri varsa, bu belleğin boyutu dahil edilmez.

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)örneğine bakın.

##  <a name="m_pbaseclass"></a>CRuntimeClass:: m_pBaseClass

Uygulamanız MFC 'ye statik olarak bağlanıyorsa, bu veri üyesi temel sınıfın `CRuntimeClass` yapısına yönelik bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Uygulamanız MFC kitaplığına dinamik olarak bağlanıyorsa, bkz. [m_pfnGetBaseClass](#m_pfngetbaseclass).

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)örneğine bakın.

##  <a name="m_pfncreateobject"></a>CRuntimeClass:: m_pfnCreateObject

Sınıfınızın bir nesnesini oluşturan varsayılan oluşturucuya yönelik bir işlev işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu işaretçi yalnızca sınıf dinamik oluşturmayı destekliyorsa geçerlidir; Aksi takdirde, işlev NULL değerini döndürür.

##  <a name="m_pfngetbaseclass"></a>CRuntimeClass:: m_pfnGetBaseClass

Uygulamanız MFC kitaplığını paylaşılan bir DLL olarak kullanıyorsa, bu veri üyesi temel sınıfın `CRuntimeClass` yapısını döndüren bir işleve işaret eder.

### <a name="remarks"></a>Açıklamalar

Uygulamanız MFC kitaplığına statik olarak bağlanıyorsa, bkz. [m_pBaseClass](#m_pbaseclass).

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)örneğine bakın.

##  <a name="m_wschema"></a>CRuntimeClass:: m_wSchema

Şema numarası (seri hale getirilebilir olmayan sınıflar için-1).

### <a name="remarks"></a>Açıklamalar

Şema numaraları hakkında daha fazla bilgi için [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makroya bakın.

### <a name="example"></a>Örnek

  [IsDerivedFrom](#isderivedfrom)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObject:: GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)<br/>
[CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)<br/>
[RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)<br/>
[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)<br/>
[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)<br/>
[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)
