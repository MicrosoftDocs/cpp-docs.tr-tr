---
title: "CRuntimeClass yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b053e963f4e252302ed4c390a648846166aff62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass yapısı
Her sınıf türetilmiş `CObject` ile ilişkili bir `CRuntimeClass` çalışma zamanında bir nesne veya onun temel sınıfı hakkında bilgi edinmek için kullanabileceğiniz yapısı.  
  
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
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|Belirtilen sınıfından türetilmiş sınıf varsa belirler.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|Sınıfın adı.|  
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|Nesnenin bayt cinsinden boyutu.|  
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|Bir işaretçi `CRuntimeClass` yapısı temel sınıf.|  
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|Dinamik Nesne oluşturur işlevi için bir işaretçi.|  
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|Döndürür `CRuntimeClass` (kullanılabilir dinamik olarak bağlı yalnızca) yapılandırın.|  
|[CRuntimeClass::m_wSchema](#m_wschema)|Sınıfın şeması sayısı.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CRuntimeClass`bir yapıdır ve bu nedenle bir taban sınıfı yok.  
  
 Çalışma zamanında bir nesne sınıfının belirleme özelliği, ek tür işlev bağımsız değişkenleri denetlemesi gerektiğinde ya da bir nesne sınıfına göre özel amaçlı kod yazmanız gerekir yararlıdır. Çalışma zamanı sınıf bilgileri doğrudan C++ dili tarafından desteklenmiyor.  
  
 `CRuntimeClass`bir işaretçi gibi ilgili C++ nesne hakkında bilgiler sağlar `CRuntimeClass` temel sınıf ve ilgili sınıf ASCII sınıf adı. Bu yapı, dinamik olarak bilinen bir ad kullanarak ve ilgili sınıfın belirli bir sınıftan türetildiği varsa belirleme nesne türünü belirleme nesneleri oluşturmak için kullanılan çeşitli işlevleri de uygular.  
  
 Kullanma hakkında daha fazla bilgi için `CRuntimeClass`, makaleye bakın [çalışma zamanı sınıf bilgilerine erişme](../../mfc/accessing-run-time-class-information.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CRuntimeClass`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="createobject"></a>CRuntimeClass::CreateObject  
 Belirtilen sınıf çalışma zamanında dinamik olarak oluşturmak için bu işlevini çağırın.  
  
```  
CObject* CreateObject();  
  
static CObject* PASCAL CreateObject(LPCSTR lpszClassName);  
  
static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszClassName`  
 Oluşturulacak sınıfın tanıdık adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan nesnenin gösteren bir işaretçi veya **NULL** sınıf adı bulunamadı veya nesnesi oluşturmak için yeterli bellek yok.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilmiş sınıflar `CObject` çalışma zamanında belirtilen sınıfın bir nesnesi oluşturma yeteneği dinamik oluşturma destekleyebilir. Örneğin, belge, Görünüm ve çerçeve sınıfları dinamik oluşturma desteklemelidir. Dinamik oluşturma hakkında daha fazla bilgi ve `CreateObject` üyesi bkz [CObject sınıfı](../../mfc/using-cobject.md) ve [CObject sınıfı: düzeyleri işlevselliğini belirtme](../../mfc/specifying-levels-of-functionality.md).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="fromname"></a>CRuntimeClass::FromName  
 Almak için bu işlevi çağırmak `CRuntimeClass` tanıdık adıyla ilişkili yapısı.  
  
```  
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);  
  
static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszClassName`  
 Tanıdık adı bir sınıfın türetildiği `CObject`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CRuntimeClass` geçirilen gibi adına karşılık gelen nesne `lpszClassName`. İşlevi döndürür **NULL** eşleşen hiçbir sınıf adı bulunursa.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]  
  
##  <a name="isderivedfrom"></a>CRuntimeClass::IsDerivedFrom  
 Arama sınıfı belirtilen sınıfından türetilen varsa belirlemek için bu işlevi çağırmak *pBaseClass* parametresi.  
  
```  
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;

 
```  
  
### <a name="parameters"></a>Parametreler  
 *pBaseClass*  
 Tanıdık adı bir sınıfın türetildiği `CObject`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** varsa sınıfı arama `IsDerivedFrom` taban türetilmiş sınıfının `CRuntimeClass` yapısı, bir parametre olarak belirtilen aksi **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 İlişki "üyenin sınıfından türetilen sınıfların zincir oluşturan tüm dön adım adım ilerlemenizi sağlayarak" belirlenir. Bu işlev yalnızca döndürür **FALSE** için temel sınıfı bir eşleşme varsa.  
  
> [!NOTE]
>  Kullanılacak `CRuntimeClass` yapısı, içermelidir `IMPLEMENT_DYNAMIC`, `IMPLEMENT_DYNCREATE`, veya `IMPLEMENT_SERIAL` makrosu çalışma zamanı nesne bilgilerini almak istediğiniz sınıfının uygulamasında.  
  
 Kullanma hakkında daha fazla bilgi için `CRuntimeClass`, makaleye bakın [CObject sınıfı: çalışma zamanı sınıf bilgilerine erişme](../../mfc/accessing-run-time-class-information.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]  
  
##  <a name="m_lpszclassname"></a>CRuntimeClass::m_lpszClassName  
 ASCII sınıf adını içeren null ile sonlandırılmış bir dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ad sınıfını kullanarak bir örneğini oluşturmak için kullanılan `FromName` üye işlevi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_nobjectsize"></a>CRuntimeClass::m_nObjectSize  
 Nesnenin bayt cinsinden boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne ayrılmış bellek o noktaya veri üyeleri varsa, bu bellek boyutu dahil değil.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_pbaseclass"></a>CRuntimeClass::m_pBaseClass  
 Uygulamanızı statik olarak MFC'ye bağlanıyorsa, bu veri üyesi için bir işaretçi içeriyor `CRuntimeClass` yapısı temel sınıf.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızı MFC kitaplığına dinamik olarak olup [m_pfnGetBaseClass](#m_pfngetbaseclass).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_pfncreateobject"></a>CRuntimeClass::m_pfnCreateObject  
 Bir işlev işaretçisi varsayılan oluşturucuya, sınıfın bir nesnesi oluşturur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işaretçinin, yalnızca sınıf dinamik oluşturma destekliyorsa geçerlidir; Aksi takdirde işlevi döndürür **NULL**.  
  
##  <a name="m_pfngetbaseclass"></a>CRuntimeClass::m_pfnGetBaseClass  
 Uygulamanız paylaşılan DLL olarak MFC kitaplığını kullanıyorsa, bu veri üyesi döndüren bir işlev işaret `CRuntimeClass` yapısı temel sınıf.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızı MFC kitaplığına statik olarak olup [m_pBaseClass](#m_pbaseclass).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_wschema"></a>CRuntimeClass::m_wSchema  
 Şema numarasını (nonserializable sınıfları için -1).  
  
### <a name="remarks"></a>Açıklamalar  
 Şema numaraları üzerinde daha fazla bilgi için bkz: [ımplement_serıal](run-time-object-model-services.md#implement_serial) makrosu.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [IsDerivedFrom](#isderivedfrom).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CObject::GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)   
 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)   
 [RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)   
 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)   
 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)   
 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)



